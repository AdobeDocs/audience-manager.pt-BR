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
source-wordcount: '268'
ht-degree: 1%

---

# Construtor de destinos {#destination-builder}

[!UICONTROL Destination Builder] permite criar destinos com base em cookies ou [!DNL URL]. Não é possível criar destinos servidor a servidor ([!DNL S2S]) com [!UICONTROL Destination Builder], mas você pode gerenciar os mapeamentos de segmentos. Contate seu consultor para configurar um destino do [!DNL S2S]. [!UICONTROL Destination Builder] está localizado em **[!UICONTROL Audience Data > Destinations]**.

## Configurações do Construtor de destinos {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] consiste nas seguintes seções e configurações:

| Seção [!UICONTROL Destination Builder] | Propósito |
|--- |--- |
| Informações básicas | Usado para nomear o destino, descrevê-lo e selecionar o tipo de destino ([!DNL URL] ou [!DNL cookie]) e a plataforma (todos, [!DNL Android], navegador ou [!DNL iOS]). |
| Configuração | Inclui controles para: <br/><ul><li>Passando dados de valor-chave para [!DNL URL] destinos. Você pode enviar dados como pares de valores-chave individuais ou serializados. Para obter detalhes, consulte [Serialização de Destino](../../features/destinations/key-value-pairs.md#destination-serialized) e [Pares de Valor-Chave Padrão e Serial](../../features/destinations/key-value-pairs.md). </li><li>Elementos de um destino de cookie, como nome do cookie, domínio, tamanho, intervalo de expiração, formato de dados etc.</li></ul> |
| Mapeamentos de segmentos | Permite a você: <br/><ul><li>Procure, adicione e gerencie segmentos associados a todos os tipos de destino. </li><li>Defina as prioridades de entrega em segmentos individuais (somente para segmentos baseados em [!DNL cookie]).</li></ul> |

## Métodos de delivery de dados {#data-delivery-methods}

Envie informações para um destino passando-as por uma cadeia de caracteres [!DNL URL], gravando em um navegador [!DNL cookie] ou por meio de transferências de dados offline de servidor para servidor.

* [!DNL URL] e destinos com base em cookies transmitem dados de forma síncrona, conforme um usuário age em uma página.
* A transmissão de dados de servidor para servidor é assíncrona e pode ocorrer muito depois que um usuário sai da página. O tipo de delivery selecionado depende dos requisitos da empresa e de como um parceiro de dados específico deseja ou pode receber dados.

Consulte [Como Escolher um Tipo de Destino](../../features/destinations/destinations.md) para obter mais informações.
