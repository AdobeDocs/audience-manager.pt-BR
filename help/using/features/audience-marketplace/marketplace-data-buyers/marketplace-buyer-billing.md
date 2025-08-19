---
description: Os compradores de dados da Audience Marketplace concordam em relatar todas as impressões de anúncios veiculadas com as características contidas no feed de dados orçado com base no custo por mil impressões de anúncios (CPM). O uso do CPM é devido no quinto dia de cada mês e inclui dados do mês anterior. Os assinantes de taxa única não precisam relatar o uso.
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
source-wordcount: '2029'
ht-degree: 0%

---

# Faturamento para compradores de feed de dados {#billing-for-data-feed-buyers}

Os compradores de dados da Audience Marketplace concordam em relatar todas as impressões de anúncios veiculadas com as características contidas no feed de dados orçado com base no custo por mil impressões de anúncios ([!DNL CPM]). O uso de [!DNL CPM] ocorre no quinto dia de cada mês e inclui os dados do mês anterior. Os assinantes de taxa única não precisam relatar o uso.

<br> 

## Como relatar o uso do CPM {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] compradores de dados concordam em relatar todas as impressões de anúncios veiculadas com as características contidas no feed de dados orçadas em uma base de custo por mil impressões de anúncios ([!DNL CPM]). O uso de [!DNL CPM] vence aos 5 dias de cada mês e inclui os dados do mês anterior. Os assinantes de taxa única não precisam relatar o uso.

[!UICONTROL Audience Marketplace] oferece duas maneiras de relatar o uso de [!DNL CPM]:

* **Relatórios no nível de segmento**: este é o método de relatório de uso [!DNL CPM] recomendado. Ao relatar o uso de [!DNL CPM] no nível do segmento, a seção de relatório no nível do feed de dados é automaticamente preenchida com os valores de uso correspondentes, com base nos algoritmos descritos em [Atribuição de custo para feeds de dados do CPM](#cost-attribution).
* **Relatórios de nível de feed de dados**: este método requer que você relate individualmente o uso de [!DNL CPM] para cada feed de dados, com base nos algoritmos descritos em [Atribuição de Custo para Feeds de Dados do CPM](#cost-attribution). No entanto, esse método é mais tedioso e propenso a erros do que o relatório em nível de segmento.

<br> 

## Relatar uso do CPM no nível do segmento {#segment-level-report}

A guia [!UICONTROL Segment Usage] permite relatar o uso em nível de segmento, ao mesmo tempo em que exibe os segmentos agrupados pelos destinos aos quais eles estão mapeados.

Depois de relatar o uso de [!DNL CPM] no nível de segmento, o [!UICONTROL Audience Marketplace] atribui automaticamente os feeds de dados correspondentes ao uso correto, com base na [Atribuição de Custo para Feeds de Dados do CPM](#cost-attribution).

Para relatar o uso de [!DNL CPM] no nível de segmento:

1. Ir para **[!UICONTROL Audience Marketplace > Payables]**.
1. Selecione a guia **[!UICONTROL Segment Usage]**.
1. Preencha o uso para seus segmentos. Você pode usar a caixa [!UICONTROL Search] para filtrar os segmentos se precisar relatar o uso de apenas alguns deles.
1. Clique em **[!UICONTROL Edit Segments Usage]**.
1. Insira o valor de uso de [!DNL CPM] na coluna [!UICONTROL Usage].
1. Clique em **[!UICONTROL Save]** quando terminar e revise a caixa de diálogo de confirmação.

   ![confirme-segment-usage](assets/confirm-segment-usage.png)

1. Clique em **[!UICONTROL Confirm]**.

Veja também nossa demonstração em vídeo de como é possível relatar o uso em nível de segmento:

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## Relatar uso do CPM no nível do feed de dados {#feed-level-report}

Os relatórios no nível do feed de dados são um processo mais tedioso e sujeito a erros, já que você deve calcular individualmente o uso de [!DNL CPM] para cada feed de dados. Em vez disso, recomendamos que você [Relate o Uso do CPM no Nível de segmento](#segment-level-report).

Para relatar o uso de [!DNL CPM] no nível de segmento:

1. Ir para **[!UICONTROL Audience Marketplace > Payables]**.
2. Selecione a guia **[!UICONTROL Feed Usage]**.
3. Use a caixa [!UICONTROL Search] para filtrar os feeds de dados e identificar aqueles para os quais você precisa relatar uso.
4. Clique em **[!UICONTROL Edit Feeds Usage]**.
5. Calcule o uso de [!DNL CPM] para cada feed de dados com base na [Atribuição de Custo para Feeds de Dados do CPM](#cost-attribution) e insira-o na coluna [!UICONTROL Usage].
6. Clique em **[!UICONTROL Save]** quando terminar e revise a caixa de diálogo de confirmação.

   ![confirme-feed-usage](assets/confirm-feed-usage.png)

7. Clique em **[!UICONTROL Confirm]**.

<br> 

## Relatório em massa

Para reduzir erros e sobrecarga ao relatar o uso de [!DNL CPM], você pode usar a opção de relatório em massa para baixar um arquivo [!DNL CSV] contendo os feeds de dados e segmentos, preencher o uso e carregá-lo de volta para [!DNL Audience Manager]. Você pode usar o relatório em massa para relatar o uso do feed e do segmento.

Para atualizar o uso de [!DNL CPM] em massa:

1. Ir para **[!UICONTROL Audience Marketplace > Payables]**.
1. Selecione a guia **[!UICONTROL Feed Usage]** ou **[!UICONTROL Segment Usage]**, dependendo do tipo de relatório que você deseja atualizar.
1. Clique em **[!UICONTROL Edit Feeds Usage]** ou **[!UICONTROL Edit Segments Usage]**.
1. Clique em **[!UICONTROL download the current usage]** para verificar se você usa um arquivo CSV válido.
1. Abra o arquivo no computador e preencha o relatório de uso.
1. Clique em **[!UICONTROL Choose a CSV file]** para carregar o relatório de uso atualizado.

   ![relatório-uso-csv](assets/usage-report-csv.png)

1. O [!DNL Audience Manager] valida o arquivo assim que você o carrega e avisa se ele detecta erros no arquivo.

<br> 

### Erros de validação de relatório em massa

| Mensagem de erro | Descrição | Correção |
| ------------- | -------------| -----|
| Entrada inválida | [!DNL Audience Manager] detectou uma alteração no esquema de arquivo [!DNL CSV], como colunas ausentes ou alterações nos títulos das colunas. | Evite alterar a estrutura da tabela. |
| Não encontrada | Para [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] não pôde identificar a combinação de [!UICONTROL Segment ID] e [!UICONTROL Destination ID]. Para [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] não pôde identificar a combinação de [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] e [!UICONTROL Use Case]. | Para [!UICONTROL Segment Level Reporting], verifique a validade da combinação [!UICONTROL Segment ID] e [!UICONTROL Destination ID]. Para [!UICONTROL Feed Level Reporting], verifique a validade da combinação de [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] e [!UICONTROL Use Case]. |
| Registros Duplicados Encontrados | [!DNL Audience Manager] detectou registros duplicados com valores de impressão diferentes. | Revise o relatório e certifique-se de não relatar valores de uso diferentes para o mesmo feed de dados ou segmento. |
| Valores não suportados | [!DNL Audience Manager] valores não numéricos detectados na coluna [!DNL Audience Manager]. | Revise o relatório e certifique-se de inserir apenas valores numéricos na coluna [!DNL Audience Manager]. |
| Cabeçalhos para campos obrigatórios ausentes | [!DNL Audience Manager] cabeçalhos de tabela ausentes detectados para campos obrigatórios. Para [!UICONTROL Segment Level Reporting], os campos obrigatórios são: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. Para [!UICONTROL Feed Level Reporting], os campos obrigatórios são: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name], [!UICONTROL Use Case] | Revise o relatório e verifique se os cabeçalhos da tabela não foram adulterados. |

>[!NOTE]
>A remoção de linhas do relatório de uso [!DNL CSV] não afeta o relatório de uso existente. [!DNL Audience Manager] processa apenas os campos incluídos no relatório.

<br> 

## Práticas recomendadas para relatórios do [!DNL CPM]

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
   <td colname="col2"> <p>Para totais de impressão do CPM: </p>
   <p> Relate o número total de impressões, sem usar decimais. O Audience Manager calcula automaticamente o CPM com base no número total relatado.</p><p>Se precisar relatar 1.234.567 impressões, relate exatamente assim. Não é necessário dividir o número total de impressões por 1.000 para calcular o CPM.</p><p>As características usadas para otimizar o conteúdo da Web ou do aplicativo (Otimização de conteúdo) usando ferramentas como o Adobe Target ou um destino do Analytics não contribuem para os totais de Uso dos planos do CPM. Os provedores de dados normalmente são compensados pela Otimização de conteúdo usando planos de taxa fixos.</p><p>Consulte <a href="#cost-attribution">Atribuição de custo para feeds de dados do CPM</a> para obter mais informações. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Manter o intervalo dos relatórios mensais</b> </p> </td> 
   <td colname="col2"> <p>O sistema de relatórios fecha depois do dia 5 de cada mês. Se você não relatar o uso do CPM até então, é necessário adicionar essa quantidade ao relatório para o mês seguinte. Por exemplo, digamos que você use 1000 impressões em outubro, perca o prazo de relatório de outubro e use 1000 impressões em novembro. Nesse caso, você informa o total de outubro e novembro (2000) em dezembro, entre os dias 1º e 5º.</p><p><b>Dica</b>: você sempre deve tentar relatar o uso do CPM para o mês anterior entre o primeiro e o quinto dias do mês seguinte.</p><p>Você pode relatar o uso do CPM até o dia 5 do novo mês, mas isso não é recomendado. Relatar o uso do CPM antes do dia 5 de cada mês dá ao Audience Manager tempo para verificar e processar os dados.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Atribuição de custo para feeds de dados do CPM {#cost-attribution}

No [!UICONTROL Audience Marketplace], você deve relatar automaticamente os valores de impressão a cada mês para cada um dos seus segmentos. Recomendamos relatar o uso de [!DNL CPM] no nível do segmento, para que a atribuição de custo seja feita automaticamente.

<!-- marketplace_cpm_billing.xml -->

### Resumo da Cobrança {#billing-summary}

Você deve enviar [!DNL CPM] valores de impressão do feed de dados entre o primeiro e o quinto dias de cada mês. Para fazer isso corretamente, recomendamos que você [Relate o Uso do CPM no Nível de Segmento](#segment-level-report).

>[!TIP]
>Ao relatar o uso de [!DNL CPM] no nível do segmento, a seção de relatório no nível do feed de dados é preenchida automaticamente com as quantidades de uso correspondentes.

Caso precise [!UICONTROL Report CPM Usage at Data Feed Level], você deve compilar individualmente todas as impressões entregues para cada feed no mês anterior e relatá-las de acordo com a alocação de faturamento descrita neste artigo.

Depois que você relatar o número [!DNL CPM] do mês anterior, [!DNL Adobe] fará o seguinte:

* Crie uma fatura e cobre com base na taxa de [!DNL CPM] para cada feed de dados assinado.
* Pague as taxas dos provedores de dados (vendedores) com base no uso relatado de [!DNL CPM].

>[!IMPORTANT]
>
>Como comprador, todos os totais de impressão relatados devem ser verdadeiros e precisos. Se você não relatar os totais de impressão até o quinto dia de cada mês, será necessário incluir os totais do mês não reportado no mês seguinte.

<br> 

## Atribuir impressões no nível do feed com base nas regras de qualificação de característica {#assign-impressions}

O caso de uso [!UICONTROL Activation] permite que você use características no feed de dados correspondente para criar segmentos no [Construtor de segmentos](../../../features/segments/segment-builder.md) e mapear esses segmentos para um destino. Os operadores booleanos [!UICONTROL AND], [!UICONTROL OR] e [!UICONTROL NOT] permitem que você defina as condições para qualificação de características e segmentos.

Ao [Relatar o Uso do CPM no Nível de Feed de Dados](#feed-level-report), você deve alocar impressões proporcionalmente para cada feed de dados, de acordo com os operadores [!DNL Boolean] usados nas regras de qualificação de característica. A tabela a seguir lista como alocar impressões corretamente por regra booleana ou tipo de característica.

>[!TIP]
>[Relate o Uso do CPM no Nível de Segmento](#segment-level-report) para que o relatório no nível de feed de dados seja feito automaticamente pelo Audience Manager.

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
   <td colname="col2"> <p>Aplique 100% dos totais de impressão entregues a todas as características do provedor em um segmento baseado em regras que usa uma condição booleana <span class="wintitle"> AND</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> OU</span> </p> </td> 
   <td colname="col2"> <p>Aplique a alocação ponderada dos totais de impressão entregues a todas as características do provedor em um segmento baseado em regras que usa uma condição OR booleana. A alocação ponderada é calculada usando a seguinte fórmula:</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>Aplique 100% dos totais de impressão entregues a todas as características do provedor em um segmento baseado em regras que usa uma condição booleana <span class="wintitle"> NOT</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segmentos algorítmicos </p> </td> 
   <td colname="col2"> <p>Aplique 100% dos totais de impressão entregues a todos os feeds de provedor em um segmento que contenha características algorítmicas. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Exemplos de cobrança {#billing-examples}

Os exemplos abaixo ilustram como a alocação de uso de [!DNL CPM] é feita no nível de feed de dados.

>[!IMPORTANT]
>Recomendamos que você [Relate o Uso do CPM no Nível de segmento](#segment-level-report), para que esse processo seja executado automaticamente.

Vamos considerar o seguinte cenário:

![exemplos de cobrança](assets/billing-examples.png)

<br> 

### Caso 1: Segmentos com regras de qualificação AND

Esse segmento contém 3 características de provedores de dados separados. Como a qualificação de segmento é baseada em uma condição [!UICONTROL AND], os visitantes têm de perceber as características de todos os três feeds para se qualificarem para o segmento.

![](assets/billing-segment-and.png)

Com uma condição [!UICONTROL AND], você deve atribuir 100% das impressões recebidas durante o mês a todos os três provedores de dados. Na seção [!UICONTROL Audience Marketplace > Payables], você credita a cada provedor com 1.000.000 impressões.

Este exemplo se aplica a segmentos que usam operadores [!DNL Boolean] [!UICONTROL NOT] ou a segmentos que contêm características algorítmicas.

<br> 

### Caso 2: Segmentos com regras de qualificação OR

Esse segmento contém 3 características de provedores de dados separados. Como a qualificação de segmento é baseada em uma condição [!UICONTROL OR], os visitantes têm de perceber pelo menos uma das três características para se qualificarem para o segmento.

Não é possível saber qual característica é responsável por uma impressão porque a qualificação se baseia em uma condição [!UICONTROL OR]. Como resultado, na seção [!UICONTROL Audience Marketplace > Payables], você credita a cada provedor uma alocação ponderada do total de impressões, com base na população de características.

![segmento de faturamento-ou](assets/billing-segment-or.png)

<br> 

### Caso 3: Segmentos com casos de uso de modelagem e ativação

Este exemplo descreve a atribuição com base em dois casos de uso do Feed de dados: Modelagem e Ativação. No exemplo, estamos observando dois provedores de dados, com as seguintes informações:

![feed de dados](assets/feed-use-cases.png)

Na tabela abaixo, o Segmento X contém duas características, T1 e T2, com a regra de segmento T1 OU T2, em que:

* T1 é uma característica do Feed de dados A;
* T2 é uma característica algorítmica modelada após características de terceiros do Feed de dados A e do Feed de dados B.

O segmento é mapeado para um destino e 1.000.000 impressões são inseridas para este segmento em um mês, usando o [Relatório de nível de segmento](#segment-level-report).

Dessas 1.000.000 impressões:

* O T1 representa 40% da população do segmento, o que significa 400.000 impressões para o Feed A.
* O T2 representa 60% da população do segmento, o que significa 600.000 impressões para o Feed A e o Feed B.

Em um nível de feed de dados, a maneira como as impressões são alocadas é:

* O Feed de dados A recebe 600.000 impressões da característica T2 (que é modelada nas características do Feed de dados A e do Feed de dados B, para que ambos recebam as impressões) e 400.000 impressões da característica T1 (que é uma característica do Feed de dados A), totalizando 1.000.000 impressões.
* O Feed de dados B recebe 600.000 impressões da característica T2 (consulte a explicação acima) e 0 impressões da característica T1.

O detalhamento rápido por feed de dados e caso de uso é o seguinte:

![detalhamento de feed](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>Para o caso de uso de modelagem, você deve relatar o uso do CPM somente após a ativação. Se você executar apenas um modelo, mas não ativá-lo, nenhum relatório de uso será necessário.

<br> 

## Alocação de impressão e cobrança para feeds de dados de taxa fixa {#billing-flat-fee}

Um feed de dados de taxa fixa fatura um valor fixo a cada mês, independentemente de quando a assinatura começa ou quantas impressões você usa. As taxas não são rateadas para uso ou intervalos parciais do mês. Assim como ocorre com o faturamento da CPM, a Adobe gerará uma fatura e cobrará com a taxa de taxa uniforme mensal dos feeds de dados que você assina.

Por exemplo, digamos que você tenha decidido ativar determinadas características em um feed no meio do mês. Você ainda será cobrado com a taxa mensal total, independentemente de quando iniciou a assinatura ou ativou características específicas.
