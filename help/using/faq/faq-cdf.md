---
description: Perguntas frequentes sobre os arquivos do Feed de dados do cliente (CDF).
seo-description: Perguntas frequentes sobre os arquivos do Feed de dados do cliente (CDF).
seo-title: Perguntas frequentes sobre o Feed de dados do cliente
solution: Audience Manager
title: Perguntas frequentes sobre o Feed de dados do cliente
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
feature: Customer Data Feeds
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 0%

---


# Perguntas frequentes sobre o Feed de dados do cliente{#customer-data-feed-faq}

Perguntas frequentes sobre os arquivos do Feed de dados do cliente (CDF).

## Armazenamento Amazon S3 {#amazon-s3-storage}

**Onde meu arquivo CDF está armazenado[!DNL Amazon]?**

Seu arquivo CDF é armazenado no diretório `aam-cdf` raiz em um [!DNL Amazon S3] servidor. Esse bucket padrão é gerenciado por [!DNL Audience Manager]. Consulte também Convenções [de nomenclatura do arquivo de feed de dados do](../features/cdf-files.md#cdf-naming-conventions)cliente.

<br> 

**O meu balde de armazenamento está seguro?**

Sim. Os clientes têm acesso apenas ao seu próprio espaço de armazenamento. Você terá acesso somente leitura ao seu armazenamento bucket. Você não terá acesso de gravação.

<br> 

**É possível personalizar meu bucket de armazenamentos ou armazenar arquivos em outro diretório?**

Não. As opções de personalização e armazenamento alternativo não estão disponíveis.

<br> 

**O meu diretório não tem um ficheiro durante uma hora específica. Onde está?**

Um arquivo ausente significa que não [!DNL Audience Manager] foi possível processar seus arquivos CDF naquela hora. Isso normalmente acontece quando nossos servidores ficam atrasados no processamento de arquivos CDF. Nesse caso, seu arquivo não é perdido. Ele aparecerá em um diretório horário posterior depois que nosso sistema tiver uma chance de alcançar. Consulte também, Notificações [de Processamento de Arquivos de Feed de Dados de](../features/cdf-files.md#cdf-file-processing-notifications)Clientes.

<br> 

**Como faço para saber quando meus arquivos CDF estão prontos?**

Consulte Notificações [de processamento de arquivos de feed de dados do](../features/cdf-files.md#cdf-file-processing-notifications)cliente.

<br> 

## Tamanhos de arquivo {#file-sizes}

**Que tipo de arquivo devo esperar? Qual é o tamanho de um arquivo CDF médio?**

É difícil estimar os tamanhos dos arquivos. E cada arquivo pode ter um tamanho diferente. Os tamanhos variam de hora para hora e dia. Se você vai receber arquivos CDF, é útil estar preparado para gerenciar muitos dados.

<br> 

**Quantos arquivos eu receberei?**

Mais uma vez, é difícil estimar isto. No entanto, se você vai receber arquivos CDF, é útil estar preparado para gerenciar muitos dados.

<br> 

## Integridade dos dados {#data-integrity}

**Como posso verificar a integridade dos dados carregados no Amazon S3?**

[!DNL Amazon] divide arquivos grandes em partes menores e os carrega para [!DNL Amazon S3] usar o upload de várias partes. Em seguida, ele gera um `ETag` valor para o upload de várias partes. Primeiro, calcula as somas de verificação individuais do MD5 de cada parte carregada e, em seguida, concatena-as em uma única string. Em seguida, calcula a soma de verificação MD5 da string. A soma de verificação resultante (o `ETag`) é então anexada com um hífen e o número total de peças usadas para upload. Por exemplo, o `ETag` para um arquivo que foi dividido em 5 partes durante o upload pode ser semelhante a: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Data Retention {#data-retension}

**Por quanto tempo você armazena arquivos CDF?**

Os dados são excluídos após 8 (oito) dias.

<br> 

**É possível obter arquivos CDF retroativamente ou para dias anteriores?**

Você só pode gerar arquivos CDF nos últimos 8 dias. Os arquivos CDF para intervalos anteriores aos últimos 8 dias não podem ser gerados novamente.

>[!MORELIKETHIS]
>
>* [Feeds de dados do cliente](../features/cdf-files.md)

