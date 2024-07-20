---
description: Descubra as vantagens, os tipos e os usos dos destinos — qualquer sistema de terceiros, como um servidor de anúncios ou DSP, em que você compartilha dados. Use o Construtor de destino para criar e gerenciar cookies, URLs ou destinos de servidor para servidor.
keywords: código de integração, destino, visão geral do destino, destino, destino, destino, destino, destino, destino, destino, destino, destino, destino, destino, destino
landing-page-description: Descubra as vantagens, os tipos e os usos dos destinos — qualquer sistema de terceiros, como um servidor de anúncios ou DSP, em que você compartilha dados. Use o Construtor de destino para criar e gerenciar cookies, URLs ou destinos de servidor para servidor.
short-description: Descubra as vantagens, os tipos e os usos dos destinos — qualquer sistema de terceiros, como um servidor de anúncios ou DSP, em que você compartilha dados. Use o Construtor de destino para criar e gerenciar cookies, URLs ou destinos de servidor para servidor.
seo-title: Destinations
solution: Audience Manager
title: Destinos
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 20%

---

# Visão geral do [!UICONTROL Destinations] {#destinations}

No Audience Manager, um [!UICONTROL destination] é qualquer sistema de terceiros (servidor de anúncios, [!DNL DSP], rede de anúncios etc.) com o qual você deseja compartilhar dados. [!UICONTROL Destination Builder] é a ferramenta que você usou para criar e gerenciar [!UICONTROL cookie], [!DNL URL] ou [!UICONTROL server-to-server destinations].

## Finalidade e vantagens {#purposes}

<!-- c_destinations.xml -->

O [!UICONTROL Destinations] e o [!UICONTROL Destination Builder] permitem criar o [!UICONTROL destinations] e enviar informações sobre usuários segmentados para seu parceiro de dados. Isso ajuda a:

* **Valor de dados do Protect:** Em vez de enviar todos os dados do usuário para um [!UICONTROL destination], o [!UICONTROL Destination Builder] permite que você compartilhe informações específicas somente sobre usuários qualificados.
* **Tome providências em relação aos seus dados:** O envio de dados a um parceiro [!UICONTROL destination] ajuda-o a desenvolver e direcionar rapidamente segmentos de público-alvo qualificados.
* **Reduza as despesas gerais técnicas:** os usuários empresariais podem configurar o [!UICONTROL destinations] com segurança na interface do [!UICONTROL Destination Builder]. Isso ajuda a reduzir o tempo necessário para testes pré-implantação. Com o [!UICONTROL Destination Builder], você cria, gerencia e exclui o [!UICONTROL destinations] à medida que suas necessidades empresariais mudam, tudo sem ter que trabalhar em um longo ciclo de desenvolvimento.

## Considerações técnicas {#technical-considerations}

<!-- destination-delivery-methods.xml -->

A entrega de dados depende de como seu parceiro de dados deseja ou pode receber informações do [!UICONTROL destination]. Restrições técnicas ou de engenharia podem impedir que um [!UICONTROL destination] receba dados por meio de processos [!DNL URL], [!UICONTROL cookie] ou [!UICONTROL server-to-server]. Trabalhe com seu parceiro de terceiros para determinar qual método eles podem usar.

## Considerações comerciais {#business-considerations}

As decisões comerciais para escolher um método de entrega em vez de outro dependem das capacidades técnicas do parceiro [!UICONTROL destination] e do que você deseja fazer com as informações de usuário qualificado. Por exemplo, restrições técnicas podem limitar suas opções se um [!UICONTROL destination] não puder receber dados por um método de entrega específico. No entanto, se não houver problemas técnicos, você poderá enviar informações com base em como deseja agir com esses dados. Por exemplo:

* [!DNL URL]s e [!UICONTROL cookie-based destinations] funcionam quase de forma síncrona com as ações do usuário em uma página.
* Os métodos [!UICONTROL Server-to-server] são bons para criar segmentos profundos de público-alvo ao longo do tempo.

## [!UICONTROL Destination] Tipos e usos típicos {#destination-types}

Os exemplos na tabela a seguir podem ajudá-lo a entender quando usar um [!UICONTROL destination] específico e as diferenças entre cada tipo.

| [!UICONTROL Destination] Tipo | Normalmente Usado Quando | Exemplo | Considerações |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | É necessário enviar dados para outras soluções da Adobe Experience Cloud. | Envio de dados para o Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Você precisa enviar segmentos de público-alvo para ambientes baseados em pessoas, como o Facebook. | Entrega de ofertas personalizadas a clientes existentes, com base em seu histórico de compras | O direcionamento de público é feito por meio de identificadores com hash. Consulte [Destinos com base em pessoas](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Servidor para servidor**) | <ul><li>A transferência imediata de dados não é necessária.</li><li>Coleta de dados para criar um grande pool de públicos-alvo de usuários qualificados.</li></ul> | Coleta de dados ao longo do tempo (horas ou dias) para usá-los em uma campanha definida para execução em uma data posterior. | <ul><li>Transfere dados sobre visitantes novos e anteriores do site. </li><li>Os visitantes não precisam ser vistos novamente para se qualificarem para outros segmentos.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** ou **Cookie**) | Você precisa transferir os dados imediatamente para que um destino possa agir em um usuário qualificado imediatamente. | Envio de dados de um site de compra de tíquetes. Use um [!UICONTROL URL] ou [!UICONTROL cookie destination] para qualificar usuário e imediatamente redirecionar. | <ul><li>Transfere dados somente sobre novos visitantes. </li><li>Os visitantes devem ser vistos novamente para se qualificarem para o segmento.</li></ul> |
