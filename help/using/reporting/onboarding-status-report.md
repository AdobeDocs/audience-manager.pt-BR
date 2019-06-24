---
description: O Relatório de status onboard verifica as taxas de sucesso e falha para processar registros nos arquivos de origem de dados de entrada. Este relatório exibe os dados em um gráfico de barras interativo e fornece métricas de resumo em forma tabular. Além disso, ele inclui a opção de arquivos de amostra para um intervalo de tempo fixo e exibe os erros mais comuns para cada tipo de erro. Você pode encontrar este relatório em Analytics > Relatório de status onboard. Este relatório também está disponível quando uma fonte de dados é criada.
seo-description: O Relatório de status onboard verifica as taxas de sucesso e falha para processar registros nos arquivos de origem de dados de entrada. Este relatório exibe os dados em um gráfico de barras interativo e fornece métricas de resumo em forma tabular. Além disso, ele inclui a opção de arquivos de amostra para um intervalo de tempo fixo e exibe os erros mais comuns para cada tipo de erro. Você pode encontrar este relatório em Analytics > Relatório de status onboard. Este relatório também está disponível quando uma fonte de dados é criada.
seo-title: Relatório de status onboard sobre
solution: Audience Manager
title: Relatório de status onboard sobre
uuid: 6 ca 8 a 90 a -436 b -4 fce-adf 1-48 f 3 b 96 b 3 ed 2
translation-type: tm+mt
source-git-commit: dd5c3d28097251c58e1fb095aaf4076883d1c1a1

---


# Onboarding Status Report{#onboarding-status-report-about}

O Relatório de status onboard verifica as taxas de sucesso e falha para processar registros nos arquivos de origem de dados de entrada. Este relatório exibe os dados em um gráfico de barras interativo e fornece métricas de resumo em forma tabular. Além disso, ele inclui a opção de arquivos de amostra para um intervalo de tempo fixo e exibe os erros mais comuns para cada tipo de erro. Você pode encontrar este relatório em Analytics &gt; Relatório de status onboard. Este relatório também está disponível quando uma fonte de dados é criada.

>[!NOTE]
>
>Somente usuários com privilégios de administrador podem ver este relatório na interface do usuário do Audience Manager. Os usuários não administradores podem receber notificações sobre o status dos arquivos de entrada enviados ao adicionar seus emails ao relatório. See [Receive E-mail Notifications](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## Onboarding Status Report: About {#onboarding-status-about}

The [!UICONTROL Onboarding Status Report] checks success and failure rates for processing records in your inbound data source files. Este relatório exibe os dados em um gráfico de barras interativo e fornece métricas de resumo em forma tabular. Além disso, ele inclui a opção de arquivos de amostra para um intervalo de tempo fixo e exibe os erros mais comuns para cada tipo de erro. You can find this report in **[!UICONTROL Analytics > Onboarding Status Report]**. Este relatório também está disponível quando uma fonte de dados é criada.

## Error Reporting and Error Sampling {#error-reporting-sampling}

Error reporting and error sampling are 2 separate features of the [!UICONTROL Onboarding Status] report.

<table id="table_4706D891D4C545E8BF9D8A0CC052CC48"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recurso </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Relatório de erros</b> </p> </td>
   <td colname="col2"> <p>O relatório de erros mostra as taxas de sucesso e de falha para o número de registros processados em uma fonte de dados de entrada. Retorna dados em um gráfico de barras interativo e empilhado e como métricas de resumo em tabelas abaixo do gráfico. </p> <p>O relatório de erros é automático. Ele é executado continuamente para todas as suas fontes de dados de entrada. Retorna dados com base no intervalo de intervalos de tempo predefinidos ou um intervalo de tempo personalizado definido com um widget de calendário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Amostra de erro</b> </p> </td>
   <td colname="col2"> <p>A amostragem de erros analisa o conteúdo de seus arquivos de dados e retorna os 10 erros mais comuns para cada tipo de erro. Os erros nos arquivos de dados de entrada impedem que registros individuais sejam processados. Use esse relatório como uma ferramenta de solução de problemas para ajudar a reduzir o número de erros de arquivo e melhorar as taxas de processamento. </p> <p>Você deve ativar a amostragem de erros manualmente. Ele é executado por 14 dias a partir do dia da ativação e desativado. É possível ativar a amostragem de erro novamente após o intervalo de 14 dias expirar. You activate error sampling when you <a href="../features/manage-datasources.md#create-data-source"> create an inbound data source</a> or by checking the <b><span class="uicontrol"> Error Sampling</span></b> check box from the <span class="wintitle"> Data Source Settings</span> section of an existing inbound data source. </p> <p>A amostragem de erros é um processo computacional exigente. Como resultado, retorna apenas os primeiros 10 erros para cada categoria de erro. Não é projetado para retornar cada erro contido em uma fonte de dados de entrada. Esses erros são uma amostra representativa de um grupo potencialmente maior de erros semelhantes. Analise todo o arquivo para os tipos de erros que esse relatório sinaliza, reformate o arquivo e envie-o novamente. </p> <p>See <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a> for more information about how to properly format an data file for an inbound data source. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Error Report Bar Chart {#error-report-bar-chart}

O relatório de erro apresenta as taxas de sucesso e falha para o processamento de registro em um gráfico de barras empilhadas, como mostrado no exemplo a seguir. O gráfico é interativo. Clicar em uma barra mostra as métricas de resumo desse dia em uma tabela abaixo do gráfico.

![](assets/stacked-graph.png)

## Error Report Tables {#error-report-tables}

O relatório de erro exibe dados tabulares abaixo do gráfico de barras. A tabela mostra taxas de sucesso e falha juntamente com totais e porcentagens.

**Registros com êxito e com falha**

Essa exibição padrão mostra uma contagem de frequência do total de registros em seu relatório e inclui uma análise dos erros por tipo de erro.

![](assets/success-failure.png)

**Totais e porcentagens**

Click **[!UICONTROL Totals & Percentages]** to see what % of your files were processed successfully.

![](assets/totals-percentages.png)

## Error Sampling Report for 14 Days {#error-reporting-14-days}

Com a amostragem de erro ativa, o relatório mostrará os 10 erros principais para cada tipo de erro. Clique em um botão de tipo de erro na parte superior do relatório para ver cada conjunto de dados de amostra.

>[!NOTE]
>
>O relatório não realça erros de registro nesta versão atual. To find and fix file errors, you should review the results and compare those to the specifications in the [Inbound Data File Contents](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) documentation.

![](assets/error-samples.png)

## Receive E-mail Notifications {#receive-email-notifications}

Você pode adicionar os endereços de email dos destinatários que deseja receber notificações sobre o status dos arquivos de entrada enviados. Observe que é possível selecionar destinatários diferentes para fontes de dados diferentes.

![](assets/mail-notifications.png)

## Create an Onboarding Status Report {#create-onboard-status-report}

A [!UICONTROL Sample Error Report] returns the number records in a data source were processed successfully and how many failed. Follow these steps to generate a [!UICONTROL Sample Error Report].

<!-- 

create-onboarding-status-report.xml

 -->


1. Go to **[!UICONTROL Analytics > Onboarding Status Report]**. Procure por uma fonte de dados ou escolha uma da lista.

2. Selecione um intervalo de datas. As opções incluem:

   * Um conjunto de intervalos de relatório fixos.
   * Widgets de calendário que permitem criar um intervalo de datas personalizado.

3. Clique em **[!UICONTROL OK]**.

## Onboarding Status Report Terms and Definitions {#report-terms-conditions}

Um guia de referência para os rótulos e termos usados neste relatório.

<table id="table_1D44A2E6B4C847848B818190DD336841"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Termo </th> 
   <th colname="col2" class="entry"> Definição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Nome do arquivo de sincronização de dados</b> </p> </td> 
   <td colname="col2"> <p>Lists files that <span class="keyword"> Audience Manager</span> received and processed from you selected inbound data source. </p> <p>O processamento de arquivos falhará se o nome do arquivo estiver formatado incorretamente. File name requirements vary depending on how you send this data to <span class="keyword"> Audience Manager</span>. Delivery methods include <span class="keyword"> Amazon S3</span> and FTP. Para obter instruções sobre como nomear seus arquivos, consulte: </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> Requisitos de nome Amazon S3 para arquivos de dados de entrada </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Erros de formato</b> </p> </td> 
   <td colname="col2"> <p>Lista o número de registros que falharam no processamento porque não correspondiam aos requisitos de sintaxe ou de formatação. See <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a> for information on how to format your data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>ID inválida do AAM</b> </p> </td> 
   <td colname="col2"> <p>Lists the number of improperly formatted <span class="keyword"> Audience Manager</span> user IDs (UUID). Geralmente, isso indica as IDs: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">Não correspondeu ao formato de 38 dígitos esperado. </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">Contiver caracteres alfabéticos. As IDs devem ser apenas números. </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>ID de dispositivo inválida</b> </p> </td> 
   <td colname="col2"> <p>Lista o número de IDs de dispositivo global formatadas incorretamente. See <a href="../reference/ids-in-aam.md">Index of IDs in Audience Manager</a> and <a href="../features/global-data-sources.md">Global Data Sources</a>  for details on how device IDs should be formatted and what global data sources you should use, based on the device type.</p>
  <p>A seção de amostragem de erro do relatório inclui informações detalhadas sobre as IDs de dispositivo inválidas, como:</p>
   <ul>
    <li>A ID da fonte de dados correspondente à ID do dispositivo inválida;</li>
    <li>A ID do dispositivo inválida;</li>
    <li>O tipo de ID do dispositivo esperado, com base na fonte de dados.</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>Nenhuma ID AAM correspondente</b> </p> </td> 
   <td colname="col2"> <p>These are onboarded IDs <span class="keyword"> Audience Manager</span> cannot match to an existing ID. Onboarded IDs can have this status when <span class="keyword"> Audience Manager</span> has not yet performed an ID sync or it still can't match the ID even after a synch. </p> <p>In the case of unmatched mobile IDs, <span class="keyword"> Audience Manager</span> will: </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">Continue a armazenar e tente sincronizar essa ID. </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Record it as a <span class="wintitle"> Stored Record</span> in the report if the ID cannot be synched. </li> 
    </ul> <p>Se o arquivo incorporado contiver IDs móveis, você pode tratar esses números de forma mais leve do que as outras métricas. Elas não afetarão as taxas de sucesso e de correspondência dos arquivos subsequentes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Sem realização de características</b> </p> </td> 
   <td colname="col2"> <p>Lists traits that <span class="keyword"> Audience Manager</span> cannot match to an onboarded trait. Isso pode ser o resultado de: </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">Características formatadas incorretamente no arquivo de dados de entrada. For on how to format your data file, see <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Traits that have not yet been defined in <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Sucesso percentual</b> </p> </td> 
   <td colname="col2"> <p>A porcentagem de registros no arquivo que foram armazenados com sucesso. Sucesso de porcentagem = registros processados/número de registros em um arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Registros recebidos</b> </p> </td> 
   <td colname="col2"> <p>O número total de registros recebidos. Na maioria dos casos, esse número deve corresponder ao número total de registros (linhas) no arquivo de dados de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Registros armazenados</b> </p> </td> 
   <td colname="col2"> <p>Número de registros armazenados com sucesso. Because of file format errors, some of the records received may not be stored by <span class="keyword"> Audience Manager</span>. O número de registros armazenados pode ser menor que o número de registros recebidos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Características totais de realização</b> </p> </td> 
   <td colname="col2"> <p>The number of traits for all users across all inbound files that get stored in the <span class="keyword"> Audience Manager</span> platform. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Total de sinais não usados</b> </p> </td> 
   <td colname="col2"> <p>O número total de sinais não usados recebidos no relatório. Esse total se baseia no número total de registros armazenados com sucesso. </p> <p>See <a href="../reporting/dynamic-reports/unused-signals.md"> Unused Signals Report</a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>
