---
description: O Construtor de destinos permite criar destinos de URL DNL ou com base em cookies. Não é possível criar destinos S2S (servidor para servidor) com o Construtor de destinos, mas você pode gerenciar os mapeamentos de segmentos deles. Entre em contato com o consultor da para configurar um destino S2S. O Construtor de destinos está localizado em Dados de público-alvo > Destinos.
seo-description: Destination Builder lets you create cookie-based or DNL URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-title: Destination Builder
solution: Audience Manager
title: Construtor de destinos
feature: Destination Basics
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 4%

---

# Construtor de destinos {#destination-builder}

[!UICONTROL Destination Builder] permite criar ou configurações baseadas em cookies [!DNL URL] destinos. Não é possível criar relatórios de servidor para servidor ([!DNL S2S]) destinos com [!UICONTROL Destination Builder], mas você pode gerenciar os mapeamentos de segmento. Entre em contato com seu consultor para configurar um [!DNL S2S] destino. [!UICONTROL Destination Builder] está localizado em **[!UICONTROL Audience Data > Destinations]**.

## Configurações do Construtor de destinos {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] O consiste nas seguintes seções e configurações:

| [!UICONTROL Destination Builder] Seção | Propósito |
|--- |--- |
| Informações básicas | Usado para nomear o destino, descrevê-lo e selecionar o tipo de destino ([!DNL URL] ou [!DNL cookie]) e plataforma (todos, [!DNL Android], navegador ou [!DNL iOS]). |
| Configuração | Inclui controles para: <br/><ul><li>Transmissão de dados de valor-chave para [!DNL URL] destinos. Você pode enviar dados como pares de valores-chave individuais ou serializados. Para obter mais detalhes, consulte [Serialização de destino](../../features/destinations/key-value-pairs.md#destination-serialized) e [Pares padrão e de valor-chave serial](../../features/destinations/key-value-pairs.md). </li><li>Elementos de um destino de cookie, como nome do cookie, domínio, tamanho, intervalo de expiração, formato de dados etc.</li></ul> |
| Mapeamentos de segmentos | Permite: <br/><ul><li>Procure, adicione e gerencie segmentos associados a todos os tipos de destino. </li><li>Definir prioridades de entrega em segmentos individuais (para [!DNL cookie]somente segmentos com base em ).</li></ul> |

## Métodos de delivery de dados {#data-delivery-methods}

Enviar informações a um destino fazendo o seu envio por meio de uma [!DNL URL] string, gravando em um navegador [!DNL cookie]ou por meio de transferências de dados offline de servidor para servidor.

* [!DNL URL] Os destinos com base em cookies transmitem dados de forma síncrona, conforme um usuário age em uma página.
* A transmissão de dados de servidor para servidor é assíncrona e pode ocorrer muito depois que um usuário sai da página. O tipo de delivery selecionado depende dos requisitos da empresa e de como um parceiro de dados específico deseja ou pode receber dados.

Consulte [Como escolher um tipo de destino](../../features/destinations/destinations.md) para obter mais informações.
