---
description: Descreve os efeitos em usuários segmentados, dados e destinos quando você pausar ou excluir um segmento ativo usando o Construtor de segmentos.
seo-description: Descreve os efeitos em usuários segmentados, dados e destinos quando você pausar ou excluir um segmento ativo usando o Construtor de segmentos.
seo-title: Segmentos pausados e excluídos
solution: Audience Manager
title: Segmentos pausados e excluídos
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 5%

---


# Segmentos pausados e excluídos {#paused-and-deleted-segments}

Descreve os efeitos em usuários segmentados, dados e destinos quando você pausar ou excluir um segmento ativo usando [!UICONTROL Segment Builder].

## Acesso aos controles Pausar e Excluir

Passe o cursor do mouse sobre o nome de um segmento na lista de segmentos para expor os ícones **[!UICONTROL pause]** e **[!UICONTROL delete]** os ícones (na [!UICONTROL Actions] coluna). Esses recursos afetam os segmentos conforme descrito abaixo.

## Funcionalidade de segmento pausada

Um segmento pausado (desativado):

* Interrompe a segmentação de usuários novos e qualificados.
* Mantém o status/associação de segmentação de um usuário (não remove um usuário do segmento).
* Permanece na lista do segmento e pode ser reativado.
* Não envia dados para destinos associados.
* Retorna dados nos relatórios disponíveis (até a data de desativação).

## Funcionalidade de segmento excluída

Um segmento excluído:

* Interrompe a segmentação de usuários novos e qualificados.
* Remove usuários qualificados da associação a segmentos.
* É removido da lista de segmentos.
* Não é possível cancelar a exclusão.
* Não envia dados para destinos associados.
* Não retorna dados nos relatórios disponíveis.

>[!NOTE]
>
>Também é possível pausar e excluir segmentos usando um [!DNL API] método. Para obter mais informações, consulte [REST APIs](../../api/rest-api-main/rest-api-main.md).