---
description: No Audience Manager, um destino é qualquer sistema de terceiros (servidor de anúncios, DSP, rede de anúncios etc.) com o qual você deseja compartilhar dados. O Construtor de destinos é a ferramenta usada para criar e gerenciar cookies, URL ou destinos de servidor para servidor.
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: No Audience Manager, um destino é qualquer sistema de terceiros (servidor de anúncios, DSP, rede de anúncios etc.) com o qual você deseja compartilhar dados. O Construtor de destinos é a ferramenta usada para criar e gerenciar cookies, URL ou destinos de servidor para servidor.
seo-title: 'Destinos '
solution: Audience Manager
title: 'Destinos '
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 17%

---


# [!UICONTROL Destinations] Visão geral {#destinations}

No Audience Manager, um [!UICONTROL destination] é qualquer sistema de terceiros (servidor de anúncios, [!DNL DSP], rede de anúncios etc.) com o qual você deseja compartilhar dados. [!UICONTROL Destination Builder] é a ferramenta usada para criar e gerenciar  [!UICONTROL cookie],  [!DNL URL]ou  [!UICONTROL server-to-server destinations].

## Propósito e vantagens {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] e  [!UICONTROL Destination Builder] permite que você crie  [!UICONTROL destinations] e envie informações sobre usuários segmentados para seu parceiro de dados. Isso ajuda você a:

* **Valor de dados da Protect:** em vez de enviar todos os dados do usuário para um  [!UICONTROL destination],  [!UICONTROL Destination Builder] permite que você compartilhe informações específicas apenas sobre usuários qualificados.
* **Agir em seus dados:** Enviar dados para um  [!UICONTROL destination] parceiro ajuda-o a desenvolver e público alvo rapidamente segmentos de audiência qualificados.
* **Reduzir as despesas gerais técnicas:Os usuários** empresariais podem configurar  [!UICONTROL destinations] com segurança na  [!UICONTROL Destination Builder] interface. Isso ajuda a reduzir o tempo necessário para testes de pré-implantação. Com [!UICONTROL Destination Builder], você cria, gerencia e exclui [!UICONTROL destinations] conforme suas necessidades de negócios mudam, tudo isso sem trabalhar em um longo ciclo de desenvolvimento.

## Considerações técnicas {#technical-considerations}

<!-- destination-delivery-methods.xml -->

O delivery de dados depende de como seu parceiro de dados deseja ou pode receber informações [!UICONTROL destination]. As restrições técnicas ou de engenharia podem impedir que um [!UICONTROL destination] receba dados por meio de [!DNL URL], [!UICONTROL cookie] ou [!UICONTROL server-to-server] processos. Trabalhe com um parceiro de terceiros para determinar que método eles podem usar.

## Considerações comerciais {#business-considerations}

As decisões de negócios para selecionar um método de delivery em vez de outro dependem dos recursos técnicos do [!UICONTROL destination] parceiro e do que você deseja fazer com as informações qualificadas do usuário. Por exemplo, restrições técnicas podem limitar suas opções se um [!UICONTROL destination] não puder receber dados por um método de delivery específico. No entanto, se não houver problemas técnicos, você poderá enviar informações com base em como deseja tomar medidas nesses dados. Por exemplo:

* [!DNL URL]s e  [!UICONTROL cookie-based destinations] funcionam quase sincronicamente com as ações do usuário em uma página.
* [!UICONTROL Server-to-server] métodos são bons para construir segmentos de audiência profunda ao longo do tempo.

## [!UICONTROL Destination] Tipos e usos comuns  {#destination-types}

Os exemplos na tabela a seguir podem ajudá-lo a entender quando usar um [!UICONTROL destination] específico e as diferenças entre cada tipo.

| [!UICONTROL Destination] Digite | Normalmente Usado Quando | Exemplo | Considerações |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Você precisa enviar dados para outras soluções da Adobe Experience Cloud. | Envio de dados para a Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | É necessário enviar segmentos de audiência para ambientes baseados em pessoas, como o Facebook. | Fornecer ofertas personalizadas aos clientes existentes, com base em seu histórico de compras | O direcionamento de audiência é feito por meio de identificadores com hash. Consulte [Destinos Baseados em Pessoas](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (Servidor **para servidor**) | <ul><li>Não é necessária a transferência imediata de dados.</li><li>Coleta de dados para criar um grande pool de audiências de usuários qualificados.</li></ul> | Coleta de dados ao longo do tempo (horas ou dias) para usá-los em um conjunto de campanhas para execução em uma data posterior. | <ul><li>Transfere dados sobre visitantes do site novos e anteriores. </li><li>Os visitantes não precisam ser vistos novamente para se qualificarem para outros segmentos.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**** URLs ou  **cookie**) | É necessário transferir dados imediatamente para que um destino possa agir imediatamente em um usuário qualificado. | Envio de dados de um site de compra de tíquete. Use [!UICONTROL URL] ou [!UICONTROL cookie destination] para qualificar o usuário e repúblico alvo imediatamente. | <ul><li>Transfere dados somente sobre novos visitantes. </li><li>Os visitantes devem ser vistos novamente para se qualificarem para o segmento.</li></ul> |
