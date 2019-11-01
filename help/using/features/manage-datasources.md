---
description: Para criar uma nova fonte de dados, vá até Dados de público-alvo > Fontes de dados > Adicionar novo e conclua as etapas para cada seção descrita aqui. São necessárias permissões de administrador para criar uma fonte de dados.
keywords: fontes de dados;gerenciar fonte de dados;fonte de dados do Audience Manager
seo-description: Para criar uma nova fonte de dados, vá até Dados de público-alvo > Fontes de dados > Adicionar novo e conclua as etapas para cada seção descrita aqui. São necessárias permissões de administrador para criar uma fonte de dados.
seo-title: Criar uma fonte de dados
solution: Audience Manager
title: Gerenciar fontes de dados
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

Para criar uma nova fonte de dados, vá até **[!UICONTROL Audience Data > Data Sources > Add New]** e conclua as etapas para cada seção descrita aqui. São necessárias permissões de administrador para criar uma fonte de dados.

<!-- create-datasource.xml -->

>[!TIP]
>
>Consulte Configurações da fonte de [dados e Opções](../features/datasources-list-and-settings.md#settings-menu-options) de menu para obter descrições desses diferentes controles.

## Detalhes da fonte de dados {#details}

Para concluir a [!UICONTROL Data Source Details] seção:

1. Nomeie a fonte de dados.
1. *(Opcional)* Descreva a fonte de dados. Uma descrição concisa ajuda a definir a função ou a finalidade da fonte de dados.
1. Forneça um código de integração. Geralmente, os códigos de integração são opcionais. Eles são necessários quando você deseja:

   * [Crie uma fonte](../features/profile-merge-rules/merge-rules-start.md#create-data-source)de dados entre dispositivos.
   * Use o serviço [da](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud ID.
   * Trabalhar com regras [de mesclagem de](../features/profile-merge-rules/merge-rules-start.md)perfil.

1. Escolha um **[!UICONTROL ID Type]**. As opções de Tipo de ID incluem:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obrigatório para criar um [!UICONTROL Profile Merge Rule]). Observe que para alguns clientes, essa seleção expõe as **[!UICONTROL ID Definition]** opções.

1. Choose an **[!UICONTROL ID Definition]** option. As opções incluem:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## Controles da exportação de dados {#export-controls}

[Os Controles](../features/data-export-controls.md) de exportação de dados são regras de classificação opcionais que podem ser aplicadas a uma fonte de dados e destino. Elas impedem que você envie dados para um destino quando essa ação viola a privacidade dos dados ou o contrato de uso. Ignore esta seção se não usar [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

Essas configurações determinam como uma fonte de dados é identificada, usada e compartilhada. Você também pode ativar o relatório de erros para arquivos de dados de entrada. Para concluir a [!UICONTROL Data Source Settings] seção:

1. Marque uma [!UICONTROL Data Source Setting] caixa de seleção para aplicar uma opção à sua fonte de dados.
2. Clique em **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Configurações da fonte de dados e opções de menu](../features/datasources-list-and-settings.md#settings-menu-options)


## Excluir uma fonte de dados {#delete-data-source}

<!-- t_datasource_delete.xml -->

Exclua uma fonte de dados que não é mais necessária.

>[!NOTE]
>
>Observe as seguintes restrições:
>
>* Não é possível excluir um Público-alvo [ativo ou uma característica](../features/traits/client-activity-synced-audience-traits.md)sincronizada da fonte de dados.
>* Para clientes que usam o Adobe Analytics: O Audience Manager não permite que você exclua fontes de dados criadas automaticamente de seus conjuntos de [!DNL Analytics] relatórios. Use o Serviço [](https://marketing.adobe.com/resources/help/en_US/mcloud/) principal para desmapear essas fontes de dados.


1. Click **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**.
1. Marque a caixa de seleção ao lado de uma ou mais fontes de dados.
Você pode usar a [!UICONTROL Search] caixa para localizar as fontes de dados desejadas se tiver uma lista longa.
1. Clique em ![](assets/icon_trash.png)e confirme a exclusão.