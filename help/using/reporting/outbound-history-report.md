---
description: Exibir informações do histórico de tarefas em lote de saída para um destino e um período de tempo especificados.
seo-description: Exibir informações do histórico de tarefas em lote de saída para um destino e um período de tempo especificados.
seo-title: Histórico de arquivos de saída
solution: Audience Manager
title: Histórico de arquivos de saída
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: Relatórios de entrada e saída
exl-id: 8072c44f-bc9a-4b40-99d9-8cb87bb58d98
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 7%

---

# Histórico de arquivos de saída {#outbound-file-history}

Exibir informações do histórico de tarefas em lote de saída para um destino e um período de tempo especificados.

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
   <td colname="col1"> Nome do arquivo de sincronização de dados </td> 
   <td colname="col2"> <p>Lista de todos os arquivos de saída <span class="keyword"> Adobe</span> gerados para esse destino que foram processados juntos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Êxito </td> 
   <td colname="col2"> <p>Número de registros que foram enviados com êxito de <span class="keyword"> Audience Manager</span> para o destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Falha </td> 
   <td colname="col2"> <p>Número de registros que não puderam ser enviados para o destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros recebidos </td> 
   <td colname="col2"> <p>Número total de registros <span class="keyword"> Adobe</span> gerados nos arquivos e tentados enviar para o destino. Na maioria dos casos, esse deve ser o número total de arquivos bem-sucedidos e arquivos com falha. </p> </td> 
  </tr> 
 </tbody> 
</table>
