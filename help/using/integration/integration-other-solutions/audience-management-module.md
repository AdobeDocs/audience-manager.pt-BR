---
description: Adicione o Módulo de gerenciamento de Audiência ao Adobe Analytics AppMeasurement para encaminhar os dados do Analytics para Audience Manager, em vez de fazer com que o código de Data Integration Library (DIL) envie um pixel da página.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Adicione o Módulo de gerenciamento de Audiência ao Adobe Analytics AppMeasurement para encaminhar os dados do Analytics para Audience Manager, em vez de fazer com que o código de Data Integration Library (DIL) envie um pixel da página.
seo-title: Implementação do módulo de gerenciamento de Audiências
solution: Audience Manager
title: Implementação do módulo de gerenciamento de Audiências
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Integration with Analytics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 5%

---


# Como encaminhar dados de [!DNL Adobe Analytics] para [!DNL Audience Manager] {#implement-the-audience-management-module}

Siga as etapas neste tutorial para encaminhar os dados [!DNL Analytics] para [!DNL Audience Manager] em vez de fazer com que o código [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) envie um pixel da página.

>[!TIP]
>
>Recomendamos que você use [!DNL Adobe Experience Platform Launch] para encaminhar [!UICONTROL Analytics] dados para [!DNL Audience Manager]. Ao usar [!UICONTROL Launch], não é necessário copiar manualmente o código em [!DNL AppMeasurement], conforme mostrado nesta página.

## Pré-requisitos {#prereqs}

Além de ativar as extensões ou implementar o código descrito neste documento, você também deve:

* Implemente o [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html).
* Ative [Encaminhamento pelo lado do servidor](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) para conjuntos de relatórios em [!UICONTROL Adobe Analytics Admin Console].

## Implementação {#implementation}

Há dois métodos para implementar o encaminhamento de dados de [!DNL Adobe Analytics] para [!DNL Audience Manager], dependendo da solução de gerenciamento de tags usada.

### Implementação usando [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] recomenda usar a extensão  [](https://docs.adobe.com/content/help/en/launch/using/overview.html) Launchextension para instrumentar  [!DNL Adobe Analytics] e  [!DNL Audience Manager] nas propriedades. Nesse caso, não é necessário copiar manualmente qualquer código. Em vez disso, você deve ativar o compartilhamento de dados na extensão [!DNL Analytics Launch], como mostrado na imagem abaixo. Consulte também a documentação [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager).

>[!TIP]
>
>Se você instalar a extensão [!DNL Adobe Analytics], *não* também instalará a extensão [!DNL Audience Manager]. O encaminhamento de dados da extensão [!DNL Analytics] substitui a funcionalidade de extensão [!DNL Audience Manager].

![Como ativar o compartilhamento de dados da extensão Adobe Analytics para Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

### Implementação usando [!DNL Adobe Digital Tag Management (DTM)] ou qualquer outra solução de gerenciamento de tags

>[!WARNING]
>
>[!DNL Adobe] , divulgou planos para pôr  [!DNL DTM] termo ao período até ao final de 2020. Para obter mais informações e agendamento, consulte [!DNL DTM] Planos para um Sunset nos [fóruns da comunidade do Adobe](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset).

Para implementar [!UICONTROL Audience Management Module] usando [Adobe DTM](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) ou outra solução de gerenciamento de tags:

1. Baixe [!UICONTROL AppMeasurement] usando o [Gerenciador de código do Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/admin/admin-tools/code-manager-admin.html) (requer a versão 1.5 ou posterior).
1. Atualize seu código [!UICONTROL AppMeasurement] para a versão incluída no arquivo zip baixado.
1. Copie todo o código de `AppMeasurement_Module_AudienceManagement.js` do arquivo zip. Cole-o no arquivo `appMeasurement.js` logo acima do texto, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Adicione o código, `s.loadModule("AudienceManagement");`, logo acima do código `AppMeasurement_Module_AudienceManagement.js` que você acabou de adicionar na etapa anterior.
1. Atualize e copie o código abaixo e adicione-o à função `doPlugins` no arquivo `AppMeasurement.js`.

```js
s.AudienceManagement.setup({ 
     "partner":"INSERT-YOUR-PARTNER-NAME-HERE", 
     "containerNSID":0, 
     "uuidCookie": { 
          "name":"aam_uuid", 
          "days":30
     },
     "visitorService": {
          "namespace": "INSERT-EXPERIENCE-CLOUD-ORGID-HERE" 
     } 
});
```

>[!TIP]
>
>A função `audienceManagement.setup` compartilha parâmetros com a função [!DNL Audience Manager] `DIL.create`, que pode ser configurada neste código. Para obter mais informações sobre esses parâmetros, consulte [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## Elementos de código definidos {#code-elements-defined}

A tabela a seguir define variáveis importantes na amostra de código.

| Parâmetro | Descrição |
|--- |--- |
| `partner` | Obrigatório. Este é um nome de parceiro atribuído a você por [!DNL Adobe]. Às vezes, ele é conhecido como seu subdomínio [!UICONTROL partner ID] ou parceiro.  Entre em contato com seu [!DNL Adobe] consultor ou [Atendimento ao cliente](https://helpx.adobe.com/br/marketing-cloud/contact-support.html) se você não souber o nome do seu parceiro. |
| `containerNSID` | Obrigatório. A maioria dos clientes pode definir `"containerNSID":0`. No entanto, se sua empresa precisar personalizar sincronizações de ID com um container diferente, você pode especificar essa ID de container aqui. |
| `uuidCookie` | Opcional. Essa configuração permite que você defina um cookie [!DNL Adobe] no domínio primário. Este [!DNL cookie] contém o [UUID](../../reference/ids-in-aam.md). |
| `visitorService` - `namespace` | Obrigatório. O parâmetro `namespace` é necessário se você usar o módulo [!DNL AudienceManagement] fornecido com [!UICONTROL AppMeasurement] versão 2.10 ou mais recente. Este módulo [!UICONTROL AudienceManagement] requer o uso de [!UICONTROL Adobe Experience Platform Identity Service] 3.3 ou mais recente. <br><br>A ID  [!UICONTROL Experience Cloud Organization ID] é fornecida por uma empresa ao se inscrever no  [!UICONTROL Experience Cloud]. Descubra a ID da organização do empresa em [Organizações e vinculação de contas](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Resultados: Encaminhamento de dados para [!DNL Audience Manager] {#results-data-forwarding}

Sua implementação [!DNL Analytics] envia dados para [!DNL Audience Manager] depois de:

* Habilitado [!UICONTROL Server-Side Forwarding] (fale com seu consultor sobre esse recurso);
* Implementado o [!DNL Adobe Experience Platform Identity Service];
* Seguidas as etapas de implementação neste tutorial.

Esse processo envia dados para [!DNL Audience Manager]:

* Chamadas de visualização na página;
* De links rastreados;
* De visualizações de vídeo de marco e pulsação.

>[!NOTE]
>
>As variáveis enviadas para [!DNL Audience Manager] de [!DNL Analytics] usam prefixos especiais. Você precisa entender e levar esses prefixos em conta ao criar [!DNL Audience Manager] características. Para obter mais informações sobre esses prefixos, consulte [Requisitos de prefixo para variáveis-chave](../../features/traits/trait-variable-prefixes.md).
