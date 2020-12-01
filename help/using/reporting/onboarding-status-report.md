---
description: O Relatório de status onboard verifica as taxas de sucesso e de falha para o processamento de registros nos arquivos de fonte de dados de entrada. Este relatório exibe dados em um gráfico de barras interativo e fornece métricas de resumo em forma tabular. Além disso, ele inclui a opção de arquivos de amostra para um intervalo de tempo fixo e exibe os erros mais comuns para cada tipo de erro. Esse relatório pode ser encontrado no Analytics > Relatório de status onboard. Este relatório também está disponível ao criar uma fonte de dados de entrada.
seo-description: O Relatório de status onboard verifica as taxas de sucesso e de falha para o processamento de registros nos arquivos de fonte de dados de entrada. Este relatório exibe dados em um gráfico de barras interativo e fornece métricas de resumo em forma tabular. Além disso, ele inclui a opção de arquivos de amostra para um intervalo de tempo fixo e exibe os erros mais comuns para cada tipo de erro. Esse relatório pode ser encontrado no Analytics > Relatório de status onboard. Este relatório também está disponível ao criar uma fonte de dados de entrada.
seo-title: Relatório de status de integração
solution: Audience Manager
title: Relatório de status de integração
uuid: 6ca8a90a-436b-4fce-adf1-48f3b96b3ed2
feature: inbound and outbound reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '1498'
ht-degree: 7%

---


# Relatório de status de integração{#onboarding-status-report-about}

O Relatório de status onboard verifica as taxas de sucesso e de falha para o processamento de registros nos arquivos de fonte de dados de entrada. Este relatório exibe dados em um gráfico de barras interativo e fornece métricas de resumo em forma tabular. Além disso, ele inclui a opção de arquivos de amostra para um intervalo de tempo fixo e exibe os erros mais comuns para cada tipo de erro. Esse relatório pode ser encontrado no Analytics > Relatório de status onboard. Este relatório também está disponível ao criar uma fonte de dados de entrada.

>[!NOTE]
>
>Somente os usuários com privilégios de Administrador podem ver esse relatório na interface do usuário do Audience Manager. Você pode fazer com que usuários não administradores sejam notificados do status dos arquivos de entrada carregados adicionando seus e-mails ao relatório. Consulte [Receber notificações por e-mail](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## Relatório de status onboard: Sobre {#onboarding-status-about}

O [!UICONTROL Onboarding Status Report] verifica as taxas de sucesso e falha para o processamento de registros nos arquivos de fonte de dados de entrada. Este relatório exibe dados em um gráfico de barras interativo e fornece métricas de resumo em forma tabular. Além disso, ele inclui a opção de arquivos de amostra para um intervalo de tempo fixo e exibe os erros mais comuns para cada tipo de erro. Você pode encontrar este relatório em **[!UICONTROL Analytics > Onboarding Status Report]**. Este relatório também está disponível ao criar uma fonte de dados de entrada.

## Relatórios de erro e amostragem de erro {#error-reporting-sampling}

Relatórios de erros e amostragem de erros são dois recursos separados do relatório [!UICONTROL Onboarding Status].

<table id="table_4706D891D4C545E8BF9D8A0CC052CC48"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recurso </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Relatórios de erro</b> </p> </td>
   <td colname="col2"> <p>O relatórios de erro mostra as taxas de sucesso e falha do número de registros processados em uma fonte de dados de entrada. Ele retorna dados em um gráfico de barras empilhadas interativo e como métricas de resumo em tabelas abaixo do gráfico. </p> <p>O relatórios de erro é automático. Ele é executado continuamente para todas as suas fontes de dados de entrada. Ele retorna dados com base no intervalo de intervalos de tempo predefinidos ou em um intervalo de tempo personalizado definido com um widget de calendário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Amostragem de erro</b> </p> </td>
   <td colname="col2"> <p>A amostragem de erros analisa o conteúdo de seus arquivos de dados e retorna os 10 erros mais comuns para cada tipo de erro. Os erros nos arquivos de dados de entrada impedem que registros individuais sejam processados. Use este relatório como uma ferramenta de solução de problemas para ajudar a reduzir o número de erros de arquivo e melhorar as taxas de processamento. </p> <p>Você deve ativar a amostragem de erros manualmente. Ela funciona por 14 dias a partir do dia da ativação e então se desliga. Você pode ativar novamente a amostragem de erros depois que o intervalo de 14 dias expirar. Você ativa a amostragem de erros quando <a href="../features/manage-datasources.md#create-data-source"> cria uma fonte de dados de entrada</a> ou marcando a caixa de seleção <b><span class="uicontrol"> Amostragem de erros</span></b> na seção <span class="wintitle"> Configurações da fonte de dados</span> de uma fonte de dados de entrada existente. </p> <p>A amostragem de erros é um processo que exige cálculos. Como resultado, retorna somente os primeiros 10 erros para cada categoria de erro. Ele não foi projetado para retornar todos os erros contidos em uma fonte de dados de entrada. Esses erros são uma amostra representativa de um grupo potencialmente maior de erros similares. Revise o arquivo inteiro para ver os tipos de erros que este relatório sinaliza, reformate o arquivo e envie-o novamente. </p> <p>Consulte <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Conteúdo do arquivo de dados de entrada: Sintaxe, variáveis e exemplos</a> para obter mais informações sobre como formatar corretamente um arquivo de dados para uma fonte de dados de entrada. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Gráfico de Barras de Relatório de Erro {#error-report-bar-chart}

O relatório de erros mapeia as taxas de sucesso e de falha do processamento de registros em um gráfico de barras empilhadas, como mostrado no exemplo a seguir. O gráfico é interativo. Clicar em uma barra mostra as métricas de resumo do dia em uma tabela abaixo do gráfico.

![](assets/stacked-graph.png)

## Tabelas de Relatório de Erro {#error-report-tables}

O relatório de erros exibe dados tabulares abaixo do gráfico de barras. A tabela mostra as taxas de sucesso e de falha, juntamente com os totais e as porcentagens.

**Registros com êxito e com falha**

Esta visualização padrão mostra uma contagem de frequência do total de registros em seu relatório e inclui uma análise dos erros por tipo de erro.

![](assets/success-failure.png)

**Totais e porcentagens**

Clique em **[!UICONTROL Totals & Percentages]** para ver qual % dos seus arquivos foram processados com êxito.

![](assets/totals-percentages.png)

## Relatório de amostragem de erros por 14 dias {#error-reporting-14-days}

Com a amostragem de erros ativa, o relatório mostrará os 10 erros principais para cada tipo de erro. Clique em um botão de tipo de erro na parte superior do relatório para ver cada conjunto de dados de amostra.

>[!NOTE]
>
>O relatório não destaca erros de registro nesta versão atual. Para localizar e corrigir erros de arquivo, você deve revisar os resultados e compará-los às especificações da documentação [Conteúdo do arquivo de dados de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

![](assets/error-samples.png)

## Receber notificações por e-mail {#receive-email-notifications}

Você pode adicionar os endereços de email dos recipient que deseja que sejam notificados sobre o status dos arquivos de entrada carregados. Observe que é possível selecionar recipient diferentes para fontes de dados diferentes.

![](assets/mail-notifications.png)

## Criar um relatório de status onboard {#create-onboard-status-report}

Um [!UICONTROL Sample Error Report] retorna o número de registros em uma fonte de dados que foram processados com êxito e quantos falharam. Siga estas etapas para gerar um [!UICONTROL Sample Error Report].

<!-- 

create-onboarding-status-report.xml

 -->


1. Vá para **[!UICONTROL Analytics > Onboarding Status Report]**. Procure uma fonte de dados ou escolha uma da lista.

2. Selecione um intervalo de datas. As opções incluem:

   * Um conjunto de intervalos de relatório fixos.
   * Widgets de calendário que permitem criar um intervalo de datas personalizado.

3. Clique em **[!UICONTROL OK]**.

## Termos e definições do relatório de status onboard {#report-terms-conditions}

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
   <td colname="col2"> <p>Lista arquivos que <span class="keyword"> Audience Manager</span> receberam e processaram a partir da fonte de dados de entrada selecionada. </p> <p>O processamento do arquivo falhará se o nome do arquivo for formatado incorretamente. Os requisitos de nome de arquivo variam dependendo de como você envia esses dados para <span class="keyword"> Audience Manager</span>. Os métodos de delivery incluem <span class="keyword"> Amazon S3</span> e FTP. Para obter instruções sobre como nomear seus arquivos, consulte: </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> Requisitos de nome Amazon S3 para arquivos de dados de entrada </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Erros de formato</b> </p> </td> 
   <td colname="col2"> <p>Lista o número de registros que falharam no processamento porque não correspondem aos requisitos de sintaxe ou formatação. Consulte <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Conteúdo do arquivo de dados de entrada: Sintaxe, variáveis e exemplos</a> para obter informações sobre como formatar seus dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>ID de AAM inválida</b> </p> </td> 
   <td colname="col2"> <p>Lista o número de IDs de usuário (UUID) <span class="keyword"> Audience Manager</span> formatadas incorretamente. Normalmente, isso indica as IDs: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">Não correspondia ao formato de 38 dígitos esperado. </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">Contém caracteres alfabéticos. As IDs devem ser apenas números. </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>ID de dispositivo inválida</b> </p> </td> 
   <td colname="col2"> <p>Lista o número de IDs de dispositivo global formatadas incorretamente. Consulte <a href="../reference/ids-in-aam.md">Índice de IDs em Audience Manager</a> e <a href="../features/global-data-sources.md">Fontes de Dados Globais</a> para obter detalhes sobre como as IDs de dispositivos devem ser formatadas e quais fontes de dados globais você deve usar, com base no tipo de dispositivo.</p>
  <p>A seção de amostragem de erros do relatório inclui informações detalhadas sobre as IDs de dispositivo inválidas, como:</p>
   <ul>
    <li>A ID da fonte de dados correspondente à ID de dispositivo inválida;</li>
    <li>A ID de dispositivo inválida;</li>
    <li>O tipo de ID de dispositivo esperado, com base na fonte de dados.</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>Nenhuma ID de AAM correspondente</b> </p> </td> 
   <td colname="col2"> <p>Essas IDs integradas <span class="keyword"> Audience Manager</span> não podem corresponder a uma ID existente. As IDs integradas podem ter esse status quando <span class="keyword"> Audience Manager</span> ainda não executaram uma sincronização de ID ou ainda não podem corresponder à ID mesmo depois de uma sincronização. </p> <p>No caso de IDs móveis não correspondentes, <span class="keyword"> Audience Manager</span> irá: </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">Continue a armazenar e tente sincronizar esta ID. </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Registre-o como <span class="wintitle"> Registro armazenado</span> no relatório se a ID não puder ser sincronizada. </li> 
    </ul> <p>Se o arquivo integrado contiver IDs móveis, você poderá tratar esses números com um pouco mais de leveza do que as outras métricas. Elas não afetarão as taxas de sucesso e de correspondência dos arquivos subsequentes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Nenhuma característica realizada</b> </p> </td> 
   <td colname="col2"> <p>Características do Lista que <span class="keyword"> Audience Manager</span> não podem corresponder a uma característica integrada. Isso pode resultar de: </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">Características formatadas incorretamente no arquivo de dados de entrada. Para saber como formatar o arquivo de dados, consulte <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Conteúdo do arquivo de dados de entrada: Sintaxe, variáveis e exemplos</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Características que ainda não foram definidas em <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Porcentagem de sucesso</b> </p> </td> 
   <td colname="col2"> <p>A porcentagem de registros no arquivo que foram armazenados com êxito. Porcentagem de sucesso = registros processados / número de registros em um arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Registros recebidos</b> </p> </td> 
   <td colname="col2"> <p>O número total de registros recebidos. Na maioria dos casos, esse número deve corresponder ao número total de registros (linhas) no arquivo de dados de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Registros armazenados</b> </p> </td> 
   <td colname="col2"> <p>Número de registros armazenados com êxito. Devido a erros de formato de arquivo, alguns dos registros recebidos podem não ser armazenados por <span class="keyword"> Audience Manager</span>. O número de registros armazenados pode ser inferior ao número de registros recebidos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Características Realizadas Totais</b> </p> </td> 
   <td colname="col2"> <p>O número de características de todos os usuários em todos os arquivos de entrada armazenados na plataforma <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Total de Sinais Não Utilizados</b> </p> </td> 
   <td colname="col2"> <p>Número total de sinais não utilizados recebidos no relatório. Esse total se baseia no número total de registros armazenados com êxito. </p> <p>Consulte <a href="../reporting/dynamic-reports/unused-signals.md"> Relatório de sinais não utilizados</a> para obter mais informações. </p> </td> 
  </tr> 
 </tbody> 
</table>
