---
description: Coloque os dados nos arquivos de log do relatório Desempenho do Delivery em tabelas que contêm somente IDs. Coloque metadados que não sejam ID em tabelas de pesquisa separadas para ajudar a reduzir o tamanho do arquivo e os tempos de processamento.
seo-description: Coloque os dados nos arquivos de log do relatório Desempenho do Delivery em tabelas que contêm somente IDs. Coloque metadados que não sejam ID em tabelas de pesquisa separadas para ajudar a reduzir o tamanho do arquivo e os tempos de processamento.
seo-title: Melhore os tempos de processamento do arquivo de log com tabelas de pesquisa
solution: Audience Manager
title: Melhore os tempos de processamento do arquivo de log com tabelas de pesquisa
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 18%

---


# Melhore os tempos de processamento do arquivo de log com tabelas de pesquisa{#improve-log-file-processing-times-with-lookup-tables}

Coloque os dados nos arquivos de log do relatório Desempenho do Delivery em tabelas que contêm somente IDs. Coloque metadados que não sejam ID em tabelas de pesquisa separadas para ajudar a reduzir o tamanho do arquivo e os tempos de processamento.

<!-- 

c_lookup_tables.xml

 -->

## Metadados de arquivos de log aumentam o tamanho do arquivo e o tempo de processamento

Um arquivo de log comum usado pelo relatório [!UICONTROL Delivery Performance] geralmente contém milhares de linhas e dezenas de colunas. Ele consiste em IDs numéricas e informações legíveis para humanos, como nomes para criativos, anunciantes, pedidos de inserção etc.

Essas informações não ID são chamadas de *`metadata`* (ou seja, informações sobre outras informações) e são gravadas em cada linha do arquivo de log.

No entanto, o relatório [!UICONTROL Delivery Performance] funciona principalmente com as IDs no arquivo de log. Os metadados são úteis, mas repetitivos. Isso aumenta o tamanho do arquivo e os tempos de ingestão de dados.

## Reduza o tamanho do arquivo e o tempo de processamento com tabelas de índice

Para ajudar a melhorar o desempenho, o arquivo de dados principal deve conter apenas IDs. Coloque os metadados em uma tabela de pesquisa (ou índice) separada e vincule esses registros ao arquivo principal com uma variável chave comum a ambos.

## Como as tabelas de pesquisa reduzem o tamanho do arquivo

Digamos que você tenha um arquivo de dados que se pareça com o que está abaixo.

| ID de usuário | ID do anúncio | Nome do anúncio | ID do pedido | Nome da Ordem | ID do anunciante | Nome do anunciante |
|---|---|---|---|---|---|---|
| 1 | 111 | Sapato A | 456 | Tênis | 27 | Empresa A |
| 2 | 111 | Sapato A | 456 | Tênis | 27 | Empresa A |
| 3 | 111 | Sapato A | 456 | Tênis | 27 | Empresa A |
| 4 | 222 | Sapato B | 789 | Caminho | 14 | Empresa B |
| 5 | 222 | Sapato B | 789 | Caminho | 14 | Empresa B |

<br> 

Aqui está o mesmo arquivo de log com os metadados removidos. O arquivo é menor e mais fácil de processar quando consiste apenas em IDs.

| ID de usuário | ID do anúncio | ID do pedido | ID do anunciante |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

O arquivo de pesquisa abaixo contém os metadados e pode ser vinculado de volta ao arquivo principal com a ID do anúncio. Observe o tamanho também. Em vez de repetir cada anunciante várias vezes, você só precisa de uma referência para cada.

| ID do anúncio | Nome do anúncio | Nome da Ordem | Nome do anunciante |
|---|---|---|---|
| 111 | Sapato A | Tênis | Empresa A |
| 222 | Sapato B | Caminho | Empresa B |

## As APIs podem eliminar a necessidade de tabelas de pesquisa

Se seu sistema de serviço de anúncios tiver uma API, talvez você não precise enviar metadados em um arquivo de pesquisa. Talvez possamos obter essas informações por meio da API. Nesse caso, seus arquivos de registro devem conter apenas IDs. Trabalharemos com você para determinar se os metadados podem ser obtidos por meio de uma API.