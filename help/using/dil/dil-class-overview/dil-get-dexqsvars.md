---
description: Recupera um valor específico de um servidor de publicidade.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
TQID: https://experienceleague.adobe.com/O8xeJARK4qVGj8SOXmO8OHLqfOcSPZZWvWoGad0Wji8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
subfeature_v2:
  - id: d7e573ad-4eda-46ec-90c4-239e75362af9
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 130
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
