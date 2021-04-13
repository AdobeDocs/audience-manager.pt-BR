---
description: Os componentes do gerenciamento de tags do Audience Manager incluem o portal do cliente, o Adobe Tag Manager (obsoleto no Adobe Dynamic Tag Manager e Adobe Experience Platform Launch), o DIL, o Akamai e o banco de dados de controle.
seo-description: Os componentes do gerenciamento de tags do Audience Manager incluem o portal do cliente, o Adobe Tag Manager (obsoleto no Adobe Dynamic Tag Manager e Adobe Experience Platform Launch), o DIL, o Akamai e o banco de dados de controle.
seo-title: Componentes do Tag Management
solution: Audience Manager
title: Componentes do Tag Management
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: 'Componentes do sistema '
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 6%

---

# Componentes do Tag Management{#tag-management-components}

Os componentes do gerenciamento de tags do Audience Manager incluem o portal do cliente, o Adobe Tag Manager (obsoleto no Adobe Dynamic Tag Manager e Adobe Experience Platform Launch), o DIL, o Akamai e o banco de dados de controle.

<!-- 

c_comptag.xml

 -->

O Audience Manager contém os seguintes componentes:

* [Portal do cliente](../../reference/system-components/components-tag-management.md#client-portal)
* [Contêiner DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Biblioteca de informações de dados (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Banco de Dados de Controle](../../reference/system-components/components-tag-management.md#control-database)

## Portal do cliente {#client-portal}

O portal do cliente é a interface do usuário principal para gerenciamento de tags e dados. Os clientes usam o portal para trabalhar com tags, criar características e segmentos, configurar destinos e monitorar o desempenho da campanha com relatórios.

## Contêiner DIL/TIM {#dil-tim}

O contêiner [!UICONTROL DIL] ajuda a implantar [!DNL Audience Manager] código de coleta de dados no seu site. [!UICONTROL TIM] é o Gerenciador de inserção de tag obsoleto. Ele não é mais usado por [!DNL Audience Manager]. Em vez disso, use [Dynamic Tag Management](https://docs.adobe.com/content/help/pt-BR/dtm/using/dtm-home.html) ou a extensão [!DNL Audience Manager] em [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html) para configurar e gerar o código do contêiner inserido nas páginas do inventário. O contêiner [!UICONTROL DTM] funciona com o [!UICONTROL Data Information Library (DIL)] para coletar dados do site e enviá-los para [!DNL Audience Manager].

## Consulte da Biblioteca de integração de dados (DIL) {#dil}

A [Data Information Library](../../dil/dil-overview.md) (DIL) é um módulo de API autocontido que coleta dados do seu site. [!UICONTROL DIL] ajuda a eliminar a necessidade de gravar um código especial para coleta de dados, integração, leitura de valores de cookies e recuperação de dados da página. [!UICONTROL DIL] O executa essas ações automaticamente. Além disso, [!UICONTROL DIL] é compacto. É uma biblioteca de códigos autocontida que ajuda a reduzir a quantidade de código necessária para coletar informações. Por fim, [!UICONTROL DIL] ajuda a integrar [!DNL Audience Manager] com outros produtos no Experience Cloud [!DNL Adobe].

## Akamai {#akamai}

[!DNL Audience Manager] O usa o host  [](https://www.akamai.com/us/en/about/) Akamaito e fornece o código do contêiner de nossa própria plataforma de gerenciamento de tags, conhecida como  [!UICONTROL TIM (Tag Insertion Manager)]. No entanto, a implantação de código com [!UICONTROL TIM] foi removida gradualmente em favor de [!DNL Adobe Dynamic Tag Management] e [!DNL Adobe Experience Platform Launch].

## Banco de Dados de Controle {#control-database}

O banco de dados de controle:

* Processa a entrada do cliente no portal (por exemplo, criação de características e destinos).
* Transmite dados para o Akamai, que inclui dados usados para criar o modelo de contêiner e o iFrame de publicação de destino.
* Retorna dados para sistemas de relatórios da interface do usuário.
