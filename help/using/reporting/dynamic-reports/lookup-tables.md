---
description: Coloque os dados nos arquivos de log do relatório de desempenho do delivery em tabelas que contêm somente IDs. Coloque metadados que não sejam ID em tabelas de pesquisa separadas para ajudar a reduzir o tamanho do arquivo e os tempos de processamento.
seo-description: Coloque os dados nos arquivos de log do relatório de desempenho do delivery em tabelas que contêm somente IDs. Coloque metadados que não sejam ID em tabelas de pesquisa separadas para ajudar a reduzir o tamanho do arquivo e os tempos de processamento.
seo-title: Melhore os tempos de processamento do arquivo de log com tabelas de pesquisa
solution: Audience Manager
title: Melhore os tempos de processamento do arquivo de log com tabelas de pesquisa
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Referência do relatório
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 18%

---

# Melhore os tempos de processamento do arquivo de log com tabelas de pesquisa{#improve-log-file-processing-times-with-lookup-tables}

Coloque os dados nos arquivos de log do relatório de desempenho do delivery em tabelas que contêm somente IDs. Coloque metadados que não sejam ID em tabelas de pesquisa separadas para ajudar a reduzir o tamanho do arquivo e os tempos de processamento.

<!-- 

c_lookup_tables.xml

 -->

## Os metadados do arquivo de log aumentam o tamanho do arquivo e o tempo de processamento

Um arquivo de log típico usado pelo relatório [!UICONTROL Delivery Performance] geralmente contém milhares de linhas e dezenas de colunas. Ele consiste em IDs numéricas e informações legíveis ao homem, como nomes para anúncios, anunciantes, pedidos de inserção etc.

Essas informações que não são da ID são chamadas de *`metadata`* (ou seja, informações sobre outras informações) e são gravadas em cada linha do arquivo de log.

No entanto, o relatório [!UICONTROL Delivery Performance] funciona principalmente com as IDs no arquivo de log. Os metadados são úteis, mas repetitivos. Aumenta o tamanho do arquivo e os tempos de ingestão de dados.

## Reduza o tamanho do arquivo e o tempo de processamento com tabelas de índice

Para ajudar a melhorar o desempenho, o arquivo de dados principal deve conter somente IDs. Coloque os metadados em uma tabela de pesquisa (ou índice) separada e vincule esses registros ao arquivo principal com uma variável de chave comum a ambos.

## Como tabelas de pesquisa reduzem o tamanho do arquivo

Digamos que você tenha um arquivo de dados semelhante ao abaixo.

| ID de usuário | ID do anúncio | Nome do anúncio | ID do pedido | Nome da Ordem | ID do anunciante | Nome do anunciante |
|---|---|---|---|---|---|---|
| 1 | 111 | Sapato A | 456 | Tênis | 27 | Empresa A |
| 2 | 111º | Sapato A | 456 | Tênis | 27º | Empresa A |
| 3 | 111º | Sapato A | 456 | Tênis | 27º | Empresa A |
| 4 | 222 | Sapato B | 789 | Caminho | 14 | Empresa B |
| 5 | 222 | Sapato B | 789 | Caminho | 14. | Empresa B |

<br> 

Aqui está o mesmo arquivo de log com os metadados removidos. O arquivo é menor e mais fácil de processar quando consiste apenas em IDs.

| ID de usuário | ID do anúncio | ID do pedido | ID do anunciante |
|---|---|---|---|
| 1 | 111º | 456 | 27º |
| 2 | 111º | 456 | 27º |
| 3 | 111º | 456 | 27º |
| 4 | 222 | 789 | 14. |
| 5 | 222 | 789 | 14. |

<br> 

O arquivo de pesquisa abaixo contém os metadados e pode ser vinculado de volta ao arquivo principal com a ID do anúncio. Observe o tamanho também. Em vez de repetir cada anunciante várias vezes, você só precisa de uma referência para cada.

| ID do anúncio | Nome do anúncio | Nome da Ordem | Nome do anunciante |
|---|---|---|---|
| 111º | Sapato A | Tênis | Empresa A |
| 222 | Sapato B | Caminho | Empresa B |

## As APIs podem eliminar a necessidade de tabelas de pesquisa

Se seu sistema de veiculação de anúncios tiver uma API, talvez você não precise enviar metadados em um arquivo de pesquisa. Talvez possamos obter essas informações por meio da API. Nesse caso, os arquivos de log devem conter somente IDs. Trabalharemos com você para determinar se os metadados podem ser obtidos por meio de uma API.
