---
description: Este relatório retorna uma lista de características que foram realizadas pelo menos 10.000 vezes nos 30 dias anteriores às datas selecionadas e têm um desvio padrão maior ou igual a 1,7 em ambas as direções, ao longo do mesmo intervalo de tempo. O relatório ajuda a avaliar como o número de impressões de usuários únicos em uma característica flutuam ao longo do tempo.
seo-description: Este relatório retorna uma lista de características que foram realizadas pelo menos 10.000 vezes nos 30 dias anteriores às datas selecionadas e têm um desvio padrão maior ou igual a 1,7 em ambas as direções, ao longo do mesmo intervalo de tempo. O relatório ajuda a avaliar como o número de impressões de usuários únicos em uma característica flutuam ao longo do tempo.
seo-title: Relatório de variação diária de características
solution: Audience Manager
title: Relatório de variação diária de características
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---


# Relatório de variação diária de características {#daily-trait-variation-report}

Este relatório retorna uma lista de características que foram realizadas pelo menos 10.000 vezes nos 30 dias anteriores às datas selecionadas e têm um desvio padrão maior ou igual a 1,7 em ambas as direções, ao longo do mesmo intervalo de tempo. O relatório ajuda a avaliar como o número de impressões de usuários únicos em uma característica flutuam ao longo do tempo.

>[!NOTE]
>
>O relatório de Variação de Características Diárias em Audience Manager respeita os princípios do RBAC. Você só pode ver características de fontes de dados às quais você tem acesso com base no [Grupo de usuários RBAC](/help/using/features/administration/administration-overview.md) ao qual você pertence.

O desvio padrão mede a quantidade de variação ou dispersão em relação à média (ou valor médio/esperado). Um desvio padrão baixo indica que os pontos de dados tendem a estar muito próximos da média. Um desvio padrão alto indica que os pontos de dados estão distribuídos por uma grande variedade de valores.

![](assets/daily_trait_variation.png)

Use a lista [!UICONTROL Date] para selecionar uma ou mais datas para seu relatório. Um gráfico de barras codificado por cores é exibido na parte inferior da lista, que fornece um representante visual do intervalo de desvio padrão para todas as características em todas as datas selecionadas. A linha vertical preta indica a média.

A coluna central contém uma lista de características, identificadas por [!UICONTROL Trait ID] e [!UICONTROL Trait Name]. Clique em qualquer característica para acessar uma caixa de diálogo pop-up que permite selecionar entre as seguintes opções:

* **Manter somente:** Remove todas as outras características do relatório e exibe dados somente para esta característica.
* **Excluir:** Remove essa característica do relatório e exibe os dados de todas as outras características. É possível excluir várias características.
* **Dados de visualização:** Permite exibir dados para essa linha. Também é possível baixar todas as linhas como um arquivo de texto.

A coluna [!UICONTROL Standard Deviation] exibe gráficos de barras codificados por cores que exibem o desvio padrão para cada característica durante o intervalo selecionado. As barras vermelhas indicam características com um desvio padrão negativo (os pontos de dados tendem a estar abaixo da média). As barras verdes indicam características com um desvio padrão positivo (os pontos de dados tendem a estar acima da média). Passe o mouse sobre qualquer barra para exibir uma caixa de diálogo pop-up com mais informações e opções para manter ou excluir essa característica e visualização com mais informações.

Os ícones são exibidos na parte inferior do relatório que permitem exportar dados em vários formatos, reverter quaisquer alterações que você tenha feito no relatório (como excluir características), ativar ou desativar atualizações automáticas e atualizar os dados do relatório. Consulte [Ícones de relatório e ferramentas explicadas](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Casos de uso {#use-cases}

**Exemplo nº 1**: este relatório pode ser muito útil em situações em que você tem características com alto nível de sazonalidade. Por exemplo, digamos que sua loja online está testando promoções sazonais de vários tipos e preços. Você tem as seguintes características definidas em [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Digamos que você execute o relatório [!UICONTROL Daily Trait Variation] no dia 20 de dezembro e observe um desvio positivo sólido nas características acima mencionadas nos últimos 30 dias. Isso pode sugerir que seus visitantes estejam procurando os produtos mencionados em sua promoção sazonal. Para aproveitar essa tendência, você pode investir mais esforços na definição de metas para as criações para aquela categoria de produtos específica em visitantes que estão interessados neles.

**Exemplo nº 2**: este relatório pode ajudá-lo a identificar anomalias de definição de metas relacionadas a problemas de marcação ou configurações incorretas de características. Imagine que você definiu a seguinte característica com base nas categorias de sua loja online:

* `productPage == "smartphones"`

Devido a uma reconfiguração da sua loja, você está dividindo a página de smartphones em várias páginas, com base nos nomes das marcas. No entanto, você se esqueceu de atualizar as características definidas em [!DNL Audience Manager].

Um mês depois, você executa o relatório [!UICONTROL Daily Trait Variation] e nota um grande desvio negativo na característica `productPage == "smartphones"`, embora seu número de visitante tenha aumentado, de acordo com as análises do site. Com base nessas informações, você percebe que não atualizou as características em [!DNL Audience Manager] para suas novas páginas de produtos, portanto, você sabe que precisa criar as seguintes características:

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

Depois de fazer isso, você verá sua audiência se qualificando para as características recém-criadas.
