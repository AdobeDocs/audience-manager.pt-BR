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
ht-degree: 91%

---


# Perguntas frequentes sobre recursos e funções do produto {#product-features-and-functions-faq}

Perguntas e problemas comuns relacionados a produtos e funções.

 

<!-- 

faq_features_functions.xml

 -->

**O que é ID da organização e como a encontro?**

A *`Organization ID`* é a ID exclusiva para identificar a organização no [!DNL Audience Manager] e na [!DNL Adobe Experience Cloud]. Consiste em uma sequência de 24 caracteres alfanuméricos, que diferencia maiúsculas de minúsculas, seguida por [!UICONTROL @AdobeOrg].

Por exemplo, uma *`Organization ID`* tem a seguinte aparência: `1FD6776A524453CC0A490D44@AdobeOrg`.

A *`Organization ID`* é usada pela API [DIL](../dil/dil-overview.md) do Audience Manager, pelo [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/pt-BR/id-service/using/home.html) e outras soluções da [!DNL Experience Cloud]. Os usuários com permissões de Administrador podem encontrar a *`Organization ID`* no [!DNL Adobe Admin Console]. Consulte as [Perguntas frequentes sobre administração - Gerenciamento de usuários](https://docs.adobe.com/content/help/pt-BR/core-services/interface/manage-users-and-products/admin-getting-started.html).

 

**É possível criar características ou destinos em massa?**

Sim. Consulte [Ferramentas de gerenciamento em massa](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>As ferramentas [!UICONTROL Bulk Management Tools] *não* são compatíveis com o [!DNL Audience Manager]. Elas são fornecidas para conveniência e apenas como cortesia. Para alterações em massa, recomendamos que você trabalhe com as [APIs do Audience Manager](../api/api.md).

 

**Ao executar uma exportação de ID em massa para um destino, algumas das IDs do cliente estão ausentes. Por que isso acontece?**

Quando uma ID de dispositivo ([AAM UUID](../reference/ids-in-aam.md)) é vinculada a várias IDs CRM ([DPUUIDs](../reference/ids-in-aam.md)), somente o mapeamento mais recente é exportado. É por isso que você pode ver um número menor do que o esperado de IDs de dispositivo sendo exportadas.

 

**O [!DNL Audience Manager] pode reduzir a necessidade de tags ou pixels de terceiros e melhorar o tempo de carregamento da página?**

Se o [!DNL Audience Manager] estiver integrado ao seu parceiro de dados de terceiros, você poderá substituir os pixels e as tags deles por uma chamada de ID de servidor para servidor [!DNL Audience Manager]. Nesse caso, o [!DNL Audience Manager] acionaria uma única chamada de ID na primeira vez que um usuário fosse exibido e sincronizaria essas informações com seu parceiro de terceiros. Isso elimina a necessidade de fazer chamadas de vários pixels de cada página. A redução de chamadas de pixel pode melhorar o tempo de carregamento da página.

 

**Eu me inscrevi em um feed de dados. Onde ficam armazenados esses dados?**

Seu feed de dados e todas as características contidas no feed aparecem como subpastas e características no [!DNL Audience Manager]. Acesse **[!UICONTROL Audience Data > Traits]** e expanda a pasta [!UICONTROL 3rd-Party Data] para visualizar suas características ou criar segmentos e modelos com esses dados.

 

**O que é o [!UICONTROL Tag Insertion Manager (TIM)]?**

O Audience Manager usou o [!UICONTROL Tag Insertion Manager] (TIM) para criar e gerenciar o [!UICONTROL data collection code (DIL)]. Esse recurso é obsoleto e foi substituído em primeiro lugar pelo [!UICONTROL Dynamic Tag Manager (DTM)] e depois pelo [!DNL Adobe Experience Platform Launch]. Para obter mais informações, consulte [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) e [Dynamic Tag Management](https://docs.adobe.com/content/help/pt-BR/dtm/using/dtm-home.html).

 

**Quais são as diferenças entre os Modelos algorítmicos e as Recomendações de características? Quando devo usar cada um deles?**

**Modelos algorítmicos**

Os Modelos algorítmicos não só encontram as características mais influentes, como também pontuam os usuários com base nessas características e atribuem a cada usuário uma pontuação individual. Em seguida, você cria características algorítmicas para direcionar os usuários. Com controles de precisão e alcance no Construtor de características, é possível especificar quais usuários entre todos aqueles que têm as características influentes você quer direcionar.

Os Modelos algorítmicos permitem selecionar usuários em diferentes níveis de precisão e testar no Audience Lab qual grupo de usuários converte melhor. Consulte o caso de uso detalhado em [Comparar modelos no Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

Em Modelos algorítmicos, o modelo é executado a cada 8 dias e atualiza os usuários qualificados para características algorítmicas.

**Recomendações de característica**

As Recomendações de características são uma forma rápida de obter insights sobre outras características semelhantes àquelas que você está usando em um segmento.

Você deve usar as Recomendações de características quando:

* Precisar de insights rápidos ao criar um segmento;
* Estiver usando os segmentos para campanhas curtas ou quando deseja suprimir rapidamente o público-alvo que converte;
* Estiver tentando maximizar o alcance.

 

**Há alguma diferença entre os segmentos do Adobe Analytics e do Audience Manager?**

Sim, leia [Entendendo segmentos no Analytics e no Audience Manager](https://docs.adobe.com/content/help/pt-BR/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) para obter uma descrição detalhada sobre as diferenças.
