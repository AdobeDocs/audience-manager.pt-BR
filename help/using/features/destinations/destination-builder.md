---
description: O Construtor de destinos permite criar destinos de cookies com base em cookies ou DNL. Não é possível criar destinos de servidor para servidor (S 2 S) com o Construtor de destinos, mas você pode gerenciar seus mapeamentos de segmento. Entre em contato com seu consultor para configurar um destino S 2 S. Construtor de destinos está localizado em Dados de público-alvo > Destinos.
seo-description: O Construtor de destinos permite criar destinos de cookies com base em cookies ou DNL. Não é possível criar destinos de servidor para servidor (S 2 S) com o Construtor de destinos, mas você pode gerenciar seus mapeamentos de segmento. Entre em contato com seu consultor para configurar um destino S 2 S. Construtor de destinos está localizado em Dados de público-alvo > Destinos.
seo-title: Construtor de destinos
solution: Audience Manager
title: Construtor de destinos
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---


# Construtor de destinos {#destination-builder}

[!UICONTROL Destination Builder] permite criar os destinos com [!DNL URL] base em cookies. Não é possível criar destinos de servidor para servidor ([!DNL S2S]) com [!UICONTROL Destination Builder], mas você pode gerenciar seus mapeamentos de segmento. Entre em contato com seu consultor para configurar um [!DNL S2S] destino. [!UICONTROL Destination Builder] está localizado **[!UICONTROL Audience Data > Destinations]**.

## Configurações do Construtor de Destino {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] consiste nas seguintes seções e configurações:

| [!UICONTROL Destination Builder] Seção | Propósito |
|--- |--- |
| Informações básicas | Usado para nomear o destino, descrevê-lo e selecionar o tipo de destino ([!DNL URL] ou [!DNL cookie]) e a plataforma (tudo [!DNL Android], navegador ou [!DNL iOS]). |
| Configuração | Inclui controles para: <br/><ul><li>Passar dados de valor chave para [!DNL URL] destinos. É possível enviar dados como pares de valor chave individuais ou serializados. Para obter detalhes, consulte Serialização [de destino](../../features/destinations/key-value-pairs.md#destination-serialized) e [Pares](../../features/destinations/key-value-pairs.md)de valores-chave padrão e padrão. </li><li>Elementos de um destino de cookie, como nome do cookie, domínio, tamanho, intervalo de expiração, formato de dados etc.</li></ul> |
| Mapeamentos de segmento | Permite: <br/><ul><li>Pesquise, adicione e gerencie segmentos associados a todos os tipos de destino. </li><li>Defina as prioridades de entrega em segmentos individuais (apenas para [!DNL cookie]segmentos com base em -).</li></ul> |

## Métodos de entrega de dados {#data-delivery-methods}

Envie informações para um destino passando-o por meio de [!DNL URL] uma sequência de caracteres, gravando em um navegador [!DNL cookie]ou por meio de transferências de dados de servidor a servidor.

* [!DNL URL] e os destinos baseados em cookies transmitem dados sincronicamente, à medida que um usuário executa uma ação em uma página.
* A transmissão de dados de servidor para servidor é assíncrona e pode ocorrer long depois que um usuário saiu da página. O tipo de entrega selecionado depende dos seus requisitos de negócios e de como um parceiro de dados específico deseja, ou pode, receber dados.

Consulte [Como escolher um tipo de destino](../../features/destinations/destinations.md) para obter mais informações.