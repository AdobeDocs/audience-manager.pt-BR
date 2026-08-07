---
description: Perguntas e problemas comuns relacionados a produtos e funções.
keywords: cookies do audience manager
seo-description: Common product and function-related questions and issues.
seo-title: Product Features and Functions FAQ
solution: Audience Manager
title: Perguntas frequentes sobre recursos e funções do produto
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
exl-id: b5884d26-0be1-4eaa-99a1-7247942bf6c9
TQID: https://experienceleague.adobe.com/gsJ4qXlNDpfWmTq0jjmtjfUWI60yRr7uBTxZjsF-pQE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: f2fdbb191013b0bcb9bdab0529e3b7f3c872fd54
workflow-type: tm+mt
source-wordcount: 428
ht-degree: 75%

---

# Perguntas frequentes sobre recursos e funções do produto{#product-features-and-functions-faq}

Perguntas e problemas comuns relacionados a produtos e funções.

 

<!-- 

faq_features_functions.xml

 -->

**O que é ID da organização e como a encontro?**

A *`Organization ID`* é a ID exclusiva para identificar a organização no [!DNL Audience Manager] e na [!DNL Adobe Experience Cloud]. Consiste em uma sequência de 24 caracteres alfanuméricos, que diferencia maiúsculas de minúsculas, seguida por [!UICONTROL @AdobeOrg].

Por exemplo, uma *`Organization ID`* tem a seguinte aparência: `1FD6776A524453CC0A490D44@AdobeOrg`.

A *`Organization ID`* é usada pela API [DIL](../dil/dil-overview.md) do Audience Manager, pelo [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) e outras soluções da [!DNL Experience Cloud]. Os usuários com permissões de Administrador podem encontrar a *`Organization ID`* no [!DNL Adobe Admin Console]. Consulte as [Perguntas frequentes sobre administração - Gerenciamento de usuários](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

 

**É possível criar características ou destinos em massa?**

Sim. Consulte [Ferramentas de gerenciamento em massa](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>As ferramentas [!UICONTROL Bulk Management Tools] *não* são compatíveis com o [!DNL Audience Manager]. Elas são fornecidas para conveniência e apenas como cortesia. Para alterações em massa, recomendamos que você trabalhe com as [APIs do Audience Manager](../api/api.md).

 

**Ao executar uma exportação de ID em massa para um destino, algumas IDs do cliente estão ausentes. Por que isso acontece?**

Quando uma ID de dispositivo ([AAM UUID](../reference/ids-in-aam.md)) é vinculada a várias IDs de CRM ([DPUUIDs](../reference/ids-in-aam.md)), somente o mapeamento mais recente é exportado. É por isso que você pode ver um número de IDs de dispositivo que está sendo exportado menor do que o esperado.

 

**O [!DNL Audience Manager] pode reduzir a necessidade de tags ou pixels de terceiros e melhorar o tempo de carregamento da página?**

Se o [!DNL Audience Manager] estiver integrado ao seu parceiro de dados de terceiros, você poderá substituir os pixels e as tags deles por uma chamada de ID de servidor para servidor [!DNL Audience Manager]. Nesse caso, o [!DNL Audience Manager] acionaria uma única chamada de ID na primeira vez que um usuário fosse exibido e sincronizaria essas informações com seu parceiro de terceiros. Isso elimina a necessidade de fazer chamadas de vários pixels de cada página. A redução de chamadas de pixel pode melhorar o tempo de carregamento da página.

 

**Eu me inscrevi em um feed de dados. Onde ficam armazenados esses dados?**

Seu feed de dados e todas as características contidas no feed aparecem como subpastas e características no [!DNL Audience Manager]. Acesse **[!UICONTROL Audience Data > Traits]** e expanda a pasta [!UICONTROL 3rd-Party Data] para visualizar suas características ou criar segmentos e modelos com esses dados.

 

**O que é o [!UICONTROL Tag Insertion Manager (TIM)]?**

O Audience Manager usou o [!UICONTROL Tag Insertion Manager] (TIM) para criar e gerenciar o [!UICONTROL data collection code (DIL)]. Esse recurso é obsoleto e foi substituído em primeiro lugar pelo [!UICONTROL Dynamic Tag Manager (DTM)] e depois pelo [!DNL Adobe Experience Platform Tags]. Para obter mais informações, consulte [Tags do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

 

**Há alguma diferença entre os segmentos do Adobe Analytics e do Audience Manager?**

Sim, leia [Entendendo segmentos no Analytics e no Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) para obter uma descrição detalhada sobre as diferenças.
