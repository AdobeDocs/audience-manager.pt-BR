---
description: Os compradores de dados da Audience Marketplace concordam em relatar todas as impressões de anúncios veiculadas com as características contidas no feed de dados orçadas com base no custo por mil impressões de anúncios (CPM). O uso do CPM ocorre no quinto dia de cada mês e inclui dados do mês anterior. Os assinantes de taxa única não precisam relatar o uso.
seo-description: Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions (CPM) basis. CPM usage is due on the 5th day of each calendar month and includes data for previous month. Flat fee subscribers do not need to report usage.
seo-title: Billing for Data Feed Buyers
solution: Audience Manager
title: Faturamento para compradores de feed de dados
keywords: Relatório em nível de segmento, nível de segmento, nível de segmento
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2002'
ht-degree: 1%

---

# Faturamento para compradores de feed de dados {#billing-for-data-feed-buyers}

Os compradores de dados da Audience Marketplace concordam em relatar todas as impressões de anúncios veiculadas com as características contidas no feed de dados cujo preço é um custo por mil impressões de anúncios ([!DNL CPM]). [!DNL CPM] o uso do é devido no quinto dia de cada mês e inclui dados do mês anterior. Os assinantes de taxa única não precisam relatar o uso.

<br> 

## Como relatar o uso do CPM {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] os compradores de dados concordam em relatar todas as impressões de anúncios veiculadas com as características contidas no feed de dados cujo preço é um custo por mil impressões de anúncios ([!DNL CPM]). [!DNL CPM] o uso do é devido aos 5 dias de cada mês e inclui dados do mês anterior. Os assinantes de taxa única não precisam relatar o uso.

[!UICONTROL Audience Marketplace] O oferece duas maneiras de gerar relatórios [!DNL CPM] uso:

* **Relatórios em nível de segmento**: este é o recomendado [!DNL CPM] método de relatório de uso. Ao relatar [!DNL CPM] uso no nível do segmento, a seção de relatórios no nível do feed de dados é preenchida automaticamente com os valores de uso correspondentes, com base nos algoritmos descritos em [Atribuição de custo para feeds de dados de CPM](#cost-attribution).
* **Relatórios de nível de feed de dados**: este método requer que você relate individualmente os [!DNL CPM] para cada feed de dados, com base nos algoritmos descritos em [Atribuição de custo para feeds de dados de CPM](#cost-attribution). No entanto, esse método é mais tedioso e propenso a erros do que o relatório em nível de segmento.

<br> 

## Relatar uso de CPM no nível do segmento {#segment-level-report}

A variável [!UICONTROL Segment Usage] permite relatar o uso em nível de segmento, ao mesmo tempo em que exibe os segmentos agrupados pelos destinos aos quais são mapeados.

Após o relatório [!DNL CPM] utilização a nível do segmento, [!UICONTROL Audience Marketplace] atribui automaticamente os feeds de dados correspondentes ao uso correto, com base na [Atribuição de custo para feeds de dados de CPM](#cost-attribution).

Para gerar relatório [!DNL CPM] uso no nível do segmento:

1. Ir para **[!UICONTROL Audience Marketplace > Payables]**.
1. Selecione o **[!UICONTROL Segment Usage]** guia.
1. Preencha o uso para seus segmentos. Você pode usar o [!UICONTROL Search] para filtrar os segmentos se precisar relatar o uso de apenas alguns deles.
1. Clique em **[!UICONTROL Edit Segments Usage]**.
1. Insira o [!DNL CPM] quantidade de uso no [!UICONTROL Usage] coluna.
1. Clique em **[!UICONTROL Save]** quando terminar, e revise a caixa de diálogo de confirmação.

   ![confirm-segment-usage](assets/confirm-segment-usage.png)

1. Clique em **[!UICONTROL Confirm]**.

Veja também nossa demonstração em vídeo de como é possível relatar o uso em nível de segmento:

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## Relatar uso de CPM no nível do feed de dados {#feed-level-report}

O relatório no nível do feed de dados é um processo mais tedioso e sujeito a erros, pois você deve calcular individualmente [!DNL CPM] para cada feed de dados. Recomendamos que você [Relatar uso de CPM no nível do segmento](#segment-level-report) em vez disso.

Para gerar relatório [!DNL CPM] uso no nível do segmento:

1. Ir para **[!UICONTROL Audience Marketplace > Payables]**.
2. Selecione o **[!UICONTROL Feed Usage]** guia.
3. Use o [!UICONTROL Search] para filtrar os feeds de dados e identificar aqueles para os quais você precisa relatar o uso.
4. Clique em **[!UICONTROL Edit Feeds Usage]**.
5. Calcule o [!DNL CPM] para cada feed de dados com base na variável [Atribuição de custo para feeds de dados de CPM](#cost-attribution)e insira-o no campo [!UICONTROL Usage] coluna.
6. Clique em **[!UICONTROL Save]** quando terminar, e revise a caixa de diálogo de confirmação.

   ![confirm-feed-usage](assets/confirm-feed-usage.png)

7. Clique em **[!UICONTROL Confirm]**.

<br> 

## Relatório em massa

Para reduzir erros e despesas gerais durante a emissão de relatórios [!DNL CPM] uso, você pode usar a opção de relatório em massa para baixar um [!DNL CSV] arquivo contendo os feeds de dados e segmentos, preencha o de uso e faça upload dele de volta para [!DNL Audience Manager]. Você pode usar o relatório em massa para relatar o uso do feed e do segmento.

Para atualizar [!DNL CPM] uso em massa:

1. Ir para **[!UICONTROL Audience Marketplace > Payables]**.
1. Selecione o **[!UICONTROL Feed Usage]** ou **[!UICONTROL Segment Usage]** dependendo do tipo de relatório que deseja atualizar.
1. Clique em **[!UICONTROL Edit Feeds Usage]** ou **[!UICONTROL Edit Segments Usage]**.
1. Clique em **[!UICONTROL download the current usage]** para garantir que você use um arquivo CSV válido.
1. Abra o arquivo no computador e preencha o relatório de uso.
1. Clique em **[!UICONTROL Choose a CSV file]** para fazer upload do relatório de uso atualizado.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] O valida o arquivo assim que você o carrega e solicita se detectar erros no arquivo.

<br> 

### Erros de validação de relatório em massa

| Mensagem de erro | Descrição | Correção |
| ------------- | -------------| -----|
| Entrada inválida | [!DNL Audience Manager] detectou uma alteração no [!DNL CSV] esquema de arquivo, como colunas ausentes ou alterações nos títulos das colunas. | Evite alterar a estrutura da tabela. |
| Não encontrada | Para [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] não foi possível identificar o [!UICONTROL Segment ID] e [!UICONTROL Destination ID] combinação. Para [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] não foi possível identificar o [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], e [!UICONTROL Use Case] combinação. | Para [!UICONTROL Segment Level Reporting], verifique a validade do [!UICONTROL Segment ID] e [!UICONTROL Destination ID] combinação. Para [!UICONTROL Feed Level Reporting], verifique a validade do [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], e [!UICONTROL Use Case] combinação. |
| Registros Duplicados Encontrados | [!DNL Audience Manager] registros duplicados detectados com valores de impressão diferentes. | Revise o relatório e certifique-se de não relatar valores de uso diferentes para o mesmo feed de dados ou segmento. |
| Valores não suportados | [!DNL Audience Manager] valores não numéricos detectados no [!DNL Audience Manager] coluna. | Revise o relatório e certifique-se de inserir apenas valores numéricos no [!DNL Audience Manager] coluna. |
| Cabeçalhos para campos obrigatórios ausentes | [!DNL Audience Manager] foram detectados cabeçalhos de tabela ausentes para campos obrigatórios. Para [!UICONTROL Segment Level Reporting], os campos obrigatórios são: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. Para [!UICONTROL Feed Level Reporting], os campos obrigatórios são: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name],  [!UICONTROL Use Case] | Revise o relatório e verifique se os cabeçalhos da tabela não foram adulterados. |

>[!NOTE]
>Remoção de linhas do [!DNL CSV] o relatório de uso não tem nenhum efeito sobre o relatório de uso existente. [!DNL Audience Manager] processa apenas os campos incluídos no relatório.

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
   <p> Relate o número total de impressões, sem usar decimais. O Audience Manager calcula automaticamente o CPM com base no número total relatado.</p><p>Se precisar relatar 1.234.567 impressões, relate exatamente assim. Não é necessário dividir o número total de impressões por 1.000 para calcular o CPM.</p><p>As características usadas para otimizar o conteúdo da Web ou do aplicativo (Otimização de conteúdo) usando ferramentas como o Adobe Target ou um destino do Analytics não contribuem para os totais de Uso para planos CPM. Os provedores de dados normalmente são compensados pela Otimização de conteúdo usando planos de taxa fixos.</p><p>Consulte <a href="#cost-attribution">Atribuição de custo para feeds de dados de CPM</a> para obter mais informações. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Manter o intervalo de relatórios mensais</b> </p> </td> 
   <td colname="col2"> <p>O sistema de relatórios fecha depois do dia 5 de cada mês. Se você não relatar o uso do CPM até lá, será necessário adicionar esse valor ao relatório para o mês seguinte. Por exemplo, digamos que você use 1000 impressões em outubro, perca o prazo de relatório de outubro e use 1000 impressões em novembro. Nesse caso, você informa o total de outubro e novembro (2000) em dezembro, entre os dias 1º e 5º.</p><p><b>Dica</b>: Você sempre deve tentar relatar o uso do CPM para o mês anterior entre o primeiro e o quinto dias do mês seguinte.</p><p>Você pode relatar o uso do CPM até o quinto dia do novo mês, mas isso não é recomendado. Relatar o uso do CPM antes do dia 5 de cada mês dá ao Audience Manager tempo para verificar e processar os dados.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Atribuição de custo para feeds de dados de CPM {#cost-attribution}

Entrada [!UICONTROL Audience Marketplace] você deve relatar automaticamente os valores de impressão a cada mês para cada um dos segmentos. Recomendamos a criação de relatórios [!DNL CPM] uso no nível do segmento, para que a atribuição de custo seja feita automaticamente.

<!-- marketplace_cpm_billing.xml -->

### Resumo da Cobrança {#billing-summary}

Você deve enviar [!DNL CPM] quantidades de impressão do feed de dados entre o primeiro e o quinto dias de cada mês. Para fazer isso corretamente, recomendamos [Relatar uso de CPM no nível do segmento](#segment-level-report).

>[!TIP]
>Ao relatar [!DNL CPM] uso no nível do segmento, a seção de relatórios no nível do feed de dados é preenchida automaticamente com as quantidades de uso correspondentes.

Se você precisar [!UICONTROL Report CPM Usage at Data Feed Level], você deve compilar individualmente todas as impressões entregues para cada feed no mês anterior e relatá-las de acordo com a alocação de faturamento descrita neste artigo.

Depois do relatório [!DNL CPM] número do mês anterior, [!DNL Adobe] O fará o seguinte:

* Criar uma NFF e faturá-lo com base na [!DNL CPM] para cada feed de dados assinado.
* Pague as taxas dos provedores de dados (vendedores) com base nas informações [!DNL CPM] usar.

>[!IMPORTANT]
>
>Como comprador, todos os totais de impressão relatados devem ser verdadeiros e precisos. Se você não relatar os totais de impressão até o quinto dia de cada mês, será necessário incluir os totais do mês não reportado no mês seguinte.

<br> 

## Atribuir impressões no nível do feed com base nas regras de qualificação de característica {#assign-impressions}

A variável [!UICONTROL Activation] caso de uso permite usar características no feed de dados correspondente para criar segmentos no [Construtor de segmentos](../../../features/segments/segment-builder.md) e mapeie esses segmentos para um destino. Os operadores booleanos [!UICONTROL AND], [!UICONTROL OR], e [!UICONTROL NOT] permitem definir as condições para qualificação de características e segmentos.

Quando você [Relatar uso de CPM no nível do feed de dados](#feed-level-report), você deve alocar impressões proporcionalmente para cada feed de dados, de acordo com [!DNL Boolean] operadores usados nas regras de qualificação de característica. A tabela a seguir lista como alocar impressões corretamente por regra booleana ou tipo de característica.

>[!TIP]
>[Relatar uso de CPM no nível do segmento](#segment-level-report) para que o relatório de nível do feed de dados seja feito automaticamente pelo Audience Manager.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Lógica ou tipo de qualificação de regra </th> 
   <th colname="col2" class="entry"> Distribuição de Cobrança </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> E</span> </p> </td> 
   <td colname="col2"> <p>Aplicar 100% dos totais de impressão entregues a todas as características do provedor em um segmento baseado em regras que usa um valor booleano <span class="wintitle"> E</span> condição. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> OU</span> </p> </td> 
   <td colname="col2"> <p>Aplique a alocação ponderada dos totais de impressão entregues a todas as características do provedor em um segmento baseado em regras que usa uma condição OR booleana. A alocação ponderada é calculada usando a seguinte fórmula:</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NÃO</span> </p> </td> 
   <td colname="col2"> <p>Aplicar 100% dos totais de impressão entregues a todas as características do provedor em um segmento baseado em regras que usa um valor booleano <span class="wintitle"> NOT</span> condição. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segmentos algorítmicos </p> </td> 
   <td colname="col2"> <p>Aplique 100% dos totais de impressão entregues a todos os feeds de provedor em um segmento que contenha características algorítmicas. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Exemplos de cobrança {#billing-examples}

Os exemplos abaixo ilustram como [!DNL CPM] a alocação de uso é feita no nível do feed de dados.

>[!IMPORTANT]
>Recomendamos que você [Relatar uso de CPM no nível do segmento](#segment-level-report) em vez disso, para que esse processo seja executado automaticamente.

Vamos considerar o seguinte cenário:

![exemplos de faturamento](assets/billing-examples.png)

<br> 

### Caso 1: Segmentos com regras de qualificação AND

Esse segmento contém 3 características de provedores de dados separados. Como a qualificação de segmento é baseada em um [!UICONTROL AND] condição, os visitantes devem perceber as características de todos os três feeds para se qualificarem para o segmento.

![](assets/billing-segment-and.png)

Com um [!UICONTROL AND] condição, você deve atribuir 100% das impressões recebidas durante o mês a todos os três provedores de dados. No [!UICONTROL Audience Marketplace > Payables] você credita a cada provedor com 1.000.000 impressões.

Este exemplo se aplica a segmentos que usam [!DNL Boolean] [!UICONTROL NOT] operadores ou para segmentos que contêm características algorítmicas.

<br> 

### Caso 2: Segmentos com regras de qualificação OR

Esse segmento contém 3 características de provedores de dados separados. Como a qualificação de segmento é baseada em um [!UICONTROL OR] condição, os visitantes devem perceber pelo menos uma das três características para se qualificarem para o segmento.

Não é possível saber qual característica é responsável por uma impressão porque a qualificação se baseia em um [!UICONTROL OR] condição. Como resultado, no [!UICONTROL Audience Marketplace > Payables] você credita a cada provedor uma alocação ponderada do total de impressões, com base na população de características.

![segmento de faturamento-ou](assets/billing-segment-or.png)

<br> 

### Caso 3: Segmentos com casos de uso de modelagem e ativação

Este exemplo descreve a atribuição com base em dois casos de uso do Feed de dados: Modelagem e Ativação. No exemplo, estamos observando dois provedores de dados, com as seguintes informações:

![feed de dados](assets/feed-use-cases.png)

Na tabela abaixo, o Segmento X contém duas características, T1 e T2, com a regra de segmento T1 OU T2, em que:

* T1 é uma característica do Feed de dados A;
* T2 é uma característica algorítmica modelada após características de terceiros do Feed de dados A e do Feed de dados B.

O segmento é mapeado para um destino e 1.000.000 impressões são inseridas para este segmento em um mês, usando [Relatórios de nível de segmento](#segment-level-report).

Dessas 1.000.000 impressões:

* O T1 representa 40% da população do segmento, o que significa 400.000 impressões para o Feed A.
* O T2 representa 60% da população do segmento, o que significa 600.000 impressões para o Feed A e o Feed B.

Em um nível de feed de dados, a maneira como as impressões são alocadas é:

* O Feed de dados A recebe 600.000 impressões da característica T2 (que é modelada nas características do Feed de dados A e do Feed de dados B, para que ambos recebam as impressões) e 400.000 impressões da característica T1 (que é uma característica do Feed de dados A), totalizando 1.000.000 impressões.
* O Feed de dados B recebe 600.000 impressões da característica T2 (consulte a explicação acima) e 0 impressões da característica T1.

O detalhamento rápido por feed de dados e caso de uso é o seguinte:

![feed-detalhamento](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>Para o caso de uso de modelagem, você só deve relatar o uso do CPM após a ativação. Se você executar apenas um modelo, mas não ativá-lo, nenhum relatório de uso será necessário.

<br> 

## Alocação de impressão e cobrança para feeds de dados de taxa fixa {#billing-flat-fee}

Um feed de dados de taxa fixa fatura um valor fixo a cada mês, independentemente de quando a assinatura começa ou quantas impressões você usa. As taxas não são rateadas para uso ou intervalos parciais do mês. Assim como no faturamento do CPM, o Adobe gerará uma fatura e o cobrará pela taxa de taxa uniforme mensal dos feeds de dados que você assina.

Por exemplo, digamos que você tenha decidido ativar determinadas características em um feed no meio do mês. Você ainda será cobrado com a taxa mensal total, independentemente de quando iniciou a assinatura ou ativou características específicas.
