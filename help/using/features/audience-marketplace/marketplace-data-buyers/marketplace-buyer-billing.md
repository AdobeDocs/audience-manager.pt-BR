---
description: Os compradores de dados do Audience Marketplace concordam em relatar todas as impressões de anúncios servidas usando características contidas no feed de dados com um preço por mil impressões de anúncios (CPM). O uso do CPM ocorre no quinto dia de cada mês do calendário e inclui dados do mês anterior. Os assinantes de taxa fixa não precisam relatar o uso.
seo-description: Os compradores de dados do Audience Marketplace concordam em relatar todas as impressões de anúncios servidas usando características contidas no feed de dados com um preço por mil impressões de anúncios (CPM). O uso do CPM ocorre no quinto dia de cada mês do calendário e inclui dados do mês anterior. Os assinantes de taxa fixa não precisam relatar o uso.
seo-title: Faturamento para compradores de feed de dados
solution: Audience Manager
title: Faturamento para compradores de feed de dados
keywords: Segment-level Reporting, segment-level, segment level
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '2027'
ht-degree: 1%

---


# Faturamento para compradores de feed de dados {#billing-for-data-feed-buyers}

Os compradores de dados do Audience Marketplace concordam em relatar todas as impressões de anúncios servidas usando características contidas no feed de dados com um preço por mil impressões de anúncios ([!DNL CPM]). [!DNL CPM] o uso é devido no quinto dia de cada mês e inclui dados do mês anterior. Os assinantes de taxa fixa não precisam relatar o uso.

<br> 

## Como informar o uso do CPM {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] os compradores de dados concordam em relatar todas as impressões de anúncios servidas usando características contidas no feed de dados com um preço por mil impressões de anúncios ([!DNL CPM]). [!DNL CPM] o uso é devido no dia 5 de cada mês e inclui dados do mês anterior. Os assinantes de taxa fixa não precisam relatar o uso.

[!UICONTROL Audience Marketplace] oferta duas maneiras de  [!DNL CPM] usar relatórios:

* **Relatórios** no nível do segmento: este é o método de relatórios de  [!DNL CPM] uso recomendado. Quando você relata o uso [!DNL CPM] no nível do segmento, a seção de relatórios no nível do feed de dados é automaticamente preenchida com as quantidades de uso correspondentes, com base nos algoritmos descritos em [Atribuição de custo para feeds de dados do CPM](#cost-attribution).
* **Relatórios** no nível do feed de dados: esse método exige que você reporte individualmente o  [!DNL CPM] uso de cada feed de dados, com base nos algoritmos descritos em Atribuição  [de custo para feeds](#cost-attribution) de dados CPM. No entanto, esse método é mais tedioso e propenso a erros do que o relatórios no nível do segmento.

<br> 

## Relatar o uso do CPM no nível do segmento {#segment-level-report}

A guia [!UICONTROL Segment Usage] permite relatar o uso no nível do segmento, enquanto exibe os segmentos agrupados pelos destinos para os quais estão mapeados.

Depois do uso [!DNL CPM] do relatórios no nível do segmento, [!UICONTROL Audience Marketplace] atribui automaticamente o uso correto dos feeds de dados correspondentes, com base na [Atribuição de custo para Feeds de dados do CPM](#cost-attribution).

Para relatar a utilização [!DNL CPM] no nível do segmento:

1. Vá para **[!UICONTROL Audience Marketplace > Payables]**.
1. Selecione a guia **[!UICONTROL Segment Usage]**.
1. Preencha o uso para seus segmentos. Você pode usar a caixa [!UICONTROL Search] para filtrar os segmentos se precisar apenas do uso de relatórios para alguns deles.
1. Clique em **[!UICONTROL Edit Segments Usage]**.
1. Insira o valor de uso [!DNL CPM] na coluna [!UICONTROL Usage].
1. Clique em **[!UICONTROL Save]** quando terminar e reveja a caixa de diálogo de confirmação.

   ![uso do segmento de confirmação](assets/confirm-segment-usage.png)

1. Clique em **[!UICONTROL Confirm]**.

Veja também nossa demonstração em vídeo de como você pode relatar o uso no nível do segmento:

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## Relatar o uso do CPM no nível do feed de dados {#feed-level-report}

O relatórios no nível do feed de dados é um processo mais tedioso e propenso a erros, uma vez que você deve calcular [!DNL CPM] individualmente o uso para cada feed de dados. Em vez disso, recomendamos que você [Relate o uso do CPM no nível do segmento](#segment-level-report).

Para relatar a utilização [!DNL CPM] no nível do segmento:

1. Vá para **[!UICONTROL Audience Marketplace > Payables]**.
2. Selecione a guia **[!UICONTROL Feed Usage]**.
3. Use a caixa [!UICONTROL Search] para filtrar os feeds de dados e identificar aqueles para os quais você precisa relatar o uso.
4. Clique em **[!UICONTROL Edit Feeds Usage]**.
5. Calcule o uso de [!DNL CPM] para cada feed de dados com base na [Atribuição de custo para feeds de dados CPM](#cost-attribution) e insira-o na coluna [!UICONTROL Usage].
6. Clique em **[!UICONTROL Save]** quando terminar e reveja a caixa de diálogo de confirmação.

   ![uso do feed de confirmação](assets/confirm-feed-usage.png)

7. Clique em **[!UICONTROL Confirm]**.

<br> 

## Relatórios em massa

Para reduzir erros e sobrecarga enquanto o relatórios [!DNL CPM] é possível usar a opção relatórios em massa para baixar um arquivo [!DNL CSV] contendo os feeds de dados e segmentos, preencher o uso e fazer upload dele de volta para [!DNL Audience Manager]. Você pode usar o relatórios em massa para relatar a utilização de feed e segmento.

Para atualizar o uso de [!DNL CPM] em massa:

1. Vá para **[!UICONTROL Audience Marketplace > Payables]**.
1. Selecione a guia **[!UICONTROL Feed Usage]** ou **[!UICONTROL Segment Usage]**, dependendo do tipo de relatórios que deseja atualizar.
1. Clique em **[!UICONTROL Edit Feeds Usage]** ou **[!UICONTROL Edit Segments Usage]**.
1. Clique em **[!UICONTROL download the current usage]** para certificar-se de usar um arquivo CSV válido.
1. Abra o arquivo em seu computador e preencha o relatório de uso.
1. Clique em **[!UICONTROL Choose a CSV file]** para fazer upload do relatório de uso atualizado.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] valida o arquivo assim que ele é carregado e solicita que você detecte quaisquer erros no arquivo.

<br> 

### Erros de validação de Relatórios em massa

| Mensagem de erro | Descrição | Correção |
| ------------- | -------------| -----|
| Entrada inválida | [!DNL Audience Manager] detectou uma alteração no schema de  [!DNL CSV] arquivo, como colunas ausentes ou alterações nos títulos das colunas. | Evite alterar a estrutura da tabela. |
| Não encontrada | Para [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] não pôde identificar a combinação [!UICONTROL Segment ID] e [!UICONTROL Destination ID]. Para [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] não pôde identificar a combinação [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] e [!UICONTROL Use Case]. | Para [!UICONTROL Segment Level Reporting], verifique a validade da combinação [!UICONTROL Segment ID] e [!UICONTROL Destination ID]. Para [!UICONTROL Feed Level Reporting], verifique a validade da combinação [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] e [!UICONTROL Use Case]. |
| Registros de duplicado encontrados | [!DNL Audience Manager] foram detectados registros de duplicados com valores de impressão diferentes. | Revise o relatório e certifique-se de não relatar valores de uso diferentes para o mesmo feed de dados ou segmento. |
| Valores não suportados | [!DNL Audience Manager] valores não numéricos detectados na  [!DNL Audience Manager] coluna. | Revise o relatório e certifique-se de inserir apenas valores numéricos na coluna [!DNL Audience Manager]. |
| Cabeçalhos para campos obrigatórios ausentes | [!DNL Audience Manager] foram detectados cabeçalhos de tabela ausentes para campos obrigatórios. Para [!UICONTROL Segment Level Reporting], os campos obrigatórios são: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. Para [!UICONTROL Feed Level Reporting], os campos obrigatórios são: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name], [!UICONTROL Use Case] | Revise o relatório e verifique se os cabeçalhos da tabela não foram adulterados. |

>[!NOTE]
>A remoção de linhas do relatório de uso [!DNL CSV] não afeta o relatório de uso existente. [!DNL Audience Manager] processa somente os campos incluídos no relatório.

<br> 

## [!DNL CPM] Práticas recomendadas para o relatórios

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recomendações </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Sempre reportar o número total de impressões</b> </p> </td> 
   <td colname="col2"> <p>Para totais de impressões do CPM: </p>
   <p> Relate o número total de impressões, sem usar decimais. O Audience Manager calcula automaticamente o CPM com base no número total de relatórios.</p><p>Se precisar reportar 1.234.567 impressões, reportar exatamente assim. Não é necessário dividir o número total de impressões por 1.000 para calcular o CPM.</p><p>As características usadas para otimizar o conteúdo da Web ou do aplicativo (Otimização de conteúdo) usando ferramentas como o Adobe Target ou um destino do Analytics não contribuem para os totais de uso dos planos do CPM. Geralmente, os provedores de dados são compensados pela Otimização de conteúdo usando planos de taxas fixas.</p><p>Consulte <a href="#cost-attribution">Atribuição de custo para feeds de dados CPM</a> para obter mais informações. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Manter o intervalo de relatórios mensal</b> </p> </td> 
   <td colname="col2"> <p>O sistema de relatórios fecha após o dia 5 de cada mês. Se você não reportar o uso do CPM até essa data, deverá adicionar esse valor ao relatório do mês seguinte. Por exemplo, digamos que você use 1000 impressões em outubro, perca o prazo limite do relatórios de outubro e use 1000 impressões em novembro. Nesse caso, você relata o total de outubro e novembro (2000) em dezembro, entre o 1º e o 5º.</p><p><b>Dica</b>: Você deve sempre tentar relatar o uso do CPM do mês anterior entre o primeiro e o quinto dias do mês seguinte.</p><p>Você pode relatar o uso do CPM até o dia 5 do novo mês, mas isso não é recomendado. O uso do CPM do relatórios antes do dia 5 de cada mês dá ao Audience Manager tempo para verificar e processar os dados.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Atribuição de custo para feeds de dados CPM {#cost-attribution}

Em [!UICONTROL Audience Marketplace] você deve relatar valores de impressão a cada mês, para cada um dos seus segmentos. Recomendamos o uso [!DNL CPM] do relatórios no nível do segmento, para que a atribuição de custo seja feita automaticamente.

<!-- marketplace_cpm_billing.xml -->

### Resumo da cobrança {#billing-summary}

Você deve enviar [!DNL CPM] valores de impressão de feed de dados entre o primeiro e o quinto dias de cada mês do calendário. Para fazer isso corretamente, recomendamos que você [Relatar o uso do CPM no nível do segmento](#segment-level-report).

>[!TIP]
>Quando você relata a utilização [!DNL CPM] no nível do segmento, a seção de relatórios no nível do feed de dados é automaticamente preenchida com as quantidades de uso correspondentes.

Caso precise [!UICONTROL Report CPM Usage at Data Feed Level], você deve compilar individualmente todas as impressões entregues para cada feed no mês anterior e relatá-las de acordo com a alocação de faturamento descrita neste artigo.

Depois que você relatar o número [!DNL CPM] do mês anterior, [!DNL Adobe] fará o seguinte:

* Crie uma fatura e uma lista com base na taxa [!DNL CPM] para cada feed de dados inscrito.
* Pague taxas devidas aos provedores de dados (vendedores) com base no seu uso [!DNL CPM] relatado.

>[!IMPORTANT]
>
>Como comprador, todos os totais de impressões reportados devem ser verdadeiros e exatos. Se você não reportar os totais de impressão até o quinto dia de cada mês, deverá incluir os totais do mês não relatado no mês seguinte.

<br> 

## Atribuir impressões no nível do feed com base nas regras de qualificação de características {#assign-impressions}

O caso de uso [!UICONTROL Activation] permite que você use características no feed de dados correspondente para criar segmentos no [Construtor de segmentos](../../../features/segments/segment-builder.md) e mapear esses segmentos para um destino. Os operadores Booleanos [!UICONTROL AND], [!UICONTROL OR] e [!UICONTROL NOT] permitem que você defina as condições para qualificação de características e segmentos.

Ao [Relatar o uso do CPM no nível do feed de dados](#feed-level-report), você deve alocar impressões proporcionalmente para cada feed de dados, de acordo com os operadores [!DNL Boolean] usados nas regras de qualificação de características. A tabela a seguir lista como alocar as impressões corretamente por regra Booleana ou tipo de característica.

>[!TIP]
>[Reportar o uso do CPM no nível do segmento](#segment-level-report) para que o relatórios no nível do feed de dados seja feito automaticamente por Audience Manager.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Lógica ou tipo de qualificação de regra </th> 
   <th colname="col2" class="entry"> Distribuição de Faturamento </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> E</span> </p> </td> 
   <td colname="col2"> <p>Aplique 100% dos totais de impressão fornecidos a todas as características do provedor em um segmento baseado em regras que usa uma condição Boolean <span class="wintitle"> AND</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> OU</span> </p> </td> 
   <td colname="col2"> <p>Aplique a alocação ponderada dos totais de impressão fornecidos a todas as características do provedor em um segmento baseado em regras que usa uma condição OR booleana. A alocação ponderada é calculada usando a seguinte fórmula:</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NÃO</span> </p> </td> 
   <td colname="col2"> <p>Aplique 100% dos totais de impressão fornecidos a todas as características do provedor em um segmento baseado em regras que usa uma condição Booliana <span class="wintitle"> NOT</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segmentos algorítmicos </p> </td> 
   <td colname="col2"> <p>Aplique 100% dos totais de impressão fornecidos a todos os feeds do provedor em um segmento que contém características algorítmicas. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Exemplos de cobrança {#billing-examples}

Os exemplos abaixo ilustram como a alocação de uso [!DNL CPM] é feita no nível do feed de dados.

>[!IMPORTANT]
>Recomendamos que você [Relatar o uso do CPM no nível do segmento](#segment-level-report), em vez disso, faça com que esse processo seja executado automaticamente.

Considere o seguinte cenário:

![exemplos de cobrança](assets/billing-examples.png)

<br> 

### Caso 1: Segmentos com regras de qualificação E

Esse segmento contém três características de provedores de dados separados. Como a qualificação de segmento se baseia em uma condição [!UICONTROL AND], os visitantes precisam perceber as características dos três feeds para se qualificarem para o segmento.

![](assets/billing-segment-and.png)

Com uma condição [!UICONTROL AND], você deve atribuir 100% das impressões recebidas durante o mês a todos os três provedores de dados. Na seção [!UICONTROL Audience Marketplace > Payables], você credita cada provedor com 1.000.000 impressões.

Este exemplo se aplica a segmentos que usam operadores [!DNL Boolean] [!UICONTROL NOT] ou a segmentos que contêm características algorítmicas.

<br> 

### Caso 2: Segmentos com regras de qualificação OU

Esse segmento contém três características de provedores de dados separados. Como a qualificação de segmento se baseia em uma condição [!UICONTROL OR], os visitantes precisam realizar pelo menos uma das três características para se qualificar para o segmento.

Não podemos saber qual característica é responsável por uma impressão, pois a qualificação é baseada em uma condição [!UICONTROL OR]. Como resultado, na seção [!UICONTROL Audience Marketplace > Payables] você credita cada provedor com uma alocação ponderada do total de impressões, com base no preenchimento da característica.

![faturamento - ou](assets/billing-segment-or.png)

<br> 

### Caso 3: Segmentos com modelagem e casos de uso de Ativação

Este exemplo descreve a atribuição com base em dois casos de uso do Feed de dados - Modelagem e Ativação. No exemplo, estamos olhando para dois provedores de dados, com as seguintes informações:

![feed de dados](assets/feed-use-cases.png)

Na tabela a seguir, o segmento X contém duas características, T1 e T2, com a regra de segmento T1 OU T2, em que:

* T1 é uma característica do Feed de dados A;
* T2 é uma característica algorítmica modelada após características de terceiros do Feed de dados A e do Feed de dados B.

O segmento é mapeado para um destino e 1.000.000 impressões são inseridas para esse segmento em um mês, usando [Relatórios de nível de segmento](#segment-level-report).

Dessas 1.000.000 impressões:

* T1 representa 40% da população de segmentos, o que significa 400 mil impressões para o Feed A.
* O T2 representa 60% da população do segmento, o que significa 600 mil impressões do Feed A e do Feed B.

Em um nível de feed de dados, a maneira como as impressões são alocadas é:

* O Feed de dados A recebe 600.000 impressões da característica T2 (que é modelada com base em características do Feed de dados A e do Feed de dados B, portanto ambos recebem as impressões) e 400.000 impressões da característica T1 (que é uma característica do Feed de dados A), totalizando 1.000.000 impressões.
* O Feed de dados B recebe 600.000 impressões da característica T2 (veja a explicação acima) e 0 impressões da característica T1.

O detalhamento instantâneo por feed de dados e caso de uso é o seguinte:

![desagregação dos alimentos para animais](assets/feed-breakdown-alt.png)

<br> 

## Alocação de Faturamento e Impressão para Feeds de Dados de Taxa Simples {#billing-flat-fee}

Um feed de dados de taxa fixa cobra uma quantia fixa a cada mês, independentemente de quando os start da subscrição ou quantas impressões você usa. As taxas não são rateadas para uso parcial de mês ou intervalos. Assim como com o faturamento do CPM, o Adobe gerará uma fatura e cobrará uma taxa mensal de taxa fixa para os feeds de dados inscritos.

Por exemplo, digamos que você decidiu ativar certas características em um feed no meio do mês. Você ainda será cobrado na taxa mensal completa, independentemente de quando tiver iniciado a subscrição ou ativado características específicas.