---
description: O Construtor de destinos permite que você crie destinos de URL com base em cookies ou DNL. Não é possível criar destinos de servidor para servidor (S2S) com o Construtor de destinos, mas é possível gerenciar os mapeamentos de segmentos. Entre em contato com seu consultor para configurar um destino S2S. O Construtor de destinos está localizado em Dados de público-alvo > Destinos.
seo-description: O Construtor de destinos permite que você crie destinos de URL com base em cookies ou DNL. Não é possível criar destinos de servidor para servidor (S2S) com o Construtor de destinos, mas é possível gerenciar os mapeamentos de segmentos. Entre em contato com seu consultor para configurar um destino S2S. O Construtor de destinos está localizado em Dados de público-alvo > Destinos.
seo-title: Construtor de destinos
solution: Audience Manager
title: Construtor de destinos
feature: Noções básicas sobre o destino
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 4%

---

# Construtor de destinos {#destination-builder}

[!UICONTROL Destination Builder] permite criar  [!DNL URL] destinos ou com base em cookies. Não é possível criar destinos de servidor para servidor ([!DNL S2S]) com [!UICONTROL Destination Builder], mas é possível gerenciar os mapeamentos de segmento. Entre em contato com seu consultor para configurar um destino [!DNL S2S]. [!UICONTROL Destination Builder] está localizado em  **[!UICONTROL Audience Data > Destinations]**.

## Configurações do Construtor de destinos {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] consiste nas seguintes seções e configurações:

| [!UICONTROL Destination Builder] Seção | Propósito |
|--- |--- |
| Informações básicas | Usado para nomear o destino, descrevê-lo e selecionar o tipo de destino ([!DNL URL] ou [!DNL cookie]) e a plataforma (tudo, [!DNL Android], navegador ou [!DNL iOS]). |
| Configuração | Inclui controles para: <br/><ul><li>Transmitindo dados de valor-chave para destinos [!DNL URL]. Você pode enviar dados como pares de valores-chave individuais ou serializados. Para obter detalhes, consulte [Serialização de destino](../../features/destinations/key-value-pairs.md#destination-serialized) e [Pares padrão e de valor-chave serial](../../features/destinations/key-value-pairs.md). </li><li>Elementos de um destino de cookie, como nome do cookie, domínio, tamanho, intervalo de expiração, formato de dados etc.</li></ul> |
| Mapeamentos de segmento | Permite: <br/><ul><li>Procure, adicione e gerencie segmentos associados a todos os tipos de destino. </li><li>Defina as prioridades do delivery em segmentos individuais (somente para segmentos baseados em [!DNL cookie]).</li></ul> |

## Métodos de entrega de dados {#data-delivery-methods}

Envie informações para um destino, passando-as por uma sequência de caracteres [!DNL URL], gravando em um navegador [!DNL cookie] ou por meio de transferências de dados offline de servidor para servidor.

* [!DNL URL] Os destinos com base em cookies e transmitem dados de forma síncrona, à medida que um usuário age em uma página.
* A transmissão de dados de servidor para servidor é assíncrona e pode ocorrer muito depois que um usuário sai da página. O tipo de delivery selecionado depende de seus requisitos comerciais e de como um determinado parceiro de dados deseja ou pode receber dados.

Consulte [Como escolher um tipo de destino](../../features/destinations/destinations.md) para obter mais informações.
