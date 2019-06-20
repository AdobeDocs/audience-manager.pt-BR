---
description: Os componentes do gerenciamento de tags do Audience Manager incluem o portal do cliente, o Adobe Tag Manager (obsoleto para o Adobe Dynamic Tag Manager e o Adobe Launch), DIL, Akamai e o banco de dados de controle.
seo-description: Os componentes do gerenciamento de tags do Audience Manager incluem o portal do cliente, o Adobe Tag Manager (obsoleto para o Adobe Dynamic Tag Manager e o Adobe Launch), DIL, Akamai e o banco de dados de controle.
seo-title: Componentes de gerenciamento de tags
solution: Audience Manager
title: Componentes de gerenciamento de tags
uuid: e 5059478-6 ba 7-4 e 1 a-afec-e 41 ad 7 a 27750
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Tag Management Components{#tag-management-components}

Os componentes do gerenciamento de tags do Audience Manager incluem o portal do cliente, o Adobe Tag Manager (obsoleto para o Adobe Dynamic Tag Manager e o Adobe Launch), DIL, Akamai e o banco de dados de controle.

<!-- 

c_comptag.xml

 -->

O Audience Manager contém os seguintes componentes:

* [Portal do cliente](../../reference/system-components/components-tag-management.md#client-portal)
* [Contêiner DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Biblioteca de informações de dados (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Controlar banco de dados](../../reference/system-components/components-tag-management.md#control-database)

## Client Portal {#client-portal}

O portal do cliente é a interface do usuário principal (IU) para a tag e o gerenciamento de dados. Os clientes usam o portal para trabalhar com tags, criar características e segmentos, configurar destinos e monitorar o desempenho da campanha com relatórios.

## DIL/TIM Container {#dil-tim}

The [!UICONTROL DIL] container helps deploy [!DNL Audience Manager] data collection code to your website. [!UICONTROL TIM] é o Gerenciador de inserção de tags obsoleto. It is no longer used by [!DNL Audience Manager]. Instead, you use [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/) or the [!DNL Audience Manager] extension in [Adobe Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) to configure and generate container code that you place on pages in your inventory. [!UICONTROL DTM] O contêiner funciona com a [!UICONTROL Data Information Library (DIL)] para coletar dados do site e enviá-lo [!DNL Audience Manager]para.

## Biblioteca da integração de dados (DIL) {#dil}

The [Data Information Library](../../dil/dil-overview.md) (DIL) is a self-contained API module that collects data from your website. [!UICONTROL DIL] ajuda a eliminar a necessidade de gravar código especial para coleta de dados, integração, leitura de valores de cookies e recuperar dados da página. [!UICONTROL DIL] executa essas ações automaticamente. Additionally, [!UICONTROL DIL] is compact. É uma biblioteca de códigos autocontida que ajuda a reduzir a quantidade de código necessária para coletar informações. Finally, [!UICONTROL DIL] helps you integrate [!DNL Audience Manager] with other products in the [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] usa [o Akamai](https://www.akamai.com/html/about/index.html) para hospedar e entregar código de contêiner de nossa própria plataforma de gerenciamento de tags conhecida como [!UICONTROL TIM (Tag Insertion Manager)]. However, code deployment with [!UICONTROL TIM] has been phased out in favor of [!UICONTROL Adobe Dynamic Tag Management] and [!UICONTROL Adobe Launch].

## Control Database {#control-database}

O banco de dados de controle:

* Processa a entrada do cliente no portal (por exemplo, criar características e destinos).
* Transmite dados ao Akamai, que inclui dados usados para criar o modelo de contêiner e o iframe de publicação de destino.
* Retorna dados para sistemas de relatório de interface de usuário.

