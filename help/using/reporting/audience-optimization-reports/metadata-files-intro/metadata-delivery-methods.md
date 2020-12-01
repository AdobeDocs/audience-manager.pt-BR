---
description: Envie ou atualize arquivos de metadados enviando-os para um diretório especial do Amazon S3 para sua conta do Audience Manager. Consulte esta seção para obter informações sobre caminhos de delivery/diretório, tempos de processamento de arquivos e atualizações.
seo-description: Envie ou atualize arquivos de metadados enviando-os para um diretório especial do Amazon S3 para sua conta do Audience Manager. Consulte esta seção para obter informações sobre caminhos de delivery/diretório, tempos de processamento de arquivos e atualizações.
seo-title: Métodos de delivery para arquivos de metadados
solution: Audience Manager
title: Métodos de delivery para arquivos de metadados
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: log files
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 4%

---


# Métodos de delivery para arquivos de metadados{#delivery-methods-for-metadata-files}

Envie ou atualize arquivos de metadados enviando-os para um diretório especial [!DNL Amazon S3] para sua conta do Audience Manager. Consulte esta seção para obter informações sobre caminhos de delivery/diretório, tempos de processamento de arquivos e atualizações.

>[!IMPORTANT]
>
> Entre em contato com seu consultor de Audience Manager ou com o Atendimento ao cliente para começar e configurar um diretório [!DNL Amazon S3] para seus arquivos de metadados.

## Sintaxe e exemplo de caminho de delivery {#syntax}

Os dados são armazenados em namespace separada para cada cliente em um diretório [!DNL Amazon S3]. O caminho do arquivo segue a sintaxe mostrada abaixo. Observação: as chaves `<>` indicam um espaço reservado variável. Os outros elementos são constantes e não são alterados.

**Sintaxe:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**Exemplo:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

A tabela a seguir define cada um desses elementos em um caminho de delivery de arquivo.


| Parâmetro de arquivo | Descrição |
---------|----------|
| `.../log_ingestion/` | Este é o start do caminho do armazenamento do diretório. Você receberá o caminho completo quando tudo estiver configurado. |
| `pid=<AAM ID>` | Esse par de valor-chave contém a ID do cliente do Audience Manager. |
| `dpid=<d_src>` | Esse par de valor-chave contém a ID da fonte de dados transmitida em uma chamada de evento. A ID da fonte de dados é o valor que vincula todo o conteúdo do arquivo aos dados reais aos quais ele pertence. </br> Por exemplo, digamos que você tenha um anúncio com a ID 123 e o nome &quot;Advertiser Creative A&quot;. Como uma chamada de evento só passa na ID, é necessário incluir &quot;Advertiser Creative A&quot; no arquivo de metadados. A campanha e o anúncio pertencem a uma fonte de dados. A ID da fonte de dados é o que os vincula e permite associar com precisão o conteúdo do arquivo a uma ID enviada em uma chamada de evento. Consulte [Como as IDs de chamada de Evento determinam os nomes de arquivo, o conteúdo e os caminhos de Delivery](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names). |
| `<yyyymmdd_0_child ID>` | Este é o nome do arquivo. Consulte [Convenções de nomenclatura para arquivos de metadados](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Tempos e atualizações de processamento de arquivo {#processing-times}

Os arquivos de metadados são processados quatro vezes por dia, em intervalos regulares.

Para atualizar seus registros de metadados, basta enviar um arquivo que contenha novas informações. Não é necessário enviar atualizações completas sempre.
