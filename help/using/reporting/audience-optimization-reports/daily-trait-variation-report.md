---
description: Esse relatório retorna uma lista de características que foram realizadas pelo menos 10.000 vezes nos 30 dias anteriores à(s) data(s) selecionada(s) e têm um desvio padrão maior ou igual a 1,7 em qualquer direção no mesmo intervalo de tempo. O relatório ajuda a avaliar como o número de impressões de usuários únicos em uma característica varia ao longo do tempo.
seo-description: This report returns a list of traits that have been realized at least 10,000 times in the 30 days prior to the selected date(s) and have a standard deviation greater or equal to 1.7 in either direction over the same time interval. The report helps you evaluate how the number of impressions from unique users in a trait fluctuate over time.
seo-title: Daily Trait Variation Report
solution: Audience Manager
title: Relatório de variação diária de características
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: Audience Optimization Reports
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 1%

---

# Relatório de variação diária de características {#daily-trait-variation-report}

Esse relatório retorna uma lista de características que foram realizadas pelo menos 10.000 vezes nos 30 dias anteriores à(s) data(s) selecionada(s) e têm um desvio padrão maior ou igual a 1,7 em qualquer direção no mesmo intervalo de tempo. O relatório ajuda a avaliar como o número de impressões de usuários únicos em uma característica varia ao longo do tempo.

>[!NOTE]
>
>O relatório Variação diária de característica no Audience Manager segue os princípios do RBAC. Você só pode ver características de fontes de dados às quais você tem acesso com base no [Grupo de usuários RBAC](/help/using/features/administration/administration-overview.md) a que você pertence.

O desvio padrão mede a quantidade de variação ou dispersão da média (ou valor médio/esperado). Um desvio padrão baixo indica que os pontos de dados tendem a estar muito próximos da média. Um desvio padrão alto indica que os pontos de dados estão distribuídos em uma grande faixa de valores.

![](assets/daily_trait_variation.png)

Use o [!UICONTROL Date] para selecionar uma ou mais datas para seu relatório. Um gráfico de barras codificado por cores é exibido na parte inferior da lista, apresentando um visual representativo do intervalo de desvio padrão de todas as características em todas as datas selecionadas. A linha vertical preta indica a média.

A coluna do meio contém uma lista de características, identificadas por [!UICONTROL Trait ID] e [!UICONTROL Trait Name]. Clique em qualquer característica para acessar uma caixa de diálogo pop-up que permite selecionar entre as seguintes opções:

* **Manter apenas:** Remove todas as outras características do relatório e exibe dados somente para essa característica.
* **Excluir:** Remove essa característica do relatório e exibe dados para todas as outras características. É possível excluir várias características.
* **Exibir dados:** Permite exibir dados para essa linha. Você também pode baixar todas as linhas como um arquivo de texto.

A variável [!UICONTROL Standard Deviation] A coluna exibe gráficos de barras codificados por cores que exibem o desvio padrão de cada característica durante o intervalo selecionado. Barras vermelhas indicam características com um desvio padrão negativo (os pontos de dados tendem a estar abaixo da média). As barras verdes indicam características com um desvio padrão positivo (os pontos de dados tendem a estar acima da média). Passe o mouse sobre qualquer barra para exibir uma caixa de diálogo pop-up com mais informações e opções para manter ou excluir essa característica e exibir mais informações.

Os ícones são exibidos na parte inferior do relatório e permitem exportar dados em vários formatos, reverter quaisquer alterações que você tenha feito no relatório (como excluir características), ativar ou desativar atualizações automáticas e atualizar os dados do relatório. Consulte [Explicação dos ícones e ferramentas de relatório](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Casos de uso {#use-cases}

**Exemplo #1**: esse relatório pode ser altamente útil em situações em que você tem características com um alto nível sazonal. Por exemplo, digamos que sua loja online está testando promoções sazonais de vários tipos e preços. Você tem as seguintes características definidas no [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Digamos que você dirija o [!UICONTROL Daily Trait Variation] O relatório do em 20 de dezembro e você perceberá um desvio positivo sólido nas características acima mencionadas nos últimos 30 dias. Isso pode sugerir que seus visitantes estão procurando os produtos mencionados em sua promoção sazonal. Para capitalizar essa tendência, você pode investir mais esforço no direcionamento de criações para essa categoria de produto específica em visitantes que estão interessados nelas.

**Exemplo #2**: este relatório pode ajudar a identificar anomalias de direcionamento relacionadas a problemas de marcação ou a configurações incorretas de características. Imagine que você tenha definido a seguinte característica com base nas categorias da sua loja online:

* `productPage == "smartphones"`

Devido a uma reconfiguração de sua loja, você está dividindo a página de smartphones em várias páginas, com base em nomes de marca. No entanto, você esquece de atualizar as características definidas no [!DNL Audience Manager].

Um mês depois, você executa o [!UICONTROL Daily Trait Variation] assinalar e constatar um grande desvio negativo na `productPage == "smartphones"` característica, embora o número de visitantes tenha aumentado, de acordo com a análise do site. Com base nessas informações, você percebe que não atualizou as características no [!DNL Audience Manager] para as novas páginas de produto, para que você saiba que precisa criar as seguintes características:

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

Depois de fazer isso, você verá seu público-alvo se qualificando para as características recém-criadas.
