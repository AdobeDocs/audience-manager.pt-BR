---
description: Como opção, você pode compactar os arquivos de dados ao enviá-los para o Audience Manager.
seo-description: Como opção, você pode compactar os arquivos de dados ao enviá-los para o Audience Manager.
seo-title: Compactação de arquivo para arquivos de transferência de dados de entrada
solution: Audience Manager
title: Compactação de arquivo para arquivos de transferência de dados de entrada
uuid: 2 a 68 f 69 c -60 b 0-4002-863 b -302 d 2320 e 356
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# File Compression for Inbound Data Transfer Files{#file-compression-for-inbound-data-transfer-files}

Como opção, você pode compactar os arquivos de dados ao enviá-los para o Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager supports gzip ( `.gz`) compression for inbound, asynchronous data transfers.

O Audience Manager também oferece suporte a arquivos descompactados.

>[!IMPORTANT]
>
>No momento, não oferecemos suporte à criptografia e compactação no mesmo arquivo de dados de entrada. You can select to either [encrypt](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md) or compress your inbound files.

## Compactação Amazon S 3

For delivery to [!DNL Amazon S3], you must use `.gz` or uncompressed files. Arquivos compactados devem ser de 1 GB ou menor. Se os arquivos estiverem maiores, discuta o arquivo e o processo de transferência com o Atendimento ao cliente. Although [!DNL Audience Manager] can handle very large files, there may be ways to reduce the file size or make transfer of data more efficient.

>[!IMPORTANT]
>
>Your [!DNL FTP] client must use binary mode to transfer compressed or encrypted files. Compressed or encrypted files sent in [!DNL ASCII] mode will corrupt the data transfer file.

## Práticas recomendadas

* Files should be [!DNL .gzip] compressed (and have a [!DNL .gz] file extension.)
* The maximum compressed file size for a `.gz` compressed file is 1 GB.
* Tamanhos de divisão ideais, para processamento mais rápido/mais rápido de arquivos, tem aproximadamente 1 GB descompactados ou 200-300 MB compactados.
* [!DNL Amazon S3] impõe seu próprio limite de tamanho de arquivo 5 GB em arquivos carregados.