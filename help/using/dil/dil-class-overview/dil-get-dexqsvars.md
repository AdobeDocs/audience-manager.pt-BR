---
description: Recupera um valor específico de um servidor de publicidade.
seo-description: Recupera um valor específico de um servidor de publicidade.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# dexGetQSVars{#dexgetqsvars}

Recupera um valor específico de um servidor de publicidade.

**** Assinatura da função: `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parâmetros**

| Nome | Tipo | Descrição |
|---|---|---|
| `variableName` | String   | O nome da variável para a qual você deseja obter um valor. |
| `partner` | String   | O nome do parceiro a procurar. |
| `containerNSID` | Número inteiro | O [!DNL NSID] contêiner que você está procurando. O padrão é `0`. |

**Resposta**

Retorna o valor da variável para uma [!UICONTROL DIL] instância.

**Código de exemplo**

<pre class="java"><code>valor var = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
