---
description: Descreve os efeitos em usuários, dados e destinos segmentados ao pausar ou excluir um segmento ativo usando o Construtor de segmentos.
seo-description: Descreve os efeitos em usuários, dados e destinos segmentados ao pausar ou excluir um segmento ativo usando o Construtor de segmentos.
seo-title: Segmentos pausados e excluídos
solution: Audience Manager
title: Segmentos pausados e excluídos
uuid: 88 efe 4 af-f 9 -4 bce -920 a -352 bd 4 d 505 dd
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Paused and Deleted Segments {#paused-and-deleted-segments}

Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using [!UICONTROL Segment Builder].

## Acesso aos controles Pausar e Excluir

Hover over a segment name in the segments list to expose the **[!UICONTROL pause]** and **[!UICONTROL delete]** icons (in the [!UICONTROL Actions] column). Esses recursos afetam os segmentos conforme descrito abaixo.

## Funcionalidade de segmento pausado

Um segmento pausado (desativado):

* Interrompe a segmentação de usuários novos e qualificados.
* Mantém o status/associação de segmentação de um usuário (não remove um usuário do segmento).
* Permanece na lista de segmentos e pode ser reativada.
* Não envia dados para destinos associados.
* Retorna dados nos relatórios disponíveis (até a data de desativação).

## Funcionalidade de segmento excluída

Um segmento excluído:

* Interrompe a segmentação de usuários novos e qualificados.
* Remove usuários qualificados da associação de segmento.
* É removido da lista de segmentos.
* Não pode ser excluída.
* Não envia dados para destinos associados.
* Não retorna dados nos relatórios disponíveis.

>[!NOTE]
>
>You can also pause and delete segments using an [!DNL API] method. For more information, see [REST APIs](../../api/rest-api-main/rest-api-main.md).