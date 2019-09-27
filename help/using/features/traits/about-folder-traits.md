---
description: As características da pasta permitem que você agregue automaticamente características que residem na mesma pasta e todas as pastas filhas em um segmento direcionável.
keywords: avaliador de tamanho de segmento;sse
seo-description: As características da pasta permitem que você agregue automaticamente características que residem na mesma pasta e todas as pastas filhas em um segmento direcionável.
seo-title: Características da pasta sobre
solution: Audience Manager
title: Características da pasta sobre
uuid: e561ce8f-6c90-44a7-b034-685533f29030
translation-type: tm+mt
source-git-commit: 9fa5a558c839da89286b1abdf77e835a92747c87

---


# Características da pasta: About {#folder-traits-about}

[!UICONTROL Folder traits] permite que você agregue automaticamente características que residem na mesma pasta e todas as pastas filhas em um segmento direcionável.

## Benefícios do uso das características da pasta {#benefits}

Um [!UICONTROL folder trait] contém todas as características em uma pasta pai e suas pastas filhas associadas. Isso permite segmentar e direcionar automaticamente seus usuários em diferentes níveis de pasta. Por exemplo, digamos que você tenha uma estrutura de pastas como esta:

`*` Eletrônicos (pai)

    `*` Notebooks (filho)

        `*` Marcas (netos)

[!UICONTROL Folder traits] qualificar todos os usuários nessas pastas em uma pasta criada automaticamente [!DNL Electronics] [!UICONTROL Folder Trait] (com base no nome da pasta pai). E esse processo se repete enquanto você move para baixo a estrutura de arquivos. Nesse caso, as características das pastas capturam todos os usuários nas pastas Notebooks e Marcas em um Laptops automaticamente criados [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] são selecionáveis em expressões de segmento. A seleção de um [!UICONTROL folder trait] é equivalente a selecionar todas as características dentro dessa pasta e suas subpastas com um [!UICONTROL OR] agrupamento.

![](assets/folder-traits-compare-border.jpg)

## Realização das características da pasta - Idade e frequência {#folder-traits-realization}

A contagem de frequência de uma característica de pasta é a soma das realizações das características em sua pasta e em suas pastas filhas. A ilustração abaixo mostra as características A, B e C, que vivem na pasta Automóvel. Considere que cada uma das características tem as seguintes realizar:

* Caractere A: 5
* Característica B: 1
* Característica C: 1

Nesse caso, o [!DNL Automobile Folder Trait] grupo tem 7 realizações.

![](assets/folder_traits_rollup_border.png)

## Relatório de características da pasta {#folder-traits-reporting}

[!UICONTROL Folder traits] capture todos os usuários das características na estrutura de pastas abaixo deles. If you move a trait from a folder to another folder, the change propagates to our data collection servers just like a trait rule change. [](../../reference/system-components/components-data-collection.md) The reporting updates in the next reporting run to reflect this change across the reporting date ranges (1, 7, 14, 30, 60, 90). The old reporting numbers from the previous days will not change.

## Role-Based Access Controls (RBAC) Permissions {#role-based-access-controls}

For companies using  (), your users with the appropriate  permissions are able to change the data source associated to the . [!UICONTROL Role-Based Access Controls][!UICONTROL RBAC][!UICONTROL RBAC][!UICONTROL folder trait] A user must belong to a group with either of the following:

* `READ` and  group permissions to a trait data source.`WRITE`
* `VIEW_ALL_TRAITS` and `EDIT_ALL_TRAITS` wild card permissions for trait data sources.

Learn how to assign [!UICONTROL RBAC] permissions in our [administration documentation](../../features/administration/administration-overview.md#create-group).

## Limits and Other Considerations {#limits}

| Item | Descrição |
|---|---|
| Trait type | [!UICONTROL Onboarded traits] and [!UICONTROL algorithmic traits] contribute at most 1 realization to a [!UICONTROL folder trait]'s frequency. |
| Moving traits between folders | Moving a trait from a folder to another will disqualify that trait from the first folder trait and qualify it for the second . [!UICONTROL folder trait] This means that if you delete or move a trait from the folder, the users in the trait's population will be unsegmented from the segments using the folder trait as a segment expression. <br> Ao mapear segmentos do Adobe Analytics ou conjuntos de relatórios para a organização da Experience Cloud, o Audience Manager cria automaticamente segmentos e características novos, correspondentes e somente leitura. Não é possível editar ou alterar o local de armazenamento dessas características do Audience Manager. No entanto, qualquer alteração que você efetuar nos segmentos do Adobe Analytics ou conjuntos de relatórios mapeados será refletida no Audience Manager. |
| Variáveis de sistema | [!UICONTROL Folder traits] não pode ser realizado em chamadas de evento usando o `d_sid` parâmetro. |
| Relatórios | [!UICONTROL Folder traits] são características calculadas automaticamente e não aparecem em **[!UICONTROL Overlap Reports]**. |