---
description: A página de detalhes de uma característica individual fornece visão geral de informações como nome de característica, ID, métricas de desempenho, expressões que definem a característica, os segmentos aos quais pertence e o log de auditoria de características. Para veicular esses detalhes, vá para Dados de público-alvo > Características e clique no nome da característica com a qual deseja trabalhar.
seo-description: A página de detalhes de uma característica individual fornece visão geral de informações como nome de característica, ID, métricas de desempenho, expressões que definem a característica, os segmentos aos quais pertence e o log de auditoria de características. Para veicular esses detalhes, vá para Dados de público-alvo > Características e clique no nome da característica com a qual deseja trabalhar.
seo-title: Página de detalhes da característica
solution: Audience Manager
title: Página de detalhes da característica
uuid: 23301376-c 1 cc -4778-b 8 c 4-9831 f 6739 db 9
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# Página de detalhes da característica {#trait-details-page}

A página de detalhes de uma característica individual fornece visão geral de informações como nome de característica, ID, métricas de desempenho, expressões que definem a característica, os segmentos aos quais pertence e o log de auditoria de características. Para veicular esses detalhes, vá [!UICONTROL Audience Data > Traits] para e clique no nome da característica com a qual deseja trabalhar.

## Informações básicas {#basics}

A [!UICONTROL Basic Information] seção mostra detalhes sobre campos obrigatórios e opcionais que você concluiu ao criar a característica. Isso inclui coisas como o tipo de característica, a ID característica, a descrição, a fonte de dados e outros metadados. Esses detalhes variam dependendo do tipo de característica (pasta, onboard ou baseado em regras).

![](assets/basicInfo.png)

## Gráfico de características {#trait-graph}

[!UICONTROL Trait Graph] Fornece métricas de desempenho para a característica selecionada. Posicione o cursor sobre uma linha de tendência para ver dados adicionais para a característica selecionada.

[!UICONTROL Unique Trait Realizations] representa uma contagem de usuários únicos que adicionaram essa característica ao perfil em relação ao intervalo de tempo especificado. O [!UICONTROL Total Trait Population] número indica o número de usuários únicos qualificados atualmente para essa característica.

* Para características baseadas em regras, a qualificação de características ocorre em tempo real, já que os usuários se qualificam para uma característica no navegador.
* Para características onboard, a qualificação de características ocorre depois que um arquivo de entrada é processado, isto é, o arquivo de entrada é [alimentado no Audience Manager](../../faq/faq-inbound-data-ingestion.md) e é quando a qualificação de características ocorre.
* **[!UICONTROL Unique Trait Realizations]**: Uma contagem de usuários únicos que adicionaram essa característica ao perfil em relação ao intervalo de tempo especificado.
* **[!UICONTROL Total Trait Population]**: O número de usuários únicos qualificados atualmente para este trait.

   ![gráfico de características](assets/trait-summary.png)

* **[!UICONTROL Identity Type Breakdown]**: As três primeiras entradas mostram as três principais fontes de dados entre dispositivos com a contagem de população mais alta qualificada para a característica, em ordem decrescente. A quarta entrada mostra a soma de todos os outros [!DNL DPUUIDs] ([!DNL CRM IDs]) que qualificados para a característica, a partir das fontes de dados entre dispositivos que não estão nas três principais. Esse relatório será exibido apenas se você selecionar a ID entre dispositivos no menu [!UICONTROL Show Results By] suspenso no lado superior direito da página. A opção suspensa padrão é [!UICONTROL Device ID], onde este relatório não é exibido.

   ![gráfico de características](assets/trait-identity.png)
   > [!NOTE]
   > O Audience Manager somente exibe o [!UICONTROL Identity Type Breakdown] relatório se houver IDs de dispositivo cruzadas qualificadas para a característica.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/?captions=por_br)

## Expressão de característica {#trait-expression}

[!UICONTROL Trait Expression] A seção mostra os critérios que os usuários precisam atender para se qualificarem para a característica. Essas regras são definidas quando você [cria ou edita uma característica](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## Segmentos de características {#trait-segments}

[!UICONTROL Segments with this Trait] A seção lista todos os segmentos aos quais a característica selecionada pertence. Você pode clicar em um nome de segmento para ver detalhes sobre esse segmento.

![](assets/traitSegments.png)

## Auditoria de características/Registro histórico {#trait-audit-history}

Para características integradas e baseadas em regras, [!UICONTROL Trait Expression Change History] mostra as últimas 10 alterações feitas nas regras de expressão característica e que as efetuaram. Se sua característica tiver mais de 10 alterações, clique em **[!UICONTROL Export to CSV]** para baixar todo o log de auditoria. O log de auditoria não está disponível para as características de pastas ou algoritmos.

>[!NOTE]
>
>[!UICONTROL Not Available] na [!UICONTROL By User] coluna significa que a conta para o usuário foi excluída.

![](assets/traitHistory.png)