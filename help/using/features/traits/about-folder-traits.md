---
description: Características de pastas permitem que você agregue características que residam na mesma pasta e todas as pastas filho em um segmento direcionável.
keywords: avaliador de tamanho de segmento; sse
seo-description: Características de pastas permitem que você agregue características que residam na mesma pasta e todas as pastas filho em um segmento direcionável.
seo-title: Características da pasta sobre
solution: Audience Manager
title: Características da pasta sobre
uuid: e 561 ce 8 f -6 c 90-44 a 7-b 034-685533 f 29030
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Folder Traits: About {#folder-traits-about}

[!UICONTROL Folder traits] permitem que você agregue características automaticamente que residam na mesma pasta e todas as pastas secundárias em um segmento direcionável.

## Benefits of Using Folder Traits {#benefits}

A [!UICONTROL folder trait] contains all the traits in a parent folder and its associated child folders. Isso permite segmentar e direcionar automaticamente os usuários em diferentes níveis de pasta. Por exemplo, digamos que você tenha uma estrutura de pastas como isto:

`*` Eletrônicos (pai)

`*` Laptops (filho)

`*` Marcas (nehas)

[!UICONTROL Folder traits] qualifica todos os usuários nessas pastas de uma forma automaticamente criada [!DNL Electronics][!UICONTROL Folder Trait] (com base no nome da pasta pai). Além disso, esse processo se repete à medida que você move para baixo a estrutura do arquivo. In this case, folder traits capture all of the users in the Laptops and Brands folders in an automatically created Laptops [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] são selecionáveis nas expressões de segmento. Selecting a [!UICONTROL folder trait] is equivalent to selecting all the traits within that folder and its subfolders with an [!UICONTROL OR] grouping.

![](assets/folder-traits-compare-border.jpg)

## Folder Traits Realization - Recency and Frequency {#folder-traits-realization}

A contagem de frequência de uma pasta característica é a soma dos realizações das características na pasta e nas pastas filho. A ilustração abaixo mostra características A, B e C, que moram na pasta Car. Considere que cada uma das características tem os seguintes resultados:

* Característica A: 5
* Característica B: 1
* Característica C: 1

In this case, the [!DNL ]Automobile [!UICONTROL Folder Trait] has 7 realizations.

![](assets/folder_traits_rollup_border.png)

## Folder Trait Reporting {#folder-traits-reporting}

[!UICONTROL Folder traits] capturar todos os usuários das características na estrutura de pastas abaixo delas. If you move a trait from a folder to another folder, the change propagates to our [data collection servers](../../reference/system-components/components-data-collection.md) just like a trait rule change. As atualizações dos relatórios no próximo relatório são executadas para refletir essa alteração nos intervalos de datas do relatório (1, 7, 14, 30, 60, 90, ciclo de vida). Os números de relatórios antigos dos dias anteriores não serão alterados.

## Role-Based Access Controls (RBAC) Permissions {#role-based-access-controls}

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), your users with the appropriate [!UICONTROL RBAC] permissions are able to change the data source associated to the [!UICONTROL folder trait]. Um usuário deve pertencer a um grupo com um dos seguintes:

* `READ` e `WRITE` permissões de grupo para uma fonte de dados característica.
* `VIEW_ALL_TRAITS` e `EDIT_ALL_TRAITS` permissões curingas para fontes de dados de características.

Learn how to assign [!UICONTROL RBAC] permissions in our [administration documentation](../../features/administration/administration-overview.md#create-group).

## Limits and Other Considerations {#limits}

| Item | Descrição |
|---|---|
| Tipo de característica | [!UICONTROL Onboarded traits] e [!UICONTROL algorithmic traits] contribuir com, no máximo, 1 realização da frequência de uma [!UICONTROL folder trait]. |
| Movimentação de características entre pastas | Moving a trait from a folder to another will disqualify that trait from the first folder trait and qualify it for the second [!UICONTROL folder trait]. Isso significa que, se você excluir ou mover uma característica da pasta, os usuários na população de características serão dessegmentados dos segmentos usando a característica de pastas como uma expressão de segmento. |
| Variáveis do sistema | [!UICONTROL Folder traits] não pode ser observado em chamadas de evento usando o `d_sid` parâmetro. |
| Relatórios | [!UICONTROL Folder traits] são características autosegregadas e não aparecem **[!UICONTROL Overlap Reports]**. |