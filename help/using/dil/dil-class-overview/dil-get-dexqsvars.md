---
description: Recupera um valor específico de um servidor de publicidade.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 7%

---

# dexGetQSVars{#dexgetqsvars}

>[!WARNING]
>
>A partir de julho de 2023, a Adobe descontinuou o desenvolvimento do [!DNL Data Integration Library (DIL)] e da extensão [!DNL DIL].
>
>Os clientes existentes podem continuar usando a implementação [!DNL DIL]. Entretanto, a Adobe não desenvolverá [!DNL DIL] além deste ponto. Os clientes são incentivados a avaliar o [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para sua estratégia de coleta de dados de longo prazo.
>
>Os clientes que desejam implementar novas integrações de coleta de dados após julho de 2023 devem usar o [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en).

Recupera um valor específico de um servidor de publicidade.

**Assinatura da Função:** `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parâmetros**

| Nome | Tipo | Descrição |
|---|---|---|
| `variableName` | String   | O nome da variável cujo valor você deseja obter. |
| `partner` | String   | O nome do parceiro a ser pesquisado. |
| `containerNSID` | Número inteiro | O [!DNL NSID] do contêiner que você está procurando. O padrão é `0`. |

**Resposta**

Retorna o valor da variável para uma instância [!UICONTROL DIL].

**Código de exemplo**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
