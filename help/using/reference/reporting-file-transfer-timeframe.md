---
description: O Audience Manager recebe uma enorme quantidade de dados todos os dias. Isso afeta o tempo necessário para processar seus dados e gerar resultados do relatório. O conteúdo desta seção descreve como esses intervalos afetam sua conta do Audience Manager. Além disso, os intervalos de tempo e os agendamentos descritos aqui são apenas diretrizes gerais. Esses agendamentos não constituem SLAs (Service-Level Agreements, contratos de nível de serviço) ou compromissos relacionados à entrega de dados. A Adobe reserva o direito de alterar os intervalos de tempo e as programações a qualquer momento, sem aviso prévio.
seo-description: O Audience Manager recebe uma enorme quantidade de dados todos os dias. Isso afeta o tempo necessário para processar seus dados e gerar resultados do relatório. O conteúdo desta seção descreve como esses intervalos afetam sua conta do Audience Manager. Além disso, os intervalos de tempo e os agendamentos descritos aqui são apenas diretrizes gerais. Esses agendamentos não constituem SLAs (Service-Level Agreements, contratos de nível de serviço) ou compromissos relacionados à entrega de dados. A Adobe reserva o direito de alterar os intervalos de tempo e as programações a qualquer momento, sem aviso prévio.
seo-title: Como a entrega de dados e os tempos de processamento de arquivos afetam os relatórios
solution: Audience Manager
title: Como a entrega de dados e os tempos de processamento de arquivos afetam os relatórios
uuid: 4b975512-f67e-4749-a7ef-168415597682
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Como a entrega de dados e os tempos de processamento de arquivos afetam os relatórios{#how-data-delivery-and-file-processing-times-affect-reports}

O Audience Manager recebe uma enorme quantidade de dados todos os dias. Isso afeta o tempo necessário para processar seus dados e gerar resultados do relatório. O conteúdo desta seção descreve como esses intervalos afetam sua conta do Audience Manager. Além disso, os intervalos de tempo e os agendamentos descritos aqui são apenas diretrizes gerais. Esses agendamentos não constituem SLAs (Service-Level Agreements, contratos de nível de serviço) ou compromissos relacionados à entrega de dados. A Adobe reserva o direito de alterar os intervalos de tempo e as programações a qualquer momento, sem aviso prévio.

## Números dos relatórios {#reporting-numbers}

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
   <td colname="col2"> <p> Os números em tempo real para hoje são para as horas das 00:00 às 23:59:59 UTC de ontem. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Dados gerais do relatório</b> </p> </td> 
   <td colname="col2"> <p>Os dados nos Relatórios <a href="../reporting/general-reports.md#general-reports-overview"></a> Gerais dependem da conclusão com êxito de outros processos de trabalho e da quantidade de dados recebidos por um dia específico. Na maioria das vezes, os dados do Relatório <span class="wintitle"></span> Geral devem ser atualizados às 18:00 UTC por dia. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Transferências de arquivos de entrada e saída {#inbound-outbound-file-transfers}

[!DNL Audience Manager] processa e envia transferências de arquivos de entrada e saída de acordo com as programações descritas nesta seção. [!UICONTROL Server-to-Server (S2S)] Dadas essas programações e os tempos de interrupção, você pode observar discrepâncias com novos segmentos entre os números de segmentos em tempo real e total.

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de arquivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Ingestão de Arquivo de Entrada (dados offline)</b> </p> </td> 
   <td colname="col2"> <p>O processamento de arquivos é executado duas vezes por dia. Esses procedimentos assimilam dados e os preparam para entrega. </p> <p>O tempo de entrega do arquivo varia porque é afetado pela quantidade total de dados do cliente que precisam ser processados. Você deve esperar uma latência máxima de 48 horas entre o momento em que o arquivo é carregado no <span class="keyword"> Audience Manager</span> e até que os dados estejam disponíveis para relatório e ativação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Arquivos de saída (exportação)</b> </p> </td> 
   <td colname="col2"> <p>O processamento e a entrega de arquivos ocorrem uma vez por dia, aproximadamente às 14:00 UTC. Lembre-se de que o processamento e a entrega são afetados pelo número e tamanho total desses arquivos. Em alguns casos, pode haver um atraso no processamento de arquivos por até 24 horas. Quando isso acontecer, <span class="keyword"> o Audience Manager</span> enviará 2 arquivos para um dia específico em vez de 1. Notificaremos nossos clientes em casos raros, nos quais o <span class="keyword"> Audience Manager</span> precisa parar de processar um arquivo. Dadas essas condições, é difícil estimar os tempos de entrega para dados de saída. </p> <p>Para determinar se você recebeu um conjunto completo de arquivos, verifique o carimbo de data e hora e procure os dias que estiverem faltando. Este é um carimbo de data e hora UNIX UTC de 13 dígitos que registra a hora em que o arquivo foi criado. Consulte Transferências <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"></a>de dados de saída em tempo real. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre ingestão de dados do cliente de entrada](../faq/faq-inbound-data-ingestion.md)

