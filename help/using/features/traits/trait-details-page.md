---
description: A página de detalhes de uma característica individual fornece uma visão geral de informações como o nome da característica, a ID, as métricas de desempenho, as expressões que definem a característica, os segmentos aos quais ela pertence e o log de auditoria de característica. Para visualizar esses detalhes, acesse Dados de público-alvo > Características e clique no nome da característica com a qual deseja trabalhar.
seo-description: A página de detalhes de uma característica individual fornece uma visão geral de informações como o nome da característica, a ID, as métricas de desempenho, as expressões que definem a característica, os segmentos aos quais ela pertence e o log de auditoria de característica. Para visualizar esses detalhes, acesse Dados de público-alvo > Características e clique no nome da característica com a qual deseja trabalhar.
seo-title: Página de detalhes da característica
solution: Audience Manager
title: Página de detalhes da característica
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: detalhamento de tipo de identidade, detalhamento de identidade, relatório de identidade de público-alvo, entre dispositivos, ID entre dispositivos, ID de dispositivo
feature: 'Características '
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 1%

---

# [!UICONTROL Trait] Página Detalhes  {#trait-details-page}

A página de detalhes de um indivíduo [!UICONTROL trait] fornece uma visão geral dos detalhes [!UICONTROL trait], como o nome [!UICONTROL trait], ID, métricas de desempenho, expressões que definem o [!UICONTROL trait], segmentos aos quais pertence e o [!UICONTROL trait] log de auditoria. Para exibir esses detalhes, vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** e clique no nome do [!UICONTROL trait] com o qual deseja trabalhar.

## [!UICONTROL Trait] Ferramentas de gerenciamento  {#trait-management-tools}

A parte superior da página de detalhes [!UICONTROL trait] hospeda as ferramentas que você pode usar para gerenciar seu [!UICONTROL traits]:

1. **[!UICONTROL Add New]**: Use essa opção para criar novo  [!UICONTROL rule-based],  [!UICONTROL algorithmic]ou  [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**: Use essa opção para alterar a configuração do  [!UICONTROL trait]atual.
3. **[!UICONTROL Delete]**: Use esta opção para remover o atual  [!UICONTROL trait] de sua conta Audience Manager.
4. **[!UICONTROL Marketplace Recommendations]**: Use essa opção para encontrar algo semelhante  [!UICONTROL traits] ao que você está visualizando, a partir das tarifas de  [!UICONTROL Audience Marketplace] dados que você não assinou. Consulte [Audience Marketplace for Data Buyers](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) para saber como navegar pelo [!UICONTROL Marketplace] e encontrar características semelhantes.

![informações básicas sobre características](assets/basic-trait-information.png)

## [!UICONTROL Trait] Informações {#basics}

A seção [!UICONTROL Trait Information] mostra detalhes sobre os campos obrigatórios e opcionais concluídos ao criar o [!UICONTROL trait]. Isso inclui coisas como o tipo [!UICONTROL trait], [!UICONTROL trait] ID, descrição, [!UICONTROL data source] e outros metadados. Esses detalhes variam dependendo do tipo [!UICONTROL trait] ([!UICONTROL folder], [!UICONTROL onboarded] ou [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

O [!UICONTROL Trait Graph] fornece imediatamente métricas de desempenho para o [!UICONTROL trait] selecionado. Mantenha o cursor sobre uma linha de tendência para ver dados adicionais para o [!UICONTROL trait] selecionado.

[!UICONTROL Unique Trait Realizations] representam uma contagem de usuários únicos que adicionaram isso  [!UICONTROL trait] ao seu perfil durante um determinado intervalo de tempo. O [!UICONTROL Total Trait Population] indica o número de usuários exclusivos qualificados atualmente para esse [!UICONTROL trait].

Para [!UICONTROL rule-based traits], a qualificação [!UICONTROL trait] acontece em tempo real, pois os usuários se qualificam para um [!UICONTROL trait] em seu navegador.

Para [!UICONTROL onboarded traits], a qualificação [!UICONTROL trait] acontece depois que um arquivo de entrada é processado, ou seja, o arquivo de entrada é [alimentado no Audience Manager](../../faq/faq-inbound-data-ingestion.md) e é quando a qualificação [!UICONTROL trait] acontece.

O [!UICONTROL Trait Graph] mostra as seguintes informações:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: selecione essa opção para ver os resultados para  [!UICONTROL traits] os que estão coletando dados para perfis autenticados. Ao selecionar essa opção, você verá somente os dados no relatório [!UICONTROL Cross-Device ID], e nenhum dado estará presente no relatório [!UICONTROL Device ID].
   * **[!UICONTROL Device ID]**: selecione essa opção para ver os resultados para  [!UICONTROL traits] os que estão coletando dados para perfis de dispositivo. Ao selecionar essa opção, você verá somente os dados no relatório [!UICONTROL Device ID], e nenhum dado estará presente no relatório [!UICONTROL Cross-Device ID].

      ![gráfico de características](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Uma contagem de usuários únicos que adicionaram isso  [!UICONTROL trait] ao seu perfil no intervalo de tempo especificado.
* **[!UICONTROL Total Trait Population]**: O número de usuários únicos qualificados no momento para isso  [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: As três primeiras entradas mostram as três principais  [!UICONTROL cross-device data sources] com a maior contagem de população que se qualificaram para o  [!UICONTROL trait], em ordem decrescente. A quarta entrada mostra a soma de todos os outros [!DNL DPUUIDs] ([!DNL CRM IDs]) que se qualificaram para [!UICONTROL trait], dos [!UICONTROL cross-device data sources] que não estão nas três principais. Este relatório aparece somente se você selecionar [!UICONTROL Cross-device ID] no menu suspenso [!UICONTROL Show Results By] na parte superior direita da página. A opção suspensa padrão é [!UICONTROL Device ID], onde este relatório não é exibido.

   ![gráfico de características](assets/trait-identity.png)

   >[!NOTE]
   >
   >O Audience Manager exibe somente o relatório [!UICONTROL Identity Type Breakdown] se você tiver [!UICONTROL cross-device] IDs qualificadas para o [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Expressão {#trait-expression}

A seção [!UICONTROL Trait Expression] mostra os critérios que os usuários devem atender para se qualificarem para [!UICONTROL trait]. Essas regras são definidas quando você [cria ou edita uma característica](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait]Segmentos {#trait-segments}

A seção [!UICONTROL Segments with this Trait] lista todos os segmentos aos quais o [!UICONTROL trait] selecionado pertence. Você pode clicar em um nome de segmento para ver detalhes sobre ele.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Log de auditoria / histórico  {#trait-audit-history}

Para [!UICONTROL rule-based] e [!UICONTROL onboarded traits], o [!UICONTROL Trait Expression Change History] mostra as últimas 10 alterações feitas nas regras de expressão [!UICONTROL trait] e quem as fez. Se [!UICONTROL trait] tiver mais de 10 alterações, clique em **[!UICONTROL Export to CSV]** para baixar todo o log de auditoria. O log de auditoria não está disponível para [!UICONTROL folder] ou [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] na  [!UICONTROL By User] coluna , significa que a conta desse usuário foi excluída.

![](assets/traitHistory.png)
