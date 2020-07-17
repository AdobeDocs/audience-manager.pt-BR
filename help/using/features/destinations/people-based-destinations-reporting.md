---
description: 'Destinos baseados em pessoas introduzem a noção de Audiência para Audience Manager. Essa métrica ajuda você a entender quantos endereços de email com hash o Audience Manager pode compartilhar com a plataforma de destino. '
seo-description: 'Destinos baseados em pessoas introduzem a noção de Audiência para Audience Manager. Essa métrica ajuda você a entender quantos endereços de email com hash o Audience Manager pode compartilhar com a plataforma de destino. '
seo-title: Públicos compartilháveis
solution: Audience Manager
title: Públicos compartilháveis
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 1%

---


# Públicos compartilháveis {#shareable-audiences}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo durante a configuração e o uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

[!DNL People-Based Destinations] trazer a noção de &quot;Audience Manager&quot; [!DNL Shareable Audiences] . Essa métrica ajuda você a entender quantos endereços de email com hash o Audience Manager pode compartilhar com a plataforma de destino.

[!DNL Shareable Audiences] é uma métrica que ajuda a interpretar os dados de audiência no contexto de [!DNL People-Based Destinations]. Você pode ver essa métrica na [!UICONTROL Destinations] página e na [!UICONTROL Segment] página.

## Audiências de compartilhamento de segmentos {#segment-shareable-audiences}

A [!DNL Segment Shareable Audience] métrica na página do segmento indica o número de endereços de email com hash da fonte de dados com [DPUUIDs](../../reference/ids-in-aam.md)correspondentes, que também se qualificam para o segmento definido no período de análise, dada a regra de mesclagem de perfil aplicada a ela, e esse Audience Manager pode compartilhar com a plataforma de destino.

Essa métrica tem um período de 1 dia de retrospectiva. Isso ajuda você a entender o alcance da audiência do segmento em um destino específico.

## Audiência compartilhável de destino {#destination-shareable-audience}

A métrica [!DNL Destination Shareable Audience] em uma página de destino baseada em pessoas indica o número total de endereços de email com hash da fonte de dados com [DPUUIDs](../../reference/ids-in-aam.md)correspondentes, que o Audience Manager pode compartilhar com a plataforma de destino, de todos os segmentos mapeados para esse destino.

![audiências compartilháveis](assets/dest-shareable-audiences.png)

Essa métrica tem um período de tempo de retrospectiva. Isso ajuda você a entender a escala da audiência que pode ser alcançada a partir da fonte de dados de endereços de email com hash.

## Exemplo

Um cliente Audience Manager tem uma fonte de dados com 110.000 [DPUUIDs](../../reference/ids-in-aam.md) (CRM IDs). Eles assimilam 100.000 endereços de email com hash no Audience Manager, para usá-los com vários destinos baseados em pessoas e executam uma sincronização de ID para os 100.000 endereços de email com hash em relação às IDs CRM. O cliente pode usar a regra de [!DNL All Cross-Device Profiles] mesclagem para criar três segmentos de audiência:

* Segmento A com uma contagem de população de 10.000, mapeado para o destino A;
* Segmento B com uma contagem de população de 20.000, mapeado para o destino A;
* Segmento C com uma contagem de população de 50.000, mapeado para o Destino B.

Neste cenário:

* Audiência Compartilhável Do Segmento A = 10.000;
* Audiência compartilhável do segmento B = 20.000;
* Audiência Compartilhável do Segmento C = 50.000;
* Audiência de destino A compartilhável = Audiência compartilhável do segmento A + Audiência compartilhável do segmento B = 30.000;
* Audiência compartilhável de destino B = Audiência compartilhável do segmento C = 50.000.

![diagrama de audiências compartilhável](assets/shareable-audiences.png)

>[!NOTE]
>
>No exemplo acima, isso não significa que todos os 80.000 endereços de email com hash dos três segmentos correspondem às contas existentes nas plataformas de destino. Isso significa apenas que o Audience Manager envia os identificadores com hash dos três segmentos para seus respectivos destinos. Ao enviar segmentos de audiência para destinos baseados em pessoas, a correspondência de audiências ocorre no lado do parceiro. O Destino A pode ter até 30.000 contas de usuário correspondentes, enquanto o Destino B pode ter até 50.000 contas de usuário correspondentes, mas não há garantia de taxas de correspondência. A Adobe não tem acesso a métricas específicas do parceiro. Consulte Taxas de [correspondência](../../faq/faq-people-based-destinations.md#match-rates) para obter perguntas frequentes sobre a visibilidade de Destinos baseados em pessoas em taxas de correspondência.
