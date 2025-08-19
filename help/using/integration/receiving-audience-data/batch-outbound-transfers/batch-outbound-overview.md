---
description: O Audience Manager envia dados em lote para provedores de conteúdo de terceiros de acordo com essas especificações.
seo-description: Adobe Audience Manager (AAM) sends batch data to third-party content providers according to these specifications.
seo-title: Batch Outbound Data Transfers in Adobe Audience Manager (AAM)
title: Transferências de dados de saída em lote
feature: Outbound Data Transfers
exl-id: 1fdcc971-3a71-4033-8501-ef3d1f1f0f47
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---

# Transferências de dados de saída em lote

O Audience Manager envia dados em lote para provedores de conteúdo de terceiros de acordo com essas especificações.

* [Nome do arquivo de dados de saída: sintaxe e exemplos](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)

  Descreve os campos obrigatórios, a sintaxe e as convenções usadas para nomear um arquivo de dados de saída.

* [Configurar a integração da transferência de dados em lote](batch-server-configuration.md)

  Descreve os métodos pelos quais você pode configurar a integração da transferência de dados em lote.

* [Arquivos de controle de transferência para transferências de arquivos de log](/help/using/integration/receiving-audience-data/batch-outbound-transfers/transfer-control-files.md)

  Os arquivos de controle de transferência (.info) fornecem informações de metadados sobre transferências de arquivos para que os parceiros possam verificar se o Audience Manager lidou com as transferências de arquivos corretamente.

* [Macros de modelo de saída](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)

  Lista as macros que você pode usar para criar modelos de saída. Isso inclui macros de nome de arquivo, macros de cabeçalho e macros de conteúdo.

* [Exemplos de macro de saída](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

  Exemplos de como algumas macros comuns são usadas para criar modelos de arquivo de saída.

* [Aproveite as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída](/help/using/integration/receiving-audience-data/batch-outbound-transfers/authorize-s3-cross-bucket.md)

  O processo de transferência de dados de saída para clientes que usam o Amazon Simple Storage Service (Amazon S3) exige que solicitemos sua chave de acesso e chave secreta do Amazon S3 para entregar os arquivos de dados de saída ao seu bucket.
