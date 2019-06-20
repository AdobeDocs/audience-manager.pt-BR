---
description: Recupera uma instância de DIL específica do parceiro.
keywords: api do Manager Manager; api aam; apis do Manager Manager; aam apis
seo-description: Recupera uma instância de DIL específica do parceiro.
seo-title: Getdil
solution: Audience Manager
title: Getdil
uuid: 7 b 95 f 9 bf -14 c 0-4 c 74-b 6 b 9-d 6 b 38513 d 487
translation-type: tm+mt
source-git-commit: 128368669163097e604f6b23ab538341adcf8d7a

---


# getDil{#getdil}

Recupera uma instância de DIL específica do parceiro.

**Assinatura da função:**`getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parâmetros

| Nome | Tipo | Descrição |
|---|---|---|
| `partner` | String   | O nome do parceiro a ser pesquisado. |
| `containerNSID` | Número inteiro | Defaults is `0`. A NSID do contêiner que está procurando. Opcional. |

## Resposta

A successful partner and container NSID match returns a partner-specific [!UICONTROL DIL] instance. If there is no match, the API returns (does not throw) an error with the message, &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Código de exemplo

<pre class="java"><code>DIL. getdil ('<i>partner</i>', <i>containernsid</i>); 
DIL. getdil ('<i>partner</i>');</code>
</pre>
