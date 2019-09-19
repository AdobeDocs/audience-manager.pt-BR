---
description: A página de resumo do segmento exibe detalhes como nome, características no segmento, regras, dados de desempenho e informações de mapeamento de destino.
seo-description: A página de resumo do segmento exibe detalhes como nome, características no segmento, regras, dados de desempenho e informações de mapeamento de destino.
seo-title: ' Exibição do resumo do segmento'
solution: Audience Manager
title: ' Exibição do resumo do segmento'
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# Exibição do resumo do segmento {#segment-summary-view}

A [!UICONTROL Segment Summary] página exibe detalhes como nome, características no segmento, dados de desempenho de regras e informações de mapeamento de destino.

Clique no nome de um segmento no painel principal para acessar a página de resumo. As seções de resumo incluem:

1. **[!UICONTROL Basic Information]** : Mostra detalhes obrigatórios e opcionais especificados quando o segmento foi criado.
2. **[!UICONTROL Segment Graph]** : Exibe dados de desempenho graficamente e para intervalos fixos de 1, 7, 14, 30, 60 e 90 dias. Explicamos os números da população de segmentos em um artigo [](../../features/segments/segment-builder-data.md)separado.

   ![gráfico de segmentos](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]** : O relatório mostra o número de pessoas ou residências que se qualificam para um segmento contando o número de IDs de dispositivos cruzados e/ou IDs de gráficos de dispositivos externos vinculados aos dispositivos qualificados para o segmento (mostrados pelo [!UICONTROL Total Segment Population]). As IDs entre dispositivos e as IDs de gráfico de dispositivo externo mostradas neste relatório são usadas para unir perfis à regra de mesclagem de perfil que o segmento está usando. Este relatório é exibido somente se você selecionou uma fonte de dados entre dispositivos ou um Gráfico de dispositivos externos na regra de mesclagem de perfil que o segmento está usando.

   ![gráfico de segmentos](assets/segment-type.png)

   >[!NOTE]
   >
   >O Audience Manager só exibe o [!UICONTROL Identity Type Breakdown] relatório se você tiver IDs de dispositivo cruzado qualificadas para o segmento.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/?captions=por_br)

4. **[!UICONTROL Segment Rules]** : Lista as características no segmento junto com as regras de qualificação.
5. **[!UICONTROL Destination Mappings]** : Lista mapeamentos de destino para o segmento.
6. **[!UICONTROL Management Tools]** : Controles que permitem criar, editar, clonar e excluir segmentos.