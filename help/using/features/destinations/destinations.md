---
description: No Audience Manager, um destino é qualquer sistema de terceiros (servidor de anúncios, DSP, rede de anúncios etc.) com os quais você deseja compartilhar dados. O Construtor de destinos é a ferramenta usada para criar e gerenciar cookies, URL ou destinos de servidor para servidor.
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: No Audience Manager, um destino é qualquer sistema de terceiros (servidor de anúncios, DSP, rede de anúncios etc.) com os quais você deseja compartilhar dados. O Construtor de destinos é a ferramenta usada para criar e gerenciar cookies, URL ou destinos de servidor para servidor.
seo-title: Destinos
solution: Audience Manager
title: Destinos
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
translation-type: tm+mt
source-git-commit: e141d04201b94bac30cdbe97818cb8eb91ebbaea

---


# Visão geral dos destinos {#destinations}

No Audience Manager, um destino é qualquer sistema de terceiros (servidor de anúncios, rede de anúncios [!DNL DSP]etc.) com os quais você deseja compartilhar dados. [!UICONTROL Destination Builder] é a ferramenta usada para criar e gerenciar cookies [!DNL URL]ou destinos servidor a servidor.

## Propósito e vantagens {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] e [!UICONTROL Destination Builder] permite criar destinos e enviar informações sobre usuários segmentados para seu parceiro de dados. Isso ajuda você a:

* **** Proteger o valor dos dados: Em vez de enviar todos os dados do usuário para um destino, [!UICONTROL Destination Builder] permita que você compartilhe informações específicas apenas sobre usuários qualificados.
* **** Execute ações em seus dados: O envio de dados para um parceiro de destino ajuda a desenvolver e direcionar rapidamente segmentos de público-alvo qualificados.
* **** Reduza a sobrecarga técnica: Os usuários comerciais podem configurar destinos com segurança na [!UICONTROL Destination Builder] interface. Isso ajuda a reduzir o tempo necessário para testes de pré-implantação. Com [!UICONTROL Destination Builder], você cria, gerencia e exclui destinos à medida que suas necessidades comerciais mudam, tudo isso sem trabalhar em um longo ciclo de desenvolvimento.

## Considerações técnicas {#technical-considerations}

<!-- destination-delivery-methods.xml -->

A entrega de dados depende de como seu parceiro de dados deseja ou pode receber informações de destino. As restrições técnicas ou de engenharia podem impedir que um destino receba dados por meio de processos [!DNL URL], cookies ou servidor a servidor. Trabalhe com um parceiro de terceiros para determinar que método eles podem usar.

## Considerações comerciais {#business-considerations}

As decisões de negócios para selecionar um método de entrega em vez de outro dependem dos recursos técnicos do seu parceiro de destino e do que você deseja fazer com informações qualificadas do usuário. Por exemplo, restrições técnicas podem limitar suas opções se um destino não puder receber dados por um método de entrega específico. No entanto, se não houver problemas técnicos, você poderá enviar informações com base em como deseja tomar medidas nesses dados. Por exemplo:

* [!DNL URL]Os destinos com base em cookies e s funcionam quase sincronicamente com as ações do usuário em uma página.
* Os métodos servidor a servidor são bons para construir segmentos profundos do público ao longo do tempo.

## Tipos de destino e usos comuns {#destination-types}

Os exemplos na tabela a seguir podem ajudá-lo a entender quando usar um destino específico e as diferenças entre cada tipo.

| Tipo de destino | Normalmente Usado Quando | Exemplo | Considerações |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | É necessário enviar dados para outras soluções da Adobe Experience Cloud. | Envio de dados para o Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | É necessário enviar segmentos de público-alvo para ambientes baseados em pessoas, como o Facebook. | Fornecer ofertas personalizadas a clientes existentes, com base em seu histórico de compras | O direcionamento de público-alvo é feito por meio de identificadores com hash. Consulte Destinos [baseados em](people-based-destinations-overview.md)pessoas. |
| **[!UICONTROL Device-Based Destinations]**(Servidor** para servidor **) | <ul><li>Não é necessária a transferência imediata de dados.</li><li>Coleta de dados para criar um grande pool de usuários qualificados.</li></ul> | Coletando dados ao longo do tempo (horas ou dias) para usá-los em um conjunto de campanhas para execução em uma data posterior. | <ul><li>Transfere dados sobre visitantes do site novos e anteriores. </li><li>Os visitantes não precisam ser vistos novamente para se qualificarem para outros segmentos.</li></ul> |
| **[!UICONTROL Custom Destinations]**(** URL **ou** cookie **) | É necessário transferir dados imediatamente para que um destino possa agir imediatamente em um usuário qualificado. | Envio de dados de um site de compra de tíquete. Use um URL ou um destino de cookie para qualificar o usuário e redirecionar imediatamente. | <ul><li>Transfere dados somente sobre novos visitantes. </li><li>Os visitantes devem ser vistos novamente para se qualificarem para o segmento.</li></ul> |
