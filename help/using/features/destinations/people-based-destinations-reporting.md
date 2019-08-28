---
description: 'Os destinos baseados em pessoas apresentam a noção de Públicos-alvo compartilháveis no Audience Manager. Essa métrica ajuda você a entender quantos endereços de email com hash o Audience Manager pode compartilhar com a plataforma de destino. '
seo-description: 'Os destinos baseados em pessoas apresentam a noção de Públicos-alvo compartilháveis no Audience Manager. Essa métrica ajuda você a entender quantos endereços de email com hash o Audience Manager pode compartilhar com a plataforma de destino. '
seo-title: Públicos-alvo compartilháveis
solution: Audience Manager
title: Públicos-alvo compartilháveis
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# Públicos-alvo compartilháveis {#shareable-audiences}

[!DNL People-Based Destinations] trazer a noção do [!DNL Shareable Audiences] Audience Manager. Essa métrica ajuda você a entender quantos endereços de email com hash o Audience Manager pode compartilhar com a plataforma de destino.

[!DNL Shareable Audiences] é uma métrica que ajuda a interpretar dados de público-alvo no contexto. [!DNL People-Based Destinations] É possível visualizar essa métrica na [!UICONTROL Destinations] página e [!UICONTROL Segment] na página.

## Públicos-alvo compartilháveis por segmento {#segment-shareable-audiences}

A [!DNL Segment Shareable Audience] métrica na página de segmento indica o número de endereços de email com hash a partir da fonte de dados com [dpuuids correspondentes](../../reference/ids-in-aam.md), que também se qualificam para o segmento definido no período de análise fornecido, considerando a regra de mesclagem de perfil aplicada e que o Audience Manager pode compartilhar com a plataforma de destino.

Essa métrica tem um período de retrospectiva de 1 dias. Isso ajuda você a entender o alcance do público-alvo para o segmento em um destino específico.

## Público compartilhável de destino {#destination-shareable-audience}

A [!DNL Destination Shareable Audience] métrica em uma página de destino baseada em pessoas indica o número total de endereços de email com hash da fonte de dados com a correspondência [dpuuids](../../reference/ids-in-aam.md), que o Audience Manager pode compartilhar com a plataforma de destino, de todos os segmentos mapeados para esse destino.

![shareable-audiences](assets/dest-shareable-audiences.png)

Essa métrica tem um período de retrospectiva vitalício. Isso ajuda você a entender a escala do público-alvo que pode atingir a partir da fonte de dados com hash lida.

## Exemplo

Um cliente do Audience Manager tem uma fonte de dados com 110,000 [dpuuids](../../reference/ids-in-aam.md) (IDs CRM). Eles assimilam addresses 00,000 endereços de email com hash no Audience Manager, para usá-los com vários destinos baseados em pessoas e executar uma sincronização de ID para endereços de email com hash 100,000 com relação às IDs CRM. O cliente pode usar a regra [!DNL All Cross-Device Profiles] de mesclagem para criar três segmentos do público-alvo:

* O segmento A com uma contagem de preenchimento de 10,000, mapeado para Destino A;
* O segmento B com uma contagem de preenchimento de 20,000, mapeado para Destino A;
* O segmento C com uma contagem de preenchimento de 50,000, mapeado para Destino B.

Neste cenário:

* Segmentar um público-alvo compartilhável = 10,000;
* Segmento shareb compartilhável = 20,000;
* Segmento sharec compartilhável = 50,000;
* Destino Um público compartilhável = Segmento Um público-alvo compartilhável + Segmento B Compartilhável compartilhável = 30,000;
* Público-alvo compartilhável B = Público compartilhável de segmento = 50,000.

![compartilhamento de públicos-alvo](assets/shareable-audiences.png)

> [!NOTE]
>
> No exemplo acima, não significa que todos os endereços de email 80,000 com hash de três segmentos correspondem às contas existentes nas plataformas de destino. Isso significa apenas que o Audience Manager envia os identificadores hash dos três segmentos para seus respectivos destinos. Ao enviar segmentos de público-alvo para destinos baseados em pessoas, a correspondência do público-alvo ocorre no parceiro. O Destino A pode ter até 30,000 contas de usuário correspondentes, enquanto o Destino B pode ter até 50,000 contas de usuário correspondentes, mas não há garantia de taxas de correspondência. A Adobe não tem acesso a métricas específicas do parceiro. Consulte [Taxas](../../faq/faq-people-based-destinations.md#match-rates) de correspondência para perguntas frequentes sobre a visibilidade de Destinos baseados em pessoas em taxas de correspondência.
