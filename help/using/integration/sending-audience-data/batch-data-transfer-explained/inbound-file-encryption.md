---
description: Como opção, você pode criptografar arquivos de dados com criptografia PGP ao enviá-los para o Audience Manager.
seo-description: Como opção, você pode criptografar arquivos de dados com criptografia PGP ao enviá-los para o Audience Manager.
seo-title: Criptografia PGP de arquivo para tipos de dados de entrada
solution: Audience Manager
title: Criptografia PGP de arquivo para tipos de dados de entrada
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 11%

---


# Criptografia PGP de arquivo para tipos de dados de entrada{#file-pgp-encryption-for-inbound-data-types}

Você pode criptografar arquivos de dados com [!DNL PGP] criptografia ao enviá-los para o Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] a criptografia inclui compactação de arquivo. Ao enviar [!DNL PGP] arquivos de entrada criptografados, certifique-se de que não [compacte](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) os arquivos usando gzip (`.gz`).
>
>[!DNL PGP] os arquivos de entrada criptografados que também são compactados são  [](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) inválidos no Audience Manager.

Siga as etapas descritas abaixo para criptografar os arquivos de dados de entrada.

1. Baixe a [chave pública Audience Manager](./assets/adobe_pgp.pub).
2. Importe a chave pública para a sua loja confiável.

   Por exemplo, se você usar [!DNL GPG], o comando poderá ser semelhante ao seguinte:

   `gpg --import adobe_pgp.pub`

3. Valide se a chave foi importada corretamente executando o seguinte comando:

   `gpg --list-keys`

   Você deve ver uma mensagem semelhante à seguinte:

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. Criptografe os dados de entrada usando o seguinte comando:

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   Todos os dados criptografados devem usar `.pgp` ou `.gpg` como a extensão do arquivo (por exemplo, `ftp_dpm_100_123456789.sync.pgp` ou `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager suporta apenas o algoritmo de criptografia de dados [!DNL Advanced Encryption Standard (AES)]. Audience Manager suporta qualquer tamanho de chave.
