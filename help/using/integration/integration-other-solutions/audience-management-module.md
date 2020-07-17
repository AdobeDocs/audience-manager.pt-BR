---
description: Adicione o Módulo de gerenciamento de Audiência ao Adobe Analytics AppMeasurement para encaminhar os dados do Analytics para o Audience Manager, em vez de fazer com que o código da Biblioteca de integração de dados do Audience Manager (DIL) envie um pixel da página.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Adicione o Módulo de gerenciamento de Audiência ao Adobe Analytics AppMeasurement para encaminhar os dados do Analytics para o Audience Manager, em vez de fazer com que o código da Biblioteca de integração de dados do Audience Manager (DIL) envie um pixel da página.
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


# How to forward data from [!DNL Adobe Analytics] to [!DNL Audience Manager] {#implement-the-audience-management-module}

Siga as etapas neste tutorial para encaminhar [!DNL Analytics] dados para [!DNL Audience Manager] em vez de fazer com que o [!DNL Audience Manager] ( [!UICONTROL Data Integration Library][!DNL DIL]) código envie um pixel da página.

>[!TIP]
>
>Recomendamos que você use [!DNL Adobe Experience Platform Launch] para encaminhar [!UICONTROL Analytics] dados para o [!DNL Audience Manager]. Ao usar [!UICONTROL Launch], não é necessário copiar manualmente o código para [!DNL AppMeasurement], conforme mostrado nesta página.

## Pré-requisitos {#prereqs}

Além de ativar as extensões ou implementar o código descrito neste documento, você também deve:

* Implement the [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html).
* Ative o encaminhamento [pelo lado do](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) servidor para conjuntos de relatórios no [!UICONTROL Adobe Analytics Admin Console].

## Implementação {#implementation}

Há dois métodos para implementar o encaminhamento de dados de [!DNL Adobe Analytics] para [!DNL Audience Manager], dependendo da solução de gerenciamento de tags usada.

### Implementação usando [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] recomenda usar a extensão [Iniciar](https://docs.adobe.com/content/help/en/launch/using/overview.html) para instrumentar [!DNL Adobe Analytics] e [!DNL Audience Manager] nas suas propriedades. Nesse caso, não é necessário copiar manualmente qualquer código. Em vez disso, você deve ativar o compartilhamento de dados na [!DNL Analytics Launch] extensão, como mostrado na imagem abaixo. Consulte também a documentação do [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) .

>[!TIP]
>
>Se você instalar a [!DNL Adobe Analytics] extensão, *não* instale também a [!DNL Audience Manager] extensão. O encaminhamento de dados da [!DNL Analytics] extensão substitui a funcionalidade da [!DNL Audience Manager] extensão.

![Como ativar o compartilhamento de dados da extensão do Adobe Analytics para o Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

### Implementação usando [!DNL Adobe Digital Tag Management (DTM)] ou qualquer outra solução de gerenciamento de tags

>[!WARNING]
>
>[!DNL Adobe] , divulgou os planos para pôr do sol [!DNL DTM] até ao final de 2020. Para obter mais informações e agendamento, consulte [!DNL DTM] Planos para um Sunset nos fóruns [da comunidade](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)Adobe.

Para implementar o [!UICONTROL Audience Management Module] usando o [Adobe DTM](https://docs.adobe.com/content/help/pt-BR/dtm/using/dtm-home.html) ou outra solução de gerenciamento de tags:

1. Baixe [!UICONTROL AppMeasurement] usando o Gerenciador [de código da](https://docs.adobe.com/content/help/pt-BR/analytics/admin/admin-tools/code-manager-admin.html) Analytics (requer a versão 1.5 ou posterior).
1. Atualize seu [!UICONTROL AppMeasurement] código para a versão incluída no arquivo zip baixado.
1. Copie todo o código do arquivo `AppMeasurement_Module_AudienceManagement.js` zip. Cole-o no `appMeasurement.js` ficheiro logo acima do texto. `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Adicione o código, `s.loadModule("AudienceManagement");`, logo acima do `AppMeasurement_Module_AudienceManagement.js` código que você acabou de adicionar na etapa anterior.
1. Atualize e copie o código abaixo e adicione-o à `doPlugins` função em seu `AppMeasurement.js` arquivo.

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
>A `audienceManagement.setup` função compartilha parâmetros com a [!DNL Audience Manager]`DIL.create` função, que você pode configurar neste código. Para obter mais informações sobre esses parâmetros, consulte Criação [de](../../dil/dil-class-overview/dil-create.md#dil-create)DIL.

## Elementos de código definidos {#code-elements-defined}

A tabela a seguir define variáveis importantes na amostra de código.

| Parâmetro | Descrição |
|--- |--- |
| `partner` | Obrigatório. Este é um nome de parceiro atribuído por [!DNL Adobe]. Às vezes, é conhecido como subdomínio do seu [!UICONTROL partner ID] ou do seu parceiro.  Entre em contato com seu [!DNL Adobe] consultor ou com o [Atendimento](https://helpx.adobe.com/br/marketing-cloud/contact-support.html) ao cliente se você não souber o nome do seu parceiro. |
| `containerNSID` | Obrigatório. A maioria dos clientes pode definir `"containerNSID":0` . No entanto, se sua empresa precisar personalizar sincronizações de ID com um container diferente, você pode especificar essa ID de container aqui. |
| `uuidCookie` | Opcional. Essa configuração permite que você defina um [!DNL Adobe] cookie no domínio primário. Isso [!DNL cookie] contém o [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Obrigatório. O `namespace` parâmetro é necessário se você usar o [!DNL AudienceManagement] módulo fornecido com a [!UICONTROL AppMeasurement] versão 2.10 ou mais recente. Este [!UICONTROL AudienceManagement] módulo requer o uso da versão [!UICONTROL Adobe Experience Platform Identity Service] 3.3 ou mais recente. <br><br>A ID [!UICONTROL Experience Cloud Organization ID] é fornecida por uma empresa ao se inscrever no [!UICONTROL Experience Cloud]. Descubra a ID da organização da empresa em [Organizações e vinculação](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html)de contas. |

## Resultados: Encaminhamento de dados para [!DNL Audience Manager] {#results-data-forwarding}

Sua [!DNL Analytics] implementação envia dados para [!DNL Audience Manager] depois de:

* Ativado [!UICONTROL Server-Side Forwarding] (fale com o seu consultor sobre este recurso);
* Implementou o [!DNL Adobe Experience Platform Identity Service];
* Seguidas as etapas de implementação neste tutorial.

Esse processo envia dados para [!DNL Audience Manager]:

* Chamadas de visualização na página;
* De links rastreados;
* De visualizações de vídeo de marco e pulsação.

>[!NOTE]
>
>As variáveis enviadas a partir [!DNL Audience Manager] do [!DNL Analytics] uso de prefixos especiais. Você precisa entender e levar esses prefixos em conta ao criar [!DNL Audience Manager] características. Para obter mais informações sobre esses prefixos, consulte Requisitos de [prefixo para variáveis](../../features/traits/trait-variable-prefixes.md)-chave.
