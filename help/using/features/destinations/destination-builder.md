---
description: O Construtor de destino permite criar destinos de URL DNL ou baseados em cookies. Não é possível criar destinos de servidor para servidor (S2S) com o Construtor de destinos, mas você pode gerenciar seus mapeamentos de segmentos. Entre em contato com seu consultor para configurar um destino S2S. O Construtor de destinos está localizado em Dados de Audiência > Destinos.
seo-description: O Construtor de destino permite criar destinos de URL DNL ou baseados em cookies. Não é possível criar destinos de servidor para servidor (S2S) com o Construtor de destinos, mas você pode gerenciar seus mapeamentos de segmentos. Entre em contato com seu consultor para configurar um destino S2S. O Construtor de destinos está localizado em Dados de Audiência > Destinos.
seo-title: Construtor de destinos
solution: Audience Manager
title: Construtor de destinos
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 4%

---


# Construtor de destinos {#destination-builder}

[!UICONTROL Destination Builder] permite que você crie destinos ou baseados em cookies [!DNL URL] . Não é possível criar destinos de servidor para servidor ([!DNL S2S]) com [!UICONTROL Destination Builder], mas é possível gerenciar seus mapeamentos de segmento. Entre em contato com seu consultor para configurar um [!DNL S2S] destino. [!UICONTROL Destination Builder] está localizado em **[!UICONTROL Audience Data > Destinations]**.

## Configurações do Construtor de destinos {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] consiste nas seguintes seções e configurações:

| [!UICONTROL Destination Builder] Seção | Propósito |
|--- |--- |
| Informações básicas | Usado para nomear o destino, descrevê-lo e selecionar o tipo de destino ([!DNL URL] ou [!DNL cookie]) e a plataforma (tudo, [!DNL Android], navegador ou [!DNL iOS]). |
| Configuração | Inclui controles para: <br/><ul><li>Transmissão de dados de valor chave para [!DNL URL] destinos. É possível enviar dados como pares de valores chave individuais ou serializados. Para obter detalhes, consulte Serialização [de](../../features/destinations/key-value-pairs.md#destination-serialized) Destino e Pares [](../../features/destinations/key-value-pairs.md)padrão e de valor de chave serial. </li><li>Elementos de um destino de cookie, como nome do cookie, domínio, tamanho, intervalo de expiração, formato de dados etc.</li></ul> |
| Mapeamentos de segmentos | Permite: <br/><ul><li>Procure, adicione e gerencie segmentos associados a todos os tipos de destino. </li><li>Defina prioridades do delivery em segmentos individuais (somente para segmentos [!DNL cookie]baseados).</li></ul> |

## Métodos de Delivery de dados {#data-delivery-methods}

Envie informações para um destino transmitindo-as por meio de uma [!DNL URL] sequência de caracteres, gravando em um navegador [!DNL cookie]ou por meio de transferências de dados offline de servidor para servidor.

* [!DNL URL] e os destinos baseados em cookies transmitem os dados de forma síncrona, à medida que o usuário age em uma página.
* A transmissão de dados de servidor para servidor é assíncrona e pode ocorrer muito depois que um usuário sai da página. O tipo de delivery selecionado depende de seus requisitos comerciais e de como um determinado parceiro de dados deseja ou pode receber dados.

Consulte [Como escolher um tipo](../../features/destinations/destinations.md) de destino para obter mais informações.