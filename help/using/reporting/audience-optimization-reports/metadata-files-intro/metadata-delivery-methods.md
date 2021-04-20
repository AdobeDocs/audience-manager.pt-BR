---
description: Envie ou atualize arquivos de metadados enviando-os para um diretório especial do Amazon S3 para sua conta do Audience Manager. Consulte esta seção para obter informações sobre caminhos de entrega/diretório, tempos de processamento de arquivos e atualizações.
seo-description: Envie ou atualize arquivos de metadados enviando-os para um diretório especial do Amazon S3 para sua conta do Audience Manager. Consulte esta seção para obter informações sobre caminhos de entrega/diretório, tempos de processamento de arquivos e atualizações.
seo-title: Métodos de delivery para arquivos de metadados
solution: Audience Manager
title: Métodos de delivery para arquivos de metadados
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: Log Files
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 4%

---

# Métodos de delivery para arquivos de metadados{#delivery-methods-for-metadata-files}

Envie ou atualize arquivos de metadados enviando-os para um diretório especial [!DNL Amazon S3] para sua conta do Audience Manager. Consulte esta seção para obter informações sobre caminhos de entrega/diretório, tempos de processamento de arquivos e atualizações.

>[!IMPORTANT]
>
> Entre em contato com seu consultor do Audience Manager ou com o Atendimento ao cliente para começar e configurar um diretório [!DNL Amazon S3] para seus arquivos de metadados.

## Sintaxe e exemplo do caminho de entrega {#syntax}

Os dados são armazenados em um namespace separado para cada cliente em um diretório [!DNL Amazon S3]. O caminho do arquivo segue a sintaxe mostrada abaixo. Observação: colchetes `<>` indicam um espaço reservado de variável. Os outros elementos são constantes e não são alterados.

**Sintaxe:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**Exemplo:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

A tabela a seguir define cada um desses elementos em um caminho de entrega de arquivo.


| Parâmetro de arquivo | Descrição |
---------|----------|
| `.../log_ingestion/` | Este é o início do caminho de armazenamento do diretório. Você receberá o caminho completo quando tudo estiver configurado. |
| `pid=<AAM ID>` | Esse par de chave-valor contém a ID do cliente do Audience Manager. |
| `dpid=<d_src>` | Esse par de valores chave contém a ID da fonte de dados transmitida em uma chamada de evento. A ID da fonte de dados é o valor que vincula todos os conteúdos do arquivo aos dados reais aos quais pertence. </br> Por exemplo, digamos que você tenha um anúncio com a ID 123 e o nome &quot;Advertiser Creative A&quot;. Como uma chamada de evento só passa na ID, é necessário incluir &quot;Advertiser Creative A&quot; no arquivo de metadados. A campanha e o anúncio pertencem a uma fonte de dados. A ID da fonte de dados é o que os vincula e permite associar com precisão o conteúdo do arquivo a uma ID enviada em uma chamada de evento. Consulte [Como as IDs de chamada de evento determinam nomes de arquivo, conteúdo e caminhos de entrega](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names). |
| `<yyyymmdd_0_child ID>` | Este é o nome do arquivo. Consulte [Convenções de nomenclatura para arquivos de metadados](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Tempos e atualizações de processamento de arquivo {#processing-times}

Os arquivos de metadados são processados quatro vezes por dia, em intervalos regulares.

Para atualizar seus registros de metadados, basta enviar um arquivo que contenha novas informações. Não é necessário enviar atualizações completas sempre.
