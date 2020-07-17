---
description: O Audience Manager envia dados em lote para provedores de conteúdo de terceiros de acordo com essas especificações.
seo-description: O Adobe Audience Manager (AAM) envia dados em lote para provedores de conteúdo de terceiros de acordo com essas especificações.
seo-title: Transferências de dados de saída em lote no Adobe Audience Manager (AAM)
title: 'Transferências de dados de saída em lote '
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 17%

---


# Transferências de dados de saída em lote 

O Audience Manager envia dados em lote para provedores de conteúdo de terceiros de acordo com essas especificações.

* [Nome do arquivo de dados de saída: sintaxe e exemplos](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)

   Descreve os campos obrigatórios, a sintaxe e as convenções usadas para nomear um arquivo de dados externo.

* [Configurar integração de transferência de dados em lote](batch-server-configuration.md)

   Descreve os métodos pelos quais você pode configurar a integração de transferência de dados em lote.

* [Arquivos de controle de transferência para transferências de arquivos de log](/help/using/integration/receiving-audience-data/batch-outbound-transfers/transfer-control-files.md)

   Os arquivos de controle de transferência (.info) fornecem informações de metadados sobre transferências de arquivos para que os parceiros possam verificar se o Audience Manager tratou transferências de arquivos corretamente.

* [Macros de modelo de saída](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)

   Lista as macros que podem ser usadas para criar modelos de saída. Elas incluem macros de nome de arquivo, macros de cabeçalho e macros de conteúdo.

* [Exemplos de macro de saída](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

   Exemplos de como algumas macros comuns são usadas para criar modelos de arquivos de saída.

* [Potencializar as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída](/help/using/integration/receiving-audience-data/batch-outbound-transfers/authorize-s3-cross-bucket.md)

   O processo de transferência de dados de saída para clientes que usam o Amazon Simple Armazenamento Service (Amazon S3) exige que solicitemos sua chave de acesso e chave secreta do Amazon S3 para entregar os arquivos de dados de saída ao seu bucket.
