---
description: Os componentes da coleta de dados incluem os Servidores de coleta de dados, a API do DIL, as transferências de dados de servidor para servidor de entrada e os arquivos de log.
seo-description: Os componentes da coleta de dados incluem os Servidores de coleta de dados, a API do DIL, as transferências de dados de servidor para servidor de entrada e os arquivos de log.
seo-title: Componentes da coleção de dados
solution: Audience Manager
title: Componentes da coleção de dados
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: System Components
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 7%

---

# Componentes da coleção de dados{#data-collection-components}

Os componentes da coleta de dados incluem os Servidores de coleta de dados, a API do DIL, as transferências de dados de servidor para servidor de entrada e os arquivos de log.

<!-- 

c_compcollect.xml

 -->

O Audience Manager contém os seguintes componentes de coleta de dados:

* [Servidores de coleta de dados (DCS) e PCS (Profile Cache Servers)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Biblioteca da integração de dados (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Servidor para servidor de entrada](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Arquivos de registro](../../reference/system-components/components-data-collection.md#log-files)

## Servidores de coleta de dados (DCS) e PCS (Profile Cache Servers) {#dcs-pcs}

O DCS e o PCS trabalham juntos e fornecem separadamente serviços relacionados à realização de características, segmentação de público-alvo e armazenamento de dados.

**[!UICONTROL Data Collection Servers (DCS)]Função**

Em [!DNL Audience Manager], o DCS:

* Recebe e avalia dados de características de uma chamada de evento. Isso inclui informações usadas para segmentação em tempo real e dados transmitidos em intervalos agendados por transferências de servidor para servidor.
* Segmenta os usuários com base em suas características realizadas e nas regras de qualificação criadas com o [Construtor de segmentos](../../features/segments/segment-builder.md).
* Cria e gerencia IDs de dispositivo e IDs de perfil autenticadas. Isso inclui identificadores como IDs do provedor de dados, IDs de usuário, IDs declaradas, códigos de integração etc.
* Verifica se o PCS tem características adicionais que um usuário já percebeu antes de uma chamada de evento em tempo real. Isso permite que o DCS qualifique usuários com base em dados em tempo real e dados históricos.
* Grava arquivos de log e os envia para sistemas de análise para armazenamento e processamento.

**[!DNL DCS]Gerencia a demanda por meio de[!UICONTROL Global Server Load Balancing (GSLB)]**

O [!DNL DCS] é um sistema distribuído geograficamente e com balanceamento de carga. Isso significa que [!DNL Audience Manager] pode direcionar solicitações de e para um data center regional com base na localização geográfica de um visitante do site. Essa estratégia ajuda a melhorar os tempos de resposta, pois uma resposta [!DNL DCS] vai diretamente para um data center que contém informações sobre esse visitante. [!UICONTROL GSLB] O torna nosso sistema eficiente, pois os dados relevantes são armazenados em cache nos servidores mais próximos do usuário.

>[!IMPORTANT]
>
>O [!DNL DCS] detecta apenas o tráfego da Web originário de dispositivos que usam IPv4.

Em uma chamada de evento, a localização geográfica é capturada em um par de valores chave retornado em um corpo maior de dados JSON. Esse par de valor-chave é o parâmetro `"dcs_region": region ID`.

![](assets/dcs-map.png)

Como cliente, você interage com o [!DNL DCS] indiretamente por meio de nosso código de coleta de dados. Você também pode trabalhar diretamente com o [!DNL DCS] por meio de um conjunto de APIs. Consulte [Métodos API do Data Collection Server (DCS) e Código](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

O [!UICONTROL PCS] é um banco de dados grande (basicamente, um cookie enorme do lado do servidor). Ele armazena dados recebidos para usuários ativos de transferências de servidor para servidor e do [!DNL DCS]. Os dados do [!UICONTROL PCS] consistem em IDs de dispositivo, IDs de perfil autenticadas e suas características associadas. Quando o [!DNL DCS] recebe uma chamada em tempo real, ele verifica o [!UICONTROL PCS] quanto a outras características que um usuário pode pertencer ou se qualificar. E, se uma característica for adicionada a um segmento posteriormente, essas IDs de característica serão adicionadas ao [!UICONTROL PCS] e os usuários poderão se qualificar para esse segmento automaticamente, sem uma visita a um site ou aplicativo específico. O [!UICONTROL PCS] ajuda a aprofundar a compreensão de [!DNL Audience Manager] seus usuários, pois pode corresponder e segmentar os usuários em tempo real ou em segundo plano com dados de características novos e históricos. Esse comportamento oferece uma imagem mais completa e precisa de seus usuários do que apenas de qualificações em tempo real.

Não há controles de interface do usuário que permitam que nossos clientes trabalhem diretamente com o [!UICONTROL PCS]. O acesso do cliente ao [!UICONTROL PCS] é indireto, por meio de sua função de armazenamento de dados e transferências de dados. O [!UICONTROL PCS] é executado no Apache Cassandra.

**Remoção de IDs inativas do[!UICONTROL PCS]**

Conforme indicado anteriormente, o [!UICONTROL PCS] armazena IDs de características para usuários ativos. Um usuário ativo é qualquer usuário que tenha sido visto pelos [servidores de dados de borda](../../reference/system-components/components-edge.md) de qualquer domínio durante os últimos 14 dias. Essas chamadas para [!UICONTROL PCS] mantêm um usuário em um estado ativo:

* [!DNL /event] chamadas
* [!DNL /ibs] chamadas (sincronizações de ID)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

O [!UICONTROL PCS] libera características se elas estiverem inativas por 17 dias. No entanto, essas características não são perdidas. Eles estão armazenados no Hadoop. Se o usuário for visto novamente em outro momento, o Hadoop enviará todas as suas características para [!UICONTROL PCS], normalmente em um período de 24 horas.

**Outros  [!UICONTROL DCS/PCS] processos: Opção de rejeição de privacidade**

Esses sistemas de servidor lidam com solicitações de privacidade e de recusa do usuário. As informações do cookie do usuário não são coletadas no arquivo de log se um usuário recusou a coleta de dados. Para obter mais informações sobre nossas políticas de privacidade, consulte o [Centro de privacidade do Adobe](https://www.adobe.com/pt/privacy/advertising-services.html).

## Consulte da Biblioteca de integração de dados (DIL) {#dil}

[!UICONTROL DIL] é o código inserido na página para a coleta de dados. Consulte a [API do DIL](../../dil/dil-overview.md) para obter mais informações sobre os serviços e métodos disponíveis.

## Servidor para servidor de entrada {#inbound-outbound-server}

Esses são sistemas que recebem dados enviados por várias integrações de servidor para servidor com nossos clientes. Consulte a documentação sobre [envio de dados de público-alvo](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) para obter mais informações.

## Arquivos de Log {#log-files}

O [!UICONTROL PCS] cria e grava dados nos arquivos de log. Elas são enviadas para outros sistemas de banco de dados para processamento, relatórios e armazenamento.

>[!MORELIKETHIS]
>
>* [Centro de privacidade da Adobe](https://www.adobe.com/br/privacy.html)

