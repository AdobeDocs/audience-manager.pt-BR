---
description: Recupera um valor específico de um servidor de publicidade.
seo-description: Recupera um valor específico de um servidor de publicidade.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: Implementação de DIL
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 17%

---

# dexGetQSVars{#dexgetqsvars}

Recupera um valor específico de um servidor de publicidade.

**Assinatura da função:** `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parâmetros**

| Nome | Tipo | Descrição |
|---|---|---|
| `variableName` | String   | O nome da variável para a qual você deseja obter um valor. |
| `partner` | String   | O nome do parceiro a procurar. |
| `containerNSID` | Número inteiro | O [!DNL NSID] do contêiner que você está procurando. Os padrões são `0`. |

**Resposta**

Retorna o valor da variável para uma instância [!UICONTROL DIL].

**Código de exemplo**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
