---
description: Os componentes de coleção de dados incluem os servidores de coleta de dados, a API DIL, transferências de dados de servidor a servidor e arquivos de log.
seo-description: Os componentes de coleção de dados incluem os servidores de coleta de dados, a API DIL, transferências de dados de servidor a servidor e arquivos de log.
seo-title: Componentes da coleção de dados
solution: Audience Manager
title: Componentes da coleção de dados
uuid: 51 bb 1719-5 ff 2-4 bc 7-8 eb 1-98795 e 05 d 08 f
translation-type: tm+mt
source-git-commit: 0b9da38fd8b999637bdf6c3fe6af8aa2426eb6ae

---


# Data Collection Components{#data-collection-components}

Os componentes de coleção de dados incluem os servidores de coleta de dados, a API DIL, transferências de dados de servidor a servidor e arquivos de log.

<!-- 

c_compcollect.xml

 -->

O Audience Manager contém os seguintes componentes da coleção de dados:

* [Servidores de coleta de dados (DCS) e servidores de cache de perfil (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Biblioteca da integração de dados (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Servidor de entrada para servidor](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Arquivos de registro](../../reference/system-components/components-data-collection.md#log-files)

## Data Collection Servers (DCS) and Profile Cache Servers (PCS) {#dcs-pcs}

O DCS e o PCS trabalham em conjunto e oferecem serviços relacionados à realização de características, à segmentação de público-alvo e ao armazenamento de dados.

**[!UICONTROL Data Collection Servers (DCS)]Função**

In [!DNL Audience Manager], the DCS:

* Recebe e avalia os dados características de uma chamada de evento. Isso inclui informações usadas para segmentação em tempo real e dados passados em intervalos programados por transferências de servidor para servidor.
* Segments users based on their realized traits and the qualification rules you create with [Segment Builder](../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74).
* Cria e gerencia IDs de dispositivo e IDs de perfil autenticado. Isso inclui identificadores como IDs do provedor de dados, IDs do usuário, IDs declaradas, códigos de integração etc.
* Verifica o PCS para características adicionais que um usuário já tenha percebido antes de uma chamada de evento em tempo real. Isso permite que o DCS qualifique os usuários com base em dados em tempo real e dados históricos.
* Grava arquivos de log e envia os arquivos para sistemas de análise para armazenamento e processamento.

**[!UICONTROL DCS]Gerencia demanda por meio[!UICONTROL Global Server Load Balancing (GSLB)]**

The [!UICONTROL DCS] is a geographically distributed and load-balanced system. This means [!DNL Audience Manager] can direct requests to and from a regional data center based on the geographic location of a site visitor. This strategy helps improve response times because a [!UICONTROL DCS] response goes directly to a data center that contains information about that visitor. [!UICONTROL GSLB] torna nosso sistema eficiente, pois os dados relevantes são armazenados em cache em servidores mais próximos do usuário.

>[!IMPORTANT]
>
>The [!UICONTROL DCS] only detects web traffic originating from devices that use IPv4.

Em uma chamada de evento, a localização geográfica é capturada em um par de valores chave retornado em um corpo maior de dados JSON. This key-value pair is the `"dcs_region": region ID` parameter.

![](assets/dcs-map.png)

As a customer, you engage with the [!UICONTROL DCS] indirectly through our data collection code. You can also work directly with the [!UICONTROL DCS] through a set of APIs. See [Data Collection Server (DCS) API Methods and Code](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

The [!UICONTROL PCS] is a large database (basically, a huge server-side cookie). It stores data received for active users from server-to-server transfers and the [!UICONTROL DCS]. [!UICONTROL PCS] são compostos por IDs de dispositivo, IDs de perfil autenticado e características associadas. When the [!UICONTROL DCS] receives a real time call, it checks the [!UICONTROL PCS] for other traits a user may belong to or qualify for. And, if a trait is added to a segment at a later time, those trait IDs are added to the [!UICONTROL PCS] and users can qualify for that segment automatically, without a visit to a particular site or app. The [!UICONTROL PCS] helps deepen [!DNL Audience Manager]'s understanding of your users because it can match and segment users in real time or behind the scenes with new and historic trait data. Esse comportamento oferece uma imagem mais completa e precisa dos usuários do que somente as qualificações em tempo real.

There are no UI controls that lets our customers work directly with the [!UICONTROL PCS]. Customer access to the [!UICONTROL PCS] is indirect, through its role as a data store and data transfers. [!UICONTROL PCS] As execuções no Apache Cassandra.

**Remoção de IDs inativas do[!UICONTROL PCS]**

As indicated previously, the [!UICONTROL PCS] stores trait IDs for active users. An active user is any user who has been seen by the [edge data servers](../../reference/system-components/components-edge.md) from any domain during the last 14-days. These calls to the [!UICONTROL PCS] keep a user in an active state:

* [!DNL /event] calls
* [!DNL /ibs] chamadas (sincronizações de ID)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

The [!UICONTROL PCS] flushes traits if they're inactive for 17-days. Contudo, essas características não são perdidas. Eles são armazenados no Hadoop. If the user is seen again at another time, then Hadoop pushes all of their traits back to the [!UICONTROL PCS], typically within a 24-hour period.

**Outros[!UICONTROL DCS/PCS]processos: Opção de não participação de privacidade**

Esses sistemas de servidor tratam de privacidade e solicitações de não participação do usuário. As informações do cookie do usuário não são coletadas no arquivo de log se um usuário não tiver optado pela coleta de dados. For more information about our privacy policies see the [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

## Biblioteca da integração de dados (DIL) {#dil}

[!UICONTROL DIL] é o código colocado na página para coleção de dados. See the [DIL API](../../dil/dil-overview.md) for more information about available services and methods.

## Inbound Server-to-Server {#inbound-outbound-server}

Esses são sistemas que recebem dados enviados por várias integrações entre servidor e servidor com nossos clientes. See the documentation on [sending audience data](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) for more information.

## Log Files {#log-files}

The [!UICONTROL PCS] creates and writes data to the log files. Eles são enviados para outros sistemas de banco de dados para processamento, relatório e armazenamento.

>[!MORE_ LIKE_ THIS]
>
>* [Centro de privacidade da Adobe](https://www.adobe.com/privacy.html)

