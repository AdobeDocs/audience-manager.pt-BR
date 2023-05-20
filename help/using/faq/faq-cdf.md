---
description: Perguntas frequentes sobre os arquivos do Feed de dados do cliente (CDF).
seo-description: Frequently asked questions about Customer Data Feed (CDF) files.
seo-title: Customer Data Feed FAQ
solution: Audience Manager
title: Perguntas frequentes sobre o Feed de dados do cliente
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
feature: Customer Data Feeds
exl-id: a948accc-6bec-4748-bcc8-2b77acf6b96a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 100%

---

# Perguntas frequentes sobre o Feed de dados do cliente{#customer-data-feed-faq}

Perguntas frequentes sobre os arquivos do Feed de dados do cliente (CDF).

## Armazenamento Amazon S3 {#amazon-s3-storage}

**Onde meu arquivo CDF é armazenado na [!DNL Amazon]?**

Seu arquivo CDF é armazenado no diretório raiz `aam-cdf` em um servidor [!DNL Amazon S3]. Esse bucket padrão é gerenciado pelo [!DNL Audience Manager]. Consulte também [Convenções de nomenclatura de arquivos de feed de dados do cliente](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**O meu bucket de armazenamento está seguro?**

Sim. Os clientes têm acesso apenas ao seu próprio espaço de armazenamento. Você terá acesso somente leitura ao seu bucket de armazenamento. Você não terá acesso de gravação.

<br> 

**É possível personalizar meu bucket de armazenamento ou armazenar arquivos em outro diretório?**

Não. A personalização e as opções de armazenamento alternativo não estão disponíveis.

<br> 

**Durante uma hora específica, um dos arquivos não aparece no diretório. Onde ele está?**

Um arquivo ausente significa que o [!DNL Audience Manager] não processou os arquivos CDF naquela hora. Isso acontece geralmente quando nossos servidores atrasam o processamento de arquivos CDF. Nesse caso, o arquivo não é perdido. Ele aparecerá em outro diretório depois que o sistema recuperar o atraso. Consulte também [Notificações de processamento de arquivos de feed de dados do cliente](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**Como sei quando meus arquivos CDF estão prontos?**

Consulte [Notificações de processamento de arquivos de feed de dados do cliente](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## Tamanhos de arquivo {#file-sizes}

**Que tipo de tamanhos de arquivo devo esperar? Qual é o tamanho médio de um arquivo CDF?**

É difícil estimar os tamanhos dos arquivos. Cada arquivo pode ter um tamanho diferente. Os tamanhos variam a cada hora e dia. Se você for receber arquivos CDF, prepare-se para gerenciar muitos dados.

<br> 

**Quantos arquivos eu receberei?**

Mais uma vez, é difícil estimar isso. No entanto, se você for receber arquivos CDF, prepare-se para gerenciar muitos dados.

<br> 

## Integridade dos dados {#data-integrity}

**Como posso verificar a integridade dos dados carregados no Amazon S3?**

A [!DNL Amazon] divide arquivos grandes em partes menores e faz o upload para o [!DNL Amazon S3] usar o upload de várias partes. Em seguida, ele gera um valor `ETag` para o upload de várias partes. Primeiro, ele calcula as somas de verificação individuais do MD5 de cada parte carregada e as combina em uma única string. Em seguida, calcula a soma de verificação MD5 da string. A soma de verificação resultante (o `ETag`) é então anexada com um hífen e o número total de partes usadas para o upload. Por exemplo, o `ETag` para um arquivo que foi dividido em 5 partes durante o upload pode ser semelhante a: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Retenção de dados {#data-retension}

**Por quanto tempo você armazena arquivos CDF?**

Os dados são excluídos após 8 (oito) dias.

<br> 

**É possível obter arquivos CDF retroativamente ou de dias anteriores?**

Você só pode gerar arquivos CDF nos últimos 8 dias. Os arquivos CDF para intervalos anteriores aos últimos 8 dias não podem ser gerados novamente.

>[!MORELIKETHIS]
>
>* [Feeds de dados do cliente](../features/cdf-files.md)

