---
description: Crie, edite e exclua características de pastas.
keywords: Característica da pasta; Características da pasta; características de pastas; característica da pasta
seo-description: Crie, edite e exclua características de pastas.
seo-title: Gerenciar características da pasta
solution: Audience Manager
title: Gerenciar características da pasta
uuid: 287 ac 280-bd 58-4985-85 bd-b 6501 eb 64 b 7 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Folder Traits {#manage-folder-traits}

Crie, edite e exclua características de pastas.

## Create a Folder Trait {#create-folder-trait}

A [!UICONTROL folder trait] is created automatically when you create a new folder in your taxonomy.

<!-- create-folder-trait.xml -->

1. Go to **[!UICONTROL Audience Data > Traits]** to navigate to the **Traits** dashboard.
1. In the [!UICONTROL Trait Storage] window, hover over:

   * Texto «Todas as características» para adicionar uma nova pasta de nível de raiz.
   * Uma pasta pai existente para adicionar uma nova pasta subordinada.
   ![](assets/folder_traits_create.PNG)

1. Clique no ícone + para criar a pasta. Observe que você pode criar um máximo de 2.000 pastas em sua taxonomia. Consulte a documentação de [limites de uso](../../features/administration/usage-limits.md) para obter mais informações.
1. Name the folder and click **Save**. Por exemplo, uma pasta denominada Eletrônicos terá uma característica de pasta chamada «Característica da pasta Eletrônicos». É possível exibir e selecionar a nova característica de pasta no painel de características.
1. The new folder trait is automatically assigned to the [!DNL Audience Manager] generated data source. Your users with appropriate [!UICONTROL Role-Based Access Control ([!DNL RBAC])] permissions can change the data source in the edit folder trait workflow. See [Edit a Folder Trait](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Edit a Folder Trait {#edit-folder-trait}

Describes how you can edit a [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. In the [!UICONTROL Traits] dashboard, hover over the **[!UICONTROL Actions]** column for the folder trait you want to edit.
1. Clique no lápis para editar a característica.

   ![](assets/folder_traits_edit_border.png)

1. The **[!UICONTROL Edit]** workflow allows you to change the data source for folder traits. Select your desired data source and click **[!UICONTROL Save]**. Data sources are sorted numerically, by [!DNL DPID], in the drop-down box.

   If your company uses [!UICONTROL Role-Based Access Rights (RBAC)], you or your users need [access permissions](../../features/traits/about-folder-traits.md#role-based-access-controls) to traits data sources.

>[!NOTE]
>
>Não é possível renomear diretamente uma característica de pasta. [Renomeie sua pasta de armazenamento associada](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) para alterar o nome da característica da pasta.

## Delete a Folder Trait {#delete-folder-trait}

Exclua uma característica de pasta ao excluir a pasta de armazenamento à qual a característica pertence.

<!-- delete-folder-trait.xml -->

1. **Dados de público-alvo &gt; Características** para navegar até o **painel Características** .
1. In the [!UICONTROL Trait Storage] window, delete a folder by hovering over it and clicking the X icon.

   ![Resultado da etapa](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Não é possível excluir uma característica de pasta, se ela for usada em uma expressão de segmento. Navigate to the [trait view](../../features/traits/trait-details-page.md) section to see which segments use the folder trait. Then, click on the segment name to open the [segment summary view](../../features/segments/segment-summary-view.md), which allows you to remove traits from segment expressions.