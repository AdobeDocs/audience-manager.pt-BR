---
description: Perguntas frequentes sobre arquivos de Feed de dados do cliente (CDF).
seo-description: Perguntas frequentes sobre arquivos de Feed de dados do cliente (CDF).
seo-title: Perguntas frequentes sobre o feed de dados do cliente
solution: Audience Manager
title: Perguntas frequentes sobre o feed de dados do cliente
uuid: 7183 b 3 e 2-e 999-4 e 1 e -892 f -2 bab 335 c 13 b 6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Customer Data Feed FAQ{#customer-data-feed-faq}

Perguntas frequentes sobre arquivos de Feed de dados do cliente (CDF).

## Amazon S3 Storage {#amazon-s3-storage}

**Onde está o arquivo CDF armazenado[!DNL Amazon]?**

Your CDF file is stored in the `aam-cdf` root directory on an [!DNL Amazon S3] server. This default bucket is managed by [!DNL Audience Manager]. See also [Customer Data Feed File Naming Conventions](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**Meu bucket de armazenamento está protegido?**

Sim. Os clientes obtêm acesso somente ao seu próprio espaço de armazenamento. Você terá acesso somente leitura ao seu bucket de armazenamento. Você não terá acesso de gravação.

<br> 

**Posso personalizar meu armazenamento de armazenamento ou armazenar arquivos em outro diretório?**

Não. As opções de personalização e de armazenamento alternativo não estão disponíveis.

<br> 

**Meu diretório está ausente de um arquivo para uma hora específica. Where is it?**

A missing file means [!DNL Audience Manager] was not able to process your CDF files for that hour. Isso normalmente acontece quando nossos servidores ficam atrás de um processamento de arquivos CDF. Nesse caso, o arquivo não será perdido. Ele será exibido em um diretório futuro depois de nosso sistema ter a chance de se recuperar. See also, [Customer Data Feed File Processing Notifications](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**Como faço para saber quando meus arquivos CDF estão prontos?**

See [Customer Data Feed File Processing Notifications](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## File Sizes {#file-sizes}

**Que tipo de arquivo devo esperar? How big is an average CDF file?**

É difícil estimar os tamanhos de arquivo. E, cada arquivo pode ser um tamanho diferente. Os tamanhos variam de hora a hora e dia a dia. Se você receber arquivos CDF, isso ajuda a gerenciar muitos dados.

<br> 

**Quantos arquivos receberei?**

Novamente, é difícil estimar isso. No entanto, se você receber arquivos CDF, ele ajuda a gerenciar muitos dados.

<br> 

## Data Integrity {#data-integrity}

**Como verificar a integridade dos dados carregados no Amazon S 3?**

Files exceeding 16MiB in size are split into 16MiB chunks and uploaded to [!DNL Amazon S3] using multi-part upload.

[!DNL Amazon] gera um `ETag` valor para uploads de várias partes. Primeiro calcula os valores de verificação MD 5 individuais de cada parte carregada e, em seguida, concatena os valores em uma única string. Em seguida, calcula a soma de verificação MD 5 da string. The resulting checksum (the `ETag`) is then appended with a hyphen and the total number of parts used for upload. For instance, the `ETag` for a file that was split into 5 parts during upload could look something like this: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Data Retention {#data-retension}

**Por quanto tempo você armazena arquivos CDF?**

Os dados são excluídos após 8 (oito) dias.

<br> 

**É possível obter arquivos CDF retroativamente ou para dias anteriores?**

Você só pode gerar arquivos CDF nos últimos 8 dias. Arquivos CDF para intervalos anteriores aos últimos 8 dias não podem ser gerados novamente.

>[!MORE_ LIKE_ THIS]
>
>* [Feeds de dados do cliente](../features/cdf-files.md)

