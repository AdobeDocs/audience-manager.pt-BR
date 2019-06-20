---
description: A Supressão instantânea entre dispositivos é a capacidade de omitir usuários entre vários dispositivos conectados a eles quando uma experiência em particular ocorrer em um desses dispositivos. Use o recurso de Supressão instantânea entre dispositivos para fornecer uma experiência consistente entre dispositivos para seus usuários. A experiência é disponibilizada pelos recursos não segmentados em tempo real do Audience Manager.
seo-description: A Supressão instantânea entre dispositivos é a capacidade de omitir usuários entre vários dispositivos conectados a eles quando uma experiência em particular ocorrer em um desses dispositivos. Use o recurso de Supressão instantânea entre dispositivos para fornecer uma experiência consistente entre dispositivos para seus usuários. A experiência é disponibilizada pelos recursos não segmentados em tempo real do Audience Manager.
seo-title: Supressão instantânea entre dispositivos
title: Supressão instantânea entre dispositivos
uuid: cb 11 b 9 cb -6 d 7 d -4 aa 9-91 b 0-c 2715857 d 821
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Supressão instantânea entre dispositivos {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] é a capacidade de suprimir usuários em vários dispositivos conectados a eles quando uma experiência específica ocorre em qualquer um desses dispositivos. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. A experiência é disponibilizada pelos recursos não segmentados em tempo real do Audience Manager.

## Visão geral {#overview}

[!UICONTROL Instant Cross-Device Suppression] fornece dois casos de uso principais: experiência do usuário e eficiência de mídia aprimorada.

* **Uma experiência do usuário aprimorada**: Os usuários que já compraram seu produto ou serviço não verão os mesmos anúncios antes da compra. Em vez disso, é possível exibir mensagens upsell ou cross-sell para produtos ou serviços que você sabe que eles não compraram.
* **Eficiência de mídia**: Otimize as despesas de sua campanha aplicando uma cap de frequência global em todos [!DNL DSP]os s. O cap de frequência pode ser implantado em tempo real para vários dispositivos que pertencem a um usuário.

The technical details of the real-time unsegmentation are described in length in [Profile Merge Rules and Device Un-Segmentation Processes](../../features/profile-merge-rules/merge-rule-unsegment.md). Leia para obter a implementação prática dos casos de uso descritos acima.

## Do Not Target Once Converted {#do-not-target-once}

Certifique-se de que os usuários que já tenham sido convertidos (compraram um produto, compraram uma assinatura etc.) não visualizarão as mesmas mensagens antes da conversão. You can obtain this using the [!UICONTROL AND NOT] logic, as follows.

1. Create a segment using two traits, and use the [!UICONTROL AND NOT] logic, as shown in the image below. Você deve usar uma característica baseada em regras para definir o evento de conversão para que o dessegmento seja acionado em tempo real. Read more about how to [create rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
1. Mapeie o segmento para qualquer número de destinos de servidor a servidor em tempo real. Read on about how to add segments to [server-to-server destinations](../../features/destinations/manage-destinations.md#add-edit-segments).

Seus visitantes se qualificam para o segmento contanto que não tenham sido convertidos. Assim que se qualificarem para a característica de conversão, eles deixarão de seguir a regra do segmento e são removidos instantaneamente do segmento.

![](assets/and_not_use_case.png)

## Do Not Target After x Impressions {#do-not-target-after-x}

Você pode ter certeza de que não está inundando seus usuários com o mesmo anúncio configurando os controles de recenticidade e frequência. Neste cenário, crie um segmento com duas características, como descrito nas etapas abaixo.

1. Create a segment using two traits, and use the [!UICONTROL AND] logic, as shown in the image below. Você deve usar uma característica baseada em regras para definir o evento de impressão para que o dessegmento seja acionado em tempo real. Read more about how to [create rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
   >[!NOTE]
   >
   >You can use [!UICONTROL Actionable Log Files] or [!UICONTROL Pixel Calls] to create traits based on user impressions. Read more about [Actionable Log Files](../../integration/media-data-integration/actionable-log-files.md) and [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md).
1. Aplique controles de frequência à segunda característica. Se desejar, você também pode adicionar controles de recenticidade. Read more about [how to apply recency and frequency controls](../../features/segments/recency-and-frequency.md).
1. Mapeie o segmento para qualquer número de destinos de servidor a servidor em tempo real. Read on about how to add segments to [server-to-server destinations](../../features/destinations/manage-destinations.md#add-edit-segments).

Nesse cenário, assim que os usuários acumularem mais de três impressões, eles serão removidos desse segmento e não verão essa criação em particular.

![](assets/impressions_use_case.png)

## Important Aspects to Note - Processing {#processing-notes}

Lembre-se destes aspectos relacionados ao processamento:

* Para que o recurso de dessegmentação em tempo real funcione, você deve mapear os segmentos desejados para destinos de servidor a servidor em tempo real.
* For devices connected to a device by a [device graph](../../features/profile-merge-rules/profile-link-use-case.md#recommendations), we enforce a four-device limit regarding evaluation and unsegmentation. This limitation is described in [Device Graph Options and Device Unsegmentation](../../features/profile-merge-rules/merge-rule-unsegment.md#device-graph-options-unsegmentation).​
* O comando descontinuado será incluído em um arquivo de lote, que é enviado para destinos a cada 24 horas, para vários dispositivos conectados pelo gráfico de dispositivos.
* The device must be seen in real-time (on the [Edge](../../reference/system-components/components-edge.md)) to prompt segment evaluation. For traits that have a [!UICONTROL time-to-live (TTL)] value, even if a trait [!DNL TTL] is met, the device will *not* automatically be unsegmented until the device is next seen in real-time.​ Read more about how to [Set a Trait Expiration Interval](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* If you are using the [!UICONTROL DCS API] to on-board rule-based traits in real-time, you can trigger the unsegment with the use of the [!UICONTROL AND NOT] logic. Read more about [sending data to the DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).​

## Important Aspects to Note - Timing {#timing-notes}

Lembre-se destes aspectos relacionados à temporização:

* A segment will be stored on the [Edge](../../reference/system-components/components-edge.md) for the same time period as a device profile is stored on the [!UICONTROL Edge], namely 14 days since last real-time interaction. Read more about data retention in our [Data Retention FAQ](../../faq/faq-privacy.md#data-retention-faq).
* It takes approximately 24 hours for the unsegment operation to propagate across [!UICONTROL DCS] regions. Read more about our [!UICONTROL DCS] regions [here](../../reference/system-components/components-data-collection.md) and [here](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).