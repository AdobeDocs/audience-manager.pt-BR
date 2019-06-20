---
description: A página de detalhes de uma característica individual fornece visão geral de informações como nome de característica, ID, métricas de desempenho, expressões que definem a característica, os segmentos aos quais pertence e o log de auditoria de características. Para veicular esses detalhes, vá para Dados de público-alvo > Características e clique no nome da característica com a qual deseja trabalhar.
seo-description: A página de detalhes de uma característica individual fornece visão geral de informações como nome de característica, ID, métricas de desempenho, expressões que definem a característica, os segmentos aos quais pertence e o log de auditoria de características. Para veicular esses detalhes, vá para Dados de público-alvo > Características e clique no nome da característica com a qual deseja trabalhar.
seo-title: Página de detalhes da característica
solution: Audience Manager
title: Página de detalhes da característica
uuid: 23301376-c 1 cc -4778-b 8 c 4-9831 f 6739 db 9
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Trait Details Page {#trait-details-page}

A página de detalhes de uma característica individual fornece visão geral de informações como nome de característica, ID, métricas de desempenho, expressões que definem a característica, os segmentos aos quais pertence e o log de auditoria de características. To vew these details, go to [!UICONTROL Audience Data > Traits] and click the name of the trait you want to work with.

## Informações básicas {#basics}

The [!UICONTROL Basic Information] section shows details about required and optional fields you completed when building the trait. Isso inclui coisas como o tipo de característica, a ID característica, a descrição, a fonte de dados e outros metadados. Esses detalhes variam dependendo do tipo de característica (pasta, onboard ou baseado em regras).

![](assets/basicInfo.png)

## Trait Graph {#trait-graph}

[!UICONTROL Trait Graph] Fornece métricas de desempenho para a característica selecionada. Posicione o cursor sobre uma linha de tendência para ver dados adicionais para a característica selecionada.

[!UICONTROL Unique Trait Realizations] representa uma contagem de usuários únicos que adicionaram essa característica ao perfil em relação ao intervalo de tempo especificado. The [!UICONTROL Total Trait Population] indicates the number of unique users currently qualified for this trait.

* Para características baseadas em regras, a qualificação de características ocorre em tempo real, já que os usuários se qualificam para uma característica no navegador.
* For onboarded traits, trait qualification happens after an inbound file is processed, i.e. the inbound file is [fed into Audience Manager](../../faq/faq-inbound-data-ingestion.md) and that is when the trait qualification happens.
* **Análise de característica exclusiva**: Uma contagem de usuários únicos que adicionaram essa característica ao perfil em relação ao intervalo de tempo especificado.
* **População de característica total**: O número de usuários únicos qualificados atualmente para este trait.

![](assets/traitGraph.png)

## Trait Expression {#trait-expression}

[!UICONTROL Trait Expression] A seção mostra os critérios que os usuários precisam atender para se qualificarem para a característica. These rules are set when you [create or edit a trait](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## Trait Segments {#trait-segments}

[!UICONTROL Segments with this Trait] A seção lista todos os segmentos aos quais a característica selecionada pertence. Você pode clicar em um nome de segmento para ver detalhes sobre esse segmento.

![](assets/traitSegments.png)

## Trait Audit/History Log {#trait-audit-history}

For rule-based and onboarded traits, the [!UICONTROL Trait Expression Change History] shows you the last 10 changes made to trait expression rules and who made them. If your trait has more than 10 changes, click **[!UICONTROL Export to CSV]** to download the entire audit log. O log de auditoria não está disponível para as características de pastas ou algoritmos.

>[!NOTE]
>
>[!UICONTROL Not Available] na [!UICONTROL By User] coluna significa que a conta para o usuário foi excluída.

![](assets/traitHistory.png)