---
description: Recupera um valor específico de um servidor de anúncios.
seo-description: Recupera um valor específico de um servidor de anúncios.
seo-title: Dexgetqsvars
solution: Audience Manager
title: Dexgetqsvars
uuid: 6 d 21 c 7 a 4-43 f 8-456 b -8831-47343 dbb 047 e
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Dexgetqsvars{#dexgetqsvars}

Recupera um valor específico de um servidor de anúncios.

**Assinatura da função:**`dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parâmetros**

| Nome | Tipo | Descrição |
|---|---|---|
| `variableName` | String   | O nome da variável para a qual você deseja obter um valor. |
| `partner` | String   | O nome do parceiro a ser pesquisado. |
| `containerNSID` | Número inteiro | O [!DNL NSID] do contêiner pelo qual está procurando. Os padrões são `0`. |

**Resposta**

Retorna o valor da variável de uma [!UICONTROL DIL] instância.

**Código de exemplo**

<pre class="java"><code>var value = DIL. dexgetqsvars ('<i>variablename</i>','<i>partnername</i>',<i>containernsid</i>);</code></pre>
