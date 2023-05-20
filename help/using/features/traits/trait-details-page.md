---
description: A página de detalhes de uma característica individual fornece visão geral de informações como nome da característica, ID, métricas de desempenho, expressões que definem a característica, segmentos aos quais ela pertence e o log de auditoria de característica. Para exibir esses detalhes, vá para Dados de público-alvo > Características e clique no nome da característica com a qual deseja trabalhar.
seo-description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-title: Trait Details Page
solution: Audience Manager
title: Página de detalhes da característica
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: detalhamento por tipo de identidade, detalhamento de identidade, relatórios de identidade de público-alvo, entre dispositivos, ID entre dispositivos, ID de dispositivo
feature: Traits
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 0%

---

# [!UICONTROL Trait] Página de detalhes {#trait-details-page}

A página de detalhes de um indivíduo [!UICONTROL trait] fornece uma visão geral do [!UICONTROL trait] detalhes, como a [!UICONTROL trait] nome, ID, métricas de desempenho, expressões que definem o [!UICONTROL trait], segmentos aos quais pertence e o [!UICONTROL trait] log de auditoria. Para visualizar esses detalhes, acesse **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** e clique no nome da variável [!UICONTROL trait] com a qual você deseja trabalhar.

## [!UICONTROL Trait] Ferramentas de gerenciamento {#trait-management-tools}

A parte superior do [!UICONTROL trait] página de detalhes hospeda as ferramentas que você pode usar para gerenciar sua [!UICONTROL traits]:

1. **[!UICONTROL Add New]**: use esta opção para criar novas [!UICONTROL rule-based], [!UICONTROL algorithmic]ou [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**: use essa opção para alterar a configuração da variável [!UICONTROL trait].
3. **[!UICONTROL Delete]**: use esta opção para remover a atual [!UICONTROL trait] da sua conta Audience Manager.
4. **[!UICONTROL Marketplace Recommendations]**: Use esta opção para localizar itens semelhantes [!UICONTROL traits] para o que você está visualizando, de [!UICONTROL Audience Marketplace] taxas de dados que você não assinou. Consulte [Audience Marketplace para compradores de dados](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) para saber como navegar na [!UICONTROL Marketplace] e encontrar características semelhantes.

![basic-trait-information](assets/basic-trait-information.png)

## [!UICONTROL Trait] Informações {#basics}

A variável [!UICONTROL Trait Information] A seção mostra detalhes sobre os campos obrigatórios e opcionais que você preencheu ao criar a [!UICONTROL trait]. Isso inclui coisas como [!UICONTROL trait] tipo, [!UICONTROL trait] ID, descrição, [!UICONTROL data source]e outros metadados. Esses detalhes variam dependendo da [!UICONTROL trait] tipo ([!UICONTROL folder], [!UICONTROL onboarded]ou [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

A variável [!UICONTROL Trait Graph] O fornece métricas de desempenho instantâneas para o [!UICONTROL trait]. Mantenha o cursor sobre uma linha de tendência para ver dados adicionais da lista selecionada [!UICONTROL trait].

[!UICONTROL Unique Trait Realizations] representa uma contagem de usuários únicos que adicionaram isso [!UICONTROL trait] ao seu perfil no intervalo de tempo determinado. A variável [!UICONTROL Total Trait Population] indica o número de usuários únicos qualificados atualmente para este [!UICONTROL trait].

Para [!UICONTROL rule-based traits], [!UICONTROL trait] a qualificação acontece em tempo real, à medida que os usuários se qualificam para uma [!UICONTROL trait] no navegador.

Para [!UICONTROL onboarded traits], [!UICONTROL trait] a qualificação ocorre depois que um arquivo de entrada é processado, ou seja, o arquivo de entrada é [alimentado no Audience Manager](../../faq/faq-inbound-data-ingestion.md) e é nesse momento que a [!UICONTROL trait] ocorre qualificação.

A variável [!UICONTROL Trait Graph] mostra as seguintes informações:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: selecione esta opção para ver os resultados de [!UICONTROL traits] que estão coletando dados para perfis autenticados. Ao selecionar essa opção, você verá apenas os dados no [!UICONTROL Cross-Device ID] relatório, e nenhum dado estará presente no [!UICONTROL Device ID] relatório.
   * **[!UICONTROL Device ID]**: selecione esta opção para ver os resultados de [!UICONTROL traits] que estão coletando dados para perfis de dispositivos. Ao selecionar essa opção, você verá apenas os dados no [!UICONTROL Device ID] relatório, e nenhum dado estará presente no [!UICONTROL Cross-Device ID] relatório.

      ![gráfico de características](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: uma contagem de usuários únicos que adicionou isso [!UICONTROL trait] ao seu perfil no intervalo de tempo determinado.
* **[!UICONTROL Total Trait Population]**: o número de usuários únicos qualificados atualmente para essa [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: as três primeiras entradas mostram as três principais [!UICONTROL cross-device data sources] com a maior contagem de população que se qualificou para a [!UICONTROL trait], em ordem descendente. A quarta entrada mostra a soma de todos os outros [!DNL DPUUIDs] ([!DNL CRM IDs]que se qualificaram para a [!UICONTROL trait], do [!UICONTROL cross-device data sources] que não estão entre os três primeiros. Este relatório só será exibido se você selecionar [!UICONTROL Cross-device ID] no [!UICONTROL Show Results By] no canto superior direito da página. A opção suspensa padrão é [!UICONTROL Device ID], em que este relatório não é exibido.

   ![gráfico de características](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager só exibe a variável [!UICONTROL Identity Type Breakdown] relatório se você tiver [!UICONTROL cross-device] IDs qualificadas para o [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Expressão {#trait-expression}

A variável [!UICONTROL Trait Expression] mostra os critérios que os usuários devem atender para se qualificarem para a [!UICONTROL trait]. Essas regras são definidas quando você [criar ou editar uma característica](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait]Segmentos  {#trait-segments}

A variável [!UICONTROL Segments with this Trait] lista todos os segmentos selecionados [!UICONTROL trait] pertence a. Você pode clicar em um nome de segmento para ver detalhes sobre ele.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Log de auditoria/histórico {#trait-audit-history}

Para [!UICONTROL rule-based] e [!UICONTROL onboarded traits], o [!UICONTROL Trait Expression Change History] mostra as 10 últimas alterações feitas no [!UICONTROL trait] regras de expressão e quem as criou. Se o seu [!UICONTROL trait] tiver mais de 10 alterações, clique em **[!UICONTROL Export to CSV]** para baixar todo o log de auditoria. O log de auditoria não está disponível para [!UICONTROL folder] ou [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] no [!UICONTROL By User] coluna significa que a conta desse usuário foi excluída.

![](assets/traitHistory.png)
