---
description: Descreve os efeitos em usuários, dados e destinos segmentados quando você pausa ou exclui um segmento ativo usando o Construtor de segmentos.
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: Segmentos pausados e excluídos
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
TQID: https://experienceleague.adobe.com/aLnmaOxB3fkGdwq4XjKz8SFKizwHI7Ll5rBUb-o34BM
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2: id: c2c33729-f309-4bc2-92ba-87c475259df3
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 0%

---

# Segmentos pausados e excluídos {#paused-and-deleted-segments}

Descreve os efeitos em usuários, dados e destinos segmentados quando você pausa ou exclui um segmento ativo usando o [!UICONTROL Segment Builder].

## Acesso aos controles Pausar e Excluir

Passe o mouse sobre um nome de segmento na lista de segmentos para expor os ícones **[!UICONTROL pause]** e **[!UICONTROL delete]** (na coluna [!UICONTROL Actions]). Esses recursos afetam os segmentos conforme descrito abaixo.

## Funcionalidade de segmento pausado

Um segmento pausado (desativado):

* Para de segmentar usuários novos e qualificados.
* Mantém o status de segmentação/associação de um usuário (não remove um usuário do segmento).
* Permanece na lista de segmentos e pode ser reativado.
* Não envia dados para destinos associados.
* Retorna dados nos relatórios disponíveis (até a data de desativação).

## Funcionalidade de segmentos excluídos

Um segmento excluído:

* Para de segmentar usuários novos e qualificados.
* Remove usuários qualificados da associação ao segmento.
* É removido da lista de segmentos.
* Não é possível cancelar a exclusão.
* Não envia dados para destinos associados.
* Não retorna dados nos relatórios disponíveis.

>[!NOTE]
>
>Também é possível pausar e excluir segmentos usando um método [!DNL API]. Para obter mais informações, consulte [REST APIs](../../api/rest-api-main/rest-api-main.md).
