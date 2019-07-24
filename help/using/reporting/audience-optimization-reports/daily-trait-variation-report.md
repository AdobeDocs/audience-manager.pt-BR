---
description: Este relatório retorna uma lista de características que foram observadas pelo menos 10,000 vezes nos 30 dias antes das datas selecionadas e têm um desvio padrão maior ou igual a 1.7 em ambas as direções ao mesmo intervalo de tempo. O relatório ajuda a avaliar como o número de impressões de usuários únicos em uma característica flutua ao longo do tempo.
seo-description: Este relatório retorna uma lista de características que foram observadas pelo menos 10,000 vezes nos 30 dias antes das datas selecionadas e têm um desvio padrão maior ou igual a 1.7 em ambas as direções ao mesmo intervalo de tempo. O relatório ajuda a avaliar como o número de impressões de usuários únicos em uma característica flutua ao longo do tempo.
seo-title: Relatório de variação de característica diária
solution: Audience Manager
title: Relatório de variação de característica diária
uuid: 4 e 82 bb 17-d 447-4 ed 1-a 4 fc-e 15 b 0 f 1 b 47 f 0
translation-type: tm+mt
source-git-commit: 8f2ec880cbbe2f516ebc240a712337dc09c4e7f7

---


# Daily Trait Variation Report {#daily-trait-variation-report}

Este relatório retorna uma lista de características que foram observadas pelo menos 10,000 vezes nos 30 dias antes das datas selecionadas e têm um desvio padrão maior ou igual a 1.7 em ambas as direções ao mesmo intervalo de tempo. O relatório ajuda a avaliar como o número de impressões de usuários únicos em uma característica flutua ao longo do tempo.

>[!NOTE]
>
>O relatório Variação de característica diária no Audience Manager acessa os princípios RBAC. You can only see traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

O desvio padrão mede a quantidade de variação ou dispersão da média (ou valor médio/esperado). Um desvio padrão baixo indica que os pontos de dados tendem a ficar muito próximos da média. Um desvio padrão alto indica que os pontos de dados são distribuídos em um grande intervalo de valores.

![](assets/daily_trait_variation.png)

Use the [!UICONTROL Date] list to select one or more dates for your report. Um gráfico de barras codificado por cores é exibido na parte inferior da lista que fornece um representante visual do intervalo de desvio padrão para todas as características em todas as datas selecionadas. A linha vertical preta indica a média.

The middle column contains a list of traits, identified by [!UICONTROL Trait ID] and [!UICONTROL Trait Name]. Clique em qualquer característica para acessar uma caixa de diálogo pop-up que permite a seleção das seguintes opções:

* **Manter apenas:** Remove todas as outras características do relatório e exibe dados somente desse trait.
* **Excluir:** Remove essa característica do relatório e exibe dados de todos os outros traços. É possível excluir várias características.
* **Exibir dados:** Permite exibir dados para essa linha. Também é possível baixar todas as linhas como um arquivo de texto.

The [!UICONTROL Standard Deviation] column displays color-coded bar charts that display the standard deviation for each trait over the selected interval. As barras vermelhas indicam características com um desvio padrão negativo (pontos de dados tendem a estar abaixo da média). As barras verdes indicam características com um desvio padrão positivo (pontos de dados tendem a estar acima da média). Passe o mouse sobre qualquer barra para exibir uma caixa de diálogo pop-up com mais informações e opções para manter ou excluir essas características e exibir mais informações.

Os ícones são exibidos na parte inferior do relatório que permite exportar dados em vários formatos, reverter quaisquer alterações que você tenha feito ao relatório (como excluir características), ativar ou desativar as atualizações automáticas e atualizar os dados do relatório. See [Report Icons and Tools Explained](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Casos de uso {#use-cases}

**Exemplo n º 1**: esse relatório pode ser muito útil em situações nas quais você tem características com um nível de sazonalidade alto. Por exemplo, digamos que sua loja online esteja testando promoções sazonais de vários tipos e preços. You have the following traits defined in [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Say you run the [!UICONTROL Daily Trait Variation] report on the 20th of December and you notice a solid positive deviation on the above mentioned traits in the past 30 days. Isso pode sugerir que os visitantes buscem pelos produtos mencionados na promoção sazonal. Para aproveitar essa tendência, você pode investir mais esforços em anúncios de definição de metas para a categoria de produtos específica em visitantes interessados neles.

**Exemplo n º 2**: este relatório pode ajudar a identificar anomalias de definição de metas relacionadas a problemas de marcação ou configurações de características. Imagine que você definiu a seguinte característica com base nas categorias de sua loja online:

* `productPage == "smartphones"`

Devido a uma reconfiguração de sua loja, você divide a página smartphones em várias páginas, com base em nomes de marcas. However, you forget to update the traits defined in [!DNL Audience Manager].

One month later, you run the [!UICONTROL Daily Trait Variation] report and notice a large negative deviation on the `productPage == "smartphones"` trait, although your visitor number has increased, according to your site analytics. Based on this information, you realize that you haven't updated the traits in [!DNL Audience Manager] for your new product pages, so you know that you need to create the following traits:

* Productpage = = "samsung"
* Productpage = = "maçã"
* Productpage = = "huawei"

Depois disso, você verá o público-alvo qualificado para as características recém-criadas.
