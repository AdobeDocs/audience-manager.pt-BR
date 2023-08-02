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
source-wordcount: '142'
ht-degree: 8%

---

# dexGetQSVars{#dexgetqsvars}

>[!WARNING]
>
>A partir de julho de 2023, a Adobe interrompeu o desenvolvimento do [!DNL Data Integration Library (DIL)] e a variável [!DNL DIL] extensão.
>
>Os clientes existentes podem continuar usando seus [!DNL DIL] execução. No entanto, o Adobe não estará em desenvolvimento [!DNL DIL] além deste ponto. Os clientes são incentivados a avaliar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para a sua estratégia de recolha de dados a longo prazo.
>
>Os clientes que desejam implementar novas integrações de coleta de dados após julho de 2023 devem usar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) em vez disso.

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
| `containerNSID` | Número inteiro | A variável [!DNL NSID] do contêiner que você está procurando. O padrão é `0`. |

**Resposta**

Retorna o valor da variável para um [!UICONTROL DIL] instância.

**Código de exemplo**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
