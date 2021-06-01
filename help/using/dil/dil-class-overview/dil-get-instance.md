---
description: Recupera uma instância DIL específica do parceiro.
keywords: api do audience manager, api do aam, apis do audience manager, apis do aam
seo-description: Recupera uma instância DIL específica do parceiro.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: Implementação de DIL
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 15%

---

# getDil{#getdil}

Recupera uma instância DIL específica do parceiro.

**Assinatura da função:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parâmetros

| Nome | Tipo | Descrição |
|---|---|---|
| `partner` | String   | O nome do parceiro a procurar. |
| `containerNSID` | Número inteiro | Os padrões são `0`. O NSID do contêiner que você está procurando. Opcional. |

## Resposta

Uma correspondência NSID de parceiro e contêiner bem-sucedida retorna uma instância [!UICONTROL DIL] específica do parceiro. Se não houver correspondência, a API retornará (não retornará) um erro com a mensagem, &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Código de exemplo

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
