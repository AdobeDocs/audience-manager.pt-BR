---
description: Crie, edite e exclua características da pasta.
keywords: Folder Trait;Folder Traits;folder traits;folder trait
seo-description: Crie, edite e exclua características da pasta.
seo-title: Gerenciar características da pasta
solution: Audience Manager
title: Gerenciar características da pasta
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
translation-type: tm+mt
source-git-commit: 4ea5ba4ebd8cd4c13c99c8272f4b5733ab5fa125
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 9%

---


# Gerenciar características da pasta {#manage-folder-traits}

Crie, edite e exclua características da pasta.

## Criar uma característica de pasta {#create-folder-trait}

Um [!UICONTROL folder trait] é criado automaticamente quando você cria uma nova pasta em sua taxonomia.

<!-- create-folder-trait.xml -->

1. Vá para **[!UICONTROL Audience Data > Traits]** para navegar até o painel **Características**.
1. Na janela [!UICONTROL Trait Storage], passe o mouse sobre:

   * Texto &quot;Todas as características&quot; para adicionar uma nova pasta de nível raiz.
   * Uma pasta pai existente para adicionar uma nova pasta secundária.

   ![](assets/folder_traits_create.PNG)

1. Clique no ícone + para criar a pasta. Observe que você pode criar um máximo de 2.000 pastas em sua taxonomia. Consulte a documentação de [limites de uso](../../features/administration/usage-limits.md) para obter mais informações.
1. Nomeie a pasta e clique em **Salvar**. Por exemplo, uma pasta chamada Eletrônicos terá uma característica de pasta chamada &#39;Características da pasta Eletrônicos&#39;. Você pode visualização e selecionar a nova característica da pasta no painel de características.
1. A nova característica da pasta é atribuída automaticamente à fonte de dados gerada por [!DNL Audience Manager]. Seus usuários com as permissões apropriadas [!UICONTROL Role-Based Access Control] ([!DNL RBAC]) podem alterar a fonte de dados no fluxo de trabalho de características da pasta de edição. Consulte [Editar uma característica de pasta](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Editar uma característica de pasta {#edit-folder-trait}

Descreve como você pode editar um [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. No painel [!UICONTROL Traits], passe o mouse sobre a coluna **[!UICONTROL Actions]** para a característica da pasta que deseja editar.
1. Clique no lápis para editar a característica.

   ![](assets/folder_traits_edit_border.png)

1. O fluxo de trabalho **[!UICONTROL Edit]** permite que você altere a fonte de dados para características de pastas. Selecione a fonte de dados desejada e clique em **[!UICONTROL Save]**. As fontes de dados são classificadas numericamente, por [!DNL DPID], na caixa suspensa.

   Se sua empresa usar [!UICONTROL Role-Based Access Rights (RBAC)], você ou seus usuários precisarão de [permissões de acesso](../../features/traits/about-folder-traits.md#role-based-access-controls) para obter as características das fontes de dados.

>[!NOTE]
>
>Não é possível renomear diretamente uma característica de pasta. [Renomeie a ](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) pasta de armazenamentos associada para alterar o nome da característica da pasta.

## Excluir uma característica de pasta {#delete-folder-trait}

Exclua uma característica de pasta excluindo a pasta de armazenamento à qual a característica pertence.

<!-- delete-folder-trait.xml -->

1. **Dados de audiência >** Características para navegar até o  **** painel de Características.
1. Na janela [!UICONTROL Trait Storage], exclua uma pasta passando o mouse sobre ela e clicando no ícone X.

   ![Resultado da etapa](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Não é possível excluir uma característica de pasta, se ela for usada em uma expressão de segmento. Navegue até a seção [visualização característica](../../features/traits/trait-details-page.md) para ver quais segmentos usam a característica da pasta. Em seguida, clique no nome do segmento para abrir a [visualização de resumo do segmento](../../features/segments/segment-summary-view.md), que permite remover as características das expressões do segmento.
