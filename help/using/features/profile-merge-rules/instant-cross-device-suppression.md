---
description: A Supressão instantânea entre dispositivos é a capacidade de omitir usuários entre vários dispositivos conectados a eles quando uma experiência em particular ocorrer em um desses dispositivos. Use o recurso de Supressão instantânea entre dispositivos para fornecer uma experiência consistente entre dispositivos para seus usuários. A experiência é disponibilizada pelos recursos não segmentados em tempo real do Audience Manager.
seo-description: A Supressão instantânea entre dispositivos é a capacidade de omitir usuários entre vários dispositivos conectados a eles quando uma experiência em particular ocorrer em um desses dispositivos. Use o recurso de Supressão instantânea entre dispositivos para fornecer uma experiência consistente entre dispositivos para seus usuários. A experiência é disponibilizada pelos recursos não segmentados em tempo real do Audience Manager.
seo-title: Supressão instantânea entre dispositivos
title: Supressão instantânea entre dispositivos
uuid: cb 11 b 9 cb -6 d 7 d -4 aa 9-91 b 0-c 2715857 d 821
translation-type: tm+mt
source-git-commit: 86b23cc4097057fceadd4d0f7c5fad0db4f4232b

---


# Supressão instantânea entre dispositivos {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] é a capacidade de suprimir usuários em vários dispositivos conectados a eles quando uma experiência específica ocorre em qualquer um desses dispositivos. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. A experiência é disponibilizada pelos recursos não segmentados em tempo real do Audience Manager.

## Visão geral {#overview}

[!UICONTROL Instant Cross-Device Suppression] fornece dois casos de uso principais: experiência do usuário e eficiência de mídia aprimorada.

* **Uma experiência do usuário aprimorada**: Os usuários que já compraram seu produto ou serviço não verão os mesmos anúncios antes da compra. Em vez disso, é possível exibir mensagens upsell ou cross-sell para produtos ou serviços que você sabe que eles não compraram.
* **Eficiência de mídia**: Otimize as despesas de sua campanha aplicando uma cap de frequência global em todos [!DNL DSP]os s. O cap de frequência pode ser implantado em tempo real para vários dispositivos que pertencem a um usuário.

Os detalhes técnicos da unsegmentação em tempo real são descritos de forma detalhada em [Regras de mesclagem de perfil e processos de dessegmentação de dispositivo](../../features/profile-merge-rules/merge-rule-unsegment.md). Leia para obter a implementação prática dos casos de uso descritos acima.

## Não segmentar uma vez convertido {#do-not-target-once}

Certifique-se de que os usuários que já tenham sido convertidos (compraram um produto, compraram uma assinatura etc.) não visualizarão as mesmas mensagens antes da conversão. Você pode obter isso usando [!UICONTROL AND NOT] a lógica, da seguinte forma:

1. Crie um segmento usando duas características e use a [!UICONTROL AND NOT] lógica, como mostrado na imagem abaixo. Você deve usar uma característica baseada em regras para definir o evento de conversão para que o dessegmento seja acionado em tempo real. Leia mais sobre como [criar características baseadas em regras](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
1. Mapeie o segmento para qualquer número de destinos de servidor a servidor em tempo real. Leia sobre como adicionar segmentos a [destinos de servidor a servidor](../../features/destinations/add-edit-segments.md).

Seus visitantes se qualificam para o segmento contanto que não tenham sido convertidos. Assim que se qualificarem para a característica de conversão, eles deixarão de seguir a regra do segmento e são removidos instantaneamente do segmento.

![](assets/and_not_use_case.png)

## Não segmentar depois de x impressões {#do-not-target-after-x}

Você pode ter certeza de que não está inundando seus usuários com o mesmo anúncio configurando os controles de recenticidade e frequência. Neste cenário, crie um segmento com duas características, como descrito nas etapas abaixo.

1. Crie um segmento usando duas características e use a [!UICONTROL AND] lógica, como mostrado na imagem abaixo. Você deve usar uma característica baseada em regras para definir o evento de impressão para que o dessegmento seja acionado em tempo real. Leia mais sobre como [criar características baseadas em regras](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
   >[!NOTE]
   >
   >Você pode usar [!UICONTROL Actionable Log Files] ou [!UICONTROL Pixel Calls] criar características com base nas impressões do usuário. Leia mais sobre [arquivos de registro acionáveis](../../integration/media-data-integration/actionable-log-files.md) e [chamadas de pixel](../../integration/media-data-integration/impression-data-pixels.md).
1. Aplique controles de frequência à segunda característica. Se desejar, você também pode adicionar controles de recenticidade. Leia mais sobre [como aplicar controles de recenticidade e frequência](../../features/segments/recency-and-frequency.md).
1. Mapeie o segmento para qualquer número de destinos de servidor a servidor em tempo real. Leia sobre como adicionar segmentos a [destinos de servidor a servidor](../../features/destinations/add-edit-segments.md).

Nesse cenário, assim que os usuários acumularem mais de três impressões, eles serão removidos desse segmento e não verão essa criação em particular.

![](assets/impressions_use_case.png)

## Aspectos importantes para nota - Processamento {#processing-notes}

Lembre-se destes aspectos relacionados ao processamento:

* Para que o recurso de dessegmentação em tempo real funcione, você deve mapear os segmentos desejados para destinos de servidor a servidor em tempo real.
* Para dispositivos conectados a um dispositivo por gráfico [de dispositivo](../../features/profile-merge-rules/profile-link-use-case.md#recommendations), nós fazemos um limite de quatro dispositivos em relação à avaliação e à dessegmentação. Essa limitação é descrita nas [Opções de gráfico de dispositivo e na Segmentação do dispositivo](../../features/profile-merge-rules/merge-rule-unsegment.md#device-graph-options-unsegmentation).
* O comando descontinuado será incluído em um arquivo de lote, que é enviado para destinos a cada 24 horas, para vários dispositivos conectados pelo gráfico de dispositivos.
* O dispositivo deve ser visualizado em tempo real (na [borda](../../reference/system-components/components-edge.md)) para solicitar a avaliação do segmento. Para características que têm [!UICONTROL time-to-live (TTL)] um valor, mesmo que uma característica [!DNL TTL] seja atendida, o dispositivo *não* será automaticamente segmentado até que o dispositivo seja visualizado em tempo real. Leia mais sobre como [definir um intervalo](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)de expiração de características.
* Se você estiver usando [!UICONTROL DCS API] as características baseadas em regras em tempo real, poderá acionar o descontinuado com o uso da [!UICONTROL AND NOT] lógica. Leia mais sobre [o envio de dados para a API DCS](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Aspectos importantes a nota - Tempo {#timing-notes}

Lembre-se destes aspectos relacionados à temporização:

* Um segmento será armazenado na [borda](../../reference/system-components/components-edge.md) para o mesmo período de tempo que um perfil de dispositivo armazenado no [!UICONTROL Edge], isto é, 14 dias desde a última interação em tempo real. Leia mais sobre a retenção de dados em nossas Perguntas frequentes sobre retenção [de dados](../../faq/faq-privacy.md#data-retention-faq).
* Leva aproximadamente 24 horas para que a operação de dessegmentação se propague entre [!UICONTROL DCS] as regiões. Leia mais sobre nossas [!UICONTROL DCS] regiões [aqui](../../reference/system-components/components-data-collection.md) e [aqui](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).