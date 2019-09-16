---
description: Exibir informações de histórico de trabalho em lote de saída para um destino e um período de tempo especificados.
seo-description: Exibir informações de histórico de trabalho em lote de saída para um destino e um período de tempo especificados.
seo-title: Histórico de Arquivos de Saída
solution: Audience Manager
title: Histórico de Arquivos de Saída
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
translation-type: tm+mt
source-git-commit: ccff7a0337d59a2e2c65c91076a1ff38814a0dd1

---


# Histórico de Arquivos de Saída {#outbound-file-history}

Exibir informações de histórico de trabalho em lote de saída para um destino e um período de tempo especificados.

<!-- 

t_reports_outbound_history.xml

 -->

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Outbound File History]**.

   ![Resultado da etapa](assets/outbound_history.png)

1. Na **[!UICONTROL Search for a Destination]** caixa, comece a digitar e selecione o destino desejado.
1. Na **[!UICONTROL Select a Date Range]** caixa, especifique as datas de início e término do seu relatório e clique em **[!UICONTROL Apply Date Filter]**.

   ![Resultado da etapa](assets/outbound_history_stats.png)

   A tabela a seguir contém informações correspondentes às colunas do relatório:

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Linha </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome do arquivo de sincronização de dados </td> 
   <td colname="col2"> <p>Lista de todos os arquivos de saída que <span class="keyword"> a Adobe</span> gerou para este destino que foram processados juntos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Êxito </td> 
   <td colname="col2"> <p>Número de registros enviados com êxito do <span class="keyword"> Audience Manager</span> para o destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Falha </td> 
   <td colname="col2"> <p>Número de registros que não puderam ser enviados para o destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros recebidos </td> 
   <td colname="col2"> <p>O número total de registros <span class="keyword"> gerados pela Adobe</span> nos arquivos e tentados enviar para o destino. Na maioria dos casos, esse deve ser o número total de arquivos bem-sucedidos e com falha. </p> </td> 
  </tr> 
 </tbody> 
</table>
