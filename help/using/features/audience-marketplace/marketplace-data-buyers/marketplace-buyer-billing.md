---
description: Os compradores de dados do Audience Marketplace aceitam relatar todas as impressões de anúncios veiculadas usando características contidas no feed de dados com base em um custo por mil impressões de anúncios (CPM). O uso de CPM ocorre no dia 5 º dia de cada mês do calendário e inclui dados do mês anterior. Assinantes de taxa fixa não precisam relatar o uso.
seo-description: Os compradores de dados do Audience Marketplace aceitam relatar todas as impressões de anúncios veiculadas usando características contidas no feed de dados com base em um custo por mil impressões de anúncios (CPM). O uso de CPM ocorre no dia 5 º dia de cada mês do calendário e inclui dados do mês anterior. Assinantes de taxa fixa não precisam relatar o uso.
seo-title: Cobrança para compradores de feed de dados
solution: Audience Manager
title: Cobrança para compradores de feed de dados
keywords: Relatório de nível de segmento, nível de segmento, nível de segmento
uuid: d 7236667-282 b -4160-9909-579721 af 4016
translation-type: tm+mt
source-git-commit: a8320894c0efcf46bd3236494e1aa7b1eded24d1

---


# Cobrança para compradores de feed de dados {#billing-for-data-feed-buyers}

Os compradores de dados do Audience Marketplace concordaram em relatar todas as impressões de anúncios veiculadas usando características contidas no feed de dados com base em um custo por mil impressões de anúncios ([!DNL CPM]). [!DNL CPM] o uso ocorre no dia 5 º dia de cada mês do calendário e inclui dados do mês anterior. Assinantes de taxa fixa não precisam relatar o uso.

<br> 

## Como relatar o uso de CPM {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] os compradores de dados aceitam relatar todas as impressões de anúncios veiculadas usando características contidas no feed de dados com base em custo por mil impressões de anúncios ([!DNL CPM]). [!DNL CPM] o uso ocorre no dia 5 dia de cada mês do calendário e inclui dados do mês anterior. Assinantes de taxa fixa não precisam relatar o uso.

[!UICONTROL Audience Marketplace] oferece duas formas de relatar [!DNL CPM] o uso:

* **Relatório de nível de segmento**: este é o método de relatório [!DNL CPM] de uso recomendado. Ao relatar o uso [!DNL CPM] no nível do segmento, a seção de relatório de nível de feed de dados é preenchida automaticamente com as quantidades de uso correspondentes, com base nos algoritmos descritos na [Atribuição de custo para Feeds de dados CPM](#cost-attribution).
* **Relatório de nível de feed de dados**: este método exige que você reporte individualmente o [!DNL CPM] uso para cada feed de dados, com base nos algoritmos descritos na [Atribuição de custo para Feeds de dados CPM](#cost-attribution). No entanto, esse método é mais tedioso e propensa a erro do que o relatório de nível de segmento.

<br> 

## Uso de CPM de relatório no nível do segmento {#segment-level-report}

A [!UICONTROL Segment Usage] guia permite relatar o uso no nível do segmento, ao exibir os segmentos agrupados pelos destinos aos quais estão mapeados.

Após o [!DNL CPM] uso do relatório no nível do segmento, [!UICONTROL Audience Marketplace] atribui automaticamente os dados correspondentes, com base na Atribuição [de custo para feeds de dados CPM](#cost-attribution).

Para reportar [!DNL CPM] o uso no nível do segmento:

1. Ir **[!UICONTROL Audience Marketplace > Payables]** para.
1. Selecione a **[!UICONTROL Segment Usage]** guia.
1. Preencha o uso para seus segmentos. Você pode usar a [!UICONTROL Search] caixa para filtrar os segmentos, caso só precise relatar o uso para alguns deles.
1. Clique em **[!UICONTROL Edit Segments Usage]**.
1. Insira o [!DNL CPM] valor de uso na [!UICONTROL Usage] coluna.
1. Clique **[!UICONTROL Save]** em quando terminar e revisar a caixa de diálogo de confirmação.

   ![confirm-segment-use](assets/confirm-segment-usage.png)

1. Clique em **[!UICONTROL Confirm]**.

Consulte também nossa demonstração em vídeo de como você pode relatar o uso no nível do segmento:

>[!VIDEO](https://video.tv.adobe.com/v/25522/?captions=por_br)

 

## Uso do CPM de relatório em nível de feed de dados {#feed-level-report}

O relatório de nível de feed de dados é mais tedioso e propensa a processar o processo, já que você deve calcular individualmente [!DNL CPM] o uso para cada feed de dados. Recomendamos [que você relate o uso de CPM em nível de segmento](#segment-level-report) em vez disso.

Para reportar [!DNL CPM] o uso no nível do segmento:

1. Ir **[!UICONTROL Audience Marketplace > Payables]** para.
2. Selecione a **[!UICONTROL Feed Usage]** guia.
3. Use [!UICONTROL Search] a caixa para filtrar os feeds de dados e identificar aquelas de que você precisa para informar o uso.
4. Clique em **[!UICONTROL Edit Feeds Usage]**.
5. Calcule o [!DNL CPM] uso para cada feed de dados com base na [Atribuição de custo para Feeds](#cost-attribution)de dados CPM e insira-o na [!UICONTROL Usage] coluna.
6. Clique **[!UICONTROL Save]** em quando terminar e revisar a caixa de diálogo de confirmação.

   ![confirm-feed-use](assets/confirm-feed-usage.png)

7. Clique em **[!UICONTROL Confirm]**.

<br> 

## Relatório em massa

Para reduzir erros e sobreposições ao [!DNL CPM] relatar o uso, você pode usar a opção de relatório em massa para baixar um [!DNL CSV] arquivo contendo os feeds de dados e os segmentos, preencher o uso e fazer o upload dele novamente [!DNL Audience Manager]. Você pode usar o relatório em massa para relatar o feed e o uso do segmento.

Para atualizar [!DNL CPM] o uso em massa:

1. Ir **[!UICONTROL Audience Marketplace > Payables]** para.
1. Selecione a **[!UICONTROL Feed Usage]** guia ou **[!UICONTROL Segment Usage]** a guia, dependendo do tipo de relatório a ser atualizado.
1. Clique **[!UICONTROL Edit Feeds Usage]** ou **[!UICONTROL Edit Segments Usage]**.
1. Clique **[!UICONTROL download the current usage]** em para certificar-se de usar um arquivo CSV válido.
1. Abra o arquivo no computador e preencha o relatório de uso.
1. Clique **[!UICONTROL Choose a CSV file]** em para carregar o relatório de uso atualizado.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] valida o arquivo assim que o carrega e solicita que ele detecte todos os erros no arquivo.

<br> 

### Erros de validação de relatório em massa

| Mensagem de erro | Descrição | Correção |
| ------------- | -------------| -----|
| Entrada inválida | [!DNL Audience Manager] detectou uma alteração no esquema [!DNL CSV] do arquivo, como colunas ausentes ou alterações nos títulos das colunas. | Evite alterar a estrutura da tabela. |
| Não encontrada | Para [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] não foi possível identificar a [!UICONTROL Segment ID] e [!UICONTROL Destination ID] combinação. Para [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] não pôde identificar o [!UICONTROL Data Provider Name], [!UICONTROL Feed Name]e [!UICONTROL Use Case] combinar. | Para [!UICONTROL Segment Level Reporting], verifique a validade da [!UICONTROL Segment ID] e [!UICONTROL Destination ID] combinação. Para [!UICONTROL Feed Level Reporting], verifique a validade do [!UICONTROL Data Provider Name], [!UICONTROL Feed Name]e [!UICONTROL Use Case] combinação. |
| Registros duplicados encontrados | [!DNL Audience Manager] registros duplicados detectados com valores de impressão diferentes. | Revise o relatório e certifique-se de não relatar valores de uso diferentes para o mesmo feed de dados ou segmento. |
| Valores não suportados | [!DNL Audience Manager] valores não numéricos na [!DNL Audience Manager] coluna. | Revise o relatório e certifique-se de inserir apenas valores numéricos na [!DNL Audience Manager] coluna. |
| Cabeçalhos para campos obrigatórios ausentes | [!DNL Audience Manager] cabeçalhos de tabela ausentes para campos obrigatórios. Para [!UICONTROL Segment Level Reporting], os campos obrigatórios são: [!UICONTROL Segment ID][!UICONTROL Destination ID]. Para [!UICONTROL Feed Level Reporting], os campos obrigatórios são: [!UICONTROL Data Provider Name][!UICONTROL Data Feed Name], [!UICONTROL Use Case] | Revise o relatório e verifique se os cabeçalhos da tabela não foram adulterados. |

>[!NOTE]
>A remoção de linhas do relatório [!DNL CSV] de uso não afeta o relatório de uso existente. [!DNL Audience Manager] processa apenas os campos incluídos no relatório.

<br> 

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
   <p> Relate o número total de impressões, sem usar decimais. O Audience Manager calcula automaticamente o CPM com base no número total de relatórios.</p><p>Se precisar relatar as impressões de 1,234,567, informe exatamente como isso. Não é necessário dividir o número total de impressões em 1,000 para calcular o CPM.</p><p>As características usadas para otimizar o conteúdo da Web ou do aplicativo (Otimização de conteúdo) usando ferramentas como o Adobe Target ou um destino do Analytics não contribuem para os totais de Uso para planos de CPM. Normalmente, os provedores de dados são compensados pela Otimização de conteúdo usando planos de taxa simples.</p><p>Consulte <a href="#cost-attribution">Atribuição de custo para feeds de dados CPM</a> para obter mais informações. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Pressionar o intervalo de relatório mensal</b> </p> </td> 
   <td colname="col2"> <p>O sistema de relatório fecha após o dia 5 de cada mês. Se você não reportar o uso de CPM em seguida, deverá adicionar essa quantia ao relatório para o mês seguinte. Por exemplo, digamos que você use impressões de 1000 em outubro, perca o prazo de relatório de outubro e use impressões 1000 em novembro. Nesse caso, você relata o total de outubro e novembro (2000) em dezembro entre the º e the º de dezembro.</p><p><b>Dica</b>: Você sempre deve tentar reportar o uso de CPM para o mês anterior entre os 1 º e 5 º dias do mês seguinte.</p><p>Você pode relatar o uso de CPM assim como o 5 º do mês do calendário, mas isso não é recomendado. Relatar o uso de CPM antes do dia 5 de cada mês dá ao Audience Manager tempo para verificar e processar os dados.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Atribuição de custo para feeds de dados CPM {#cost-attribution}

Em [!UICONTROL Audience Marketplace] você, você deve reportar valores de impressão a cada mês, para cada segmento. Recomendamos o [!DNL CPM] uso de relatórios no nível do segmento, para que a atribuição de custo seja feita automaticamente.

<!-- marketplace_cpm_billing.xml -->

### Resumo de faturamento {#billing-summary}

É necessário enviar [!DNL CPM] quantidades de impressão do feed de dados entre o primeiro e o 5 º dias de cada mês do calendário. Para fazer isso corretamente, recomendamos [que você relate o uso de CPM em nível de segmento](#segment-level-report).

>[!TIP]
>Ao relatar [!DNL CPM] o uso no nível do segmento, a seção de relatório de nível de feed de dados é preenchida automaticamente com as quantidades de uso correspondentes.

Se necessário, você deve compilar [!UICONTROL Report CPM Usage at Data Feed Level]individualmente todas as impressões entregues para cada feed no mês anterior do calendário e relatá-las de acordo com a alocação de faturamento descrita neste artigo.

Após o [!DNL CPM] número do relatório anterior, [!DNL Adobe] faça o seguinte:

* Crie uma fatura e faça uma cobrança com base na [!DNL CPM] taxa de cada feed de dados assinado.
* Pague os encargos de provedores de dados (vendedores) devidos com base no [!DNL CPM] uso informado.

>[!IMPORTANT]
>
>Como comprador, todos os totais de impressão relatados devem ser verdadeiros e precisos. Se você não relatar os totais de impressão até o dia 5 º de cada mês, deverá incluir totais para o mês não relatado no mês seguinte.

<br> 

## Atribuir impressões no nível do feed com base nas regras de qualificação de características {#assign-impressions}

O caso [!UICONTROL Activation] de uso permite usar características no feed de dados correspondente para criar segmentos no [Construtor de segmentos](../../../features/segments/segment-builder.md) e mapear esses segmentos para um destino. Os operadores [!UICONTROL AND]booleanos, [!UICONTROL OR]e [!UICONTROL NOT] permitem que você defina as condições para a qualificação de características e segmentos.

Ao [reportar o Uso de CPM de relatório em Nível de feed de dados](#feed-level-report), você deve alocar impressões proporcionalmente para cada feed de dados, de acordo com [!DNL Boolean] os operadores usados nas regras de qualificação de característica. A tabela a seguir lista como alocar apropriadamente impressões por regra booleana ou tipo de característica.

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
   <td colname="col2"> <p>Aplique 100% dos totais de impressão entregues a todas as características do provedor em um segmento baseado em regras que use uma condição <span class="wintitle"> E</span> booleana. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> OU</span> </p> </td> 
   <td colname="col2"> <p>Aplique a alocação ponderada dos totais de impressão entregues a todas as características do provedor em um segmento baseado em regras que use uma condição OU booleana. A alocação ponderada é calculada usando a seguinte fórmula:</p><p><code>(População característica/População de segmentos) * Número de impressões * Custo do CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NÃO</span> </p> </td> 
   <td colname="col2"> <p>Aplique 100% dos totais de impressão entregues a todas as características do provedor em um segmento baseado em regras que use uma condição <span class="wintitle"> Não</span> booleana. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segmentos algorítmicos </p> </td> 
   <td colname="col2"> <p>Aplique 100% dos totais de impressão entregues a todos os feeds de provedor em um segmento que contenha características algorítmicas. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Exemplos de faturamento {#billing-examples}

Os exemplos abaixo destinam-se a ilustrar como [!DNL CPM] a alocação de uso é feita no nível do feed de dados.

>[!IMPORTANT]
>Recomendamos que você [relate o uso de CPM em nível de segmento](#segment-level-report) para fazer com que esse processo seja feito automaticamente.

Considere o seguinte cenário:

![faturamento-exemplos](assets/billing-examples.png)

<br> 

### Caso 1: Segmentos com regras de qualificação E

Esse segmento contém 3 características de provedores de dados separados. Como a qualificação de segmentos é baseada em [!UICONTROL AND] uma condição, os visitantes precisam perceber as características dos três feeds para se qualificarem para o segmento.

![](assets/billing-segment-and.png)

Com uma [!UICONTROL AND] condição, você deve atribuir 100% das impressões recebidas durante o mês para os três provedores de dados. Na [!UICONTROL Audience Marketplace > Payables] seção, você dá crédito a cada provedor com 1,000,000 impressões.

Este exemplo aplica-se a segmentos que usam [!DNL Boolean][!UICONTROL NOT] operadores ou para segmentos que contenham características algorítmicas.

<br> 

### Caso 2: Segmentos com regras de qualificação OU

Esse segmento contém 3 características de provedores de dados separados. Como a qualificação de segmentos é baseada em [!UICONTROL OR] uma condição, os visitantes precisam perceber pelo menos um dos três traços para se qualificarem para o segmento.

Não é possível saber qual característica é responsável por uma impressão porque a qualificação é baseada em [!UICONTROL OR] uma condição. Como resultado, na [!UICONTROL Audience Marketplace > Payables] seção você dá crédito a cada provedor com uma alocação ponderada do total de impressões, com base na população de características.

![faturamento de faturamento ou](assets/billing-segment-or.png)

<br> 

### Caso 3: Segmentos com casos de uso de modelagem e ativação

Este exemplo descreve a atribuição com base em dois casos de uso do Feed de dados - Modelagem e Ativação. No exemplo, estamos observando dois provedores de dados com as seguintes informações:

![feed de dados](assets/feed-use-cases.png)

Na tabela mais abaixo, o Segmento X contém duas características, T 1 e T 2, com a regra de segmento T 1 OU T 2, em que:

* T 1 é uma característica do Feed de dados A;
* T 2 é uma característica algorítmica com características de terceiros do Feed de dados A e do Feed de dados B.

O segmento é mapeado para um destino e as impressões 1,000,000 são inseridas para esse segmento em um mês, usando Relatórios [de nível de segmento](#segment-level-report).

Destas impressões 1,000,000:

* T 1 torna 40% da população do segmento, o que equivale a 400,000 impressões para o Feed A.
* T 2 torna 60% da população do segmento, o que equivale a 600,000 impressões para Feed A e Feed B.

Em um nível de feed de dados, a forma como as impressões são alocadas é:

* O Feed de dados A recebe impressões 600,000 de características T 2 (modeladas em características do Feed de dados A e Feed de dados B, portanto, ambas recebem impressões) e impress00,000 impressas de características T 1 (que é uma característica do Feed de dados A), totalizando 1,000,00impressimpressões.
* O Feed de dados B recebe impressões 600,000 de características T 2 (consulte explicação acima) e 0 impressões de características T 1.

O detalhamento geral por feed de dados e casos de uso é o seguinte:

![divisão do feed](assets/feed-breakdown-alt.png)

<br> 

## Faturamento e alocação de impressão para feeds de dados de taxa simples {#billing-flat-fee}

Um feed de dados de taxa fixa recebe um valor fixo a cada mês, independentemente do início da assinatura ou de quantas impressões você usa. As taxas não são raticadas para uso ou intervalos de mês parciais. Assim como com o faturamento de CPM, a Adobe gerará uma fatura e sua taxa de taxa fixa e fixa para os feeds de dados assinados.

Por exemplo, digamos que você decida ativar certas características em um feed no meio do mês. Você ainda será cobrado a taxa mensal completa, independentemente da data de início da assinatura ou de características específicas ativadas.