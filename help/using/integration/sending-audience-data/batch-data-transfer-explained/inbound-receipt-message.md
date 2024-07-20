---
description: Sempre que um arquivo de entrada de servidor para servidor é processado, um recibo é enviado por email para soluções de parceiros e, se configurado, para o parceiro.
seo-description: Whenever an inbound Server-to-Server file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner.
seo-title: Sample Message to Partners after Inbound Processing
solution: Audience Manager
title: Mensagem de amostra para parceiros após o processamento de entrada
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: Inbound Data Transfers
exl-id: acfc788f-63e6-445f-a086-0a2cc6c8865b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 0%

---

# Mensagem de amostra para parceiros após o processamento de entrada{#sample-message-to-partners-after-inbound-processing}

Sempre que um arquivo de entrada [!UICONTROL Server-to-Server] é processado, um recibo é enviado por email para soluções de parceiros e, se configurado, para o parceiro.

<!-- r_inbound_message.xml -->

O exemplo a seguir é um exemplo de mensagem de email. A tabela abaixo da mensagem descreve as várias linhas na mensagem.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>De: aam-noreply@adobe.com </b> </p> <p> <b>Assunto: Resultado Do Processamento De Servidor Para Servidor Do Adobe Audience Manager:</b> </p> <p> <b>Prezado Parceiro de Adobe: (ID:7)</b> <b></b> </p> <p> <b>Recebemos sua entrega de arquivos de Servidor para Servidor do Adobe Audience Manager</b> </p> <p> <b>Nome do arquivo:</b> <i></i> </p> <p> <b> s3n://&lt;<i>nome_do_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b> </p> <p> <b> s3n://&lt;<i>nome_do_bucket&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync </b> </p> <p> <b>s3n://&lt;<i>nome_do_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync </b> </p> <p> <b>s3n://&lt;<i>nome_do_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync </b> </p> <p> <b>s3n://&lt;<i>nome_do_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync </b> </p> <p> <b>s3n://&lt;<i>nome_do_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync </b> </p> <p> <b>s3n://&lt;<i>nome_do_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b> </p> <p> <b>Registros recebidos: 40669900</b> </p> <p><b>Erros de Formato: 0</b> </p> <p> <b>ID inválida do AAM: 112 </b> </p> <p> <b>Nenhuma identificação de AAM correspondente: 0 </b> </p> <p> <b>Nenhuma Característica Realizada: 26730823 </b> </p> <p> <b>Registros processados: 40669900 </b> </p> <p> <b>Registros Armazenados: 13938958 </b> </p> <p> <b>Total de dispositivos: 21 </b> </p> <p> <b>Total de sinais: 918878926 </b> </p> <p> <b>Total de sinais não utilizados: 660348376 </b> </p> <p> <b>Total de características realizadas: 258086908 </b> </p> <p> <b>Total de características removidas: 0 </b> </p> <p> <b>Total de características com falha na validação: 0 </b> </p> <p> <b>Total de usuários com características que falharam na validação: 0 </b> </p> <p> <b>Hora de início do trabalho: 17/05/2018 18:07:49 </b> </p> <p> <b>Hora de término do trabalho: 17/05/2018 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

A tabela a seguir contém linhas correspondentes às linhas na mensagem de email recebida.

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Linha </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome do arquivo </td> 
   <td colname="col2"> <p>Lista de todos os arquivos de entrada que o Adobe recebeu para este parceiro que foram processados juntos. Na mensagem de email de amostra anterior, a ID do parceiro é 7 e a ID do proprietário dos dados é 901. </p> <p>O tail number (1,2,3...) é o número de divisão adicionado pelo cliente ou pelo distribuidor de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros recebidos </td> 
   <td colname="col2"> <p>Número total de Adobe de registros recebidos em todos os arquivos. Na maioria dos casos, esse deve ser o número total de linhas nos arquivos de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erros de formato </td> 
   <td colname="col2"> <p>Número de linhas que não correspondem ao formato esperado. Essas linhas não eram reconhecíveis pelo trabalho de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de AAM inválida </td> 
   <td colname="col2"> <p>Número de UUIDs de Audience Manager que não correspondem ao formato de 38 dígitos esperado. Ou os UUIDs de Audience Manager enviados no arquivo não são números. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nenhuma ID de AAM correspondente </td> 
   <td colname="col2"> <p>Número total de usuários para os quais o Audience Manager não conseguiu localizar um UUID correspondente. Esses arquivos não foram sincronizados com a ID, portanto, o Audience Manager não pode pesquisar a UUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nenhuma característica realizada </td> 
   <td colname="col2"> <p>Número de registros em que nenhum dos sinais na linha é mapeado para uma característica Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros processados </td> 
   <td colname="col2"> <p>Número total de Audience Manager de registros processados. Na maioria dos casos, esse número deve ser o mesmo que "Registros recebidos". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros armazenados </td> 
   <td colname="col2"> <p>Número de registros que resultaram nos dados a serem carregados no sistema = Registros Processados - Erros de Formato - IDs AAM inválidas - Nenhuma ID AAM correspondente - Nenhuma Característica Realizada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de dispositivos </td> 
   <td colname="col2"> <p>Número de dispositivos cujos dados foram carregados no sistema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de sinais </td> 
   <td colname="col2"> <p> Número total de sinais para todos os usuários em todos os arquivos de entrada (número total de pares de chave/valor nos registros processados). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de sinais não utilizados </td> 
   <td colname="col2"> <p>Número total de sinais não utilizados para todos os usuários em todos os arquivos de entrada (pares de chave/valor que não mapearam para características de Audience Manager). Na maioria dos casos, isso significa que o Audience Manager não tem regras definidas para o sinal. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de características realizadas </td> 
   <td colname="col2"> <p>Número de características de Audience Manager para todos os usuários em todos os arquivos de entrada com base nos sinais. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de características removidas </td> 
   <td colname="col2"> <p> Número total de características removidas de todos os usuários em todos os arquivos de entrada. Para sincronizações completas, isso acontece se o usuário tiver a característica em uma execução anterior, mas não na execução atual. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de características com falha na validação </td> 
   <td colname="col2"> <p>Representa o número de características que não pertencem à fonte de dados declarada no nome do arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de usuários com características que falharam na validação </td> 
   <td colname="col2"> <p>O número de registros com características que falharam na validação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de início do trabalho </td> 
   <td colname="col2"> <p>A hora em que o trabalho de entrada começa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de término do trabalho </td> 
   <td colname="col2"> <p>A hora em que o trabalho de entrada termina. </p> </td> 
  </tr> 
 </tbody> 
</table>
