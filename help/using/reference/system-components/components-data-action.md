---
description: Os componentes de ação de dados incluem Feeds de dados do cliente, o servidor de coleta de dados, os editores SFTP/S 3/HTTP, a Íris e o Servidor de cache de perfil.
seo-description: Os componentes de ação de dados incluem Feeds de dados do cliente, o servidor de coleta de dados, os editores SFTP/S 3/HTTP, a Íris e o Servidor de cache de perfil.
seo-title: Componentes de ação de dados
solution: Audience Manager
title: Componentes de ação de dados
uuid: c 4 c 4 cc 46-8 c 96-4 ef 5-8269-571 cc 5 ac 9276
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Action Components{#data-action-components}

Os componentes de ação de dados incluem Feeds de dados do cliente, o servidor de coleta de dados, os editores SFTP/S 3/HTTP, a Íris e o Servidor de cache de perfil.

<!-- 

c_compact.xml

 -->

Action components are systems and processes that let you move data in and out of [!DNL Audience Manager] and (for the lack of a better phrase) do things with it. These [!DNL Audience Manager] components include:

## Customer Data Feeds (CDF) {#cdf}

[!UICONTROL CDF] são arquivos enviados por hora aos clientes. Eles contêm IDs de usuário juntamente com IDs de segmento associadas, IDs características e outros dados. For more information, see [Customer Data Feed Overview](../../features/cdf-files.md).

## Data Collection Server (DCS) {#dcs}

See [Data Collection Components](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

[!UICONTROL SFTP/S3] Os editores recebem dados sincronizados de ID do [!UICONTROL Outbound Feed Converter]. When these files are ready, the [!UICONTROL SFTP/S3 publishers] send this data to a destination specified by the client. These files contain synchronized ID data with a one-to-many mapping of [!DNL Audience Manager] user IDs (UUID) to:

* ID do dispositivo/IDs do provedor de dados (DPUUID)
* IDs de segmento qualificadas
* IDs de características

[!DNL Audience Manager] os clientes não têm acesso aos recursos que controlam diretamente o [!UICONTROL SFPT/S3 publishers]. Os clientes usam esse serviço indiretamente quando criam e enviam dados para destinos. The [!UICONTROL SFTP/S3] system is, essentially, an automated job process that runs at scheduled intervals.

## IRIS {#iris}

In Greek mythology, [!UICONTROL Iris] is a figure who travels and delivers messages rapidly. [!UICONTROL IRIS] O sistema é um namesake que reflete as características dessa figura do mundo antigo. In modern terms, [!UICONTROL IRIS] is a low-latency, high-frequency cookie synchronization and data transfer service.

[!UICONTROL IRIS] funciona com o mesmo tipo de dados que o [!UICONTROL SFTP/S3] sistema. However, [!UICONTROL IRIS] is different because it sends data to destinations in real time rather than at set intervals. This is a separate system because the [!UICONTROL SFTP/S3] publishers can't send data to an HTTP destination and they're not designed for real-time data transfers.

There are no UI controls that let customers work directly with [!UICONTROL IRIS]. Customers work with [!UICONTROL IRIS] indirectly when they create and send data to destinations, and for other processes that require rapid data transfers.

Examples of [!UICONTROL IRIS] services and features include:

* Fornecer sincronização rápida (dentro de 30 segundos) para cookies e segmentos. It can synchronize the [!DNL Audience Manager] cookie, partner cookies, or both.
* Transferências de dados em tempo real. [!UICONTROL IRIS] é responsável por enviar eventos de qualificação de segmento em tempo real a um parceiro ou outro destino. This data is JSON-formatted and sent via an HTTP `POST` request.

* Bulk server-to-server data transfers: If you exchange large amounts of data with [!DNL Audience Manager], [!UICONTROL IRIS] is the system that your servers engage with to transfer data.

* Infraestrutura confiável que funciona em escala e é tolerante de falhas. Systems that power [!UICONTROL IRIS] include Amazon SQS, Amazon EC2, and Cassandra.

**Regras de mapeamento de segmento**

To optimize traffic between [!UICONTROL IRIS] and segment destinations, [!UICONTROL IRIS] sends segments to destinations based on a set of rules.

1. **Nova qualificação de segmento**: quando um dispositivo é qualificado para um novo segmento, [!UICONTROL IRIS] envia todos os segmentos associados a esse dispositivo para todos os destinos mapeados para esses segmentos.

1. **Nova desqualificação de segmento**: quando um dispositivo não é mais qualificado para um segmento, [!UICONTROL IRIS] envia todas as qualificações e desqualificações de segmento associadas a esse dispositivo para todos os destinos mapeados para esses segmentos.

1. **Atualizações de mapeamento de destino**: quando um mapeamento de destino é atualizado, [!UICONTROL IRIS] envia todos os segmentos associados a um dispositivo para todos os destinos mapeados para esses segmentos, na próxima vez que o Audience Manager visualizar o dispositivo.

1. **Atualizações do gráfico de dispositivos**: quando qualquer ID de dispositivo é adicionada ou removida do gráfico de dispositivos usado para avaliar um segmento, [!UICONTROL IRIS] envia todos os segmentos associados a esse dispositivo para todos os destinos mapeados para esses segmentos, na próxima vez que o Audience Manager visualizar o dispositivo.

>[!IMPORTANT]
>
>If Audience Manager doesn't detect any of the updates above for 3 consecutive days, [!UICONTROL IRIS] sends all segments associated to a device to all of the destinations mapped to these segments, the next time Audience Manager sees the device.

**Arquivo de dados de amostra**

The following example contains real-time segment data from [!UICONTROL IRIS]. Lembre-se apenas de dados de amostra. Cada cliente pode ter requisitos de formatação diferentes para que o conteúdo possa variar.

```
{
    "ProcessTime": "Tue Jul 21 19:12:45 UTC 2015",
    "Client_ID": "111111",
    "AAM_Destination_Id": "22222",
    "User_count": "5",
    "Users": [
        {
            "AAM_UUID": "28272096202945091600036434734793744071",
            "DataPartner_UUID": "CAESEFdv5pk-Lurd8vL9Yfb3qFg",
            "Segments": [
                {
                    "Segment_ID": "1200598",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:12 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "35183292386788708387827965829455926157",
            "DataPartner_UUID": "CAESEF_d8blvZjchQ2WTzdB65yk",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:15 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "28012470144260632050402316345856327572",
            "DataPartner_UUID": "CAESEEPfHBiRjhkzvBPXQ-0MFRE|UzCESAAABOnFeHJy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:33 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "18981483751565214534184221210627150539",
            "DataPartner_UUID": "CAK4NDH0ESEE6NBEhoWDkB7s7ZY|VPYFQQAAASXPElL0",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:36 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "04761851136483019318109155624251711702",
            "DataPartner_UUID": "CAESEDkM5aSaKMV8MfaBhgSspmE|VYnTNwAAASzvVhxy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:42 UTC 2015"
                }
            ]
        }
    ]
}
```

## Profile Cache Server (PCS) {#pcs}

See [Data Collection Components](../../reference/system-components/components-data-collection.md).
