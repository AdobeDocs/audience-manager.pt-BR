---
description: Criar, editar e excluir características da pasta.
keywords: Característica da Pasta;Características da Pasta;características da pasta;característica da pasta
seo-description: Create, edit, and delete folder traits.
seo-title: Manage Folder Traits
solution: Audience Manager
title: Gerenciar características da pasta
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
exl-id: fa7a8d2a-dacc-413e-89d6-d3b7ce7bbbe3
source-git-commit: f7a4478589f4af1d467f1045a97dbb7f5cd6f9e5
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 4%

---

# Gerenciar características da pasta {#manage-folder-traits}

Criar, editar e excluir características da pasta.

## Criar uma característica de pasta {#create-folder-trait}

Um [!UICONTROL folder trait] é criado automaticamente quando você cria uma nova pasta na sua taxonomia.

<!-- create-folder-trait.xml -->

1. Vá para **[!UICONTROL Audience Data > Traits]** para navegar até o painel **Características**.
1. Na janela [!UICONTROL Trait Storage], passe o mouse sobre:

   * Texto &quot;Todas as características&quot; para adicionar uma nova pasta de nível raiz.
   * Uma pasta pai existente para adicionar uma nova pasta subordinada.

   ![](assets/folder_traits_create.PNG)

1. Clique no ícone + para criar a pasta. Observe que você pode criar no máximo 2000 pastas em sua taxonomia. Consulte a documentação de [limites de uso](../../features/administration/usage-limits.md) para obter mais informações.
1. Nomeie a pasta e clique em **Salvar**. Por exemplo, uma pasta chamada Eletrônicos terá uma característica de pasta chamada &quot;Característica de pasta eletrônica&quot;. Você pode visualizar e selecionar a nova característica da pasta no painel de características.
1. A nova característica de pasta é automaticamente atribuída à fonte de dados gerada [!DNL Audience Manager]. Seus usuários com as permissões [!UICONTROL Role-Based Access Control] ([!DNL RBAC]) apropriadas podem alterar a fonte de dados no fluxo de trabalho editar características da pasta. Consulte [Editar uma característica de pasta](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Editar uma característica da pasta {#edit-folder-trait}

Descreve como você pode editar um [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. No painel [!UICONTROL Traits], passe o mouse sobre a coluna **[!UICONTROL Actions]** referente à característica de pasta que você deseja editar.
1. Clique no lápis para editar a característica.

   ![](assets/folder_traits_edit_border.png)

1. O fluxo de trabalho **[!UICONTROL Edit]** permite alterar a fonte de dados para características da pasta. Selecione a fonte de dados desejada e clique em **[!UICONTROL Save]**. As fontes de dados são classificadas numericamente, por [!DNL DPID], na caixa suspensa.

   Se sua empresa usa o [!UICONTROL Role-Based Access Rights (RBAC)], você ou seus usuários precisam de [permissões de acesso](../../features/traits/about-folder-traits.md#role-based-access-controls) para as fontes de dados de características.

>[!NOTE]
>
>Não é possível renomear diretamente uma característica de pasta. [Renomeie sua pasta de armazenamento associada](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) para alterar o nome da característica da pasta.

## Excluir uma característica de pasta {#delete-folder-trait}

Exclua uma característica de pasta excluindo a pasta de armazenamento à qual a característica pertence.

<!-- delete-folder-trait.xml -->

1. **Dados de público-alvo > Características** para navegar até o painel **Características**.
1. Na janela [!UICONTROL Trait Storage], exclua uma pasta passando o mouse sobre ela e clicando no ícone X.

   ![Resultado da etapa](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Não é possível excluir uma característica de pasta, se ela for usada em uma expressão de segmento. Navegue até a seção [exibição de característica](../../features/traits/trait-details-page.md) para ver quais segmentos usam a característica da pasta. Em seguida, clique no nome do segmento para abrir a [exibição do resumo do segmento](../../features/segments/segment-summary-view.md), que permite remover características de expressões de segmento.
