---
description: Os componentes da coleta de dados incluem os Servidores de coleta de dados, a API de DIL, as transferências de dados de entrada de servidor para servidor e os arquivos de log.
seo-description: Data collection components include the Data Collection Servers, the DIL API, inbound server-to-server data transfers, and log files.
seo-title: Data Collection Components
solution: Audience Manager
title: Componentes da coleção de dados
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: System Components
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 6%

---

# Componentes da coleção de dados{#data-collection-components}

Os componentes da coleta de dados incluem os Servidores de coleta de dados, a API de DIL, as transferências de dados de entrada de servidor para servidor e os arquivos de log.

<!-- 

c_compcollect.xml

 -->

Audience Manager contém os seguintes componentes de coleção de dados:

* [Servidores de coleta de dados (DCS) e Servidores de cache de perfil (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Biblioteca da integração de dados (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Servidor de entrada para servidor](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Arquivos de log](../../reference/system-components/components-data-collection.md#log-files)

## Servidores de coleta de dados (DCS) e Servidores de cache de perfil (PCS) {#dcs-pcs}

O DCS e o PCS trabalham juntos e separadamente fornecem serviços relacionados à realização de características, segmentação de público e armazenamento de dados.

**[!UICONTROL Data Collection Servers (DCS)]Função**

Entrada [!DNL Audience Manager], o DCS:

* Recebe e avalia dados de características de uma chamada de evento. Isso inclui informações usadas para segmentação em tempo real e dados transmitidos em intervalos programados por transferências de servidor para servidor.
* Segmenta usuários com base em suas características realizadas e nas regras de qualificação criadas com [Construtor de segmentos](../../features/segments/segment-builder.md).
* Cria e gerencia IDs de dispositivo e IDs de perfil autenticadas. Isso inclui identificadores como IDs de provedor de dados, IDs de usuário, IDs declaradas, códigos de integração etc.
* Verifica se há características adicionais no PCS que um usuário já tenha percebido antes de uma chamada de evento em tempo real. Isso permite que o DCS qualifique usuários com base em dados em tempo real e dados históricos.
* Grava arquivos de log e os envia para sistemas de análise para armazenamento e processamento.

**[!DNL DCS]Gerencia A Demanda Por Meio De[!UICONTROL Global Server Load Balancing (GSLB)]**

A variável [!DNL DCS] O é um sistema distribuído geograficamente e com balanceamento de carga. Isso significa [!DNL Audience Manager] O pode direcionar solicitações de e para um data center regional com base na localização geográfica de um visitante do site. Essa estratégia ajuda a melhorar os tempos de resposta, pois uma [!DNL DCS] A resposta do vai diretamente para um data center que contém informações sobre esse visitante. [!UICONTROL GSLB] O torna nosso sistema eficiente, pois os dados relevantes são armazenados em cache nos servidores mais próximos do usuário.

>[!IMPORTANT]
>
>A variável [!DNL DCS] O detecta apenas o tráfego da Web originado de dispositivos que usam IPv4.

Em uma chamada de evento, a localização geográfica é capturada em um par de valores chave retornado em um corpo maior de dados JSON. Esse par de valor-chave é o `"dcs_region": region ID` parâmetro.

![](assets/dcs-map.png)

Como cliente, você interage com a [!DNL DCS] indiretamente por meio de nosso código de coleta de dados. Você também pode trabalhar diretamente com o [!DNL DCS] por meio de um conjunto de APIs. Consulte [Métodos e código API do Data Collection Server (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

A variável [!UICONTROL PCS] O é um banco de dados grande (basicamente, um cookie enorme do lado do servidor). Ele armazena dados recebidos para usuários ativos de transferências de servidor para servidor e do [!DNL DCS]. Os dados do [!UICONTROL PCS] consistem em IDs de dispositivo, IDs de perfil autenticadas e suas características associadas. Quando a variável [!DNL DCS] recebe uma chamada em tempo real, ele verifica o [!UICONTROL PCS] para outras características às quais um usuário pode pertencer ou se qualificar. E, se uma característica for adicionada a um segmento posteriormente, essas IDs de característica serão adicionadas ao [!UICONTROL PCS] e os usuários podem se qualificar para esse segmento automaticamente, sem uma visita a um site ou aplicativo específico. A variável [!UICONTROL PCS] ajuda a aprofundar [!DNL Audience Manager]O compreende seus usuários porque pode corresponder e segmentar usuários em tempo real ou nos bastidores com dados de características novos e históricos. Esse comportamento oferece uma imagem mais completa e precisa dos usuários do que apenas das qualificações em tempo real.

Não há controles de interface do usuário que permitam que nossos clientes trabalhem diretamente com a [!UICONTROL PCS]. Acesso do cliente à [!UICONTROL PCS] é indireta, por meio de sua função como armazenamento de dados e transferências de dados. A variável [!UICONTROL PCS] O programa é executado no Apache Cassandra.

**Remoção de IDs inativas do[!UICONTROL PCS]**

Tal como indicado anteriormente, a [!UICONTROL PCS] O armazena IDs de características para usuários ativos. Um usuário ativo é qualquer usuário que tenha sido visto pelo [servidores de dados de borda](../../reference/system-components/components-edge.md) de qualquer domínio durante os últimos 14 dias. Essas chamadas para o [!UICONTROL PCS] manter um usuário no estado ativo:

* [!DNL /event] chamadas
* [!DNL /ibs] chamadas (sincronizações de ID)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

A variável [!UICONTROL PCS] O libera as características se estiverem inativas por 17 dias. No entanto, essas características não são perdidas. Eles são armazenados no Hadoop. Se o usuário for visto novamente em outro momento, o Hadoop enviará todas as suas características de volta para o [!UICONTROL PCS], normalmente em um período de 24 horas.

**Outro [!UICONTROL DCS/PCS] Processos: recusa de privacidade**

Esses sistemas de servidor lidam com privacidade e solicitações de recusa do usuário. As informações de cookie do usuário não serão coletadas no arquivo de log se um usuário optar por não participar da coleta de dados. Para obter mais informações sobre nossas políticas de privacidade, consulte [Centro de privacidade do Adobe](https://www.adobe.com/pt/privacy/advertising-services.html).

## Biblioteca de integração de dados (DIL) {#dil}

[!UICONTROL DIL] é o código que você insere na página para a coleta de dados. Consulte a [API DIL](../../dil/dil-overview.md) para obter mais informações sobre serviços e métodos disponíveis.

## Servidor de entrada para servidor {#inbound-outbound-server}

Esses são sistemas que recebem dados enviados por várias integrações servidor a servidor com nossos clientes. Consulte a documentação em [envio de dados de público](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) para obter mais informações.

## Arquivos de log {#log-files}

A variável [!UICONTROL PCS] cria e grava dados nos arquivos de log. Elas são enviadas para outros sistemas de banco de dados para processamento, emissão de relatórios e armazenamento.

>[!MORELIKETHIS]
>
>* [Centro de privacidade da Adobe](https://www.adobe.com/br/privacy.html)

