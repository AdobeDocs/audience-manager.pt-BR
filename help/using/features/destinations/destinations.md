---
description: No Audience Manager, um destino é qualquer sistema de terceiros (servidor de anúncios, DSP, rede de anúncios etc.) que deseja compartilhar dados. Construtor de destinos é a ferramenta usada para criar e gerenciar cookies, URL ou destinos de servidor a servidor.
keywords: código de integração, destino, visão geral de destino
seo-description: No Audience Manager, um destino é qualquer sistema de terceiros (servidor de anúncios, DSP, rede de anúncios etc.) que deseja compartilhar dados. Construtor de destinos é a ferramenta usada para criar e gerenciar cookies, URL ou destinos de servidor a servidor.
seo-title: Destinos
solution: Audience Manager
title: Destinos
uuid: 5 c 7 dbdec-f 73 f -46 fe -9 f 12-7685 e 8 d 7334 f
translation-type: tm+mt
source-git-commit: 75eada471bc898be2f8903316285fe60890972cc

---


# Visão geral dos destinos {#destinations}

No Audience Manager, um destino é qualquer sistema de terceiros (servidor de anúncios, [!DNL DSP]rede de anúncios, etc.) que deseja compartilhar dados. [!UICONTROL Destination Builder] é a ferramenta usada para criar e gerenciar cookies, [!DNL URL]ou destinos de servidor a servidor.

## Finalidade e vantagens {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] e [!UICONTROL Destination Builder] permite criar destinos e enviar informações sobre usuários segmentados ao seu parceiro de dados. Isso ajuda você a:

* **Proteger o valor de dados:** Em vez de enviar todos os dados do usuário para um destino, [!UICONTROL Destination Builder] permita que você compartilhe informações específicas apenas sobre usuários qualificados.
* **Execute ações em seus dados:** Enviar dados para um parceiro de destino os ajuda a desenvolver e direcionar rapidamente os segmentos de público-alvo qualificados.
* **Reduzir sobrecarga técnica:** Os usuários corporativos podem configurar destinos com segurança na [!UICONTROL Destination Builder] interface. Isso ajuda a reduzir o tempo necessário para o teste pré-implantação. Com [!UICONTROL Destination Builder], você pode criar, gerenciar e excluir destinos conforme suas necessidades de negócios mudam, tudo sem trabalhar em um longo ciclo de desenvolvimento.

## Considerações técnicas {#technical-considerations}

<!-- destination-delivery-methods.xml -->

A entrega de dados depende de como seu parceiro de dados deseja ou pode receber informações de destino. As restrições técnicas ou de engenharia podem impedir que um destino receba dados por meio [!DNL URL]de processos, cookies ou processos de servidor a servidor. Entre em contato com seu parceiro de terceiros para determinar qual método eles podem usar.

## Considerações comerciais {#business-considerations}

As decisões empresariais para selecionar um método de entrega em outro dependem dos recursos técnicos do seu parceiro de destino e do que você deseja fazer com informações de usuário qualificadas. Por exemplo, as restrições técnicas podem limitar suas opções se um destino não puder receber dados por um método de entrega específico. No entanto, se não houver problemas técnicos, você pode enviar informações com base em como deseja tomar uma ação nesses dados. Por exemplo:

* [!DNL URL]os destinos s e cookies funcionam quase sincronicamente com as ações do usuário em uma página.
* Métodos de servidor para servidor são bons para criar segmentos profundos do público com o tempo.

## Tipos de destino e usos típicos {#destination-types}

Os exemplos na tabela a seguir podem ajudá-lo a entender quando usar um destino específico e as diferenças entre cada tipo.

| Tipo de destino | Normalmente usada quando | Exemplo | Considerações |
|--- |--- |--- |--- |
| **URL** ou **cookie** | É necessário transferir dados imediatamente para que um destino possa agir em um usuário qualificado imediatamente. | Envio de dados de um site de compra de bilhetes. Use um URL ou destino do cookie para qualificar usuário e redirecionar imediatamente. | <ul><li>Transfere dados apenas sobre novos visitantes. </li><li>Os visitantes devem ser vistos novamente para se qualificarem para o segmento.</li></ul> |
| **Servidor a servidor** | <ul><li>A transferência imediata de dados não é necessária.</li><li>Coleta de dados para criar um grande conjunto de público-alvo de usuários qualificados.</li></ul> | Coleta de dados ao longo do tempo (horas ou dias) para usá-los em uma campanha definida para ser executada em uma data posterior. | <ul><li>Transfere dados sobre visitantes novos e anteriores do site. </li><li>Os visitantes não precisam ser vistos novamente para se qualificarem para outros segmentos.</li></ul> |
