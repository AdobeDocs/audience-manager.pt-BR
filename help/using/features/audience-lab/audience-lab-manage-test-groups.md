---
description: Este procedimento aborda as etapas necessárias para criar, editar ou excluir um grupo de teste no Audience Lab
seo-description: Este procedimento aborda as etapas necessárias para criar, editar ou excluir um grupo de teste no Audience Lab
seo-title: Gerenciar grupos de teste
solution: Audience Manager
title: Gerenciar grupos de teste
uuid: 2 fadddeb -7574-4853-8 c 52-c 58456582 c 62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Test Groups {#manage-test-groups}

This procedure walks you through the steps needed to create, edit, or delete a test group in [!UICONTROL Audience Lab].

## Create Segment Test Groups {#create-test-groups}

### Pré-requisitos

<!-- create-test-group.xml -->

* You need to have at least one **conversion trait** set up. You can set up conversion traits in the [Trait Builder](../../features/traits/create-onboarded-rule-based-traits.md), by selecting **conversion** as the event type. For more information on what conversion traits are and how to set them up, we prepared a [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) for you.

   >[!IMPORTANT]
   >
   >[Os traços](../../features/traits/about-folder-traits.md) da pasta **não são suportados**[!UICONTROL Audience Lab]. Setting the [Event Type](../../features/traits/create-onboarded-rule-based-traits.md) of a folder trait to **conversion** will not generate any data in [!UICONTROL Audience Lab] for that specific folder trait.

* For companies using [Role-Based Access Control](../../features/administration/administration-overview.md): Assign the [!UICONTROL Audience Lab] [wildcard permission](../../features/administration/administration-overview.md#wild-card-permissions) to **[!UICONTROL User Groups]** to provide access. Essa permissão permite que o usuário crie e visualize os resultados de um teste. A user will only be able to use segments from a data source they have **read** and **map to destination** privileges for. The user will only be able to use conversion traits from a data source for which they have **"read"** permissions. Um usuário só poderá ver os destinos aos quais eles têm acesso. So, before adding the [!DNL Audience Lab] wildcard permission to a group, make sure the group has:
   * acesso para ler características de conversão relevantes;
   * acesso a ler e mapear segmentos relevantes para testes;
   * acesso a destinos relevantes.

To create a new [!UICONTROL Segment Test Group]:

1. Select **[!UICONTROL Create New Test Group]** in the [!UICONTROL Audience Lab] dashboard to start the wizard.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Fill in a **[!UICONTROL Test Group Name]** and a **[!UICONTROL Description]**.
   * Choose the **[!UICONTROL Base Segment]** either by navigating in the file browser or by typing in the search bar, confirm by pressing **[!UICONTROL Choose Segment.]**
   * Você pode salvar o grupo de teste como rascunho e retomar o trabalho nele depois.
   * Um alerta será exibido caso o segmento base selecionado seja utilizado em outros grupos de teste. O uso do segmento base duas vezes pode distorcer os resultados de conversão para ambos os testes.

1. **[!UICONTROL Allocate Test Segments]**

   * You can create **up to 15 test segments** and divide the percentage of devices as you wish.
   * Você pode editar o nome dos segmentos de teste clicando neles.
   * As porcentagens dividem automaticamente em 100% quando novos segmentos de teste são alocados. Você pode editar manualmente as porcentagens. Clique na caixa de seleção após editar as porcentagens e verifique se elas adicionam 100%; caso contrário, não será possível continuar para a próxima etapa.

1. **[!UICONTROL Set a Control Segment]**

   * Selecione um segmento de controle se desejar que uma determinada parte do segmento seja usada como um grupo de controle. Os grupos de controle permitem que você veja o impacto dos segmentos de teste criados em comparação com um benchmark.
   * You can select a test segment as control segment in the drop-down list, or you can choose **[!UICONTROL None]** for no control.
   * Click **[!UICONTROL Next]** when you're done.

1. **[!UICONTROL Select Conversion Traits]**

   * Adicione características de conversão digitando na janela de características de conversão. This is a **mandatory** step and you cannot proceed to the next step unless you add at least one conversion trait.
   * Se desejar, você pode adicionar até 5 características de conversão.
   * Um alerta será exibido caso você selecione uma característica de conversão já usada para outros grupos de teste.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Digite os destinos desejados no campo de pesquisa ou use a seta suspensa. [!UICONTROL Audience Lab] os segmentos de teste podem ser enviados para os destinos URL, cookie ou servidor para servidor.
   * Arraste e solte segmentos em destinos.
   * After dropping a segment in a destination, fill in the **[!UICONTROL Destination Mapping Value]** in the blind.
   * É possível enviar o mesmo segmento de teste para vários destinos e você pode adicionar vários segmentos de teste a um único destino.
   * Destinations are grayed out if they are not available for a certain test segment based on [Data Export Controls](../../features/data-export-controls.md).
   * Users will only see the destinations they have access to based on the [RBAC User Group](../../features/administration/administration-overview.md) they belong to.
   * Por fim, você deve selecionar uma data de início para o seu grupo de teste. Esta data marca o início do período em que o seu grupo de teste será publicado nos destinos. Select **No End Date** for an indefinite comparison of the test segments.
   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] com um perfil autenticado são suportados apenas em destinos em tempo real. Se um segmento de teste com uma regra de mesclagem de perfil da configuração for enviado para um destino de servidor a servidor baseado em arquivo, os públicos-alvo poderão não preencher.

   Click **[!UICONTROL Next]** to review and finalize your test group.

1. **[!UICONTROL Summary & Finalize]**

   * Review the information you added in the previous steps and select **[!UICONTROL Finalize Group]**.
   * Lembre-se de que depois de finalizar um grupo de teste, ele pode ser duplicado ou excluído, mas não pode ser editado.
   >[!NOTE]
   >* Você pode salvar os grupos de teste em qualquer momento no processo de criação e retornar ao assistente posteriormente. The test group status will be **[!UICONTROL Draft]** and the test group will not send any data to destinations until you finalize the segment test group.
   >* For draft tests, you can go back and edit the test groups by clicking **[!UICONTROL Edit]** in the test group card in the main [!UICONTROL Audience Lab] view.


## Edit Segment Test Groups {#edit-test-groups}

In [!UICONTROL Audience Lab], you are only able to edit draft test groups. In the [!UICONTROL Create Segment Test Group] wizard, you can save your test group as a draft and resume working on it later.

1. Navigate to the [!UICONTROL Audience Lab] main view.
1. Search for your draft test groups and select the **[!UICONTROL Edit]** control in the test group card.
1. Resume the [Create Segment Test Group](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) wizard and select **[!UICONTROL Finalize Group]** when you're done.

## Delete Segment Test Groups {#delete-test-groups}

1. Navigate to the [!UICONTROL Audience Lab] main view.
1. Encontre o grupo de teste que deseja excluir. Você pode:

   * press the **[!UICONTROL Delete]** control in the test group card, or
   * press the test group title in the test group card to go to the [Test Group Information](../../features/audience-lab/audience-lab-information-view.md) view and press the **[!UICONTROL Delete]** control in the title bar.

1. For [completed test segments](../../features/audience-lab/audience-lab.md#status), an alert will prompt you to download the CSV file to save the reporting if you wish.
