---
description: A página de detalhes de uma característica individual fornece uma visão geral de informações como o nome da característica, a ID, as métricas de desempenho, as expressões que definem a característica, os segmentos aos quais ela pertence e o log de auditoria de características. Para visualizar esses detalhes, vá para Dados de público-alvo > Características e clique no nome da característica com a qual deseja trabalhar.
seo-description: A página de detalhes de uma característica individual fornece uma visão geral de informações como o nome da característica, a ID, as métricas de desempenho, as expressões que definem a característica, os segmentos aos quais ela pertence e o log de auditoria de características. Para visualizar esses detalhes, vá para Dados de público-alvo > Características e clique no nome da característica com a qual deseja trabalhar.
seo-title: Página Detalhes da Característica
solution: Audience Manager
title: Página Detalhes da Característica
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: detalhamento de tipo de identidade, detalhamento de identidade, relatório de identidade de público-alvo
translation-type: tm+mt
source-git-commit: 51f38819bfbc72c2588f63a63fb8ba2e963919ff

---


# Página Detalhes da Característica {#trait-details-page}

A página de detalhes de uma característica individual fornece uma visão geral dos detalhes da característica, como nome da característica, ID, métricas de desempenho, expressões que definem a característica, segmentos aos quais ela pertence e o registro de auditoria da característica. Para exibir esses detalhes, vá até **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Traits]** e clique no nome da característica que deseja trabalhar.

## Ferramentas de gerenciamento de características {#trait-management-tools}

A parte superior da página de detalhes da característica hospeda as ferramentas que você pode usar para gerenciar suas características:

1. **[!UICONTROL Add New]**: Use essa opção para criar novas características integradas, algorítmicas ou baseadas em regras.
2. **[!UICONTROL Edit]**: Use essa opção para alterar a configuração da característica atual.
3. **[!UICONTROL Delete]**: Use essa opção para remover a característica atual da sua conta do Audience Manager.
4. **[!UICONTROL Marketplace Recommendations]**: Use essa opção para localizar características semelhantes àquelas que você está visualizando, a partir de taxas de [!UICONTROL Audience Marketplace] dados às quais você não está inscrito. Consulte [Audience Marketplace para Compradores](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) de Dados para saber como navegar no Marketplace e encontrar características semelhantes.

![informações de características básicas](assets/basic-trait-information.png)

## Informações de características {#basics}

A [!UICONTROL Trait Information] seção mostra detalhes sobre os campos obrigatórios e opcionais que você concluiu ao criar a característica. Isso inclui itens como tipo de característica, ID de característica, descrição, fonte de dados e outros metadados. Esses detalhes variam dependendo do tipo de característica (pasta, integrada ou baseada em regras).

## Gráfico de características {#trait-graph}

O [!UICONTROL Trait Graph] fornece rapidamente métricas de desempenho para a característica selecionada. Mantenha o cursor sobre uma linha de tendência para ver dados adicionais para a característica selecionada.

[!UICONTROL Unique Trait Realizations] representam uma contagem de usuários únicos que adicionaram essa característica ao perfil durante um determinado intervalo de tempo. O [!UICONTROL Total Trait Population] indica o número de usuários exclusivos atualmente qualificados para essa característica.

* Para características baseadas em regras, a qualificação de características acontece em tempo real, já que os usuários se qualificam para uma característica em seu navegador.
* Para características integradas, a qualificação de características ocorre depois que um arquivo de entrada é processado, isto é, o arquivo de entrada é [alimentado no Audience Manager](../../faq/faq-inbound-data-ingestion.md) e é quando a qualificação de características acontece.
* **[!UICONTROL Unique Trait Realizations]**: Uma contagem de usuários únicos que adicionaram essa característica ao perfil no intervalo de tempo especificado.
* **[!UICONTROL Total Trait Population]**: O número de usuários exclusivos atualmente qualificados para essa característica.

   ![traço gráfico](assets/trait-summary.png)

* **[!UICONTROL Identity Type Breakdown]**: As três primeiras entradas mostram as três principais fontes de dados entre dispositivos com a maior contagem de população que se qualificaram para a característica, em ordem decrescente. A quarta entrada mostra a soma de todas as outras [!DNL DPUUIDs] ([!DNL CRM IDs]) qualificadas para a característica, das fontes de dados entre dispositivos que não estão nas três principais. Este relatório aparece somente se você selecionar ID entre dispositivos no menu suspenso no lado superior direito da página. [!UICONTROL Show Results By] A opção suspensa padrão é [!UICONTROL Device ID], onde esse relatório não é exibido.

   ![traço gráfico](assets/trait-identity.png)
   > [!NOTE]
   > O Audience Manager só exibe o [!UICONTROL Identity Type Breakdown] relatório se você tiver IDs de dispositivo cruzado qualificadas para a característica.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/?captions=por_br)

## Expressão de características {#trait-expression}

A [!UICONTROL Trait Expression] seção mostra os critérios que os usuários devem atender para se qualificarem para a característica. Essas regras são definidas quando você [cria ou edita uma característica](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## Segmentos de características {#trait-segments}

A [!UICONTROL Segments with this Trait] seção lista todos os segmentos aos quais a característica selecionada pertence. Você pode clicar no nome de um segmento para ver detalhes sobre ele.

![](assets/traitSegments.png)

## Registro de histórico/auditoria de características {#trait-audit-history}

Para traços baseados em regras e integrados, o [!UICONTROL Trait Expression Change History] mostra as últimas 10 alterações feitas nas regras de expressão de características e quem as fez. Se a sua característica tiver mais de 10 alterações, clique **[!UICONTROL Export to CSV]** para baixar todo o log de auditoria. O registro de auditoria não está disponível para características de pasta ou algoritmo.

>[!NOTE]
>
>[!UICONTROL Not Available] na [!UICONTROL By User] coluna, significa que a conta desse usuário foi excluída.

![](assets/traitHistory.png)