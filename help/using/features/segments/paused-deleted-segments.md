---
description: Descreve os efeitos em usuários, dados e destinos segmentados quando você pausa ou exclui um segmento ativo usando o Construtor de segmentos.
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: Segmentos pausados e excluídos
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '187'
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
