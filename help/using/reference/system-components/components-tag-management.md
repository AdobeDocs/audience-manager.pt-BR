---
description: Os componentes do gerenciamento de tags do Audience Manager incluem o portal do cliente, o Adobe Tag Manager (obsoleto em favor do Adobe Dynamic Tag Manager e do Adobe Launch), o DIL, o Akamai e o banco de dados de controle.
seo-description: Os componentes do gerenciamento de tags do Audience Manager incluem o portal do cliente, o Adobe Tag Manager (obsoleto em favor do Adobe Dynamic Tag Manager e do Adobe Launch), o DIL, o Akamai e o banco de dados de controle.
seo-title: Componentes do Gerenciamento de tags
solution: Audience Manager
title: Componentes do Gerenciamento de tags
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Componentes do Gerenciamento de tags{#tag-management-components}

Os componentes do gerenciamento de tags do Audience Manager incluem o portal do cliente, o Adobe Tag Manager (obsoleto em favor do Adobe Dynamic Tag Manager e do Adobe Launch), o DIL, o Akamai e o banco de dados de controle.

<!-- 

c_comptag.xml

 -->

O Audience Manager contém os seguintes componentes:

* [Portal do cliente](../../reference/system-components/components-tag-management.md#client-portal)
* [Contêiner DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Biblioteca de informações de dados (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Banco de dados de controle](../../reference/system-components/components-tag-management.md#control-database)

## Portal do cliente {#client-portal}

O portal do cliente é a interface do usuário principal (UI) para gerenciamento de tags e dados. Os clientes usam o portal para trabalhar com tags, criar características e segmentos, configurar destinos e monitorar o desempenho da campanha com relatórios.

## Contêiner DIL/TIM {#dil-tim}

O [!UICONTROL DIL] contêiner ajuda a implantar o código de coleta [!DNL Audience Manager] de dados em seu site. [!UICONTROL TIM] é o Gerenciador de inserção de tag obsoleto. Não é mais usado por [!DNL Audience Manager]. Em vez disso, use o Gerenciamento [dinâmico de tags ou a](https://marketing.adobe.com/resources/help/en_US/dtm/) extensão no [!DNL Audience Manager] Adobe Launch [](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) para configurar e gerar o código do contêiner que você coloca nas páginas do inventário. O [!UICONTROL DTM] contêiner trabalha com o [!UICONTROL Data Information Library (DIL)] para coletar dados do site e enviá-los para [!DNL Audience Manager].

## Biblioteca da integração de dados (DIL) {#dil}

A Biblioteca [de informações de](../../dil/dil-overview.md) dados (DIL) é um módulo de API autocontido que coleta dados de seu site. [!UICONTROL DIL] ajuda a eliminar a necessidade de gravar código especial para coleta de dados, integração, leitura de valores de cookies e recuperação de dados da página. [!UICONTROL DIL] executa essas ações automaticamente. Além disso, [!UICONTROL DIL] é compacto. É uma biblioteca de códigos independente que ajuda a reduzir a quantidade de código necessária para coletar informações. Por fim, [!UICONTROL DIL] ajuda você a se integrar [!DNL Audience Manager] com outros produtos na [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] usa o [Akamai](https://www.akamai.com/html/about/index.html) para hospedar e fornecer o código do contêiner de nossa própria plataforma de gerenciamento de tags, conhecida como [!UICONTROL TIM (Tag Insertion Manager)]. No entanto, a implantação de código com [!UICONTROL TIM] foi removida gradualmente em favor de [!UICONTROL Adobe Dynamic Tag Management] e [!UICONTROL Adobe Launch].

## Banco de dados de controle {#control-database}

A base de dados de controlo:

* Processa a entrada do cliente a partir do portal (por exemplo, criar características e destinos).
* Transmite dados para o Akamai, que inclui dados usados para criar o modelo de contêiner e o iFrame de publicação de destino.
* Retorna dados para sistemas de relatório de interface.

