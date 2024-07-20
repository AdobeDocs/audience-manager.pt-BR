---
description: As Características principais não usadas são representadas como um diagrama de dispersão de características que ainda não são membros de um segmento, com base no tipo de característica, na fonte de dados e no desempenho.
seo-description: Top Unused Traits are represented as a scatter diagram of traits that are not yet members of a segment, based on trait type, data source, and performance.
seo-title: Top Unused Traits
solution: Audience Manager
title: Características principais não usadas
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: Audience Optimization Reports
exl-id: d0ae72c0-1fb1-423a-a7e6-de955bd7f3c5
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 0%

---

# Características principais não usadas{#top-unused-traits}

As Características principais não usadas são representadas como um diagrama de dispersão de características que ainda não são membros de um segmento, com base no tipo de característica, na fonte de dados e no desempenho.

## Caso de uso {#use-cases}

Com o relatório [!UICONTROL Top Unused Traits], é possível analisar e comparar o desempenho de características próprias e de terceiros que não estão mapeadas a um segmento no momento. Essa exibição pode apontar as melhores características para usar em um segmento de público-alvo para otimização de campanha ou novas oportunidades.

## Uso do relatório Principais características não utilizadas {#using-the-report}

Use os controles **[!UICONTROL Data Provider Type]** para alternar entre características próprias e de terceiros. Selecione **[!UICONTROL All]** para retornar características próprias e de terceiros no relatório.

Com o controle deslizante **[!UICONTROL Impressions]**, é possível selecionar um valor mínimo e máximo para impressões retornadas. Quaisquer características responsáveis por menos ou mais do que os limites definidos não são exibidas no relatório.

Use os controles **[!UICONTROL Day Range]** e **[!UICONTROL Date Through]** para ajustar o intervalo de retrospectiva. Observe que somente o período retroativo de 30 dias está disponível para esse relatório.

Use a caixa suspensa **[!UICONTROL Order]** para selecionar as propriedades da Web no portfólio para as quais deseja retornar informações.

Na caixa suspensa **[!UICONTROL Data Provider]**, selecione as fontes de dados que contêm as características que você deseja ver no relatório.

Use a caixa suspensa **[!UICONTROL Traits]** para selecionar quais características você deseja ver no relatório.

>[!IMPORTANT]
>
>Ao habilitar [!UICONTROL Audience Optimization for Publishers], você deve incluir metadados descritivos para [!UICONTROL Order IDs], conforme descrito na Etapa 3 de [Importar arquivos de dados do Google Ad Manager (antigo DFP) para o Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ao fazer isso, você garante que o relatório detalhe a propriedade da Web como [!UICONTROL Order] em vez de [!UICONTROL Order ID].

## Interpretação dos resultados {#interpreting-results}

**Relatório de Exemplo**

O relatório [!UICONTROL Top Unused Traits] pode ser semelhante ao mostrado abaixo. No relatório, clique em uma bolha para visualizar os dados subjacentes.

Consulte as descrições para obter as informações adicionais na tabela abaixo do relatório de amostra.

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
   <td colname="col2"> <p>Especifica se a fonte de dados selecionada contém características próprias ou de terceiros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID da característica</span> </p> </td> 
   <td colname="col2"> <p>A ID exclusiva desta característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nome da característica</span> </p> </td> 
   <td colname="col2"> <p>O nome alfanumérico que você ou o provedor de dados atribuiu a essa característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Ordem</span> </p> </td> 
   <td colname="col2"> <p>A propriedade da Web para a qual você está vendo este relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressões</span> </p> </td> 
   <td colname="col2"> <p>O número de vezes que os membros desta característica foram expostos ao inventário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Características únicas</span> </p> </td> 
   <td colname="col2"> <p>O número de membros de característica nos últimos 30 dias. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

A posição das suas características em um relatório pode informar muito sobre quais características você pode usar para otimizar segmentos de público-alvo existentes.

As características situadas mais acima no eixo Impressões são as que você deseja usar em suas campanhas. Para características com um número baixo de impressões, é improvável que você esteja atingindo esse público-alvo na sua propriedade da Web, com base nos seus dados do [!DNL Google Ad Manager].

Olhe à esquerda do eixo [!UICONTROL Unique Trait Realizations] para características altamente precisas e à direita para características que podem gerar escala.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Posicionamento indica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Superior esquerdo</b> </p> </td> 
   <td colname="col2"> <p>Alto número de impressões, baixo número de realizações de características. </p> <p>Este é um público-alvo altamente preciso que ainda não é membro de um segmento. Considere para direcionamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior esquerdo</b> </p> </td> 
   <td colname="col2"> <p>Baixo número de impressões, baixo número de realizações de características. </p> <p> Exclua essas características, pois os membros não estão contribuindo para impressões em suas propriedades da Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Cima à Direita</b> </p> </td> 
   <td colname="col2"> <p>Alto número de impressões, alto número de realizações de características. </p> <p>Um alto alcance em relação a um público que ainda não é denotado em um segmento. Esse público-alvo é um excelente candidato para direcionamento devido ao alto número de impressões e à escala. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Parte Inferior Direita</b> </p> </td> 
   <td colname="col2"> <p>Baixo número de impressões, alto número de realizações de características. </p> <p> Você pode descartar essas características, pois os membros não estão contribuindo para impressões em suas propriedades da Web. </p> </td> 
  </tr> 
 </tbody> 
</table>
