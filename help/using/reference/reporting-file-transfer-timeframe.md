---
description: Audience Manager recebe uma quantidade enorme de dados todos os dias. Isso afeta o tempo necessário para processar seus dados e gerar resultados do relatório. O conteúdo desta seção descreve como esses intervalos de tempo afetam sua conta de Audience Manager. Além disso, os intervalos de tempo e os agendamentos descritos aqui são apenas diretrizes gerais. Esses agendamentos não constituem SLAs (Service-Level Agreements, contratos de nível de serviço) ou compromissos relacionados ao delivery de dados. O Adobe reserva-se o direito de alterar os intervalos de tempo e as programações a qualquer momento, sem aviso prévio.
seo-description: Audience Manager recebe uma quantidade enorme de dados todos os dias. Isso afeta o tempo necessário para processar seus dados e gerar resultados do relatório. O conteúdo desta seção descreve como esses intervalos de tempo afetam sua conta de Audience Manager. Além disso, os intervalos de tempo e os agendamentos descritos aqui são apenas diretrizes gerais. Esses agendamentos não constituem SLAs (Service-Level Agreements, contratos de nível de serviço) ou compromissos relacionados ao delivery de dados. O Adobe reserva-se o direito de alterar os intervalos de tempo e as programações a qualquer momento, sem aviso prévio.
seo-title: Como o delivery de dados e os tempos de processamento de arquivos afetam os relatórios
solution: Audience Manager
title: Como o delivery de dados e os tempos de processamento de arquivos afetam os relatórios
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 5%

---


# Como o delivery de dados e os tempos de processamento de arquivos afetam os relatórios{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager recebe uma quantidade enorme de dados todos os dias. Isso afeta o tempo necessário para processar seus dados e gerar resultados do relatório. O conteúdo desta seção descreve como esses intervalos de tempo afetam sua conta de Audience Manager. Além disso, os intervalos de tempo e os agendamentos descritos aqui são apenas diretrizes gerais. Esses agendamentos não constituem SLAs (Service-Level Agreements, contratos de nível de serviço) ou compromissos relacionados ao delivery de dados. O Adobe reserva-se o direito de alterar os intervalos de tempo e as programações a qualquer momento, sem aviso prévio.

## Números de relatórios {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

A tabela a seguir lista e descreve os intervalos de tempo em nossos relatórios gerais e em tempo real.


| Tipo de dados | Descrição |
|---|---|
| Dados em tempo real | Os números em tempo real para hoje são para as horas das 00:00 às 23:59:59 UTC de ontem. |
| Dados gerais do relatório | Os dados nos [Relatórios Gerais](../reporting/general-reports.md#general-reports-overview) dependem da conclusão com êxito de outros processos de trabalho e da quantidade de dados recebidos para um dia específico. Na maioria das vezes, os dados de [!UICONTROL General Report] devem ser atualizados às 18:00 UTC por dia. |

## Transferências de arquivos de entrada e saída {#inbound-outbound-file-transfers}

[!DNL Audience Manager] processa e envia transferências de  [!UICONTROL Server-to-Server (S2S)] arquivos de entrada e de saída de acordo com as programações descritas nesta seção. Dadas essas programações e os tempos de interrupção, você pode observar discrepâncias com novos segmentos entre os números de segmentos em tempo real e total.

| Tipo de arquivo | Descrição |
|---|---|
| Ingestão de Arquivo de Entrada (dados offline) | O processamento de arquivos é executado duas vezes por dia. Esses procedimentos assimilam dados e os preparam para o delivery. Os tempos de delivery de arquivos variam porque são afetados pela quantidade total de dados do cliente que precisam ser processados. Você deve esperar uma latência máxima de 48 horas entre o momento em que o arquivo é carregado no Audience Manager e até que os dados estejam disponíveis para relatórios e ativação. |
| Arquivos de saída (Exportar) | O processamento e o delivery de arquivos ocorrem uma vez por dia, aproximadamente às 14:00 UTC. Lembre-se de que o processamento e o delivery são afetados pelo número e tamanho totais desses arquivos. Em alguns casos, pode haver um atraso no processamento de arquivos por até 24 horas. Quando isso acontecer, o Audience Manager enviará 2 arquivos para um dia específico em vez de 1. Notificaremos nossos clientes em casos raros, em que a Audience Manager deve parar de processar um arquivo. Dadas estas condições, é difícil estimar os tempos de delivery para dados de saída. Para determinar se você recebeu um conjunto completo de arquivos, verifique o carimbo de data e hora e procure os dias que estiverem faltando. Este é um carimbo de data e hora UNIX UTC de 13 dígitos que registra a hora em que o arquivo foi criado. Consulte [Transferências de Dados de Saída em Tempo Real](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md). |
| Arquivos de log do servidor de publicidade | O processamento de arquivos é executado em tempo quase real para assimilar registros de arquivos de log, já que os arquivos por hora estão prontos. O processo para preparar os arquivos para o relatórios é executado uma vez por dia. Os tempos de delivery de arquivos variam porque são afetados pela quantidade total de dados do cliente que precisam ser processados. Você deve esperar uma latência máxima de 48 horas entre o momento em que você carrega o arquivo no Audience Manager e o momento em que os dados estão disponíveis para relatórios e ativação. |

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre assimilação de dados de entrada do cliente](../faq/faq-inbound-data-ingestion.md)

