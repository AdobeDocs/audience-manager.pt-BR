---
description: Os componentes do gerenciamento de tags da Audience Manager incluem o portal do cliente, o Adobe Tag Manager (obsoleto em favor do Adobe Experience Platform Launch), o DIL, o Akamai e o banco de dados de controle.
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Componentes do Tag Management
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
TQID: 'https://experienceleague.adobe.com/iOniWbVTajyhGmIl3IDdxrP5dZ-ULKkA-9ySOXniqUI'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
    internal-label: Reporting
  - id: c814092e-2730-45e8-a12d-e084529f52cb
    internal-label: Destinations
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
    internal-label: Administration
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
    internal-label: Overlap Reports
  - id: f518b7e7-52a7-4298-a970-88c25c36ab31
    internal-label: System components
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 1%
---
# Componentes do Tag Management{#tag-management-components}

Os componentes do gerenciamento de tags da Audience Manager incluem o portal do cliente, o Adobe Tag Manager (obsoleto em favor das tags da Adobe Experience Platform), o DIL, o Akamai e o banco de dados de controle.

<!-- 

c_comptag.xml

 -->

O Audience Manager contém os seguintes componentes:

* [Portal do Cliente](../../reference/system-components/components-tag-management.md#client-portal)
* [Contêiner DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Biblioteca de Informações de Dados (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Banco de Dados de Controle](../../reference/system-components/components-tag-management.md#control-database)

## Portal do cliente {#client-portal}

O portal do cliente é a principal interface do usuário para gerenciamento de tags e dados. Os clientes usam o portal para trabalhar com tags, criar características e segmentos, configurar destinos e monitorar o desempenho da campanha com relatórios.

## Contêiner DIL/TIM {#dil-tim}

O contêiner [!UICONTROL DIL] ajuda a implantar o código de coleta de dados [!DNL Audience Manager] em seu site. [!UICONTROL TIM] é o Gerenciador de Inserção de Marca obsoleto. Ele não é mais usado por [!DNL Audience Manager]. Em vez disso, você usa a extensão [!DNL Audience Manager] em [Tags do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) para configurar e gerar o código de contêiner que você coloca nas páginas do inventário.

## Biblioteca de integração de dados (DIL) {#dil}

A [Biblioteca de Informações de Dados](../../dil/dil-overview.md) (DIL) é um módulo de API independente que coleta dados do seu site. O [!UICONTROL DIL] ajuda a eliminar a necessidade de gravar código especial para coleta de dados, integração, leitura de valores de cookie e recuperação de dados de página. O [!UICONTROL DIL] executa essas ações automaticamente. Além disso, o [!UICONTROL DIL] é compacto. É uma biblioteca de código independente que ajuda a reduzir a quantidade de código necessária para coletar informações. Finalmente, o [!UICONTROL DIL] ajuda a integrar o [!DNL Audience Manager] com outros produtos na Experience Cloud [!DNL Adobe].

## Akamai {#akamai}

[!DNL Audience Manager] usa o [Akamai](https://www.akamai.com/us/en/about/) para hospedar e entregar o código de contêiner de nossa própria plataforma de gerenciamento de tags conhecida como [!UICONTROL TIM (Tag Insertion Manager)]. No entanto, a implantação de código com [!UICONTROL TIM] foi removida em favor de [!DNL Adobe Experience Platform Tags].

## Banco de Dados de Controle {#control-database}

O banco de dados de controle:

* Processa a entrada do cliente no portal (por exemplo, criando características e destinos).
* Transmite dados para o Akamai, que inclui dados usados para criar o modelo de contêiner e o iFrame de publicação de destino.
* Retorna dados para sistemas de relatório de interface do usuário.
