---
description: As Características principais não usadas são representadas como um diagrama de dispersão de características que ainda não são membros de um segmento, com base no tipo de característica, fonte de dados e desempenho.
seo-description: As Características principais não usadas são representadas como um diagrama de dispersão de características que ainda não são membros de um segmento, com base no tipo de característica, fonte de dados e desempenho.
seo-title: Características principais não usadas
solution: Audience Manager
title: Características principais não usadas
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Características principais não usadas{#top-unused-traits}

As Características principais não usadas são representadas como um diagrama de dispersão de características que ainda não são membros de um segmento, com base no tipo de característica, fonte de dados e desempenho.

## Caso de uso {#use-cases}

Com o [!UICONTROL Top Unused Traits] relatório, você pode analisar e comparar o desempenho de características originais e de terceiros que não estão mapeadas no momento para um segmento. Esta exibição pode indicar as melhores características a serem usadas em um segmento de público-alvo para otimização de campanha ou novas oportunidades líquidas.

## Usando o relatório Principais características não usadas {#using-the-report}

Use os **[!UICONTROL Data Provider Type]** controles para alternar entre características de terceiros e de terceiros. Selecione **[!UICONTROL All]** para retornar características originais e de terceiros no relatório.

Com o **[!UICONTROL Impressions]** controle deslizante, é possível selecionar um valor mínimo e máximo para impressões retornadas. Quaisquer características responsáveis por menos ou mais dos limites definidos não serão exibidas no relatório.

Use os controles **[!UICONTROL Day Range]** e **[!UICONTROL Date Through]** para ajustar o intervalo de retorno. Observe que apenas o período de 30 dias de análise está disponível para este relatório.

Use a caixa **[!UICONTROL Order]** suspensa para selecionar as propriedades da Web no seu portfólio para as quais deseja retornar informações.

Na caixa **[!UICONTROL Data Provider]** suspensa, selecione as fontes de dados que contêm as características que você deseja ver no relatório.

Use a caixa **[!UICONTROL Traits]** suspensa para selecionar quais características você deseja ver no relatório.

>[!IMPORTANT]
>
>Ao ativar [!UICONTROL Audience Optimization for Publishers], você deve incluir metadados descritivos para [!UICONTROL Order IDs], conforme descrito na Etapa 3 de [Importar arquivos de dados DFP para o Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ao fazer isso, você garante que o relatório detalhe a propriedade da Web como [!UICONTROL Order] não como [!UICONTROL Order ID].

## Interpretação dos resultados {#interpreting-results}

**Relatório de exemplo**

O seu [!UICONTROL Top Unused Traits] relatório pode ser semelhante ao que se segue. Em seu relatório, clique em uma bolha para exibir os dados subjacentes.

Consulte descrições para obter as informações adicionais na tabela abaixo do relatório de amostra.

![](assets/publisher_unused_traits.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tipo de provedor de dados</span> </p> </td> 
   <td colname="col2"> <p>Especifica se a fonte de dados selecionada contém características originais ou de terceiros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID da característica</span> </p> </td> 
   <td colname="col2"> <p>A ID exclusiva dessa característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nome da característica</span> </p> </td> 
   <td colname="col2"> <p>O nome alfanumérico que você ou o provedor de dados atribuiu a essa característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Pedido</span> </p> </td> 
   <td colname="col2"> <p>A propriedade da Web para a qual você está vendo este relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressões</span> </p> </td> 
   <td colname="col2"> <p>O número de vezes que membros dessa característica foram expostos ao seu inventário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Características únicas</span> </p> </td> 
   <td colname="col2"> <p>O número de membros características, nos últimos 30 dias. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

A posição de suas características em um relatório pode informar muito sobre quais características você pode usar para otimizar segmentos de público-alvo existentes.

As características situadas acima no eixo Impressões são aquelas que você deseja usar em suas campanhas. Para características com um número baixo de impressões, é improvável que você esteja atingindo esse público-alvo em sua propriedade da Web, com base nos dados do DFP.

À esquerda do [!UICONTROL Unique Trait Realizations] eixo, procure traços altamente precisos e à direita por traços que possam impulsionar a escala.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Posição </th> 
   <th colname="col2" class="entry"> A disposição indica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Superior esquerdo</b> </p> </td> 
   <td colname="col2"> <p>Número alto de impressões, número baixo de realização de características. </p> <p>Este é um público-alvo altamente preciso que ainda não é membro de um segmento. Considere a definição de metas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior esquerdo</b> </p> </td> 
   <td colname="col2"> <p>Número baixo de impressões, número baixo de realização de características. </p> <p> Exclua essas características, já que os membros não estão contribuindo para impressões em suas propriedades da Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Superior direito</b> </p> </td> 
   <td colname="col2"> <p>Alto número de impressões, alto número de realização de características. </p> <p>Um alto alcance contra um público-alvo que ainda não está denotado em um segmento. Esse público é um candidato importante para a definição de metas devido ao alto número de impressões e à escala. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior direito</b> </p> </td> 
   <td colname="col2"> <p>Número baixo de impressões, número elevado de realização de características. </p> <p> Você pode descartar essas características, já que os membros não estão contribuindo para impressões em suas propriedades da Web. </p> </td> 
  </tr> 
 </tbody> 
</table>
