---
description: Esta página lista as integrações personalizadas entre o Audience Manager e os parceiros de dados.
seo-description: Esta página lista as integrações personalizadas entre o Audience Manager e os parceiros de dados.
seo-title: Integrações de parceiros personalizadas
solution: Audience Manager
title: Integrações de parceiros personalizadas
translation-type: tm+mt
source-git-commit: 3e7c993b1ddd2829e382de56ea246a667ff3ce0c

---


# Custom Partner Integrations {#custom-partner-integrations}

Esta página lista as integrações personalizadas entre o Audience Manager e os parceiros de dados.

## Oracle Data Cloud {#oracle-data-cloud}

**Descrição**

O Audience Manager assimila dados de cookies e de IDs de dispositivos móveis do Oracle Data Cloud para o Audience Marketplace por meio de arquivos de dados de entrada. As especificações de integração personalizadas descritas abaixo referem-se apenas a arquivos de dados de entrada que contenham IDs móveis (IDs de dispositivo IDFA e Android).

<br> 

**Especificações de integração**

Inbound Data Files received from the Oracle Data Cloud differ from the standard inbound file name syntax described in [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) and from the standard inbound file content syntax described in [Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Os elementos destacados abaixo são necessários, além dos campos de implementação padrão para arquivos de dados de entrada. Para obter descrições de todos os outros elementos padrão e elementos de nome de arquivo, consulte Sintaxe de nome de arquivo e Sintaxe de conteúdo de arquivo nas duas páginas vinculadas acima.

<br> 

**Nomeação de arquivo**

Os nomes de arquivos ODC estão estruturados como:

<pre>ftp_dpm_<b>odc</b>_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]</pre>

The `odc` file name element identifies the file as being imported from the Oracle Data Cloud and instructs the Audience Manager inbound file validator to process it as such.

<br> 

**Conteúdo do arquivo**

Os campos no arquivo de dados de entrada do ODC devem aparecer na ordem mostrada abaixo:

<pre>&lt;<b>ID type</b>&gt;&lt;TAB&gt;&lt;user ID&gt;&lt;TAB&gt;&lt;trait ID&gt;,&lt;trait ID&gt;,&lt;trait ID&gt;,...</pre>

The `ID type` can be:

* IDFA
* ID do dispositivo Android

>[!IMPORTANT]
>
>Não envie IDs de dispositivo IDFA e Android no mesmo arquivo de dados de entrada.

<br> 

**Amostra de arquivo de entrada do ODC**

Download the [sample file](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Esse arquivo classifica vários idfas para a ID de característica 38838. Você pode abrir esse arquivo em um editor de texto padrão ou editor de códigos.