---
description: 'Destinos com base em pessoas apresentam a noção de públicos-alvo compartilháveis para o Audience Manager. Essa métrica ajuda você a entender quantos endereços de email com hash o Audience Manager pode compartilhar com a plataforma de destino. '
seo-description: 'Destinos com base em pessoas apresentam a noção de públicos-alvo compartilháveis para o Audience Manager. Essa métrica ajuda você a entender quantos endereços de email com hash o Audience Manager pode compartilhar com a plataforma de destino. '
seo-title: Públicos compartilháveis
solution: Audience Manager
title: Públicos compartilháveis
feature: Destinos com base em pessoas
exl-id: 2860c105-1091-4779-bf40-e66faa941af0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# Públicos compartilháveis {#shareable-audiences}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e uso deste recurso. Nada neste documento é de aconselhamento jurídico. Consulte o seu advogado para obter orientação jurídica.

[!DNL People-Based Destinations] trazer a noção de  [!DNL Shareable Audiences] para Audience Manager. Essa métrica ajuda você a entender quantos endereços de email com hash o Audience Manager pode compartilhar com a plataforma de destino.

[!DNL Shareable Audiences] é uma métrica que ajuda a interpretar os dados do público-alvo no contexto de  [!DNL People-Based Destinations]. Você pode ver essa métrica na página [!UICONTROL Destinations] e na página [!UICONTROL Segment].

## Segmentar públicos compartilháveis {#segment-shareable-audiences}

A métrica [!DNL Segment Shareable Audience] na página de segmento indica o número de endereços de email com hash da fonte de dados com [DPUUIDs](../../reference/ids-in-aam.md) correspondentes, que também se qualificam para o segmento definido no período de lookback específico, considerando a regra de mesclagem de perfis aplicada a ela, e esse Audience Manager pode compartilhar com a plataforma de destino.

Essa métrica tem um período de análise de 1 dia. Isso ajuda você a entender o alcance do público-alvo para o segmento em um destino específico.

## Público-alvo compartilhável de destino {#destination-shareable-audience}

A métrica [!DNL Destination Shareable Audience] em uma página de destino com base em pessoas indica o número total de endereços de email com hash da fonte de dados com [DPUUIDs](../../reference/ids-in-aam.md) correspondente, que o Audience Manager pode compartilhar com a plataforma de destino, de todos os segmentos mapeados para esse destino.

![públicos-alvo compartilháveis](assets/dest-shareable-audiences.png)

Essa métrica tem um período de análise vitalício. Isso ajuda você a entender a escala do público-alvo que pode ser acessado da fonte de dados de endereços de email com hash.

## Exemplo

Um cliente do Audience Manager tem uma fonte de dados com 110.000 [DPUUIDs](../../reference/ids-in-aam.md) (IDs do CRM). Eles assimilam 100.000 endereços de email com hash no Audience Manager, para usá-los com vários destinos com base em pessoas e executar uma sincronização de ID para os 100.000 endereços de email com hash em relação às IDs do CRM. O cliente pode usar a regra de mesclagem [!DNL All Cross-Device Profiles] para criar três segmentos de público-alvo:

* Segmento A com uma contagem de população de 10.000, mapeado para o Destino A;
* Segmento B com uma contagem de população de 20.000, mapeado para o Destino A;
* Segmento C com uma contagem de população de 50.000, mapeado para o Destino B.

Neste cenário:

* Público-alvo compartilhável do segmento A = 10.000;
* Público-alvo compartilhável do segmento B = 20.000;
* Público-alvo compartilhável do segmento C = 50.000;
* Destino A Público-alvo compartilhável = Segmento A Público-alvo compartilhável + Segmento B Público-alvo compartilhável = 30.000;
* Público-alvo compartilhável de destino B = Público-alvo compartilhável do segmento C = 50.000.

![diagrama de públicos-alvo compartilháveis](assets/shareable-audiences.png)

>[!NOTE]
>
>No exemplo acima, não significa que todos os 80.000 endereços de email com hash dos três segmentos correspondam às contas existentes nas plataformas de destino. Isso significa apenas que o Audience Manager envia os identificadores com hash dos três segmentos para seus respectivos destinos. Ao enviar segmentos de público-alvo para destinos com base em pessoas, a correspondência de públicos-alvo ocorre no lado do parceiro. O Destino A pode ter até 30.000 contas de usuário correspondentes, enquanto o Destino B pode ter até 50.000 contas de usuário correspondentes, mas não há garantia de taxas de correspondência. O Adobe não tem acesso a métricas específicas do parceiro. Consulte [Taxas de correspondência](../../faq/faq-people-based-destinations.md#match-rates) para obter perguntas frequentes sobre a visibilidade de Destinos com base em pessoas em taxas de correspondência.
