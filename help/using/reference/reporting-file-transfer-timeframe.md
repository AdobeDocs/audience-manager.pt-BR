---
description: O Gerenciador de Audiências recebe uma quantidade enorme de dados todos os dias. Isso afeta o tempo necessário para processar seus dados e gerar resultados do relatório. O conteúdo desta seção descreve como esses intervalos afetam sua conta do Audiência Manager. Além disso, os intervalos de tempo e os agendamentos descritos aqui são apenas diretrizes gerais. Esses agendamentos não constituem SLAs (Service-Level Agreements, contratos de nível de serviço) ou compromissos relacionados ao delivery de dados. A Adobe reserva o direito de alterar os intervalos de tempo e as programações a qualquer momento, sem aviso prévio.
seo-description: O Gerenciador de Audiências recebe uma quantidade enorme de dados todos os dias. Isso afeta o tempo necessário para processar seus dados e gerar resultados do relatório. O conteúdo desta seção descreve como esses intervalos afetam sua conta do Audiência Manager. Além disso, os intervalos de tempo e os agendamentos descritos aqui são apenas diretrizes gerais. Esses agendamentos não constituem SLAs (Service-Level Agreements, contratos de nível de serviço) ou compromissos relacionados ao delivery de dados. A Adobe reserva o direito de alterar os intervalos de tempo e as programações a qualquer momento, sem aviso prévio.
seo-title: Como o Delivery de dados e os tempos de processamento de arquivos afetam os relatórios
solution: Audience Manager
title: Como o Delivery de dados e os tempos de processamento de arquivos afetam os relatórios
uuid: 4b975512-f67e-4749-a7ef-168415597682
translation-type: tm+mt
source-git-commit: 6bdf79b17ec96ed0d54ed97ab5d69fadb68763b5

---


# Como o Delivery de dados e os tempos de processamento de arquivos afetam os relatórios{#how-data-delivery-and-file-processing-times-affect-reports}

O Gerenciador de Audiências recebe uma quantidade enorme de dados todos os dias. Isso afeta o tempo necessário para processar seus dados e gerar resultados do relatório. O conteúdo desta seção descreve como esses intervalos afetam sua conta do Audiência Manager. Além disso, os intervalos de tempo e os agendamentos descritos aqui são apenas diretrizes gerais. Esses agendamentos não constituem SLAs (Service-Level Agreements, contratos de nível de serviço) ou compromissos relacionados ao delivery de dados. A Adobe reserva o direito de alterar os intervalos de tempo e as programações a qualquer momento, sem aviso prévio.

## Números dos Relatórios {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

A tabela a seguir lista e descreve os intervalos de tempo em nossos relatórios gerais e em tempo real.


| Tipo de dados | Descrição |
|---|---|
| Dados em tempo real | Os números em tempo real para hoje são para as horas das 00:00 às 23:59:59 UTC de ontem. |
| Dados gerais do relatório | Os dados nos Relatórios [](../reporting/general-reports.md#general-reports-overview) Gerais dependem da conclusão com êxito de outros processos de trabalho e da quantidade de dados recebidos por um dia específico. Na maioria das vezes, os dados devem ser atualizados [!UICONTROL General Report] até às 18:00 UTC por dia. |

## Transferências de arquivos de entrada e de saída {#inbound-outbound-file-transfers}

[!DNL Audience Manager] processa e envia transferências de arquivos de entrada e saída de acordo com as programações descritas nesta seção. [!UICONTROL Server-to-Server (S2S)] Dadas essas programações e os tempos de interrupção, você pode observar discrepâncias com novos segmentos entre os números de segmentos em tempo real e total.

| Tipo de arquivo | Descrição |
|---|---|
| Ingestão de Arquivo de Entrada (dados offline) | O processamento de arquivos é executado duas vezes por dia. Esses procedimentos assimilam dados e os preparam para o delivery. Os tempos de delivery de arquivos variam porque são afetados pela quantidade total de dados do cliente que precisam ser processados. Você deve esperar uma latência máxima de 48 horas entre o momento em que o arquivo é carregado no Gerenciador de Audiências e até que os dados estejam disponíveis para relatórios e ativação. |
| Arquivos de saída (Exportar) | O processamento e o delivery de arquivos ocorrem uma vez por dia, aproximadamente às 14:00 UTC. Lembre-se de que o processamento e o delivery são afetados pelo número e tamanho totais desses arquivos. Em alguns casos, pode haver um atraso no processamento de arquivos por até 24 horas. Quando isso acontecer, o Audiência Manager enviará 2 arquivos para um dia específico em vez de 1. Notificaremos nossos clientes em casos raros em que o Gerenciador de Audiências tiver que parar de processar um arquivo. Dadas estas condições, é difícil estimar os tempos de delivery para dados de saída. Para determinar se você recebeu um conjunto completo de arquivos, verifique o carimbo de data e hora e procure os dias que estiverem faltando. Este é um carimbo de data e hora UNIX UTC de 13 dígitos que registra a hora em que o arquivo foi criado. Consulte Transferências [de dados de saída em tempo](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md)real. |
| Arquivos de log do servidor de publicidade | O processamento de arquivos é executado em tempo quase real para assimilar registros de arquivos de log, já que os arquivos por hora estão prontos. O processo para preparar os arquivos para o relatórios é executado uma vez por dia. Os tempos de delivery de arquivos variam porque são afetados pela quantidade total de dados do cliente que precisam ser processados. Você deve esperar uma latência máxima de 48 horas entre o momento em que você carrega o arquivo no Gerenciador de Audiências e o momento em que os dados estão disponíveis para relatórios e ativação. |

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre ingestão de dados do cliente de entrada](../faq/faq-inbound-data-ingestion.md)

