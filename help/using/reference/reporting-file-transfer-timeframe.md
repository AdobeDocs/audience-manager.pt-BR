---
description: O Audience Manager recebe uma enorme quantidade de dados todos os dias. Isso afeta o tempo necessário para processar seus dados e gerar resultados de relatório. O conteúdo desta seção descreve como esses intervalos de tempo afetam sua conta Audience Manager. Além disso, os cronogramas e cronogramas descritos aqui são somente diretrizes gerais. Esses cronogramas não constituem Contratos de nível de serviço (SLAs) nem compromissos relacionados à entrega de dados. A Adobe reserva-se o direito de alterar os cronogramas e horários a qualquer momento sem aviso prévio.
seo-description: Audience Manager receives a tremendous amount of data every day. This affects the amount of time it takes to process your data and generate report results. The content in this section describes how these time intervals affect your Audience Manager account. Also, the time frames and schedules described here are general guidelines only. These schedules do not constitute Service-Level Agreements (SLAs) or commitments related to data delivery. Adobe reserves the right to change the time frames and schedules at any time without notice.
seo-title: How Data Delivery and File Processing Times Affect Reports
solution: Audience Manager
title: Como o delivery de dados e os tempos de processamento de arquivos afetam os relatórios
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: Reference
exl-id: d13102c3-fd1b-4c31-8003-9fdc0df36838
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 4%

---

# Como o delivery de dados e os tempos de processamento de arquivos afetam os relatórios{#how-data-delivery-and-file-processing-times-affect-reports}

O Audience Manager recebe uma enorme quantidade de dados todos os dias. Isso afeta o tempo necessário para processar seus dados e gerar resultados de relatório. O conteúdo desta seção descreve como esses intervalos de tempo afetam sua conta Audience Manager. Além disso, os cronogramas e cronogramas descritos aqui são somente diretrizes gerais. Esses cronogramas não constituem Contratos de nível de serviço (SLAs) nem compromissos relacionados à entrega de dados. A Adobe reserva-se o direito de alterar os cronogramas e horários a qualquer momento sem aviso prévio.

## Números de relatório {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

A tabela a seguir lista e descreve os intervalos de tempo em nossos relatórios gerais e em tempo real.


| Tipo de dados | Descrição |
|---|---|
| Dados em tempo real | Os números em tempo real de hoje são para as horas 00:00 a 23:59:59 UTC de ontem. |
| Dados de Relatório Geral | Os dados na variável [Relatórios gerais](../reporting/general-reports.md#general-reports-overview) depende da conclusão bem-sucedida de outros processos de trabalho e da quantidade de dados recebidos para um determinado dia. Na maioria das vezes, [!UICONTROL General Report] Os dados do devem ser atualizados todos os dias até às 18h00 (UTC). |

## Transferências de arquivos de entrada e saída {#inbound-outbound-file-transfers}

[!DNL Audience Manager] processa e envia informações de entrada e saída [!UICONTROL Server-to-Server (S2S)] transferências de arquivos de acordo com os agendamentos descritos nesta seção. Dadas essas programações e os tempos limite, você pode ver discrepâncias com novos segmentos entre os números de segmento em tempo real e total.

| Tipo de arquivo | Descrição |
|---|---|
| Assimilação de arquivo de entrada (dados offline) | O processamento de arquivos é executado duas vezes por dia. Esses procedimentos assimilam dados e os preparam para o delivery. Os prazos de entrega de arquivos variam porque são afetados pela quantidade total de dados do cliente que precisam ser processados. Você deve esperar uma latência máxima de 48 horas entre o momento em que o arquivo é carregado no Audience Manager e até que os dados estejam disponíveis para relatório e ativação. |
| Arquivos de saída (exportação) | O processamento e a entrega do arquivo ocorrem uma vez por dia, aproximadamente às 14h00 UTC. Lembre-se de que o processamento e o delivery são afetados pelo número total e pelo tamanho desses arquivos. Em alguns casos, pode haver um atraso no processamento do arquivo de até 24 horas. Quando isso acontecer, o Audience Manager enviará 2 arquivos para um dia específico em vez de 1. Notificaremos nossos clientes sobre os raros casos em que o Audience Manager precisa interromper o processamento de um arquivo. Dadas essas condições, é difícil estimar os prazos de delivery para dados de saída. Para determinar se você recebeu um conjunto completo de arquivos, verifique o carimbo de data e hora e procure os dias ausentes. É um carimbo de data e hora UNIX UTC de 13 dígitos que registra a hora em que o arquivo foi criado. Consulte [Transferências de dados de saída em tempo real](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md). |
| Arquivos de registro do servidor de publicidade | O processamento de arquivos é executado em tempo quase real para assimilar registros do arquivo de log, pois os arquivos por hora estão prontos. O processo para preparar os arquivos para relatórios é executado uma vez por dia. Os prazos de entrega de arquivos variam porque são afetados pela quantidade total de dados do cliente que precisam ser processados. Você deve esperar uma latência máxima de 48 horas entre o momento em que você carrega o arquivo no Audience Manager e o momento em que os dados estão disponíveis para relatório e ativação. |

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre assimilação de dados de entrada do cliente](../faq/faq-inbound-data-ingestion.md)

