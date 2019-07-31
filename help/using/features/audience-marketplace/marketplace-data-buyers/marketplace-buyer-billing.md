---
description: Os compradores de dados do Audience Marketplace aceitam relatar todas as impressões de anúncios veiculadas usando características contidas no feed de dados com base em um custo por mil impressões de anúncios (CPM). O uso de CPM ocorre no dia 5 º dia de cada mês do calendário e inclui dados do mês anterior. Assinantes de taxa fixa não precisam relatar o uso.
seo-description: Os compradores de dados do Audience Marketplace aceitam relatar todas as impressões de anúncios veiculadas usando características contidas no feed de dados com base em um custo por mil impressões de anúncios (CPM). O uso de CPM ocorre no dia 5 º dia de cada mês do calendário e inclui dados do mês anterior. Assinantes de taxa fixa não precisam relatar o uso.
seo-title: Cobrança para compradores de feed de dados
solution: Audience Manager
title: Cobrança para compradores de feed de dados
keywords: Relatório de nível de segmento, nível de segmento, nível de segmento
uuid: d 7236667-282 b -4160-9909-579721 af 4016
translation-type: tm+mt
source-git-commit: a02ef4cfa987c05e3db173f8e6e9a635d1ecd1fd

---


# Billing for Data Feed Buyers {#billing-for-data-feed-buyers}

Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions ([!DNL CPM]) basis. [!DNL CPM] o uso ocorre no dia 5 º dia de cada mês do calendário e inclui dados do mês anterior. Assinantes de taxa fixa não precisam relatar o uso.

## How to Report CPM Usage {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] os compradores de dados aceitam relatar todas as impressões de anúncios veiculadas usando características contidas no feed de dados com base em custo por mil impressões de anúncios ([!DNL CPM]). [!DNL CPM] o uso ocorre no dia 5 dia de cada mês do calendário e inclui dados do mês anterior. Assinantes de taxa fixa não precisam relatar o uso.

[!UICONTROL Audience Marketplace] oferece duas formas de relatar [!DNL CPM] o uso:

* **Relatório de nível de segmento**: este é o método de relatório [!DNL CPM] de uso recomendado. When you report [!DNL CPM] usage at segment level, the data feed-level reporting section is automatically filled in with the corresponding usage amounts, based on the algorithms described in [Cost Attribution for CPM Data Feeds](#cost-attribution).
* **Relatório de nível de feed de dados**: este método exige que você reporte individualmente o [!DNL CPM] uso para cada feed de dados, com base nos algoritmos descritos na [Atribuição de custo para Feeds de dados CPM](#cost-attribution). No entanto, esse método é mais tedioso e propensa a erro do que o relatório de nível de segmento.

## Report CPM Usage at Segment Level {#segment-level-report}

The [!UICONTROL Segment Usage] tab allows you to report segment-level usage, while displaying the segments grouped by the destinations they are mapped to.

After reporting [!DNL CPM] usage at segment level, [!UICONTROL Audience Marketplace] automatically assigns the corresponding data feeds the correct usage, based on the [Cost Attribution for CPM Data Feeds](#cost-attribution).

To report [!DNL CPM] usage at segment level:

1. Go to **[!UICONTROL Audience Marketplace > Payables]**.
2. Select the **[!UICONTROL Segment Usage]** tab.
3. Preencha o uso para seus segmentos. You can use the [!UICONTROL Search] box to filter the segments if you only need to report usage for some of them.
4. Clique em **[!UICONTROL Edit Segments Usage]**.
5. Enter the [!DNL CPM] usage amount in the [!UICONTROL Usage] column.
6. Click **[!UICONTROL Save]** when you're done and review the confirmation dialog.
   ![confirm-segment-use](assets/confirm-segment-usage.png)
7. Clique em **[!UICONTROL Confirm]**.

## Report CPM Usage at Data Feed Level {#feed-level-report}

Data feed-level reporting is a more tedious and prone to error process, since you must individually calculate [!DNL CPM] usage for each data feed. We recommend that you [Report CPM Usage at Segment Level](#segment-level-report) instead.

To report [!DNL CPM] usage at segment level:

1. Go to **[!UICONTROL Audience Marketplace > Payables]**.
2. Select the **[!UICONTROL Feed Usage]** tab.
3. Use the [!UICONTROL Search] box to filter the data feeds and identify the ones that you need to report usage for.
4. Clique em **[!UICONTROL Edit Feeds Usage]**.
5. Calculate the [!DNL CPM] usage for each data feed based on the [Cost Attribution for CPM Data Feeds](#cost-attribution), and enter it in the [!UICONTROL Usage] column.
6. Click **[!UICONTROL Save]** when you're done and review the confirmation dialog.

   ![confirm-feed-use](assets/confirm-feed-usage.png)

7. Clique em **[!UICONTROL Confirm]**.

## Relatório em massa

To reduce errors and overhead while reporting [!DNL CPM] usage, you can use the bulk reporting option to download a [!DNL CSV] file containing the data feeds and segments, fill in the usage, and upload it back to [!DNL Audience Manager]. Você pode usar o relatório em massa para relatar o feed e o uso do segmento.

To update [!DNL CPM] usage in bulk:

1. Go to **[!UICONTROL Audience Marketplace > Payables]**.
1. Select the **[!UICONTROL Feed Usage]** or **[!UICONTROL Segment Usage]** tab, depending on the type of reporting that you want to update.
1. Click **[!UICONTROL Edit Feeds Usage]** or **[!UICONTROL Edit Segments Usage]**.
1. Click **[!UICONTROL download the current usage]** to make sure you use a valid CSV file.
1. Abra o arquivo no computador e preencha o relatório de uso.
1. Click **[!UICONTROL Choose a CSV file]** to upload the updated usage report.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] valida o arquivo assim que o carrega e solicita que ele detecte todos os erros no arquivo.

### Erros de validação de relatório em massa

| Mensagem de erro | Descrição | Correção |
| ------------- | -------------| -----|
| Entrada inválida | [!DNL Audience Manager] detectou uma alteração no esquema [!DNL CSV] do arquivo, como colunas ausentes ou alterações nos títulos das colunas. | Evite alterar a estrutura da tabela. |
| Não encontrada | For [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Segment ID] and [!UICONTROL Destination ID] combination. For [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. | For [!UICONTROL Segment Level Reporting], check the validity of the [!UICONTROL Segment ID] and [!UICONTROL Destination ID] combination. For [!UICONTROL Feed Level Reporting], check the validity of the [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. |
| Registros duplicados encontrados | [!DNL Audience Manager] registros duplicados detectados com valores de impressão diferentes. | Revise o relatório e certifique-se de não relatar valores de uso diferentes para o mesmo feed de dados ou segmento. |
| Valores não suportados | [!DNL Audience Manager] valores não numéricos na [!DNL Audience Manager] coluna. | Review the report and make sure you only enter numerical values in the [!DNL Audience Manager] column. |
| Cabeçalhos para campos obrigatórios ausentes | [!DNL Audience Manager] cabeçalhos de tabela ausentes para campos obrigatórios. For [!UICONTROL Segment Level Reporting], the mandatory fields are: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. For [!UICONTROL Feed Level Reporting], the mandatory fields are: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name],  [!UICONTROL Use Case] | Revise o relatório e verifique se os cabeçalhos da tabela não foram adulterados. |

>[!NOTE]
>Removing rows from the [!DNL CSV] usage report does not have any effect on the existing usage report. [!DNL Audience Manager] processa apenas os campos incluídos no relatório.

## [!DNL CPM] Práticas recomendadas para relatórios

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recomendações </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Sempre relatar o número total de impressões</b> </p> </td> 
   <td colname="col2"> <p>Para totais de impressão CPM: </p>
   <p> Relate o número total de impressões, sem usar decimais. O Audience Manager calcula automaticamente o CPM com base no número total de relatórios.</p><p>Se precisar relatar as impressões de 1,234,567, informe exatamente como isso. Não é necessário dividir o número total de impressões em 1,000 para calcular o CPM.</p><p>As características usadas para otimizar o conteúdo da Web ou do aplicativo (Otimização de conteúdo) usando ferramentas como o Adobe Target ou um destino do Analytics não contribuem para os totais de Uso para planos de CPM. Normalmente, os provedores de dados são compensados pela Otimização de conteúdo usando planos de taxa simples.</p><p>See <a href="#cost-attribution">Cost Attribution for CPM Data Feeds</a> for more information. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Pressionar o intervalo de relatório mensal</b> </p> </td> 
   <td colname="col2"> <p>O sistema de relatório fecha após o dia 5 de cada mês. Se você não reportar o uso de CPM em seguida, deverá adicionar essa quantia ao relatório para o mês seguinte. Por exemplo, digamos que você use impressões de 1000 em outubro, perca o prazo de relatório de outubro e use impressões 1000 em novembro. Nesse caso, você relata o total de outubro e novembro (2000) em dezembro entre the º e the º de dezembro.</p><p><b>Dica</b>: Você sempre deve tentar reportar o uso de CPM para o mês anterior entre os 1 º e 5 º dias do mês seguinte.</p><p>Você pode relatar o uso de CPM assim como o 5 º do mês do calendário, mas isso não é recomendado. Relatar o uso de CPM antes do dia 5 de cada mês dá ao Audience Manager tempo para verificar e processar os dados.</p> </td>
  </tr> 
 </tbody> 
</table>

## Cost Attribution for CPM Data Feeds {#cost-attribution}

In [!UICONTROL Audience Marketplace] you must self-report impression amounts each month, for each of your segments. We recommend reporting [!DNL CPM] usage at segment level, so that cost attribution is done automatically.

<!-- marketplace_cpm_billing.xml -->

### Billing Summary {#billing-summary}

You must submit [!DNL CPM] data feed impression amounts between the 1st and the 5th days of each calendar month. To do this correctly, we recommend that you [Report CPM Usage at Segment Level](#segment-level-report).

>[!TIP]
>When you report [!DNL CPM] usage at segment level, the data feed-level reporting section is automatically filled in with the corresponding usage amounts.

Should you need to [!UICONTROL Report CPM Usage at Data Feed Level], you must individually compile all impressions delivered for each feed in the previous calendar month, and report them according to the billing allocation described in this article.

After you report [!DNL CPM] number for the previous calendar month, [!DNL Adobe] will do the following:

* Create an invoice and bill you based on the [!DNL CPM] rate for each subscribed data feed.
* Pay data providers (sellers) fees owed based on your reported [!DNL CPM] use.

>[!IMPORTANT]
>
>Como comprador, todos os totais de impressão relatados devem ser verdadeiros e precisos. Se você não relatar os totais de impressão até o dia 5 º de cada mês, deverá incluir totais para o mês não relatado no mês seguinte.

## Assign Impressions at Feed Level Based on Trait Qualification Rules {#assign-impressions}

The [!UICONTROL Activation] use case lets you use traits in the corresponding data feed to create segments in [Segment Builder](../../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74) and map those segments to a destination. The Boolean operators [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT] let you set the conditions for trait and segment qualification.

When you [Report CPM Usage at Data Feed Level](#feed-level-report), you must allocate impressions proportionally for each data feed, according to the [!DNL Boolean] operators used in the trait qualification rules. A tabela a seguir lista como alocar apropriadamente impressões por regra booleana ou tipo de característica.

>[!TIP]
>[Relate o uso de CPM no nível do segmento](#segment-level-report) para fazer com que o relatório de nível de feed de dados faça o mesmo automaticamente pelo Audience Manager.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Lógica ou Tipo de qualificação de regra </th> 
   <th colname="col2" class="entry"> Distribuição de faturamento </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> AND</span> </p> </td> 
   <td colname="col2"> <p>Apply 100% of the delivered impression totals to all the provider traits in a rules-based segment that uses a Boolean <span class="wintitle"> AND</span> condition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> OU</span> </p> </td> 
   <td colname="col2"> <p>Aplique a alocação ponderada dos totais de impressão entregues a todas as características do provedor em um segmento baseado em regras que use uma condição OU booleana. A alocação ponderada é calculada usando a seguinte fórmula:</p><p><code>(População característica/População de segmentos) * Número de impressões * Custo do CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NÃO</span> </p> </td> 
   <td colname="col2"> <p>Apply 100% of the delivered impression totals to all the provider traits in a rules-based segment that uses a Boolean <span class="wintitle"> NOT</span> condition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segmentos algorítmicos </p> </td> 
   <td colname="col2"> <p>Aplique 100% dos totais de impressão entregues a todos os feeds de provedor em um segmento que contenha características algorítmicas. </p> </td> 
  </tr>
 </tbody>
</table>

## Billing Examples {#billing-examples}

The examples below are meant to illustrate how [!DNL CPM] usage allocation is done at data feed level.

>[!MPORTANT]
>We recommend that you [Report CPM Usage at Segment Level](#segment-level-report) instead, to have this process done automatically.

Considere o seguinte cenário:

![faturamento-exemplos](assets/billing-examples.png)

### Caso 1: Segmentos com regras de qualificação E

Esse segmento contém 3 características de provedores de dados separados. Since segment qualification is based on an [!UICONTROL AND] condition, visitors have to realize the traits from all three feeds to qualify for the segment.

![](assets/billing-segment-and.png)

With an [!UICONTROL AND] condition, you must assign 100% of the impressions received during the month to all three data providers. In the [!UICONTROL Audience Marketplace > Payables] section, you credit each provider with 1,000,000 impressions.

This example applies to segments that use [!DNL Boolean] [!UICONTROL NOT] operators or for segments that contain algorithmic traits.

### Caso 2: Segmentos com regras de qualificação OU

Esse segmento contém 3 características de provedores de dados separados. Since segment qualification is based on an [!UICONTROL OR] condition, visitors have to realize at least one of the three traits to qualify for the segment.

We cannot tell which trait is responsible for an impression because qualification is based on an [!UICONTROL OR] condition. As a result, in the [!UICONTROL Audience Marketplace > Payables] section you credit each provider with a weighted allocation of the total impressions, based on trait population.

![faturamento de faturamento ou](assets/billing-segment-or.png)

>[!MORE_ LIKE_ THIS]
>
>* [Faturamento e alocação de impressão para feeds de dados de taxa simples](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)


## Billing and Impression Allocation for Flat Fee Data Feeds {#billing-flat-fee}

Um feed de dados de taxa fixa recebe um valor fixo a cada mês, independentemente do início da assinatura ou de quantas impressões você usa. As taxas não são raticadas para uso ou intervalos de mês parciais. Assim como com o faturamento de CPM, a Adobe gerará uma fatura e sua taxa de taxa fixa e fixa para os feeds de dados assinados.

Por exemplo, digamos que você decida ativar certas características em um feed no meio do mês. Você ainda será cobrado a taxa mensal completa, independentemente da data de início da assinatura ou de características específicas ativadas.