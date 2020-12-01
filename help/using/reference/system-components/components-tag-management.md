---
description: Os componentes do gerenciamento de tags do Audience Manager incluem o portal do cliente, o Adobe Tag Manager (obsoleto em favor do Adobe Dynamic Tag Manager e do Adobe Experience Platform Launch), o DIL, o Akamai e o banco de dados de controle.
seo-description: Os componentes do gerenciamento de tags do Audience Manager incluem o portal do cliente, o Adobe Tag Manager (obsoleto em favor do Adobe Dynamic Tag Manager e do Adobe Experience Platform Launch), o DIL, o Akamai e o banco de dados de controle.
seo-title: Componentes do Tag Management
solution: Audience Manager
title: Componentes do Tag Management
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 5%

---


# Componentes do Tag Management{#tag-management-components}

Os componentes do gerenciamento de tags do Audience Manager incluem o portal do cliente, o Adobe Tag Manager (obsoleto em favor do Adobe Dynamic Tag Manager e do Adobe Experience Platform Launch), o DIL, o Akamai e o banco de dados de controle.

<!-- 

c_comptag.xml

 -->

O Audience Manager contém os seguintes componentes:

* [Portal do cliente](../../reference/system-components/components-tag-management.md#client-portal)
* [CONTAINER DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Biblioteca de informações de dados (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Banco de dados de controle](../../reference/system-components/components-tag-management.md#control-database)

## Portal do cliente {#client-portal}

O portal do cliente é a interface do usuário principal (UI) para tag e gestão de dados. Os clientes usam o portal para trabalhar com tags, criar características e segmentos, configurar destinos e monitorar o desempenho da campanha com relatórios.

## CONTAINER DIL/TIM {#dil-tim}

O container [!UICONTROL DIL] ajuda a implantar [!DNL Audience Manager] o código de coleta de dados em seu site. [!UICONTROL TIM] é o Gerenciador de inserção de tag obsoleto. Não é mais usado por [!DNL Audience Manager]. Em vez disso, use o [Gerenciamento dinâmico de tags](https://docs.adobe.com/content/help/pt-BR/dtm/using/dtm-home.html) ou a extensão [!DNL Audience Manager] em [Adobe Experience Platform Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) para configurar e gerar o código de container que você coloca nas páginas do inventário. O container [!UICONTROL DTM] funciona com o [!UICONTROL Data Information Library (DIL)] para coletar dados do site e enviá-los para [!DNL Audience Manager].

## Consulte da Biblioteca de integração de dados (DIL) {#dil}

A [Biblioteca de informações de dados](../../dil/dil-overview.md) (DIL) é um módulo de API autocontido que coleta dados de seu site. [!UICONTROL DIL] ajuda a eliminar a necessidade de gravar um código especial para coleta de dados, integração, leitura de valores de cookies e recuperação de dados da página. [!UICONTROL DIL] executa essas ações automaticamente. Além disso, [!UICONTROL DIL] é compacto. É uma biblioteca de códigos independente que ajuda a reduzir a quantidade de código necessária para coletar informações. Finalmente, [!UICONTROL DIL] ajuda a integrar [!DNL Audience Manager] com outros produtos no Experience Cloud [!DNL Adobe].

## Akamai {#akamai}

[!DNL Audience Manager] usa o host  [](https://www.akamai.com/html/about/index.html) Akamaito e fornece código de container de nossa própria plataforma de gerenciamento de tags, conhecida como  [!UICONTROL TIM (Tag Insertion Manager)]. No entanto, a implantação de código com [!UICONTROL TIM] foi removida gradualmente em favor de [!DNL Adobe Dynamic Tag Management] e [!DNL Adobe Experience Platform Launch].

## Banco de dados de controle {#control-database}

A base de dados de controlo:

* Processa a entrada do cliente a partir do portal (por exemplo, criar características e destinos).
* Transmite dados para o Akamai, que inclui dados usados para criar o modelo de container e o iFrame de publicação de destino.
* Retorna dados para sistemas de relatórios da interface do usuário.

