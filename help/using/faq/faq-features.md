---
description: Perguntas e problemas comuns relacionados a produtos e funções.
keywords: cookies do Audience Manager
seo-description: Perguntas e problemas comuns relacionados a produtos e funções.
seo-title: Perguntas frequentes sobre recursos e funções do produto
solution: Audience Manager
title: Perguntas frequentes sobre recursos e funções do produto
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Perguntas frequentes sobre recursos e funções do produto{#product-features-and-functions-faq}

Perguntas e problemas comuns relacionados a produtos e funções.

<br> 

<!-- 

faq_features_functions.xml

 -->

**O que é minha ID da organização e como a encontro?**

A ID *`Organization ID`* é exclusiva para identificar a organização [!DNL Audience Manager] e o [!DNL Adobe Experience Cloud]. Consiste em uma sequência de 24 caracteres alfanuméricos, que diferencia maiúsculas de minúsculas, seguida por [!UICONTROL @AdobeOrg].

Por exemplo, um *`Organization ID`* tem a seguinte aparência: `1FD6776A524453CC0A490D44@AdobeOrg`.

O *`Organization ID`* é usado pela API [DIL](../dil/dil-overview.md) do Audience Manager, o serviço [da](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud ID e outras [!DNL Experience Cloud] soluções. Os usuários com permissões de Administrador podem encontrar o *`Organization ID`* na [!DNL Adobe Admin Console]. Consulte as Perguntas frequentes sobre [Administração - Gerenciamento de usuários](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html).

<br> 

**É possível criar características ou destinos em massa?**

Sim. Consulte Ferramentas [de gerenciamento em](../reference/bulk-management-tools/bulk-management-intro.md)massa.

>[!NOTE]
>
>As [!UICONTROL Bulk Management Tools] ferramentas não *são* suportadas por [!DNL Audience Manager]. Eles são fornecidos para conveniência e apenas como cortesia. Para alterações em massa, recomendamos que você trabalhe com as APIs [do](../api/api.md) Audience Manager.

<br> 

**É possível[!DNL Audience Manager]reduzir a necessidade de tags ou pixels de terceiros e melhorar o tempo de carregamento da página?**

Se [!DNL Audience Manager] estiver integrado ao seu parceiro de dados de terceiros, você poderá substituir os pixels e tags deles por uma chamada de ID de servidor para servidor [!DNL Audience Manager]. Nesse caso, [!DNL Audience Manager] acionaria uma única chamada de ID na primeira vez que um usuário fosse exibido e sincronizaria essas informações com seu parceiro de terceiros. Isso elimina a necessidade de fazer chamadas de vários pixels de cada página. A redução de chamadas de pixel pode melhorar o tempo de carregamento da página.

<br> 

**Assinei um feed de dados. Onde estão armazenados esses dados?**

Seu feed de dados e todas as características contidas no feed aparecem como subpastas e características no [!DNL Audience Manager]. Vá até **[!UICONTROL Audience Data > Traits]** e expanda a [!UICONTROL 3rd-Party Data] pasta para exibir suas características ou criar segmentos e modelos com esses dados.

<br> 

**O que é[!UICONTROL Tag Insertion Manager (TIM)]?**

O Audience Manager usou [!UICONTROL Tag Insertion Manager] (TIM) para criar e gerenciar [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Launch]. Para obter mais informações, consulte [Adobe Launch](https://docs.adobelaunch.com/) e Gerenciamento [](https://marketing.adobe.com/resources/help/en_US/dtm/)dinâmico de tags.

<br> 

**Quais são as diferenças entre os Modelos algorítmicos e as Recomendações de características? Quando devo usar cada um deles?**

**Modelos algorítmicos**

Os Modelos algorítmicos não só encontram as características mais influentes, como também pontuam os usuários com base nessas características e atribuem a cada usuário uma pontuação individual. Em seguida, você cria características algorítmicas para direcionar seus usuários. Com os controles de precisão e alcance no Construtor de características, você pode especificar quais usuários entre todos aqueles que têm as características influentes que deseja direcionar.

Os Modelos algorítmicos permitem selecionar usuários em diferentes níveis de precisão e testar no Audience Lab qual grupo de usuários converte melhor. Consulte o caso de uso detalhado em [Comparar modelos no Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

Em Modelos Algorítmicos, o modelo é executado a cada 8 dias e atualiza os usuários qualificados para características algorítmicas.

**Recomendações de característica**

As Recomendações de características são uma forma rápida de obter insights sobre outras características semelhantes àquelas que você está usando em um segmento.

Você deve usar as Recomendações de características quando:

* Você precisa de insights rápidos ao criar um segmento;
* Você está usando os segmentos para campanhas curtas ou quando deseja suprimir rapidamente o público-alvo que converte;
* Você está tentando maximizar o alcance.

<br> 

**Há alguma diferença entre os segmentos do Adobe Analytics e do Audience Manager?**

Sim, leia [Entendendo segmentos no Analytics e no Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) para obter uma descrição detalhada das diferenças.
