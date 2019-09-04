---
description: Recupera uma instância de DIL específica do parceiro.
keywords: api do Manager Manager; api aam; apis do Manager Manager; aam apis
seo-description: Recupera uma instância de DIL específica do parceiro.
seo-title: Getdil
solution: Audience Manager
title: Getdil
uuid: 7 b 95 f 9 bf -14 c 0-4 c 74-b 6 b 9-d 6 b 38513 d 487
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Getdil{#getdil}

Recupera uma instância de DIL específica do parceiro.

**Assinatura da função:**`getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parâmetros

| Nome | Tipo | Descrição |
|---|---|---|
| `partner` | String   | O nome do parceiro a ser pesquisado. |
| `containerNSID` | Número inteiro | Os padrões são `0`. A NSID do contêiner que está procurando. Opcional. |

## Resposta

Uma correspondência de parceiro bem-sucedida e de contêiner NSID retorna uma [!UICONTROL DIL] instância específica do parceiro. Se não houver correspondência, a API retorna (não fornece) um erro com a mensagem " `The DIL instance with partner <name> and containerNSID <ID> was not found.`"

## Código de exemplo

<pre class="java"><code>DIL. getdil ('<i>partner</i>', <i>containernsid</i>); 
DIL. getdil ('<i>partner</i>');</code></pre>
