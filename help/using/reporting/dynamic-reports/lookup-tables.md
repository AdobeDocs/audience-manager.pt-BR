---
description: Coloque dados nos arquivos de log do relatório de Desempenho de entrega em tabelas que contenham apenas IDs. Coloque metadados não ID em tabelas de pesquisa separadas para ajudar a reduzir o tamanho do arquivo e os tempos de processamento.
seo-description: Put data in Delivery Performance report log files into tables that contain IDs only. Put non-ID metadata in separate lookup tables to help reduce file size and processing times.
seo-title: Improve Log File Processing Times with Lookup Tables
solution: Audience Manager
title: Melhore os tempos de processamento do arquivo de log com tabelas de pesquisa
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Reporting Reference
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 13%

---

# Melhore os tempos de processamento do arquivo de log com tabelas de pesquisa{#improve-log-file-processing-times-with-lookup-tables}

Coloque dados nos arquivos de log do relatório de Desempenho de entrega em tabelas que contenham apenas IDs. Coloque metadados não ID em tabelas de pesquisa separadas para ajudar a reduzir o tamanho do arquivo e os tempos de processamento.

<!-- 

c_lookup_tables.xml

 -->

## Os metadados do arquivo de log aumentam o tamanho do arquivo e o tempo de processamento

Um arquivo de log típico usado pelo relatório [!UICONTROL Delivery Performance] geralmente contém milhares de linhas e dezenas de colunas. Ele consiste em IDs numéricas e informações legíveis por humanos, como nomes de criadores, anunciantes, pedidos de inserção etc.

Essas informações não ID são chamadas de *`metadata`* (ou seja, informações sobre outras informações) e são gravadas em cada linha do arquivo de log.

No entanto, o relatório [!UICONTROL Delivery Performance] funciona principalmente com as IDs no arquivo de log. Os metadados são úteis, mas repetitivos. Ele aumenta o tamanho do arquivo e o tempo de assimilação dos dados.

## Reduza o tamanho do arquivo e o tempo de processamento com tabelas de índice

Para ajudar a melhorar o desempenho, o arquivo de dados principal deve conter apenas IDs. Coloque metadados em uma tabela de pesquisa (ou índice) separada e vincule esses registros ao arquivo principal com uma variável principal comum a ambos.

## Como as tabelas de pesquisa reduzem o tamanho do arquivo

Digamos que você tenha um arquivo de dados semelhante ao abaixo.

| ID de usuário | ID do anúncio | Nome do anúncio | ID do pedido | Nome do pedido | ID de anunciante | Nome do anunciante |
|---|---|---|---|---|---|---|
| 1 | 111 | Sapato A | 456 | Tênis | 27 | Empresa A |
| 2 | 111 | Sapato A | 456 | Tênis | 27 | Empresa A |
| 3 | 111 | Sapato A | 456 | Tênis | 27 | Empresa A |
| 4 | 222 | Sapato B | 789 | Caminhada | 14 | Empresa B |
| 5 | 222 | Sapato B | 789 | Caminhada | 14 | Empresa B |

<br> 

Aqui está o mesmo arquivo de log com os metadados removidos. O arquivo é menor e mais fácil de processar quando consiste apenas em IDs.

| ID de usuário | ID do anúncio | ID do pedido | ID de anunciante |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

O arquivo de pesquisa abaixo contém os metadados e pode ser vinculado ao arquivo principal com a ID do anúncio. Observe o tamanho também. Em vez de repetir cada anunciante várias vezes, você precisa apenas de uma referência para cada um.

| ID do anúncio | Nome do anúncio | Nome do pedido | Nome do anunciante |
|---|---|---|---|
| 111 | Sapato A | Tênis | Empresa A |
| 222 | Sapato B | Caminhada | Empresa B |

## As APIs podem eliminar a necessidade de tabelas de pesquisa

Se o sistema de veiculação de anúncios tiver uma API, talvez não seja necessário enviar metadados em um arquivo de pesquisa. Podemos obter essas informações por meio da API. Quando esse for o caso, os arquivos de log deverão conter somente IDs. Trabalharemos com você para determinar se os metadados podem ser obtidos por meio de uma API.
