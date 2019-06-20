---
description: Como opção, você pode criptografar arquivos de dados com criptografia PGP ao enviá-los ao Audience Manager.
seo-description: Como opção, você pode criptografar arquivos de dados com criptografia PGP ao enviá-los ao Audience Manager.
seo-title: Criptografia PGP de arquivo para tipos de dados de entrada
solution: Audience Manager
title: Criptografia PGP de arquivo para tipos de dados de entrada
uuid: 89 caace 1-0259-48 fc -865 b-d 525 ec 7822 f 7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# File PGP Encryption for Inbound Data Types{#file-pgp-encryption-for-inbound-data-types}

As an option, you can encrypt data files with [!DNL PGP] encryption when sending them to Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>No momento, não oferecemos suporte à criptografia e compactação no mesmo arquivo de dados de entrada. You can select to either encrypt or [compress](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) your inbound files.

Siga as etapas descritas abaixo para criptografar arquivos de dados de entrada.

1. Download the [Audience Manager public key](./assets/adobe_pgp.pub).
1. Importe a chave pública para sua loja confiável.

   For example, if you use [!DNL GPG], the command could be similar to the following:

   `gpg --import adobe_pgp.pub`

1. Valide se a tecla foi importada corretamente executando o seguinte comando:

   `gpg --list-keys`

   Você verá uma mensagem semelhante ao seguinte:

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

1. Criptografar os dados de entrada usando o seguinte comando:

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   All encrypted data must use `.pgp` or `.gpg` as the file extension (e.g. `ftp_dpm_100_123456789.sync.pgp` or `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager supports only the [!DNL Advanced Encryption Standard (AES)] data-encryption algorithm. O Audience Manager oferece suporte para qualquer tamanho de chave.