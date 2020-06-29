---
description: Esta página lista as integrações personalizadas entre o Audience Manager e os parceiros de dados.
seo-description: Esta página lista as integrações personalizadas entre o Audience Manager e os parceiros de dados.
seo-title: Integrações personalizadas de parceiros
solution: Audience Manager
title: Integrações personalizadas de parceiros
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 19%

---


# Integrações personalizadas de parceiros {#custom-partner-integrations}

Esta página lista as integrações personalizadas entre o Audience Manager e os parceiros de dados.

## Oracle Data Cloud {#oracle-data-cloud}

### Descrição

O Audience Manager assimila dados de cookies e de IDs de dispositivos móveis do Oracle Data Cloud para o Audience Marketplace por meio de arquivos de dados de entrada. As especificações de integração personalizadas descritas abaixo referem-se somente aos arquivos de dados de entrada que contêm IDs móveis (IDFA e IDs de dispositivo Android).

### Especificações de integração

Os Arquivos de Dados de Entrada recebidos da Oracle Data Cloud diferem da sintaxe padrão de nome de arquivo de entrada descrita em [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) and from the default input file content sintaxe descrita em Conteúdo de Arquivo de Dados de [Entrada: Sintaxe, caracteres inválidos, variáveis e exemplos](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Os elementos destacados abaixo são obrigatórios, além dos campos de implementação padrão para arquivos de dados de entrada. Para obter descrições de todos os outros campos padrão e elementos de nome de arquivo, consulte Sintaxe de nome de arquivo e Sintaxe de conteúdo de arquivo nas duas páginas vinculadas acima.

### Nomeação de arquivo

Os nomes de arquivos ODC são estruturados como:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

O elemento de nome de `odc` arquivo identifica o arquivo como sendo importado da Oracle Data Cloud e instrui o validador de arquivo de entrada do Audience Manager a processá-lo como tal.

### Conteúdo do arquivo

Os campos no arquivo de dados de entrada do ODC devem aparecer na ordem mostrada abaixo:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

O `ID type` pode ser:

* IDFA
* ID do dispositivo Android

>[!IMPORTANT]
>
>Não envie IDs de dispositivos IDFA e Android no mesmo arquivo de dados de entrada.

## Exemplo de arquivo de entrada ODC

Baixe o arquivo [de](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync)amostra. Esse arquivo qualifica vários IDFAs para a ID de característica 38838. Você pode abrir esse arquivo em um editor de texto padrão ou editor de código.