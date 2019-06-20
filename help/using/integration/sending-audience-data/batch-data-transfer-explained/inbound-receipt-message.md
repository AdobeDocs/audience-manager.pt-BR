---
description: Sempre que um arquivo de servidor para servidor é processado, um recibo é enviado por email para soluções de parceiros e, se configurado, para o parceiro.
seo-description: Sempre que um arquivo de servidor para servidor é processado, um recibo é enviado por email para soluções de parceiros e, se configurado, para o parceiro.
seo-title: Amostra de mensagem para parceiros após o processamento de entrada
solution: Audience Manager
title: Amostra de mensagem para parceiros após o processamento de entrada
uuid: 69 e 3 a 8 b 3-8465-4 f 4 c -8005-8 a 9 ff 15 ae 19 a
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Sample Message to Partners after Inbound Processing{#sample-message-to-partners-after-inbound-processing}

Whenever an inbound [!UICONTROL Server-to-Server] file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner.

<!-- r_inbound_message.xml -->

O exemplo a seguir é uma amostra de mensagem de e-mail. A tabela abaixo da mensagem descreve as várias linhas na mensagem.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>De: aam-noreply@adobe.com </b> </p> <p> <b>Assunto: Resultado do processamento do Adobe Audience Manager Server-To-Server:</b> </p> <p> <b>Prezado Adobe Partner: (ID: 7)</b><b></b> </p> <p> <b>Recebemos a entrega de arquivos do Adobe Audience Manager Server Server Server</b> </p> <p> <b>Nome do arquivo:</b><i></i> </p> <p> <b> s 3 n:// &lt;<i>nome_ do_ bucket &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806402. sync</b> </p> <p> <b> s 3 n:// &lt;<i>nome_ do_ bucket &gt;</i>/2018-05-16/ftp_ dpm_ 7_ 901_ 1368655202. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nome_ do_ bucket &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784804. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nome_ do_ bucket &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806403. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nome_ do_ bucket &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784802. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nome_ do_ bucket &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784803. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nome_ do_ bucket &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806404. sync</b> </p> <p> <b>Registros recebidos: 40669900</b> </p> <p><b>Erros de formato: 0</b> </p> <p> <b>ID AAM inválida: 112 </b> </p> <p> <b>Nenhuma ID AAM correspondente: 0 </b> </p> <p> <b>Nenhuma característica realizada: 26730823 </b> </p> <p> <b>Registros processados: 40669900 </b> </p> <p> <b>Registros armazenados: 13938958 </b> </p> <p> <b>Total de dispositivos: 21 </b> </p> <p> <b>Total de sinais: 918878926 </b> </p> <p> <b>Total de sinais não usados: 660348376 </b> </p> <p> <b>Características totais de conclusão: 258086908 </b> </p> <p> <b>Total de características removidas: 0 </b> </p> <p> <b>Falha na validação do total de características: 0 </b> </p> <p> <b>Total de usuários com características que falharam na validação: 0 </b> </p> <p> <b>Hora de início do trabalho: 2018-05-17 18:07:49 </b> </p> <p> <b>Hora de término do trabalho: 2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

A tabela a seguir contém linhas correspondendo a linhas na mensagem de email recebida.

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
   <td colname="col2"> <p>Lista de todos os arquivos de entrada recebidos pela Adobe para este parceiro que foram processados juntos. Na mensagem de email de amostra anterior, a ID do parceiro é 7 e a ID do proprietário de dados é 901. </p> <p>O número de cauda (1,2,3…) é o número dividido pelo cliente ou pelo distribuidor de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros recebidos </td> 
   <td colname="col2"> <p>O número total de registros recebidos pela Adobe em todos os arquivos. Na maioria dos casos, esse deve ser o número total de linhas em arquivos de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erros de formato </td> 
   <td colname="col2"> <p>Número de linhas que não correspondiam ao formato esperado. Essas linhas não eram reconhecíveis pelo trabalho de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID inválida do AAM </td> 
   <td colname="col2"> <p>Número de uuids do Audience Manager que não correspondiam ao formato de 38 dígitos esperado. Ou os uuids do Audience Manager enviados no arquivo não são números. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nenhuma ID AAM correspondente </td> 
   <td colname="col2"> <p>O número total de usuários para os quais o Audience Manager não localiza um UUID correspondente. Esses arquivos não foram sincronizados por ID, portanto o Audience Manager não pode procurar o UUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sem realização de características </td> 
   <td colname="col2"> <p>Número de registros em que nenhum dos sinais na linha é mapeado para uma característica do Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros processados </td> 
   <td colname="col2"> <p>O número total de registros processados pelo Audience Manager. Na maioria dos casos, esse número deve ser o mesmo que "Registros recebidos". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros armazenados </td> 
   <td colname="col2"> <p>Número de registros que resultava em carregamento de dados no sistema = Registros processados - Erros de formato - IDs AAM inválidas - Sem ID AAM correspondente - Sem realização de características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de dispositivos </td> 
   <td colname="col2"> <p>Número de dispositivos para os quais os dados foram carregados no sistema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de sinais </td> 
   <td colname="col2"> <p> O número total de sinais para todos os usuários em todos os arquivos de entrada (número total de pares chave/valor nos registros processados). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de sinais não usados </td> 
   <td colname="col2"> <p>O número total de sinal não usado para todos os usuários em todos os arquivos de entrada (pares chave/valor que não foram mapeados para as características do Audience Manager). Na maioria dos casos, isso significa que o Audience Manager não possui regras definidas para o sinal. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Características totais de realização </td> 
   <td colname="col2"> <p>Número de características do Audience Manager para todos os usuários em todos os arquivos de entrada com base nos sinais. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de características removidas </td> 
   <td colname="col2"> <p> O número total de características removidas para todos os usuários em todos os arquivos de entrada. Para sincronizações completas, isso acontece se o usuário tiver a característica em uma execução anterior, mas não na execução atual. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Falha na validação de características totais </td> 
   <td colname="col2"> <p>Representa o número de características que não pertencem à fonte de dados declarada no nome do arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de usuários com características que falharam na validação </td> 
   <td colname="col2"> <p>O número de registros que tiveram características que falharam na validação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de início do trabalho </td> 
   <td colname="col2"> <p>A hora em que o serviço de entrada é iniciado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de término do trabalho </td> 
   <td colname="col2"> <p>A hora em que o serviço de entrada é encerrado. </p> </td> 
  </tr> 
 </tbody> 
</table>