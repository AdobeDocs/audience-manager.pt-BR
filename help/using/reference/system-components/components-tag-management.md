---
description: Os componentes do gerenciamento de tags do Audience Manager incluem o portal do cliente, o Adobe Tag Manager (obsoleto em favor do Adobe Experience Platform Launch), o DIL, o Akamai e o banco de dados de controle.
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Componentes do Tag Management
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 3%

---

# Componentes do Tag Management{#tag-management-components}

Os componentes do gerenciamento de tags do Audience Manager incluem o portal do cliente, o Adobe Tag Manager (descontinuado em favor das tags do Adobe Experience Platform), o DIL, o Akamai e o banco de dados de controle.

<!-- 

c_comptag.xml

 -->

Audience Manager contém os seguintes componentes:

* [Portal do cliente](../../reference/system-components/components-tag-management.md#client-portal)
* [Contêiner de DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Biblioteca de informações de dados (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Banco de Dados de Controle](../../reference/system-components/components-tag-management.md#control-database)

## Portal do cliente {#client-portal}

O portal do cliente é a principal interface do usuário para gerenciamento de tags e dados. Os clientes usam o portal para trabalhar com tags, criar características e segmentos, configurar destinos e monitorar o desempenho da campanha com relatórios.

## Contêiner de DIL/TIM {#dil-tim}

A variável [!UICONTROL DIL] o contêiner ajuda a implantar [!DNL Audience Manager] código de coleta de dados para seu site. [!UICONTROL TIM] O é o Gerenciador de inserção de tag obsoleto. Não é mais usado por [!DNL Audience Manager]. Em vez disso, use o [!DNL Audience Manager] extensão no [Tags do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) para configurar e gerar o código de contêiner que você coloca nas páginas do inventário.

## Biblioteca de integração de dados (DIL) {#dil}

A variável [Biblioteca de informações de dados](../../dil/dil-overview.md) (DIL) é um módulo de API independente que coleta dados do seu site. [!UICONTROL DIL] O ajuda a eliminar a necessidade de gravar código especial para coleta de dados, integração, leitura de valores de cookie e recuperação de dados de página. [!UICONTROL DIL] O executa essas ações automaticamente. Além disso, [!UICONTROL DIL] é compacto. É uma biblioteca de código independente que ajuda a reduzir a quantidade de código necessária para coletar informações. Por último, [!UICONTROL DIL] ajuda a integrar [!DNL Audience Manager] com outros produtos na [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] usos [Akamai](https://www.akamai.com/us/en/about/) para hospedar e entregar o código de contêiner de nossa própria plataforma de gerenciamento de tags conhecida como [!UICONTROL TIM (Tag Insertion Manager)]. No entanto, a implantação de código com [!UICONTROL TIM] foi eliminado progressivamente em favor de [!DNL Adobe Experience Platform Tags].

## Banco de Dados de Controle {#control-database}

O banco de dados de controle:

* Processa a entrada do cliente no portal (por exemplo, criando características e destinos).
* Transmite dados para o Akamai, que inclui dados usados para criar o modelo de contêiner e o iFrame de publicação de destino.
* Retorna dados para sistemas de relatório de interface do usuário.
