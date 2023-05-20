---
description: Recupera uma instância DIL específica do parceiro.
keywords: api do audience manager;api do aam;apis do audience manager;apis do aam
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 15%

---

# getDil{#getdil}

Recupera uma instância DIL específica do parceiro.

**Assinatura da Função:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parâmetros

| Nome | Tipo | Descrição |
|---|---|---|
| `partner` | String   | O nome do parceiro a ser pesquisado. |
| `containerNSID` | Número inteiro | O padrão é `0`. O NSID do contêiner que você está procurando. Opcional. |

## Resposta

Uma correspondência NSID de parceiro e contêiner bem-sucedida retorna uma correspondência específica de parceiro [!UICONTROL DIL] instância. Se não houver correspondência, a API retornará (não lançará) um erro com a mensagem &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Código de exemplo

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
