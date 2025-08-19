---
description: O relatório de Sobreposição de unidade de anúncio é exibido como um gráfico térmico que destaca as sobreposições alta e baixa entre as unidades de anúncio.
seo-description: The Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units.
seo-title: Ad Unit Overlap
solution: Audience Manager
title: Sobreposição da unidade de anúncio
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Audience Optimization Reports
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# Sobreposição da unidade de anúncio{#ad-unit-overlap}

O relatório **[!UICONTROL Ad Unit Overlap]** é exibido como um gráfico de calor que destaca as sobreposições alta e baixa entre suas Unidades de anúncio.

## Caso de uso {#use-cases}

Com o relatório **[!UICONTROL Ad Unit Overlap]**, você pode obter informações do insight sobre onde seu público-alvo se sobrepõe em suas propriedades da Web. O relatório considera suas 100 principais propriedades relacionadas e mostra a sobreposição entre elas.

## Uso do Relatório de sobreposição de unidade de anúncio {#using-the-report}

Use os controles **[!UICONTROL Top N Base Ad Units]** e **[!UICONTROL Top N Overlapping Ad Units]** para selecionar o número desejado de unidades de anúncio para a sobreposição. É possível selecionar um número máximo de 100 itens para cada um.

Use os controles **Intervalo de Dias** e **De Data até** para ajustar o intervalo de retrospectiva. Observe que os períodos retroativos de 7 dias e 30 dias só estão disponíveis para datas domingo.

Use os controles **[!UICONTROL Base Ad Unit]** e **[!UICONTROL Overlap Ad Unit]** para selecionar qual das suas unidades de anúncio deseja exibir no relatório de sobreposição.

>[!IMPORTANT]
>
>Ao habilitar [!UICONTROL Audience Optimization for Publishers], você deve incluir metadados descritivos para [!UICONTROL Ad Unit IDs], conforme descrito na Etapa 3 de [Importar Arquivos de Dados do Google Ad Manager (antigo DFP) para o Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ao fazer isso, você garante que o relatório detalhe a propriedade da Web como [!UICONTROL Ad Unit] em vez de [!UICONTROL Ad Unit ID].

## Interpretação dos resultados {#interpreting-results}

O relatório [!UICONTROL Ad Unit Overlap] pode ser semelhante ao mostrado abaixo. Passe o mouse sobre qualquer célula para obter mais informações sobre essa sobreposição específica. Consulte as descrições para obter as informações adicionais na tabela abaixo do relatório de amostra.

![](assets/publisher_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unidade de anúncio sobreposta</span> </p> </td> 
   <td colname="col2"> <p>O nome do item de inventário. Por exemplo, pode ser um dos sites ou um artigo do site. Na imagem acima, as unidades de base do anúncio são os artigos 9 - 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unidade base de publicidade</span> </p> </td> 
   <td colname="col2"> <p>O nome do item de inventário. Por exemplo, pode ser um dos sites ou um artigo do site. Na imagem acima, as unidades de base do anúncio são os Artigos 1 - 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem de únicos da unidade de anúncio sobreposta</span> </p> </td> 
   <td colname="col2"> <p>O número de usuários que visitaram os itens da unidade de anúncio 9 - 18. Essas informações são extraídas dos registros do Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem de únicos da unidade de publicidade base</span> </p> </td> 
   <td colname="col2"> <p>O número de usuários que visitaram os itens 1 a 8 da unidade de anúncio. Essas informações são extraídas dos registros do Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem de únicos de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>A sobreposição entre seus usuários que visitaram uma <span class="wintitle"> Unidade base de anúncio</span> e <span class="wintitle"> Unidade de sobreposição de anúncio</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentagem de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>A sobreposição entre seus usuários que visitaram uma <span class="wintitle"> Unidade base de anúncio</span> e <span class="wintitle"> Unidade de sobreposição de anúncio</span>. Esta é a <span class="wintitle"> Contagem de Únicos de Sobreposição</span>, expressa como uma porcentagem de <span class="wintitle"> Unidade Base de Anúncio</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
