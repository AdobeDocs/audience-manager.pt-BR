---
description: O relatório de sobreposição da unidade de publicidade é exibido como um gráfico de calor que destaca sobreposições elevadas e baixas entre as suas Unidades de publicidade.
seo-description: O relatório de sobreposição da unidade de publicidade é exibido como um gráfico de calor que destaca sobreposições elevadas e baixas entre as suas Unidades de publicidade.
seo-title: Sobreposição da unidade de publicidade
solution: Audience Manager
title: Sobreposição da unidade de publicidade
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---


# Sobreposição da unidade de publicidade{#ad-unit-overlap}

O **[!UICONTROL Ad Unit Overlap]** relatório é exibido como um gráfico de calor que destaca sobreposições elevadas e baixas entre as suas Unidades de publicidade.

## Caso de uso {#use-cases}

Com o **[!UICONTROL Ad Unit Overlap]** relatório, você pode obter informações sobre onde sua audiência se sobrepõe nas propriedades da Web. O relatório considera suas 100 principais propriedades relacionadas e mostra a sobreposição entre elas.

## Uso do relatório de sobreposição da unidade de publicidade {#using-the-report}

Use os controles **[!UICONTROL Top N Base Ad Units]** e **[!UICONTROL Top N Overlapping Ad Units]** para selecionar o número desejado de unidades de publicidade para a sobreposição. Você pode selecionar um número máximo de 100 itens para cada um.

Use os controles Intervalo **de** dias e Intervalo de **datas até** para ajustar o intervalo de retrospectiva. Observe que os períodos de retrospectiva de 7 e 30 dias só estão disponíveis para datas de domingo.

Use os controles **[!UICONTROL Base Ad Unit]** e **[!UICONTROL Overlap Ad Unit]** para selecionar qual de suas unidades de publicidade você deseja exibir no relatório de sobreposição.

>[!IMPORTANT]
>
>Ao ativar [!UICONTROL Audience Optimization for Publishers], você deve incluir metadados descritivos para [!UICONTROL Ad Unit IDs], conforme descrito na Etapa 3 de [Importar arquivos de dados DFP para o Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ao fazer isso, você garante que o relatório detalhe a propriedade da Web como [!UICONTROL Ad Unit] não como [!UICONTROL Ad Unit ID].

## Interpretação dos resultados {#interpreting-results}

O seu [!UICONTROL Ad Unit Overlap] relatório pode ser semelhante ao que se segue. Passe o mouse sobre qualquer célula para obter mais informações sobre essa sobreposição específica. Consulte descrições para obter as informações adicionais na tabela abaixo do relatório de amostra.

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
   <td colname="col1"> <p><span class="wintitle"> Unidade de publicidade sobreposta</span> </p> </td> 
   <td colname="col2"> <p>O nome do item de inventário. Por exemplo, este pode ser um de seus sites ou um artigo em seu site. Na imagem acima, as unidades de base são os artigos 9 º - 18 º. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unidade básica de anúncio</span> </p> </td> 
   <td colname="col2"> <p>O nome do item de inventário. Por exemplo, este pode ser um de seus sites ou um artigo em seu site. Na imagem acima, as unidades de base são os artigos 1 º a 8 º. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem exclusiva de unidade de publicidade sobreposta</span> </p> </td> 
   <td colname="col2"> <p>O número de usuários que visitaram os itens da unidade de publicidade 9 a 18. Essas informações são extraídas dos registros DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem de únicos da unidade de anúncios base</span> </p> </td> 
   <td colname="col2"> <p>O número de usuários que visitaram os itens da unidade de publicidade 1 a 8. Essas informações são extraídas dos registros DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Contagem exclusiva de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>A sobreposição entre os usuários que visitaram uma unidade <span class="wintitle"> de anúncios base e uma unidade</span> de anúncios <span class="wintitle"></span>sobreposta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentagem de sobreposição</span> </p> </td> 
   <td colname="col2"> <p>A sobreposição entre os usuários que visitaram uma unidade <span class="wintitle"> de anúncios base e uma unidade</span> de anúncios <span class="wintitle"></span>sobreposta. Esta é a Contagem <span class="wintitle"> Únicos de Sobreposição, expressa como uma porcentagem da Unidade</span>de anúncio <span class="wintitle"></span>base. </p> </td> 
  </tr> 
 </tbody> 
</table>
