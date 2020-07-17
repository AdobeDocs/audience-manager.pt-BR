---
description: A página de detalhes de uma característica individual fornece uma visão geral das informações, como o nome da característica, a ID, as métricas de desempenho, as expressões que definem a característica, os segmentos aos quais ela pertence e o registro de auditoria de características. Para visualizar esses detalhes, vá até Dados de Audiência > Características e clique no nome da característica que deseja trabalhar.
seo-description: A página de detalhes de uma característica individual fornece uma visão geral das informações, como o nome da característica, a ID, as métricas de desempenho, as expressões que definem a característica, os segmentos aos quais ela pertence e o registro de auditoria de características. Para visualizar esses detalhes, vá até Dados de Audiência > Características e clique no nome da característica que deseja trabalhar.
seo-title: Página de detalhes da característica
solution: Audience Manager
title: Página de detalhes da característica
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 1%

---


# [!UICONTROL Trait] Página Detalhes {#trait-details-page}

A página de detalhes de um indivíduo [!UICONTROL trait] fornece uma visão geral dos [!UICONTROL trait] detalhes, como o [!UICONTROL trait] nome, a ID, as métricas de desempenho, as expressões que definem o [!UICONTROL trait], os segmentos aos quais ele pertence e o log de [!UICONTROL trait] auditoria. Para visualização desses detalhes, vá até **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** e clique no nome do [!UICONTROL trait] que você deseja trabalhar.

## [!UICONTROL Trait] Ferramentas de gerenciamento {#trait-management-tools}

A parte superior da página de [!UICONTROL trait] detalhes hospeda as ferramentas que você pode usar para gerenciar seu [!UICONTROL traits]:

1. **[!UICONTROL Add New]**: Use essa opção para criar novos [!UICONTROL rule-based], [!UICONTROL algorithmic]ou [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**: Use esta opção para alterar a configuração do atual [!UICONTROL trait].
3. **[!UICONTROL Delete]**: Use esta opção para remover o atual [!UICONTROL trait] da sua conta do Audience Manager.
4. **[!UICONTROL Marketplace Recommendations]**: Use essa opção para encontrar algo semelhante [!UICONTROL traits] ao que você está visualizando, a partir das taxas de [!UICONTROL Audience Marketplace] dados às quais você não está inscrito. Consulte [Audience Marketplace para Data Buyers](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) para saber como navegar no [!UICONTROL Marketplace] e encontrar características semelhantes.

![informações de características básicas](assets/basic-trait-information.png)

## [!UICONTROL Trait] Informações {#basics}

A [!UICONTROL Trait Information] seção mostra detalhes sobre os campos obrigatórios e opcionais que você concluiu ao criar o [!UICONTROL trait]. Isso inclui itens como [!UICONTROL trait] tipo, [!UICONTROL trait] ID, descrição [!UICONTROL data source]e outros metadados. Esses detalhes variam dependendo do [!UICONTROL trait] tipo ([!UICONTROL folder], [!UICONTROL onboarded]ou [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

O [!UICONTROL Trait Graph] fornece rapidamente métricas de desempenho para a sua seleção [!UICONTROL trait]. Mantenha o cursor sobre uma linha de tendência para ver dados adicionais para os selecionados [!UICONTROL trait].

[!UICONTROL Unique Trait Realizations] representam uma contagem de usuários únicos que adicionaram isso [!UICONTROL trait] ao seu perfil no intervalo de tempo especificado. O [!UICONTROL Total Trait Population] indica o número de usuários exclusivos atualmente qualificados para isso [!UICONTROL trait].

Por exemplo, [!UICONTROL rule-based traits]a qualificação acontece em tempo real, já que os usuários se qualificam para uma qualificação [!UICONTROL trait] [!UICONTROL trait] em seu navegador.

Por exemplo, [!UICONTROL onboarded traits]a qualificação ocorre depois que um arquivo de entrada é processado, isto é, o arquivo de entrada é [!UICONTROL trait] alimentado no Audience Manager [e é quando a](../../faq/faq-inbound-data-ingestion.md) [!UICONTROL trait] qualificação acontece.

A [!UICONTROL Trait Graph] mostra as seguintes informações:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: selecione essa opção para ver os resultados para [!UICONTROL traits] os quais estão coletando dados de perfis autenticados. Ao selecionar essa opção, você verá apenas os dados no [!UICONTROL Cross-Device ID] relatório, e nenhum dado estará presente no [!UICONTROL Device ID] relatório.
   * **[!UICONTROL Device ID]**: selecione essa opção para ver os resultados para [!UICONTROL traits] os quais estão coletando dados para perfis de dispositivos. Ao selecionar essa opção, você verá apenas os dados no [!UICONTROL Device ID] relatório, e nenhum dado estará presente no [!UICONTROL Cross-Device ID] relatório.

      ![traço gráfico](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Uma contagem de usuários únicos que adicionaram isso [!UICONTROL trait] ao seu perfil no intervalo de tempo especificado.
* **[!UICONTROL Total Trait Population]**: O número de usuários exclusivos atualmente qualificados para isso [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: As três primeiras entradas mostram as três principais [!UICONTROL cross-device data sources] com a maior contagem de população que se qualificaram para o [!UICONTROL trait], em ordem decrescente. A quarta entrada mostra a soma de todas as outras [!DNL DPUUIDs] ([!DNL CRM IDs]) qualificadas para a [!UICONTROL trait], das [!UICONTROL cross-device data sources] que não estão nas três principais. Esse relatório será exibido somente se você selecionar [!UICONTROL Cross-device ID] no menu [!UICONTROL Show Results By] suspenso no lado superior direito da página. A opção suspensa padrão é [!UICONTROL Device ID], onde esse relatório não é exibido.

   ![traço gráfico](assets/trait-identity.png)

   >[!NOTE]
   >
   >O Audience Manager só exibe o [!UICONTROL Identity Type Breakdown] relatório se você tiver [!UICONTROL cross-device] IDs qualificadas para o [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Expressão {#trait-expression}

A [!UICONTROL Trait Expression] seção mostra os critérios que os usuários devem atender para se qualificarem para o [!UICONTROL trait]. Essas regras são definidas quando você [cria ou edita uma característica](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait]Segmentos {#trait-segments}

A [!UICONTROL Segments with this Trait] seção lista todos os segmentos aos quais a seleção [!UICONTROL trait] pertence. Você pode clicar no nome de um segmento para ver detalhes sobre ele.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Registro de auditoria / histórico {#trait-audit-history}

Para [!UICONTROL rule-based] e [!UICONTROL onboarded traits], o [!UICONTROL Trait Expression Change History] mostra as últimas 10 alterações feitas nas regras de [!UICONTROL trait] expressão e quem as fez. Se você [!UICONTROL trait] tiver mais de 10 alterações, clique **[!UICONTROL Export to CSV]** para baixar o log de auditoria inteiro. O log de auditoria não está disponível para [!UICONTROL folder] ou [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] na [!UICONTROL By User] coluna, significa que a conta desse usuário foi excluída.

![](assets/traitHistory.png)