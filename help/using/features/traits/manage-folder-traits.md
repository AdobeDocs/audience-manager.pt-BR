---
description: Crie, edite e exclua características da pasta.
keywords: Caractere da pasta;Características da pasta;características da pasta;característica da pasta
seo-description: Crie, edite e exclua características da pasta.
seo-title: Gerenciar características da pasta
solution: Audience Manager
title: Gerenciar características da pasta
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Gerenciar características da pasta {#manage-folder-traits}

Crie, edite e exclua características da pasta.

## Criar uma característica de pasta {#create-folder-trait}

Uma pasta [!UICONTROL folder trait] é criada automaticamente quando você cria uma nova pasta na sua taxonomia.

<!-- create-folder-trait.xml -->

1. Vá até **[!UICONTROL Audience Data > Traits]** para navegar até o painel **Características** .
1. Na [!UICONTROL Trait Storage] janela, passe o mouse sobre:

   * Texto "Todas as características" para adicionar uma nova pasta de nível raiz.
   * Uma pasta pai existente para adicionar uma nova pasta subordinada.
   ![](assets/folder_traits_create.PNG)

1. Clique no ícone + para criar a pasta. Observe que você pode criar um máximo de 2.000 pastas em sua taxonomia. Consulte a documentação de [limites de uso](../../features/administration/usage-limits.md) para obter mais informações.
1. Nomeie a pasta e clique em **Salvar**. Por exemplo, uma pasta chamada Eletrônicos terá uma característica de pasta chamada 'Características da pasta Eletrônicos'. Você pode exibir e selecionar a nova característica da pasta no painel de características.
1. A nova característica da pasta é atribuída automaticamente à fonte de dados [!DNL Audience Manager] gerada. Seus usuários com as permissões [!UICONTROL Role-Based Access Control ([!DNL RBAC])] apropriadas podem alterar a fonte de dados no fluxo de trabalho de características da pasta de edição. Consulte [Editar uma característica](../../features/traits/manage-folder-traits.md#edit-folder-trait)da pasta.

## Editar uma característica de pasta {#edit-folder-trait}

Descreve como você pode editar uma [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. No [!UICONTROL Traits] painel, passe o mouse sobre a **[!UICONTROL Actions]** coluna referente à característica da pasta que deseja editar.
1. Clique no lápis para editar a característica.

   ![](assets/folder_traits_edit_border.png)

1. O **[!UICONTROL Edit]** fluxo de trabalho permite alterar a fonte de dados para características da pasta. Selecione a fonte de dados desejada e clique em **[!UICONTROL Save]**. As fontes de dados são classificadas numericamente, por [!DNL DPID], na caixa suspensa.

   Se a sua empresa usa [!UICONTROL Role-Based Access Rights (RBAC)], você ou seus usuários precisam de permissões [de](../../features/traits/about-folder-traits.md#role-based-access-controls) acesso às características das fontes de dados.

>[!NOTE]
>
>Não é possível renomear diretamente uma característica de pasta. [Renomeie sua pasta](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) de armazenamento associada para alterar o nome da característica da pasta.

## Excluir uma característica da pasta {#delete-folder-trait}

Exclua uma característica de pasta excluindo a pasta de armazenamento à qual a característica pertence.

<!-- delete-folder-trait.xml -->

1. **Dados de público-alvo &gt; Características** para navegar até o painel **Características** .
1. Na [!UICONTROL Trait Storage] janela, exclua uma pasta passando o mouse sobre ela e clicando no ícone X.

   ![Resultado da etapa](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Não é possível excluir uma característica de pasta se ela for usada em uma expressão de segmento. Navegue até a seção de exibição [](../../features/traits/trait-details-page.md) de características para ver quais segmentos usam a característica da pasta. Em seguida, clique no nome do segmento para abrir a exibição [de resumo do](../../features/segments/segment-summary-view.md)segmento, que permite remover características das expressões do segmento.