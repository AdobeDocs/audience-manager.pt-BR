---
description: O relatório de sobreposição da unidade de anúncio é exibido como um gráfico de calor que destaca sobreposições altas e baixas entre as unidades de anúncios.
seo-description: O relatório de sobreposição da unidade de anúncio é exibido como um gráfico de calor que destaca sobreposições altas e baixas entre as unidades de anúncios.
seo-title: Sobreposição da unidade de anúncio
solution: Audience Manager
title: Sobreposição da unidade de anúncio
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Relatórios de otimização de público-alvo
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 3%

---

# Sobreposição da unidade de anúncio{#ad-unit-overlap}

O relatório **[!UICONTROL Ad Unit Overlap]** é exibido como um gráfico de calor que destaca as sobreposições altas e baixas entre as Unidades de publicidade.

## Caso de uso {#use-cases}

Com o relatório **[!UICONTROL Ad Unit Overlap]**, você pode obter informações sobre onde seu público-alvo se sobrepõe nas propriedades da Web. O relatório considera suas 100 principais propriedades relacionadas e mostra a sobreposição entre elas.

## Uso do Relatório de sobreposição da unidade de anúncio {#using-the-report}

Use os controles **[!UICONTROL Top N Base Ad Units]** e **[!UICONTROL Top N Overlapping Ad Units]** para selecionar o número desejado de unidades de publicidade para a sobreposição. Você pode selecionar um número máximo de 100 itens para cada.

Use os controles **Intervalo de dia** e **Até** para ajustar o intervalo de análise. Observe que os períodos de retrospectiva de 7 dias e 30 dias só estão disponíveis para datas de domingo.

Use os **[!UICONTROL Base Ad Unit]** e os **[!UICONTROL Overlap Ad Unit]** controles para selecionar qual de suas unidades de publicidade você deseja exibir no relatório de sobreposição.

>[!IMPORTANT]
>
>Ao ativar [!UICONTROL Audience Optimization for Publishers], você deve incluir metadados descritivos para [!UICONTROL Ad Unit IDs], conforme descrito na Etapa 3 de [Importar arquivos de dados do Google Ad Manager (antigo DFP) para o Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ao fazer isso, você garante que o relatório detalhe a propriedade da Web como [!UICONTROL Ad Unit] em vez de [!UICONTROL Ad Unit ID].

## Interpretação dos resultados {#interpreting-results}

Seu relatório [!UICONTROL Ad Unit Overlap] pode ser semelhante ao abaixo. Passe o mouse sobre qualquer célula para obter mais informações sobre essa sobreposição específica. Consulte descrições para obter as informações adicionais na tabela abaixo do relatório de amostra.

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
   <td colname="col1"> <p><span class="wintitle"> Unidade de anúncio de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>O nome do item de inventário. Por exemplo, este pode ser um de seus sites ou um artigo em seu site. Na imagem acima, as unidades de base são os artigos 9.º a 18.º. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unidade básica de anúncio</span> </p> </td> 
   <td colname="col2"> <p>O nome do item de inventário. Por exemplo, este pode ser um de seus sites ou um artigo em seu site. Na imagem acima, as unidades de anúncio base são os artigos 1.º a 8.º. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem Única De Unidade De Anúncio De Sobreposição</span> </p> </td> 
   <td colname="col2"> <p>O número de usuários que visitaram os itens da unidade de anúncios 9 - 18. Essas informações são extraídas dos registros do Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem Única de Unidades de Anúncio Base</span> </p> </td> 
   <td colname="col2"> <p>O número de usuários que visitaram os itens da unidade de anúncios 1 - 8. Essas informações são extraídas dos registros do Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem de únicos de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>A sobreposição entre os usuários que visitaram uma <span class="wintitle"> Unidade de anúncio base</span> e <span class="wintitle"> Unidade de anúncio de sobreposição</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentagem de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>A sobreposição entre os usuários que visitaram uma <span class="wintitle"> Unidade de anúncio base</span> e <span class="wintitle"> Unidade de anúncio de sobreposição</span>. Esta é a <span class="wintitle"> Contagem de únicos de sobreposição</span>, expressa como uma porcentagem da <span class="wintitle"> Unidade de anúncio base</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
