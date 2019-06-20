---
description: O Audience Manager recebe uma grande quantidade de dados todos os dias. Isso afeta o tempo necessário para processar seus dados e gerar resultados de relatório. O conteúdo nesta seção descreve como esses intervalos de tempo afetam sua conta do Audience Manager. Além disso, os intervalos de tempo e agendamentos descritos aqui são diretrizes gerais apenas. Esses cronogramas não constituem os Contratos de nível de serviço (slas) ou os compromissos relacionados à entrega de dados. A Adobe reserva o direito de alterar os intervalos de tempo e horários a qualquer momento sem aviso prévio.
seo-description: O Audience Manager recebe uma grande quantidade de dados todos os dias. Isso afeta o tempo necessário para processar seus dados e gerar resultados de relatório. O conteúdo nesta seção descreve como esses intervalos de tempo afetam sua conta do Audience Manager. Além disso, os intervalos de tempo e agendamentos descritos aqui são diretrizes gerais apenas. Esses cronogramas não constituem os Contratos de nível de serviço (slas) ou os compromissos relacionados à entrega de dados. A Adobe reserva o direito de alterar os intervalos de tempo e horários a qualquer momento sem aviso prévio.
seo-title: Como a entrega de dados e os tempos de processamento de arquivos afetam os relatórios
solution: Audience Manager
title: Como a entrega de dados e os tempos de processamento de arquivos afetam os relatórios
uuid: 4 b 975512-f 67 e -4749-a 7 ef -168415597682
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# How Data Delivery and File Processing Times Affect Reports{#how-data-delivery-and-file-processing-times-affect-reports}

O Audience Manager recebe uma grande quantidade de dados todos os dias. Isso afeta o tempo necessário para processar seus dados e gerar resultados de relatório. O conteúdo nesta seção descreve como esses intervalos de tempo afetam sua conta do Audience Manager. Além disso, os intervalos de tempo e agendamentos descritos aqui são diretrizes gerais apenas. Esses cronogramas não constituem os Contratos de nível de serviço (slas) ou os compromissos relacionados à entrega de dados. A Adobe reserva o direito de alterar os intervalos de tempo e horários a qualquer momento sem aviso prévio.

## Reporting Numbers {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

A tabela a seguir lista e descreve os intervalos de tempo em nossos relatórios gerais e em tempo real.

<table id="table_73AF95DF5D3A423894486444505D816A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de dados </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Dados em tempo real</b> </p> </td> 
   <td colname="col2"> <p> Os números em tempo real para hoje são horas de 00:00 a 23:59:59 UTC a partir de ontem. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Dados gerais de relatório</b> </p> </td> 
   <td colname="col2"> <p>The data in the <a href="../reporting/general-reports.md#general-reports-overview"> General Reports</a> depends on the successful completion of other job processes and the amount of data received for a particular day. Most of the time, <span class="wintitle"> General Report</span> data should be updated by 18:00 UTC each day. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Inbound and Outbound File Transfers {#inbound-outbound-file-transfers}

[!DNL Audience Manager] processa e envia transferências [!UICONTROL Server-to-Server (S2S)] de arquivos de entrada e saída de acordo com os cronogramas descritos nesta seção. Considerando esses horários e os tempos de corte, você pode ver discrepâncias com novos segmentos entre os números de segmentos em tempo real e total.

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de arquivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Ingestão de arquivo de entrada (dados offline)</b> </p> </td> 
   <td colname="col2"> <p>O processamento de arquivos é executado duas vezes por dia. Esses procedimentos assimilam dados e o preparam para entrega. </p> <p>Os tempos de entrega do arquivo variam porque são afetados pela quantidade total de dados do cliente que precisam ser processados. You should expect a maximum latency of 48 hours between the moment the file is uploaded in <span class="keyword"> Audience Manager</span> and until the data is available for reporting and activation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Arquivos de saída (Exportar)</b> </p> </td> 
   <td colname="col2"> <p>O processamento e a entrega de arquivos ocorre uma vez por dia, aproximadamente 14:00 UTC. Lembre-se de que o processamento e a entrega são afetados pelo número total e tamanho desses arquivos. Em alguns casos, pode haver um atraso no processamento de arquivos por até 24 horas. When this happens, <span class="keyword"> Audience Manager</span> will send 2 files for a particular day instead of 1. We will notify our customers in the rare case where <span class="keyword"> Audience Manager</span> has to stop processing a file altogether. Considerando essas condições, é difícil estimar o tempo de entrega para dados de saída. </p> <p>Para determinar se você recebeu um conjunto completo de arquivos, verifique o carimbo de data e hora e procure por qualquer dia ausente. Esse é um carimbo de data e hora de 13 dígitos UNIX UTC que registra o horário em que o arquivo foi criado. See <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> Real-Time Outbound Data Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Perguntas frequentes sobre ingestão de dados do cliente](../faq/faq-inbound-data-ingestion.md)

