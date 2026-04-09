---
description: Esta página lista as integrações personalizadas entre o Audience Manager e os parceiros de dados.
seo-description: This page lists custom integrations between Audience Manager and data partners.
seo-title: Custom Partner Integrations
solution: Audience Manager
title: Integrações personalizadas de parceiros
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
TQID: https://experienceleague.adobe.com/0QvyTQOmjkES1ZO47uu7JTh07-5--uHIgCbJ9iAYfrE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
  - id: d8f86c1e-15ad-457f-9d6f-5e756573fad4
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 15%

---

# Integrações personalizadas de parceiros {#custom-partner-integrations}

Esta página lista as integrações personalizadas entre o Audience Manager e os parceiros de dados.

## Oracle Data Cloud {#oracle-data-cloud}

### Descrição

O Audience Manager assimila dados de cookies e de IDs de dispositivos móveis do Oracle Data Cloud para o Audience Marketplace por meio de arquivos de dados de entrada. As especificações de integração personalizadas descritas abaixo referem-se apenas a arquivos de dados de entrada que contêm IDs móveis (IDFA e IDs de dispositivo do Android).

### Especificações da integração

Os arquivos de dados de entrada recebidos da Oracle Data Cloud diferem da sintaxe de nome de arquivo de entrada padrão descrita nos [Requisitos de nome e tamanho de arquivo do Amazon S3 para arquivos de dados de entrada](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) e da sintaxe de conteúdo de arquivo de entrada padrão descrita em [Conteúdo do arquivo de dados de entrada: sintaxe, caracteres inválidos, variáveis e exemplos](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Os elementos destacados abaixo são obrigatórios, além dos campos de implementação padrão para arquivos de dados de entrada. Para obter descrições de todos os outros campos padrão e elementos de nome de arquivo, consulte Sintaxe de nome de arquivo e Sintaxe de conteúdo de arquivo nas duas páginas vinculadas acima.

### Nomeação do arquivo

Os nomes de arquivo ODC são estruturados como:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

O elemento de nome de arquivo `odc` identifica o arquivo como importado da Oracle Data Cloud e instrui o validador de arquivo de entrada do Audience Manager a processá-lo como tal.

### Conteúdo do arquivo

Os campos no arquivo de dados de entrada ODC devem aparecer na ordem mostrada abaixo:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

O `ID type` pode ser:

* IDFA
* ID do dispositivo Android

>[!IMPORTANT]
>
>Não envie IDs de dispositivo IDFA e Android no mesmo arquivo de dados de entrada.

## Arquivo de entrada ODC de exemplo

Baixe o [arquivo de amostra](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Esse arquivo qualifica vários IDFAs para a ID de característica 38838. Você pode abrir esse arquivo em um editor de texto padrão ou em um editor de código.
