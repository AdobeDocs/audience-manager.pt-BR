---
description: Como opção, você pode compactar arquivos de dados ao enviá-los para o Audience Manager.
seo-description: As an option, you can compress data files when sending them to Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: Compactação de arquivos de transferência de dados de entrada
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 7%

---

# Compactação de arquivos de transferência de dados de entrada{#file-compression-for-inbound-data-transfer-files}

Você pode compactar arquivos de dados ao enviá-los para o Audience Manager.

<!-- inbound-file-compression.xml -->

O Audience Manager suporta gzip (`.gz`) para transferências de dados assíncronas e de entrada.

O Audience Manager também suporta arquivos descompactados.

>[!IMPORTANT]
>
>Não oferecemos suporte à criptografia em arquivos de entrada compactados com gzip (`.gz`).
>
>Para criptografar e compactar arquivos de entrada, use [Criptografia PGP](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] A criptografia inclui compactação de arquivo.

## Compactação Amazon S3

Para entrega em [!DNL Amazon S3], você deve usar `.gz` ou arquivos descompactados. Os arquivos compactados devem ter 1 GB ou menos. Se os arquivos forem maiores, discuta o processo de arquivo e transferência com o Atendimento ao cliente. Embora [!DNL Audience Manager] pode lidar com arquivos muito grandes, pode haver maneiras de reduzir o tamanho do arquivo ou tornar a transferência de dados mais eficiente.

>[!IMPORTANT]
>
>Seu [!DNL FTP] o cliente deve usar o modo binário para transferir arquivos compactados ou criptografados. Arquivos compactados ou criptografados enviados [!DNL ASCII] O modo corromperá o arquivo de transferência de dados.

## Práticas recomendadas

* Os arquivos devem ser [!DNL .gzip] compactado (e tem um [!DNL .gz] extensão de arquivo).
* O tamanho máximo de arquivo compactado para um `.gz` o arquivo compactado é de 1 GB.
* Os tamanhos de divisão ideais, para o processamento mais rápido/antecipado de seus arquivos, são aproximadamente 1 GB descompactados ou 200-300 MB compactados.
* [!DNL Amazon S3] O impõe seu próprio limite de tamanho de arquivo de 5 GB em arquivos carregados.
