---
description: Adicione o Módulo de gerenciamento de público-alvo ao Adobe Analytics AppMeasurement para encaminhar os dados do Analytics para o Audience Manager, em vez de ter o código de Data Integration Library de Audience Manager (DIL) para enviar um pixel da página.
keywords: análise de público-alvo; análises; ssf; encaminhamento pelo lado do servidor
seo-description: Adicione o Módulo de gerenciamento de público-alvo ao Adobe Analytics AppMeasurement para encaminhar os dados do Analytics para o Audience Manager, em vez de ter o código de Data Integration Library de Audience Manager (DIL) para enviar um pixel da página.
seo-title: Implementar o módulo Gerenciamento de público-alvo
solution: Audience Manager
title: Implementar o módulo Gerenciamento de público-alvo
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 5%

---

# Como encaminhar dados de [!DNL Adobe Analytics] para [!DNL Audience Manager] {#implement-the-audience-management-module}

Siga as etapas neste tutorial para encaminhar [!DNL Analytics] dados para [!DNL Audience Manager] em vez de ter o código [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) enviado um pixel da página.

>[!TIP]
>
>Recomendamos que você use [!DNL Adobe Experience Platform Launch] para encaminhar [!UICONTROL Analytics] dados para [!DNL Audience Manager]. Ao usar [!UICONTROL Launch], não é necessário copiar manualmente o código para [!DNL AppMeasurement], conforme mostrado nesta página.

## Pré-requisitos {#prereqs}

Além de ativar as extensões ou implementar o código descrito neste documento, você também deve:

* Implemente o [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html).
* Ative [Encaminhamento pelo lado do servidor](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) para conjuntos de relatórios no [!UICONTROL Adobe Analytics Admin Console].

## Implementação {#implementation}

Há dois métodos para implementar o encaminhamento de dados de [!DNL Adobe Analytics] para [!DNL Audience Manager], dependendo da solução de gerenciamento de tags usada.

### Implementação usando [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] O recomenda usar a extensão  [](https://docs.adobe.com/content/help/en/launch/using/overview.html) Launch para preparar  [!DNL Adobe Analytics] e  [!DNL Audience Manager] ativar as propriedades. Nesse caso, não é necessário copiar manualmente qualquer código. Em vez disso, você deve ativar o compartilhamento de dados na extensão [!DNL Analytics Launch], conforme mostrado na imagem abaixo. Consulte também a documentação [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager).

>[!TIP]
>
>Se você instalar a extensão [!DNL Adobe Analytics], *não* também instalará a extensão [!DNL Audience Manager]. O encaminhamento de dados da extensão [!DNL Analytics] substitui a funcionalidade da extensão [!DNL Audience Manager].

![Como habilitar o compartilhamento de dados da extensão do Adobe Analytics para o Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

### Implementação usando [!DNL Adobe Digital Tag Management (DTM)] ou qualquer outra solução de gerenciamento de tags

>[!WARNING]
>
>[!DNL Adobe] O divulgou planos para pôr termo  [!DNL DTM] até ao final de 2020. Para obter mais informações e o agendamento, consulte [!DNL DTM] Planos para uma descontinuação nos [fóruns da comunidade do Adobe](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset).

Para implementar o [!UICONTROL Audience Management Module] usando o [Adobe DTM](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) ou outra solução de gerenciamento de tags:

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
| `partner` | Obrigatório. Este é um nome de parceiro atribuído a você por [!DNL Adobe]. Às vezes, ele é chamado de [!UICONTROL partner ID] ou subdomínio do parceiro.  Entre em contato com seu consultor [!DNL Adobe] ou [Atendimento ao cliente](https://helpx.adobe.com/br/marketing-cloud/contact-support.html) se você não souber o nome do seu parceiro. |
| `containerNSID` | Obrigatório. A maioria dos clientes pode apenas definir `"containerNSID":0` . No entanto, se sua empresa precisar personalizar sincronizações de ID com um contêiner diferente, especifique essa ID do contêiner aqui. |
| `uuidCookie` | Opcional. Essa configuração permite definir um cookie [!DNL Adobe] no domínio próprio. Este [!DNL cookie] contém o [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Obrigatório. O parâmetro `namespace` é necessário se você usar o módulo [!DNL AudienceManagement] fornecido com [!UICONTROL AppMeasurement] versão 2.10 ou mais recente. Este módulo [!UICONTROL AudienceManagement] requer o uso de [!UICONTROL Adobe Experience Platform Identity Service] 3.3 ou mais recente. <br><br>A ID  [!UICONTROL Experience Cloud Organization ID] é fornecida por uma empresa ao se inscrever no  [!UICONTROL Experience Cloud]. Descubra a ID da organização de sua empresa em [Organizações e vinculação de contas](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Resultados: Encaminhamento de dados para [!DNL Audience Manager] {#results-data-forwarding}

Sua implementação [!DNL Analytics] envia dados para [!DNL Audience Manager] após:

* Ativado [!UICONTROL Server-Side Forwarding] (fale com o consultor sobre esse recurso);
* Implementou o [!DNL Adobe Experience Platform Identity Service];
* Seguidas as etapas de implementação neste tutorial.

Esse processo envia dados para [!DNL Audience Manager]:

* Em chamadas de exibição de página;
* A partir de links rastreados;
* De marcos de vídeo e exibições de vídeo de pulsação.

>[!NOTE]
>
>As variáveis enviadas para [!DNL Audience Manager] de [!DNL Analytics] usam prefixos especiais. Você precisa entender e levar esses prefixos em conta ao criar [!DNL Audience Manager] características. Para obter mais informações sobre esses prefixos, consulte [Requisitos de prefixo para variáveis-chave](../../features/traits/trait-variable-prefixes.md).
