---
description: Adicione o Módulo de gerenciamento de público-alvo ao appmeasurement do Adobe Analytics para encaminhar os dados do Analytics para o Audience Manager em vez de ter o código DIL (Audience Manager Integration Integration Library) enviando um pixel da página.
keywords: análises de público-alvo; análises; ssf; encaminhamento pelo lado do servidor
seo-description: Adicione o Módulo de gerenciamento de público-alvo ao appmeasurement do Adobe Analytics para encaminhar os dados do Analytics para o Audience Manager em vez de ter o código DIL (Audience Manager Integration Integration Library) enviando um pixel da página.
seo-title: Implementar o Módulo de gerenciamento de público-alvo
solution: Audience Manager
title: Implementar o Módulo de gerenciamento de público-alvo
uuid: 08846427-def 3-4 a 15-88 e 5-08882 d 8 d 57 ce
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Implement the Audience Management Module {#implement-the-audience-management-module}

Add the [!UICONTROL Audience Management Module] to [!DNL Adobe Analytics] [!UICONTROL AppMeasurement] to forward [!DNL Analytics] data to Audience Manager instead of having the Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) code send a pixel from the page.

## Pré-requisitos {#prereqs}

Além de implementar o código descrito neste documento, você também deve:

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Enable [!UICONTROL Server-Side Forwarding] for report suites in the [!UICONTROL Adobe Analytics Admin Console].

## Implementação {#implementation}

To implement the [!UICONTROL Audience Management Module]:

1. Download [!UICONTROL AppMeasurement] using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (requires version 1.5 or later).
1. Update your [!UICONTROL AppMeasurement] code to the version included in the downloaded zip file.
1. Copy all of the code from `AppMeasurement_Module_AudienceManagement.js` from the zip file. Paste it into the `appMeasurement.js` file just above the text, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Add the code, `s.loadModule("AudienceManagement");`, just above the `AppMeasurement_Module_AudienceManagement.js` code you just added in the previous step.
1. Update and copy the code below and add it to the `doPlugins` function in your `AppMeasurement.js` file.

```js
s.AudienceManagement.setup({ 
     "partner":"partner name", 
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
>`audienceManagement.setup` A função compartilha parâmetros com `DIL.create` a função do Audience Manager, que pode ser configurada nesse código. For more information about these parameters, see [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## Code Elements Defined {#code-elements-defined}

A tabela a seguir define variáveis importantes na amostra de código.

| Parâmetro | Descrição |
|--- |--- |
| `partner` | Obrigatório. Este é um nome de parceiro atribuído a você pela Adobe. Às vezes, ela é chamada de &quot;ID do parceiro&quot; ou &quot;subdomínio do parceiro&quot;. Contact your Adobe consultant or [Customer Care](https://helpx.adobe.com/marketing-cloud/contact-support.html) if you don&#39;t know your partner name. |
| `containerNSID` | Obrigatório. Most customers can just set  `"containerNSID":0` . No entanto, se a sua empresa precisar personalizar sincronizações de ID com um contêiner diferente, você pode especificar essa ID do contêiner aqui. |
| `uuidCookie` | Opcional. Essa configuração permite definir um cookie da Adobe no domínio próprio. This cookie contains the [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Obrigatório. The `namespace` parameter is required if you use the AudienceManagement module bundled with [!UICONTROL AppMeasurement] version 2.10 or newer. This [!UICONTROL AudienceManagement] module requires that you use [!UICONTROL Experience Cloud ID Service] 3.3 or newer. <br>É [!UICONTROL Experience Cloud Organization ID] a ID com a qual uma empresa é fornecida ao se inscrever para o [!UICONTROL Experience Cloud]. Find out your company&#39;s Organization ID in [Organizations and Account Linking](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## Results: Data Forwarding to Audience Manager {#results-data-forwarding}

Your [!DNL Analytics] implementation sends data to Audience Manager after you have:

* Enabled [!UICONTROL Server-Side Forwarding] (talk to your consultant about this feature);
* Implementação do serviço de ID;
* Installed the [!UICONTROL Audience Management Module].

This process sends data to [!DNL Audience Manager]:

* Nas chamadas de exibição de página;
* De links rastreados;
* Das exibições de vídeo de marco e heartbeat de vídeo.

>[!NOTE]
>
>The variables sent to Audience Manager from [!DNL Analytics] use special prefixes. Você precisa entender e considerar esses prefixos ao criar características do Audience Manager. For more information on these prefixes, see [Prefix Requirements for Key Variables](../../features/traits/trait-variable-prefixes.md).