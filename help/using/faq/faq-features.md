---
description: Perguntas e problemas comuns relacionados a produtos e funções.
keywords: audience manager cookies
seo-description: Perguntas e problemas comuns relacionados a produtos e funções.
seo-title: Perguntas frequentes sobre recursos e funções do produto
solution: Audience Manager
title: Perguntas frequentes sobre recursos e funções do produto
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 1%

---


# Perguntas frequentes sobre recursos e funções do produto{#product-features-and-functions-faq}

Perguntas e problemas comuns relacionados a produtos e funções.

 

<!-- 

faq_features_functions.xml

 -->

**O que é minha ID da organização e como a encontro?**

A ID *`Organization ID`* é exclusiva para identificar a organização [!DNL Audience Manager] e o [!DNL Adobe Experience Cloud]. Consiste em uma sequência de 24 caracteres alfanuméricos, que diferencia maiúsculas de minúsculas, seguida por [!UICONTROL @AdobeOrg].

Por exemplo, um *`Organization ID`* tem a seguinte aparência: `1FD6776A524453CC0A490D44@AdobeOrg`.

O *`Organization ID`* é usado pela API Audience Manager [DIL](../dil/dil-overview.md) , pelo Serviço [de identificação do](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform e outras [!DNL Experience Cloud] soluções. Os usuários com permissões de Administrador podem encontrar o *`Organization ID`* na [!DNL Adobe Admin Console]. Consulte as Perguntas frequentes sobre [Administração - Gerenciamento de usuários](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).

 

**É possível criar características ou destinos em massa?**

Sim. Consulte Ferramentas [de gerenciamento em](../reference/bulk-management-tools/bulk-management-intro.md)massa.

>[!NOTE]
>
>As [!UICONTROL Bulk Management Tools] ferramentas não *são* suportadas por [!DNL Audience Manager]. Eles são fornecidos para conveniência e apenas como cortesia. Para alterações em massa, recomendamos que você trabalhe com as APIs [de](../api/api.md) Audience Manager.

 

**Ao executar uma exportação de ID em massa para um destino, algumas das IDs do cliente estão ausentes. Why does that happen?**

Quando uma ID de dispositivo (UUID[do](../reference/ids-in-aam.md)AAM) é vinculada a várias IDs CRM ([DPUUIDs](../reference/ids-in-aam.md)), somente o mapeamento mais recente é exportado. É por isso que você pode ver um número menor do que o esperado de IDs de dispositivo sendo exportadas.

 

**É possível[!DNL Audience Manager]reduzir a necessidade de tags ou pixels de terceiros e melhorar o tempo de carregamento da página?**

Se [!DNL Audience Manager] estiver integrado ao seu parceiro de dados de terceiros, você poderá substituir os pixels e as tags deles por uma chamada de ID de servidor para servidor [!DNL Audience Manager]. Nesse caso, [!DNL Audience Manager] acionaria uma única chamada de ID na primeira vez que um usuário fosse exibido e sincronizaria essas informações com seu parceiro de terceiros. Isso elimina a necessidade de fazer chamadas de vários pixels de cada página. A redução de chamadas de pixel pode melhorar o tempo de carregamento da página.

 

**Eu me inscrevi em um feed de dados. Onde estão armazenados esses dados?**

Seu feed de dados e todas as características contidas no feed aparecem como subpastas e características no [!DNL Audience Manager]. Vá até **[!UICONTROL Audience Data > Traits]** e expanda a [!UICONTROL 3rd-Party Data] pasta para visualização de suas características ou criar segmentos e modelos com esses dados.

 

**O que é[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager usado [!UICONTROL Tag Insertion Manager] (TIM) para criar e gerenciar [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Experience Platform Launch]. For more information, see [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html).

 

**Quais são as diferenças entre os Modelos algorítmicos e as Recomendações de características? Quando devo usar cada um deles?**

**Modelos algorítmicos**

Os Modelos algorítmicos não só encontram as características mais influentes, como também pontuam os usuários com base nessas características e atribuem a cada usuário uma pontuação individual. Em seguida, você cria traços algorítmicos para público alvo de seus usuários. Com controles de precisão e alcance no Construtor de características, você pode especificar quais usuários entre todos aqueles que têm as características influentes que deseja público alvo.

Os Modelos algorítmicos permitem selecionar usuários em diferentes níveis de precisão e testar no Audiência Lab qual grupo de usuários converte melhor. Consulte o caso de uso detalhado em [Comparar modelos no Laboratório](../features/audience-lab/audience-lab-use-cases.md#compare-models)de Audiências.

Em Modelos Algorítmicos, o modelo é executado a cada 8 dias e atualiza os usuários qualificados para características algorítmicas.

**Recomendações de característica**

As Recomendações de características são uma forma rápida de obter insights sobre outras características semelhantes àquelas que você está usando em um segmento.

Você deve usar as Recomendações de características quando:

* Você precisa de insights rápidos ao criar um segmento;
* Você está usando os segmentos para campanhas curtas ou quando deseja suprimir rapidamente a audiência que converte;
* Você está tentando maximizar o alcance.

 

**Há alguma diferença entre os segmentos Analytics da Adobe e Audience Manager?**

Sim, leia [Como entender segmentos no Analytics e Audience Manager](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) para obter uma descrição detalhada das diferenças.
