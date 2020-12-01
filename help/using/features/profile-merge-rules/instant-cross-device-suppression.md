---
description: A Supressão instantânea entre dispositivos é a capacidade de omitir usuários entre vários dispositivos conectados a eles quando uma experiência em particular ocorrer em um desses dispositivos. Use o recurso de Supressão instantânea entre dispositivos para fornecer uma experiência consistente entre dispositivos para seus usuários. A experiência é disponibilizada pelos recursos não segmentados em tempo real do Audience Manager.
seo-description: A Supressão instantânea entre dispositivos é a capacidade de omitir usuários entre vários dispositivos conectados a eles quando uma experiência em particular ocorrer em um desses dispositivos. Use o recurso de Supressão instantânea entre dispositivos para fornecer uma experiência consistente entre dispositivos para seus usuários. A experiência é disponibilizada pelos recursos não segmentados em tempo real do Audience Manager.
seo-title: Supressão instantânea entre dispositivos
title: Supressão instantânea entre dispositivos
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 15%

---


# Supressão instantânea entre dispositivos {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] é a capacidade de suprimir usuários em vários dispositivos conectados a eles quando uma experiência específica ocorre em qualquer um desses dispositivos. Use o recurso [!UICONTROL Instant Cross-Device Suppression] para fornecer uma experiência consistente em todos os dispositivos aos usuários. A experiência é disponibilizada pelos recursos não segmentados em tempo real do Audience Manager.

## Visão geral {#overview}

[!UICONTROL Instant Cross-Device Suppression] oferece dois casos principais de uso: melhor experiência do usuário e eficiência de mídia.

* **Uma experiência** do usuário aprimorada: Os usuários que já compraram seu produto ou serviço não verão as mesmas criações que antes da compra. Em vez disso, você pode exibir mensagens de venda ou venda cruzada para produtos ou serviços que você sabe que eles não compraram.
* **Eficiência** de mídia: Otimize seus gastos com campanhas aplicando um limite de frequência global em todos os  [!DNL DSP]s. A limitação de frequência pode ser acionada em tempo real para vários dispositivos pertencentes a um usuário.

Os detalhes técnicos da dessegmentação em tempo real são descritos em comprimento em [Regras de mesclagem de Perfis e Processos de dessegmentação de dispositivos](merge-rule-unsegment.md). Leia a seguir a implementação prática dos casos de uso descritos acima.

## Não Público alvo uma vez convertido {#do-not-target-once}

Certifique-se de que os usuários que já converteram (compraram um produto, adquiriram uma subscrição etc.) não visualizarão as mesmas mensagens que antes da conversão. Você pode obter isso usando a lógica [!UICONTROL AND NOT], como a seguir.

1. Crie um segmento usando duas características e use a lógica [!UICONTROL AND NOT], conforme mostrado na imagem abaixo. Você deve usar uma característica baseada em regras para definir o evento de conversão para que o cancelamento de segmento seja acionado em tempo real. Leia mais sobre como [criar características com base em regras](../traits/create-onboarded-rule-based-traits.md).
2. Mapeie o segmento para qualquer número de destinos de servidor para servidor em tempo real. Leia sobre como adicionar segmentos a [destinos servidor a servidor](../destinations/add-edit-segments.md).

Seus visitantes se qualificam para o segmento desde que não tenham sido convertidos. Assim que se qualificam para a característica de conversão, deixam de seguir a regra de segmento e são removidos instantaneamente do segmento.

![](assets/and_not_use_case.png)

## Não Público alvo após x impressões {#do-not-target-after-x}

Você pode garantir que não esteja inundando seus usuários com a mesma criatividade ao configurar controles de recenticidade e frequência. Nesse cenário, crie um segmento com duas características, conforme descrito nas etapas abaixo.

1. Crie um segmento usando duas características e use a lógica [!UICONTROL AND], conforme mostrado na imagem abaixo. Você deve usar uma característica baseada em regras para definir o evento de impressão para que o cancelamento de segmento seja acionado em tempo real. Leia mais sobre como [criar características com base em regras](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >Você pode usar [!UICONTROL Actionable Log Files] ou [!UICONTROL Pixel Calls] para criar características com base nas impressões do usuário. Leia mais sobre [Arquivos de registro acionáveis](../../integration/media-data-integration/actionable-log-files.md) e [Chamadas de pixel](../../integration/media-data-integration/impression-data-pixels.md).
2. Aplique controles de frequência à segunda característica. Se desejar, você também pode adicionar controles de recenticidade. Leia mais sobre [como aplicar controles de recenticidade e frequência](../segments/recency-and-frequency.md).
3. Mapeie o segmento para qualquer número de destinos de servidor para servidor em tempo real. Leia sobre como adicionar segmentos a [destinos servidor a servidor](../destinations/add-edit-segments.md).

Nesse cenário, depois que os usuários acumularem mais de três impressões, eles serão removidos desse segmento e não visualizarão mais essa criação específica.

![](assets/impressions_use_case.png)

## Aspectos importantes a observar - Processando {#processing-notes}

Lembre-se destes aspectos relacionados ao processamento:

* Para que o recurso de cancelamento de segmento em tempo real funcione, é necessário mapear os segmentos desejados para destinos de servidor para servidor em tempo real.
* Para dispositivos conectados a um dispositivo por um [gráfico de dispositivo](profile-link-use-case.md#recommendations), impomos um limite de quatro dispositivos em relação à avaliação e à dessegmentação. Essa limitação é descrita em [Opções de gráfico de dispositivo e Dessegmentação de dispositivo](merge-rule-unsegment.md#device-graph-options-unsegmentation). &#x200B;
* O comando unsegment será incluído em um arquivo de lote, enviado para destinos a cada 24 horas, para vários dispositivos conectados pelo gráfico de dispositivos.
* O dispositivo deve ser visto em tempo real (em [Edge](../../reference/system-components/components-edge.md) para solicitar a avaliação de segmentos em tempo real. Para características que têm [!UICONTROL time-to-live (TTL)] quando a característica [!DNL TTL] é atendida, o dispositivo será automaticamente não segmentado dentro de 24 horas por meio do arquivo de lote.. &#x200B; Leia mais sobre como [Definir um intervalo de expiração de característica](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Se você estiver usando [!UICONTROL DCS API] para as características baseadas em regras a bordo em tempo real, é possível acionar o cancelamento de segmento com o uso da lógica [!UICONTROL AND NOT]. Leia mais sobre [como enviar dados para a API do DCS](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## Aspectos importantes da observação - Tempo {#timing-notes}

Lembre-se destes aspectos relacionados à temporização:

* Um segmento será armazenado no [Edge](../../reference/system-components/components-edge.md) pelo mesmo período de tempo em que um perfil de dispositivo é armazenado no [!UICONTROL Edge], ou seja, 14 dias desde a última interação em tempo real. Leia mais sobre a retenção de dados nas [Perguntas frequentes sobre retenção de dados](../../faq/faq-privacy.md#data-retention-faq).
* Leva aproximadamente 24 horas para a operação de cancelamento de segmento se propagar pelas regiões [!DNL DCS]. Leia mais sobre nossas [!DNL DCS] regiões [aqui](../..//reference/system-components/components-data-collection.md) e [aqui](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
