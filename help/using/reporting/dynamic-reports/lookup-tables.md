---
description: Coloque dados nos arquivos de log de entrega de entrega em tabelas que contêm apenas IDs. Coloque metadados não ID em tabelas de pesquisa separadas para ajudar a reduzir o tamanho do arquivo e o tempo de processamento.
seo-description: Coloque dados nos arquivos de log de entrega de entrega em tabelas que contêm apenas IDs. Coloque metadados não ID em tabelas de pesquisa separadas para ajudar a reduzir o tamanho do arquivo e o tempo de processamento.
seo-title: Melhorar tempos de processamento de arquivos de log com tabelas de pesquisa
solution: Audience Manager
title: Melhorar tempos de processamento de arquivos de log com tabelas de pesquisa
uuid: ffc 77618-474 b -455 e -9 c 91-15 b 32 fc 151 a 5
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Improve Log File Processing Times with Lookup Tables{#improve-log-file-processing-times-with-lookup-tables}

Coloque dados nos arquivos de log de entrega de entrega em tabelas que contêm apenas IDs. Coloque metadados não ID em tabelas de pesquisa separadas para ajudar a reduzir o tamanho do arquivo e o tempo de processamento.

<!-- 

c_lookup_tables.xml

 -->

## Os metadados do arquivo de log aumentam o tamanho e o tempo de processamento do arquivo

A typical log file used by the [!UICONTROL Delivery Performance] report usually contains thousands of rows and dozens of columns. Ela consiste em IDs numéricas e informações legível por humanos, como nomes para anúncios, anunciantes, pedidos de inserção etc.

This non-ID information is referred to as *`metadata`* (i.e., information about other information) and gets written in each row of the log file.

However, the [!UICONTROL Delivery Performance] report mainly works with the IDs in the log file. Os metadados são úteis, mas repetitivos. Aumenta o tamanho do arquivo e os tempos de ingestão dos dados.

## Reduzir tamanho de arquivo e reduzir tempo de processamento com tabelas de índice

Para ajudar a melhorar o desempenho, seu arquivo de dados principal deve conter apenas IDs. Coloque metadados em uma tabela de pesquisa (ou índice) separada e vincule esses registros ao arquivo principal com uma variável chave comum a ambos.

## Como as tabelas de pesquisa reduzem o tamanho do arquivo

Considere que você tem um arquivo de dados semelhante ao abaixo.

| ID de usuário | ID do anúncio | Nome do anúncio | ID do pedido | Nome da Ordem | ID do anunciante | Nome do anunciante |
|---|---|---|---|---|---|---|
| 1 | 111 | Shoe A | 456 | Tneakers | 27 | Empresa A |
| 2 | 111 | Shoe A | 456 | Tneakers | 27 | Empresa A |
| 3 | 111 | Shoe A | 456 | Tneakers | 27 | Empresa A |
| 4 | 222 | Shoe B | 789 | Hiking | 14 | Empresa B |
| 5 | 222 | Shoe B | 789 | Hiking | 14 | Empresa B |

<br> 

Aqui está o mesmo arquivo de log com os metadados removidos. O arquivo é menor e mais fácil de processar quando é formado por IDs apenas.

| ID de usuário | ID do anúncio | ID do pedido | ID do anunciante |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

O arquivo de pesquisa abaixo contém os metadados e pode ser vinculado novamente ao arquivo principal com a ID do anúncio. Observe também o tamanho. Em vez de repetir cada anunciante várias vezes, você precisa apenas de uma referência para cada um.

| ID do anúncio | Nome do anúncio | Nome da Ordem | Nome do anunciante |
|---|---|---|---|
| 111 | Shoe A | Tneakers | Empresa A |
| 222 | Shoe B | Hiking | Empresa B |

## As apis podem eliminar a necessidade das tabelas de pesquisa

Se o seu sistema de serviço de publicidade tiver uma API, talvez você não precise enviar metadados em um arquivo de pesquisa. Talvez seja possível obter essas informações por meio da API. Nesse caso, os arquivos de registro devem conter apenas IDs. Trabalharemos com você para determinar se os metadados podem ser obtidos por meio de uma API.

>[!MORE_ LIKE_ THIS]
>
>* [Relatório de entrega e desempenho](../../reporting/dynamic-reports/delivery-performance-report.md)

