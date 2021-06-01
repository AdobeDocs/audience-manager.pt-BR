---
description: Descreve os efeitos nos usuários segmentados, dados e destinos quando você pausar ou excluir um segmento ativo usando o Construtor de segmentos.
seo-description: Descreve os efeitos nos usuários segmentados, dados e destinos quando você pausar ou excluir um segmento ativo usando o Construtor de segmentos.
seo-title: Segmentos pausados e excluídos
solution: Audience Manager
title: Segmentos pausados e excluídos
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: 'Segmentos '
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 6%

---

# Segmentos pausados e excluídos {#paused-and-deleted-segments}

Descreve os efeitos nos usuários segmentados, dados e destinos quando você pausar ou excluir um segmento ativo usando [!UICONTROL Segment Builder].

## Acesso aos Controles de pausa e exclusão

Passe o mouse sobre um nome de segmento na lista de segmentos para expor os ícones **[!UICONTROL pause]** e **[!UICONTROL delete]** (na coluna [!UICONTROL Actions]). Esses recursos afetam os segmentos conforme descrito abaixo.

## Funcionalidade de segmento pausado

Um segmento pausado (desativado):

* Interrompe a segmentação de novos usuários qualificados.
* Mantém o status/associação de segmentação de um usuário (não remove um usuário do segmento).
* Permanece na lista de segmentos e pode ser reativado.
* Não envia dados para destinos associados.
* Retorna dados nos relatórios disponíveis (até a data de desativação).

## Funcionalidade de segmento excluída

Um segmento excluído:

* Interrompe a segmentação de novos usuários qualificados.
* Remove usuários qualificados da associação de segmentos.
* É removido da lista de segmentos.
* Não é possível remover a eliminação.
* Não envia dados para destinos associados.
* Não retorna dados nos relatórios disponíveis.

>[!NOTE]
>
>Você também pode pausar e excluir segmentos usando um método [!DNL API]. Para obter mais informações, consulte [REST APIs](../../api/rest-api-main/rest-api-main.md).
