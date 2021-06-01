---
description: As principais características não usadas são representadas como um diagrama de dispersão de características que ainda não são membros de um segmento, com base no tipo de característica, fonte de dados e desempenho.
seo-description: As principais características não usadas são representadas como um diagrama de dispersão de características que ainda não são membros de um segmento, com base no tipo de característica, fonte de dados e desempenho.
seo-title: Características principais não usadas
solution: Audience Manager
title: Características principais não usadas
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: Relatórios de otimização de público-alvo
exl-id: d0ae72c0-1fb1-423a-a7e6-de955bd7f3c5
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 2%

---

# Características principais não usadas{#top-unused-traits}

As principais características não usadas são representadas como um diagrama de dispersão de características que ainda não são membros de um segmento, com base no tipo de característica, fonte de dados e desempenho.

## Caso de uso {#use-cases}

Com o relatório [!UICONTROL Top Unused Traits], é possível analisar e comparar o desempenho de características originais e de terceiros que não estão mapeadas no momento para um segmento. Essa visualização pode destacar as melhores características a serem usadas em um segmento de público-alvo para otimização de campanha ou novas oportunidades líquidas.

## Usando o Relatório de Principais Características Não Usadas {#using-the-report}

Use os controles **[!UICONTROL Data Provider Type]** para alternar entre características originais e de terceiros. Selecione **[!UICONTROL All]** para retornar características próprias e de terceiros no relatório.

Com o controle deslizante **[!UICONTROL Impressions]**, é possível selecionar um valor mínimo e máximo para impressões retornadas. Quaisquer características responsáveis por menos ou mais dos limites definidos não são exibidas no relatório.

Use os controles **[!UICONTROL Day Range]** e **[!UICONTROL Date Through]** para ajustar o intervalo de retrospectiva. Observe que somente o período de análise de 30 dias está disponível para este relatório.

Use a caixa suspensa **[!UICONTROL Order]** para selecionar as propriedades da Web no seu portfólio para as quais deseja retornar informações.

Na caixa suspensa **[!UICONTROL Data Provider]**, selecione as fontes de dados que contêm as características que deseja ver no relatório.

Use a caixa suspensa **[!UICONTROL Traits]** para selecionar quais características deseja ver no relatório.

>[!IMPORTANT]
>
>Ao ativar [!UICONTROL Audience Optimization for Publishers], você deve incluir metadados descritivos para [!UICONTROL Order IDs], conforme descrito na Etapa 3 de [Importar arquivos de dados do Google Ad Manager (antigo DFP) para o Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ao fazer isso, você garante que o relatório detalhe a propriedade da Web como [!UICONTROL Order] em vez de [!UICONTROL Order ID].

## Interpretação dos resultados {#interpreting-results}

**Relatório de exemplo**

Seu relatório [!UICONTROL Top Unused Traits] pode ser semelhante ao abaixo. No seu relatório, clique em uma bolha para visualizar os dados subjacentes.

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
   <td colname="col2"> <p>O nome alfanumérico que você ou o provedor de dados atribuíram a essa característica. </p> </td> 
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
   <td colname="col2"> <p>O número de membros de características, nos últimos 30 dias. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

A posição de suas características em um relatório pode dizer muito sobre quais características você pode usar para otimizar segmentos de público-alvo existentes.

As características situadas acima no eixo Impressões são aquelas que você deseja usar em suas campanhas. Para características com um número baixo de impressões, é improvável que você esteja atingindo esse público-alvo na propriedade da Web, com base nos dados [!DNL Google Ad Manager].

Procure à esquerda do eixo [!UICONTROL Unique Trait Realizations] por características altamente precisas e à direita por características que possam direcionar a escala.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Indicações de posicionamento </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Superior esquerdo</b> </p> </td> 
   <td colname="col2"> <p>Alto número de impressões, baixo número de realizações de características. </p> <p>Esse é um público-alvo de alta precisão que ainda não é membro de um segmento. Considere o direcionamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior Esquerdo</b> </p> </td> 
   <td colname="col2"> <p>Baixo número de impressões, baixo número de realizações de características. </p> <p> Exclua essas características, pois os membros não estão contribuindo para impressões em suas propriedades da Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Superior direito</b> </p> </td> 
   <td colname="col2"> <p>Alto número de impressões, alto número de realizações de características. </p> <p>Um alto alcance em relação a um público-alvo que ainda não está indicado em um segmento. Esse público-alvo é o principal candidato para definição de metas devido ao alto número de impressões e à escala. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Parte inferior direita</b> </p> </td> 
   <td colname="col2"> <p>Baixo número de impressões, alto número de realizações de características. </p> <p> Você pode descartar essas características, pois os membros não estão contribuindo para impressões em suas propriedades da Web. </p> </td> 
  </tr> 
 </tbody> 
</table>
