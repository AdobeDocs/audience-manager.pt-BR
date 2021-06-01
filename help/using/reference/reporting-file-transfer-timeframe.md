---
description: O Audience Manager recebe uma enorme quantidade de dados todos os dias. Isso afeta o tempo necessário para processar seus dados e gerar resultados do relatório. O conteúdo desta seção descreve como esses intervalos afetam sua conta do Audience Manager. Além disso, os prazos e as programações descritos aqui são apenas diretrizes gerais. Esses cronogramas não constituem SLAs (Service-Level Agreements, contratos de nível de serviço) ou compromissos relacionados à entrega de dados. O Adobe reserva-se o direito de alterar os prazos e as programações a qualquer momento sem aviso prévio.
seo-description: O Audience Manager recebe uma enorme quantidade de dados todos os dias. Isso afeta o tempo necessário para processar seus dados e gerar resultados do relatório. O conteúdo desta seção descreve como esses intervalos afetam sua conta do Audience Manager. Além disso, os prazos e as programações descritos aqui são apenas diretrizes gerais. Esses cronogramas não constituem SLAs (Service-Level Agreements, contratos de nível de serviço) ou compromissos relacionados à entrega de dados. O Adobe reserva-se o direito de alterar os prazos e as programações a qualquer momento sem aviso prévio.
seo-title: Como o delivery de dados e os tempos de processamento de arquivos afetam os relatórios
solution: Audience Manager
title: Como o delivery de dados e os tempos de processamento de arquivos afetam os relatórios
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: 'Referência '
exl-id: d13102c3-fd1b-4c31-8003-9fdc0df36838
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 5%

---

# Como o delivery de dados e os tempos de processamento de arquivos afetam os relatórios{#how-data-delivery-and-file-processing-times-affect-reports}

O Audience Manager recebe uma enorme quantidade de dados todos os dias. Isso afeta o tempo necessário para processar seus dados e gerar resultados do relatório. O conteúdo desta seção descreve como esses intervalos afetam sua conta do Audience Manager. Além disso, os prazos e as programações descritos aqui são apenas diretrizes gerais. Esses cronogramas não constituem SLAs (Service-Level Agreements, contratos de nível de serviço) ou compromissos relacionados à entrega de dados. O Adobe reserva-se o direito de alterar os prazos e as programações a qualquer momento sem aviso prévio.

## Números dos relatórios {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

A tabela a seguir lista e descreve os intervalos de tempo em nossos relatórios gerais e em tempo real.


| Tipo de dados | Descrição |
|---|---|
| Dados em tempo real | Os números em tempo real para hoje são para as horas de 00:00 às 23:59:59 UTC de ontem. |
| Dados gerais do relatório | Os dados nos [Relatórios Gerais](../reporting/general-reports.md#general-reports-overview) dependem da conclusão bem-sucedida de outros processos de trabalho e da quantidade de dados recebidos por um dia específico. Na maioria das vezes, os dados [!UICONTROL General Report] devem ser atualizados por 18:00 UTC todos os dias. |

## Transferências de arquivos de entrada e saída {#inbound-outbound-file-transfers}

[!DNL Audience Manager] processa e envia transferências de  [!UICONTROL Server-to-Server (S2S)] arquivos de entrada e saída de acordo com as programações descritas nesta seção. Dadas essas programações e os tempos de interrupção, você pode ver discrepâncias com novos segmentos entre os números de segmentos em tempo real e total.

| Tipo de arquivo | Descrição |
|---|---|
| Assimilação de arquivo de entrada (dados offline) | O processamento de arquivos é executado duas vezes por dia. Esses procedimentos assimilam dados e os preparam para entrega. Os tempos de entrega do arquivo variam porque são afetados pela quantidade total de dados do cliente que precisam ser processados. Você deve esperar uma latência máxima de 48 horas entre o momento em que o arquivo é carregado no Audience Manager e até que os dados estejam disponíveis para relatórios e ativação. |
| Arquivos de saída (exportação) | O processamento e a entrega de arquivos ocorrem uma vez por dia, aproximadamente às 14:00 UTC. Lembre-se de que o processamento e a entrega são afetados pelo número e tamanho total desses arquivos. Em alguns casos, pode haver um atraso no processamento do arquivo por até 24 horas. Quando isso acontecer, o Audience Manager enviará 2 arquivos para um dia específico em vez de 1. Notificaremos nossos clientes nos raros casos em que o Audience Manager tiver que parar de processar um arquivo completamente. Dadas essas condições, é difícil estimar os tempos de delivery para dados de saída. Para determinar se recebeu um conjunto completo de arquivos, verifique o carimbo de data e hora e procure por dias ausentes. Este é um carimbo de data e hora UNIX UTC de 13 dígitos que registra a hora em que o arquivo foi criado. Consulte [Transferências de dados de saída em tempo real](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md). |
| Arquivos de log do servidor de anúncios | O processamento de arquivos é executado em tempo quase real para assimilar registros de arquivo de log, pois os arquivos por hora estão prontos. O processo para preparar os arquivos para relatórios é executado uma vez por dia. Os tempos de entrega do arquivo variam porque são afetados pela quantidade total de dados do cliente que precisam ser processados. Você deve esperar uma latência máxima de 48 horas entre o momento em que você carrega o arquivo no Audience Manager e o momento em que os dados estão disponíveis para relatórios e ativação. |

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre assimilação de dados de entrada do cliente](../faq/faq-inbound-data-ingestion.md)

