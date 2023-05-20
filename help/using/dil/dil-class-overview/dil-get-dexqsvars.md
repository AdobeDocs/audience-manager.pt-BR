---
description: Recupera um valor específico de um servidor de publicidade.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 18%

---

# dexGetQSVars{#dexgetqsvars}

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
