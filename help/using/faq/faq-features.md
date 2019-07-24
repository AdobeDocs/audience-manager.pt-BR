---
description: Perguntas e problemas comuns sobre produtos e funções.
keywords: cookies do Manager Manager
seo-description: Perguntas e problemas comuns sobre produtos e funções.
seo-title: Perguntas frequentes sobre recursos e funções do produto
solution: Audience Manager
title: Perguntas frequentes sobre recursos e funções do produto
uuid: da 5 f 5089-24 a 8-4455-88 a 6-eb 62 d 83939 d 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Product Features and Functions FAQ{#product-features-and-functions-faq}

Perguntas e problemas comuns sobre produtos e funções.

<br> 

<!-- 

faq_features_functions.xml

 -->

**Qual é minha ID de organização e como encontrá-la?**

The *`Organization ID`* is a unique ID that identifies your organization to [!DNL Audience Manager] and the [!DNL Adobe Experience Cloud]. It consists of a case-sensitive, 24-character alphanumeric string followed by [!UICONTROL @AdobeOrg].

For example, an *`Organization ID`* looks like this: `1FD6776A524453CC0A490D44@AdobeOrg`.

The *`Organization ID`* is used by Audience Manager's [DIL](../dil/dil-overview.md) API, the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/), and other [!DNL Experience Cloud] solutions. Users with Administrator permissions can find the *`Organization ID`* on the [!DNL Adobe Admin Console]. See the [Administration - User Management FAQ](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html).

<br> 

**Posso criar características ou destinos em massa?**

Sim. See [Bulk Management Tools](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] tools *are not* supported by [!DNL Audience Manager]. Elas são fornecidas para conveniência e como cortesia apenas. For bulk changes, we recommend you work with the [Audience Manager APIs](../api/api.md) instead.

<br> 

**[!DNL Audience Manager]Pode reduzir a necessidade de tags ou pixels de terceiros e melhorar o tempo de carregamento de página?**

If [!DNL Audience Manager] is integrated with your third-party data partner, you can replace their pixels and tags with a server-to-server ID call to [!DNL Audience Manager]. In this case, [!DNL Audience Manager] would fire a single ID call the first time we see a user and synchronize that information with your third-party partner. Isso elimina a necessidade de fazer vários pixels de cada página. A redução das chamadas de pixel pode melhorar o tempo de carregamento de página.

<br> 

**Assinei um feed de dados. Where is that data stored?**

Your data feed and all the traits contained in the feed appear as subfolders and traits in [!DNL Audience Manager]. Go to **[!UICONTROL Audience Data > Traits]** and expand the [!UICONTROL 3rd-Party Data] folder to view your traits or create segments and models with this data.

<br> 

**O que é[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager used [!UICONTROL Tag Insertion Manager] (TIM) to create and manage [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Launch]. For more information, see [Adobe Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

<br> 

**Quais são as diferenças entre Modelos algorítmicos e Recomendações de características? When should I use each of them?**

**Modelos algorítmicos**

Os Modelos algoritmicos encontram as características mais influentes, mas também pontuam os usuários com base nessas características e atribui cada usuário uma pontuação individual. Em seguida, crie características algorítmicas para direcionar seus usuários. Com controles de precisão e alcance no Construtor de traços, você pode especificar quais usuários entre todos os que têm as características influentes que deseja direcionar.

Os modelos algorítmicos permitem selecionar usuários em diferentes níveis de precisão e teste no Audience Lab que grupo de usuários converte melhor. See the detailed use case in [Compare Models in Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

Em Modelos algorítmicos, o modelo é executado a cada 8 dias e atualiza os usuários qualificados para as características algorítmicas.

**Recomendações de característica**

As Recomendações de características são uma forma rápida de obter insights em outras características semelhantes àqueles usados em um segmento.

Você deve usar o Recommendations Recommendations quando:

* Você precisa de insights rápidos ao criar um segmento;
* Você está usando os segmentos para campanhas curtas ou quando deseja suprimir rapidamente o público-alvo que converte;
* Você está tentando maximizar o alcance.

<br> 

**Há alguma diferença entre os segmentos do Adobe Analytics e do Audience Manager?**

Yes, please read [Understanding Segments in Analytics and Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) for an in-depth description of the differences.
