---
description: Exibir informações históricas de trabalho em lotes de saída para um destino e um período de tempo especificados.
seo-description: View outbound batch job history information for a specified destination and time period.
seo-title: Outbound File History
solution: Audience Manager
title: Histórico de arquivos de saída
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: Inbound and Outbound Reports
exl-id: 8072c44f-bc9a-4b40-99d9-8cb87bb58d98
TQID: https://experienceleague.adobe.com/bAoUgntw3hZBsEuyPQV6yX2ftNRFV9HIv9QbierOgmA
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 152
ht-degree: 1%

---

# Histórico de arquivos de saída {#outbound-file-history}

Exibir informações históricas de trabalho em lotes de saída para um destino e um período de tempo especificados.

<!-- 

t_reports_outbound_history.xml

 -->

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Outbound File History]**.

   ![Resultado da etapa](assets/outbound_history.png)

1. Na caixa **[!UICONTROL Search for a Destination]**, comece a digitar e selecione o destino desejado.
1. Na caixa **[!UICONTROL Select a Date Range]**, especifique as datas de início e término do relatório e clique em **[!UICONTROL Apply Date Filter]**.

   ![Resultado da etapa](assets/outbound_history_stats.png)

   A tabela a seguir contém informações correspondentes às colunas no relatório:

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Linha </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome do Arquivo de Sincronização de Dados </td> 
   <td colname="col2"> <p>Lista de todos os arquivos de saída que o <span class="keyword"> Adobe</span> gerou para este destino que foram processados juntos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bem-sucedido </td> 
   <td colname="col2"> <p>Número de registros enviados com êxito do <span class="keyword"> Audience Manager</span> para o destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Falha </td> 
   <td colname="col2"> <p>Número de registros que não puderam ser enviados ao destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros recebidos </td> 
   <td colname="col2"> <p>Número total de registros <span class="keyword"> Adobe</span> gerados nos arquivos e tentou enviar para o destino. Na maioria dos casos, esse deve ser o número total de arquivos bem-sucedidos e com falha. </p> </td> 
  </tr> 
 </tbody> 
</table>
