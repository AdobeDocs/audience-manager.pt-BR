---
description: 'Destinos baseados em pessoas apresentam a noção de Públicos compartilháveis ao Audience Manager. Essa métrica ajuda você a entender quantos endereços de email com hash o Audience Manager pode compartilhar com a plataforma de destino. '
seo-description: 'Destinos baseados em pessoas apresentam a noção de Públicos compartilháveis ao Audience Manager. Essa métrica ajuda você a entender quantos endereços de email com hash o Audience Manager pode compartilhar com a plataforma de destino. '
seo-title: Públicos-alvo compartilháveis
solution: Audience Manager
title: Públicos-alvo compartilháveis
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# Públicos-alvo compartilháveis {#shareable-audiences}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a guiá-lo pela configuração e uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

[!DNL People-Based Destinations] trazer a noção de [!DNL Shareable Audiences] para o Audience Manager. Essa métrica ajuda você a entender quantos endereços de email com hash o Audience Manager pode compartilhar com a plataforma de destino.

[!DNL Shareable Audiences] é uma métrica que ajuda a interpretar os dados do público-alvo no contexto de [!DNL People-Based Destinations]. Você pode ver essa métrica na [!UICONTROL Destinations] página e na [!UICONTROL Segment] página.

## Públicos-alvo compartilháveis do segmento {#segment-shareable-audiences}

A [!DNL Segment Shareable Audience] métrica na página do segmento indica o número de endereços de email com hash da fonte de dados com [DPUUIDs](../../reference/ids-in-aam.md)correspondentes, que também se qualificam para o segmento definido no período de análise, dada a regra de mesclagem de perfil aplicada a ela, e que o Audience Manager pode compartilhar com a plataforma de destino.

Essa métrica tem um período de 1 dia de retrospectiva. Isso ajuda a entender o alcance do público-alvo para o segmento em um destino específico.

## Público-alvo compartilhável de destino {#destination-shareable-audience}

A métrica [!DNL Destination Shareable Audience] em uma página de destino baseada em pessoas indica o número total de endereços de email com hash da fonte de dados com [DPUUIDs](../../reference/ids-in-aam.md)correspondentes, que o Audience Manager pode compartilhar com a plataforma de destino, de todos os segmentos mapeados para esse destino.

![públicos-alvo compartilháveis](assets/dest-shareable-audiences.png)

Essa métrica tem um período de tempo de retrospectiva. Isso ajuda a entender a escala do público-alvo que você pode alcançar da fonte de dados de endereços de email com hash.

## Exemplo

Um cliente do Audience Manager tem uma fonte de dados com 110.000 [DPUUIDs](../../reference/ids-in-aam.md) (CRM IDs). Eles assimilam 100.000 endereços de email com hash no Audience Manager, para usá-los com vários destinos baseados em pessoas e executar uma sincronização de ID para os 100.000 endereços de email com hash em relação às IDs CRM. O cliente pode usar a regra de [!DNL All Cross-Device Profiles] mesclagem para criar três segmentos de público-alvo:

* Segmento A com uma contagem de população de 10.000, mapeado para o destino A;
* Segmento B com uma contagem de população de 20.000, mapeado para o destino A;
* Segmento C com uma contagem de população de 50.000, mapeado para o Destino B.

In this scenario:

* Segmento A Público-Alvo Compartilhável = 10.000;
* Público-alvo compartilhável do segmento B = 20.000;
* Público-alvo compartilhável do segmento C = 50.000;
* Destino A Público Compartilhável = Segmento A Público Compartilhável + Público Compartilhável Do Segmento B = 30.000;
* Público-alvo compartilhável de destino B = Público-alvo compartilhável do segmento C = 50.000.

![diagrama compartilhável-audiences](assets/shareable-audiences.png)

> [!NOTE]
>
> No exemplo acima, isso não significa que todos os 80.000 endereços de email com hash dos três segmentos correspondem às contas existentes nas plataformas de destino. Isso significa apenas que o Audience Manager envia os identificadores com hash dos três segmentos para seus respectivos destinos. Ao enviar segmentos de público-alvo para destinos baseados em pessoas, a correspondência de público-alvo ocorre no lado do parceiro. O Destino A pode ter até 30.000 contas de usuário correspondentes, enquanto o Destino B pode ter até 50.000 contas de usuário correspondentes, mas não há garantia de taxas de correspondência. A Adobe não tem acesso a métricas específicas do parceiro. Consulte Taxas de [correspondência](../../faq/faq-people-based-destinations.md#match-rates) para obter perguntas frequentes sobre a visibilidade de Destinos baseados em pessoas em taxas de correspondência.
