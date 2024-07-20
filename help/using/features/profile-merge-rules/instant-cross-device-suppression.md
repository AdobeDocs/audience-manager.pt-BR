---
description: A Supressão instantânea entre dispositivos é a capacidade de omitir usuários entre vários dispositivos conectados a eles quando uma experiência em particular ocorrer em um desses dispositivos. Use o recurso de Supressão instantânea entre dispositivos para fornecer uma experiência consistente entre dispositivos para seus usuários. A experiência é disponibilizada pelos recursos não segmentados em tempo real do Audience Manager.
seo-description: Instant Cross-Device Suppression is the ability to suppress users across multiple devices connected to them when a particular experience occurs on any of these devices. Use the Instant Cross-Device Suppression capability to deliver a consistent experience across devices to your users. This experience is made possible by the real-time unsegment capabilities in Audience Manager.
seo-title: Instant Cross-Device Suppression
title: Supressão instantânea entre dispositivos
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: 2643bebea8618124d5c96906e8dc89e21024d51a
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 6%

---

# Supressão instantânea entre dispositivos {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] é a capacidade de suprimir usuários em vários dispositivos conectados a eles quando uma determinada experiência ocorrer em um desses dispositivos. Use o recurso [!UICONTROL Instant Cross-Device Suppression] para fornecer uma experiência consistente entre dispositivos para seus usuários. A experiência é disponibilizada pelos recursos não segmentados em tempo real do Audience Manager.

## Visão geral {#overview}

O [!UICONTROL Instant Cross-Device Suppression] fornece dois casos de uso importantes: melhor experiência do usuário e eficiência de mídia.

* **Uma experiência de usuário aprimorada**: os usuários que já compraram seu produto ou serviço não verão os mesmos elementos de criação que antes da compra. Em vez disso, você pode exibir mensagens de venda adicional ou venda cruzada para produtos ou serviços que você sabe que eles não compraram.
* **Eficiência da mídia**: otimize seus gastos com campanha aplicando um limite de frequência global em todos os [!DNL DSP]s. O limite de frequência pode ser acionado em tempo real para vários dispositivos pertencentes a um usuário.

Os detalhes técnicos do cancelamento de segmentação em tempo real estão descritos detalhadamente em [Regras de mesclagem de perfis e Processos de cancelamento de segmentação de dispositivos](merge-rule-unsegment.md). Leia para a implementação prática dos casos de uso descritos acima.

## Não Direcionar Depois De Convertido {#do-not-target-once}

Verifique se os usuários já converteram (compraram um produto, compraram uma assinatura etc.) O não verá as mesmas mensagens que tinham antes da conversão. Você pode obter isso usando a lógica [!UICONTROL AND NOT] da seguinte maneira.

1. Crie um segmento usando duas características e use a lógica [!UICONTROL AND NOT], conforme mostrado na imagem abaixo. Você deve usar uma característica com base em regras para definir o evento de conversão para que o cancelamento de segmentos seja acionado em tempo real. Leia mais sobre como [criar características com base em regras](../traits/create-onboarded-rule-based-traits.md).
2. Mapeie o segmento para qualquer número de destinos de servidor para servidor em tempo real. Leia sobre como adicionar segmentos a [destinos de servidor para servidor](../destinations/add-edit-segments.md).

Seus visitantes se qualificam para o segmento desde que não tenham convertido. Assim que se qualificarem para a característica de conversão, elas deixarão de seguir a regra de segmento e serão instantaneamente removidas do segmento.

![](assets/and_not_use_case.png)

## Não direcionar após x impressões {#do-not-target-after-x}

Você pode garantir que não esteja inundando seus usuários com a mesma criatividade ao definir controles de recenticidade e frequência. Nesse cenário, crie um segmento com duas características, conforme descrito nas etapas abaixo.

1. Crie um segmento usando duas características e use a lógica [!UICONTROL AND], conforme mostrado na imagem abaixo. Você deve usar uma característica com base em regras para definir o evento de impressão para que o cancelamento de segmento seja acionado em tempo real. Leia mais sobre como [criar características com base em regras](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >Você pode usar o [!UICONTROL Actionable Log Files] ou o [!UICONTROL Pixel Calls] para criar características com base nas impressões do usuário. Leia mais sobre [Arquivos de Log Acionáveis](../../integration/media-data-integration/actionable-log-files.md) e [Chamadas de Pixel](../../integration/media-data-integration/impression-data-pixels.md).
2. Aplique controles de frequência à segunda característica. Se desejar, também é possível adicionar controles de recenticidade. Leia mais sobre [como aplicar controles de recenticidade e frequência](../segments/recency-and-frequency.md).
3. Mapeie o segmento para qualquer número de destinos de servidor para servidor em tempo real. Leia sobre como adicionar segmentos a [destinos de servidor para servidor](../destinations/add-edit-segments.md).

Nesse cenário, uma vez que os usuários tenham acumulado mais de três impressões, eles serão removidos desse segmento e não verão mais esse criativo específico.

![](assets/impressions_use_case.png)

## Aspectos importantes a observar - Processamento {#processing-notes}

Lembre-se dos seguintes aspectos relacionados ao processamento:

* Para que a capacidade não segmentada em tempo real funcione, mapeie os segmentos desejados para destinos de servidor para servidor em tempo real.
* Para dispositivos conectados a um dispositivo por um [gráfico de dispositivos](profile-link-use-case.md#recommendations), impomos um limite de quatro dispositivos em relação à avaliação e ao cancelamento de segmentação. Essa limitação é descrita em [Opções de gráfico de dispositivo e Cancelamento de segmentação de dispositivo](merge-rule-unsegment.md#device-graph-options-unsegmentation).&#x200B;
* O comando cancelar segmentos será incluído em um arquivo em lote, enviado para destinos a cada 24 horas, para vários dispositivos conectados pelo gráfico de dispositivos.
* O dispositivo deve ser visto em tempo real (no [Edge](../../reference/system-components/components-edge.md)) para solicitar a avaliação de segmentos em tempo real. Para características que têm um [!UICONTROL time-to-live (TTL)] quando a característica [!DNL TTL] é atendida, o dispositivo será automaticamente dessegmentado em 24 horas por meio do arquivo de lote..&#x200B; Leia mais sobre como [Definir um Intervalo de Expiração de Característica](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Se você estiver usando o [!UICONTROL DCS API] para integrar características baseadas em regras em tempo real, será possível acionar o cancelamento de segmentos com o uso da lógica [!UICONTROL AND NOT]. Leia mais sobre [envio de dados à API DCS](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).&#x200B;

## Aspectos importantes a serem observados - Tempo {#timing-notes}

Lembre-se destes aspectos relacionados ao tempo:

* Um segmento será armazenado no [Edge](../../reference/system-components/components-edge.md) pelo mesmo período em que um perfil de dispositivo é armazenado no [!UICONTROL Edge], ou seja, 14 dias desde a última interação em tempo real. Leia mais sobre retenção de dados em nossas [Perguntas frequentes sobre retenção de dados](../../faq/faq-privacy.md#data-retention-faq).
* Leva aproximadamente 24 horas para a operação de cancelamento de segmentos se propagar em [!DNL DCS] regiões. Leia mais sobre as [!DNL DCS] regiões [aqui](../../reference/system-components/components-data-collection.md) e [aqui](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
