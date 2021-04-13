---
description: Este relatório retorna uma lista de características que foram realizadas pelo menos 10.000 vezes nos 30 dias anteriores às datas selecionadas e que têm um desvio padrão maior ou igual a 1,7 em qualquer direção no mesmo intervalo de tempo. O relatório ajuda a avaliar como o número de impressões de usuários únicos em uma característica flutuam ao longo do tempo.
seo-description: Este relatório retorna uma lista de características que foram realizadas pelo menos 10.000 vezes nos 30 dias anteriores às datas selecionadas e que têm um desvio padrão maior ou igual a 1,7 em qualquer direção no mesmo intervalo de tempo. O relatório ajuda a avaliar como o número de impressões de usuários únicos em uma característica flutuam ao longo do tempo.
seo-title: Relatório de variação diária de características
solution: Audience Manager
title: Relatório de variação diária de características
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: Relatórios de otimização de público-alvo
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 2%

---

# Relatório de variação diária de características {#daily-trait-variation-report}

Este relatório retorna uma lista de características que foram realizadas pelo menos 10.000 vezes nos 30 dias anteriores às datas selecionadas e que têm um desvio padrão maior ou igual a 1,7 em qualquer direção no mesmo intervalo de tempo. O relatório ajuda a avaliar como o número de impressões de usuários únicos em uma característica flutuam ao longo do tempo.

>[!NOTE]
>
>O relatório Variação diária de característica no Audience Manager adere aos princípios do RBAC. Você só pode ver características de fontes de dados às quais tem acesso com base no [Grupo de usuários RBAC](/help/using/features/administration/administration-overview.md) ao qual pertence.

O desvio-padrão mede a quantidade de variação ou dispersão em relação à média (ou valor médio/valor esperado). Um desvio padrão baixo indica que os pontos de dados tendem a estar muito próximos da média. Um desvio padrão alto indica que os pontos de dados estão distribuídos por uma grande variedade de valores.

![](assets/daily_trait_variation.png)

Use a lista [!UICONTROL Date] para selecionar uma ou mais datas para seu relatório. Um gráfico de barras codificado por cores é exibido na parte inferior da lista, que fornece um representante visual do intervalo de desvio padrão para todas as características em todas as datas selecionadas. A linha vertical preta indica a média.

A coluna central contém uma lista de características, identificadas por [!UICONTROL Trait ID] e [!UICONTROL Trait Name]. Clique em qualquer característica para acessar uma caixa de diálogo pop-up que permite selecionar entre as seguintes opções:

* **Manter somente:** Remove todas as outras características do relatório e exibe dados apenas para essa característica.
* **Excluir:** remove essa característica do relatório e exibe dados de todas as outras características. É possível excluir várias características.
* **Exibir dados:** permite exibir dados dessa linha. Também é possível baixar todas as linhas como um arquivo de texto.

A coluna [!UICONTROL Standard Deviation] exibe gráficos de barras codificados por cores que exibem o desvio padrão para cada característica no intervalo selecionado. As barras vermelhas indicam características com um desvio padrão negativo (os pontos de dados tendem a estar abaixo da média). As barras verdes indicam características com um desvio padrão positivo (os pontos de dados tendem a estar acima da média). Passe o mouse sobre qualquer barra para exibir uma caixa de diálogo pop-up com mais informações e opções para manter ou excluir essa característica e exibir mais informações.

Os ícones são exibidos na parte inferior do relatório que permitem exportar dados em vários formatos, reverter qualquer alteração que você tenha feito no relatório (como excluir características), ativar ou desativar atualizações automáticas e atualizar os dados do relatório. Consulte [Ícones e ferramentas de relatório explicados](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Casos de uso {#use-cases}

**Exemplo #1**: esse relatório pode ser altamente útil em situações em que você tem características com um nível de sazonalidade alto. Por exemplo, considere que sua loja online está testando promoções sazonais de vários tipos e preços. Você tem as seguintes características definidas em [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Digamos que você execute o relatório [!UICONTROL Daily Trait Variation] no dia 20 de dezembro e observe um desvio positivo sólido nas características mencionadas acima nos últimos 30 dias. Isso pode sugerir que seus visitantes estejam procurando os produtos mencionados em sua promoção sazonal. Para capitalizar essa tendência, você pode investir mais esforço na segmentação de anúncios para essa categoria específica de produto em visitantes que estejam interessados neles.

**Exemplo #2**: este relatório pode ajudar a identificar anomalias de direcionamento relacionadas a problemas de marcação ou configurações de características incorretas. Imagine que você tenha definido a seguinte característica com base nas categorias de sua loja online:

* `productPage == "smartphones"`

Devido a uma reconfiguração da sua loja, você está dividindo a página de smartphones em várias páginas, com base nos nomes de marca. No entanto, você se esqueça de atualizar as características definidas em [!DNL Audience Manager].

Um mês depois, você executa o relatório [!UICONTROL Daily Trait Variation] e nota um grande desvio negativo na característica `productPage == "smartphones"`, embora seu número de visitantes tenha aumentado, de acordo com as análises do site. Com base nessas informações, você percebe que não atualizou as características em [!DNL Audience Manager] para suas novas páginas de produtos, para que saiba que precisa criar as seguintes características:

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

Depois disso, você verá seu público-alvo qualificado para as características recém-criadas.
