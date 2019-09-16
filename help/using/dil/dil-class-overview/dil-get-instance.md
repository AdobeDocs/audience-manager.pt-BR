---
description: Recupera uma instância DIL específica do parceiro.
keywords: audience manager api;aam api;audience manager apis;aam apis
seo-description: Recupera uma instância DIL específica do parceiro.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# getDil{#getdil}

Recupera uma instância DIL específica do parceiro.

**** Assinatura da função: `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parâmetros

| Nome | Tipo | Descrição |
|---|---|---|
| `partner` | String   | O nome do parceiro a procurar. |
| `containerNSID` | Número inteiro | O padrão é `0`. O NSID do contêiner que você está procurando. Opcional. |

## Resposta

Uma correspondência NSID de parceiro e contêiner bem-sucedida retorna uma [!UICONTROL DIL] instância específica do parceiro. Se não houver correspondência, a API retornará (não retornará) um erro com a mensagem, " `The DIL instance with partner <name> and containerNSID <ID> was not found.`"

## Código de exemplo

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
