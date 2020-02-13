---
description: Como opção, você pode compactar arquivos de dados ao enviá-los para o Audience Manager.
seo-description: Como opção, você pode compactar arquivos de dados ao enviá-los para o Audience Manager.
seo-title: Compactação de arquivos para arquivos de transferência de dados de entrada
solution: Audience Manager
title: Compactação de arquivos para arquivos de transferência de dados de entrada
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
translation-type: tm+mt
source-git-commit: b2e0b560a944f2ad63a48476be647f1355712342

---


# Compactação de arquivos para arquivos de transferência de dados de entrada{#file-compression-for-inbound-data-transfer-files}

Você pode compactar arquivos de dados ao enviá-los para o Audience Manager.

<!-- inbound-file-compression.xml -->

O Audience Manager oferece suporte à compactação gzip (`.gz`) para transferências de dados assíncronas e de entrada.

O Audience Manager também suporta arquivos descompactados.

>[!IMPORTANT]
>
>Não oferecemos suporte à criptografia em arquivos de entrada compactados usando gzip (`.gz`).
>
> Para criptografar e compactar arquivos de entrada, use a criptografia [](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)PGP. [!DNL PGP] a criptografia inclui compactação de arquivo.

## Compactação Amazon S3

Para entrega em [!DNL Amazon S3], você deve usar `.gz` ou descompactar arquivos. Os arquivos compactados devem ter 1 GB ou menos. Se os arquivos forem maiores, discuta o arquivo e o processo de transferência com o Atendimento ao cliente. Embora [!DNL Audience Manager] possa lidar com arquivos muito grandes, pode haver maneiras de reduzir o tamanho do arquivo ou tornar a transferência de dados mais eficiente.

>[!IMPORTANT]
>
>Seu [!DNL FTP] cliente deve usar o modo binário para transferir arquivos compactados ou criptografados. Arquivos compactados ou criptografados enviados no [!DNL ASCII] modo corromperão o arquivo de transferência de dados.

## Práticas recomendadas

* Os arquivos devem ser [!DNL .gzip] compactados (e ter uma extensão de [!DNL .gz] arquivo).
* O tamanho máximo de arquivo compactado para um arquivo `.gz` compactado é de 1 GB.
* Os tamanhos de divisão ideais, para o processamento mais rápido/anterior dos arquivos, são de aproximadamente 1 GB descompactados ou 200 a 300 MB compactados.
* [!DNL Amazon S3] impõe seu próprio limite de tamanho de arquivo de 5 GB em arquivos carregados.
