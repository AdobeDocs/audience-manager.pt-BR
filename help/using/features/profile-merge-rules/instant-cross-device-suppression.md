---
description: A Supressão instantânea entre dispositivos é a capacidade de omitir usuários entre vários dispositivos conectados a eles quando uma experiência em particular ocorrer em um desses dispositivos. Use o recurso de Supressão instantânea entre dispositivos para fornecer uma experiência consistente entre dispositivos para seus usuários. A experiência é disponibilizada pelos recursos não segmentados em tempo real do Audience Manager.
seo-description: A Supressão instantânea entre dispositivos é a capacidade de omitir usuários entre vários dispositivos conectados a eles quando uma experiência em particular ocorrer em um desses dispositivos. Use o recurso de Supressão instantânea entre dispositivos para fornecer uma experiência consistente entre dispositivos para seus usuários. A experiência é disponibilizada pelos recursos não segmentados em tempo real do Audience Manager.
seo-title: Supressão instantânea entre dispositivos
title: Supressão instantânea entre dispositivos
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# Supressão instantânea entre dispositivos {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] é a capacidade de suprimir usuários em vários dispositivos conectados a eles quando uma experiência específica ocorre em qualquer um desses dispositivos. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. A experiência é disponibilizada pelos recursos não segmentados em tempo real do Audience Manager.

## Visão geral {#overview}

[!UICONTROL Instant Cross-Device Suppression] oferece dois casos principais de uso: melhor experiência do usuário e eficiência de mídia.

* **Uma experiência** do usuário aprimorada: Os usuários que já compraram seu produto ou serviço não verão as mesmas criações que antes da compra. Em vez disso, você pode exibir mensagens de venda ou venda cruzada para produtos ou serviços que você sabe que eles não compraram.
* **Eficiência** de mídia: Otimize os gastos com sua campanha aplicando um limite de frequência global em todos os [!DNL DSP]s. A limitação de frequência pode ser acionada em tempo real para vários dispositivos pertencentes a um usuário.

Os detalhes técnicos da dessegmentação em tempo real são descritos em detalhe nas Regras de mesclagem de [perfis e nos Processos](merge-rule-unsegment.md)de dessegmentação de dispositivos. Leia a seguir a implementação prática dos casos de uso descritos acima.

## Não direcionar uma vez convertido {#do-not-target-once}

Certifique-se de que os usuários que já converteram (compraram um produto, compraram uma assinatura etc.) não visualizarão as mesmas mensagens que antes da conversão. Você pode obtê-la usando a [!UICONTROL AND NOT] lógica, como segue.

1. Crie um segmento usando duas características e use a [!UICONTROL AND NOT] lógica, como mostrado na imagem abaixo. Você deve usar uma característica baseada em regras para definir o evento de conversão para que o cancelamento de segmento seja acionado em tempo real. Leia mais sobre como [criar características](../traits/create-onboarded-rule-based-traits.md)baseadas em regras.
2. Mapeie o segmento para qualquer número de destinos de servidor para servidor em tempo real. Leia sobre como adicionar segmentos a destinos [](../destinations/add-edit-segments.md)servidor a servidor.

Seus visitantes se qualificam para o segmento desde que não tenham sido convertidos. Assim que se qualificam para a característica de conversão, deixam de seguir a regra de segmento e são removidos instantaneamente do segmento.

![](assets/and_not_use_case.png)

## Não direcionar após x impressões {#do-not-target-after-x}

Você pode garantir que não esteja inundando seus usuários com a mesma criatividade ao configurar controles de recenticidade e frequência. Nesse cenário, crie um segmento com duas características, conforme descrito nas etapas abaixo.

1. Crie um segmento usando duas características e use a [!UICONTROL AND] lógica, como mostrado na imagem abaixo. Você deve usar uma característica baseada em regras para definir o evento de impressão para o cancelamento de segmento ser acionado em tempo real. Leia mais sobre como [criar características](../traits/create-onboarded-rule-based-traits.md)baseadas em regras.
   >[!NOTE]
   >
   >Você pode usar [!UICONTROL Actionable Log Files] ou [!UICONTROL Pixel Calls] criar características com base em impressões do usuário. Leia mais sobre arquivos [de registro acionáveis e chamadas](../../integration/media-data-integration/actionable-log-files.md) de [](../../integration/media-data-integration/impression-data-pixels.md)pixels.
2. Aplique controles de frequência à segunda característica. Se desejar, você também pode adicionar controles de recenticidade. Leia mais sobre [como aplicar controles](../segments/recency-and-frequency.md)recentes e de frequência.
3. Mapeie o segmento para qualquer número de destinos de servidor para servidor em tempo real. Leia sobre como adicionar segmentos a destinos [](../destinations/add-edit-segments.md)servidor a servidor.

Nesse cenário, depois que os usuários acumularem mais de três impressões, eles serão removidos desse segmento e não visualizarão mais essa criação específica.

![](assets/impressions_use_case.png)

## Aspectos importantes da observação - Processamento {#processing-notes}

Lembre-se destes aspectos relacionados ao processamento:

* Para que o recurso de cancelamento de segmento em tempo real funcione, é necessário mapear os segmentos desejados para destinos de servidor para servidor em tempo real.
* Para dispositivos conectados a um dispositivo por um gráfico [de](profile-link-use-case.md#recommendations)dispositivos, impomos um limite de quatro dispositivos em relação à avaliação e à dessegmentação. Essa limitação é descrita em Opções de gráfico de [dispositivo e Dessegmentação](merge-rule-unsegment.md#device-graph-options-unsegmentation)de dispositivo. &#x200B;
* O comando unsegment será incluído em um arquivo de lote, enviado para destinos a cada 24 horas, para vários dispositivos conectados pelo gráfico de dispositivos.
* O dispositivo deve ser visto em tempo real (no [Edge](../../reference/system-components/components-edge.md) ) para solicitar a avaliação de segmentos em tempo real. Para características que têm um [!UICONTROL time-to-live (TTL)] momento em que a característica [!DNL TTL] é atendida, o dispositivo será dessegmentado automaticamente em 24 horas por meio do arquivo de lote.. &#x200B; Leia mais sobre como [definir um intervalo](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval)de expiração de característica.
* Se você estiver usando as características com base em regras integradas [!UICONTROL DCS API] em tempo real, é possível acionar a anulação de segmento com o uso da [!UICONTROL AND NOT] lógica. Leia mais sobre como [enviar dados para a API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)DCS. &#x200B;

## Aspectos importantes da observação - Tempo {#timing-notes}

Lembre-se destes aspectos relacionados à temporização:

* Um segmento será armazenado no [Edge](../../reference/system-components/components-edge.md) pelo mesmo período de tempo que um perfil de dispositivo é armazenado no [!UICONTROL Edge], ou seja, 14 dias desde a última interação em tempo real. Leia mais sobre retenção de dados nas Perguntas frequentes sobre retenção de [dados](../../faq/faq-privacy.md#data-retention-faq).
* Leva aproximadamente 24 horas para a operação de cancelamento de segmento se propagar pelas [!UICONTROL DCS] regiões. Leia mais sobre nossas [!UICONTROL DCS] regiões [aqui](../..//reference/system-components/components-data-collection.md) e [aqui](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
