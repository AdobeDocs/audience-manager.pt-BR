---
description: Este procedimento o orienta pelas etapas necessárias para criar, editar ou excluir um grupo de teste no Audience Lab
seo-description: Este procedimento o orienta pelas etapas necessárias para criar, editar ou excluir um grupo de teste no Audience Lab
seo-title: Gerenciar grupos de teste
solution: Audience Manager
title: Gerenciar grupos de teste
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: 'Audience Lab '
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 1%

---

# Gerenciar grupos de teste {#manage-test-groups}

Este procedimento o orienta pelas etapas necessárias para criar, editar ou excluir um grupo de teste em [!UICONTROL Audience Lab].

## Criar grupos de teste de segmento {#create-test-groups}

### Pré-requisitos

<!-- create-test-group.xml -->

* Você precisa ter pelo menos um **característica de conversão** configurado. Você pode configurar características de conversão no [Construtor de características](../../features/traits/create-onboarded-rule-based-traits.md), selecionando **conversão** como o tipo de evento. Para obter mais informações sobre quais características de conversão são e como configurá-las, preparamos um [vídeo](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) para você.

   >[!IMPORTANT]
   >
   >[As ](../../features/traits/about-folder-traits.md) características da pasta  **não são** suportadas pela  [!UICONTROL Audience Lab]. Definir o [Tipo de Evento](../../features/traits/create-onboarded-rule-based-traits.md) de uma característica de pasta para **conversion** não gerará dados em [!UICONTROL Audience Lab] para essa característica de pasta específica.

* Para empresas que usam [Controle de Acesso Baseado em Função](../../features/administration/administration-overview.md): Atribua a [!UICONTROL Audience Lab] [permissão curinga](../../features/administration/administration-overview.md#wild-card-permissions) a **[!UICONTROL User Groups]** para fornecer acesso. Essa permissão permite que o usuário crie e visualize os resultados de um teste. Um usuário só poderá usar segmentos de uma fonte de dados para a qual tem privilégios **read** e **mapear para destino**. O usuário só poderá usar características de conversão de uma fonte de dados para a qual tenha permissões **&quot;read&quot;**. Um usuário só poderá ver destinos aos quais ele tem acesso. Portanto, antes de adicionar a permissão curinga [!DNL Audience Lab] a um grupo, verifique se o grupo tem:
   * Acesso à leitura das características de conversão relevantes;
   * Acesso a segmentos relevantes para leitura e mapeamento para testes;
   * acesso aos destinos pertinentes.

Para criar um novo [!UICONTROL Segment Test Group]:

1. Selecione **[!UICONTROL Create New Test Group]** no painel [!UICONTROL Audience Lab] para iniciar o assistente.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Preencha um **[!UICONTROL Test Group Name]** e um **[!UICONTROL Description]**.
   * Escolha **[!UICONTROL Base Segment]** navegando no navegador de arquivos ou digitando na barra de pesquisa, confirme pressionando **[!UICONTROL Choose Segment.]**
   * Você pode salvar o grupo de teste como rascunho e retomar seu trabalho posteriormente.
   * Um alerta será exibido caso o segmento base selecionado já esteja sendo usado em outros grupos de teste. Usar o segmento base duas vezes pode distorcer os resultados de conversão para ambos os testes.

1. **[!UICONTROL Allocate Test Segments]**

   * Você pode criar **até 15 segmentos de teste** e dividir a porcentagem de dispositivos conforme desejar.
   * É possível editar o nome dos segmentos de teste clicando neles.
   * As porcentagens se dividem automaticamente em 100% quando novos segmentos de teste são alocados. É possível editar as porcentagens manualmente. Clique na caixa de seleção após editar as porcentagens e verifique se elas somam até 100%; caso contrário, você não poderá prosseguir para a próxima etapa.

1. **[!UICONTROL Set a Control Segment]**

   * Selecione um segmento de controle se desejar definir uma parte específica do segmento a ser usada como um grupo de controle. Os grupos de controle permitem que você veja o impacto dos segmentos de teste criados em comparação a um referencial.
   * Você pode selecionar um segmento de teste como segmento de controle na lista suspensa ou pode escolher **[!UICONTROL None]** para nenhum controle.
   * Clique em **[!UICONTROL Next]** quando terminar.

1. **[!UICONTROL Select Conversion Traits]**

   * Adicione características de conversão digitando na janela de característica de conversão. Esta é uma etapa **obrigatória** e não é possível prosseguir para a próxima etapa a menos que você adicione pelo menos uma característica de conversão.
   * Se desejar, é possível adicionar até 5 características de conversão.
   * Um alerta será exibido caso você selecione uma característica de conversão já usada para outros grupos de teste.
   * Observe que o Audience Manager não suporta o uso de [traços da pasta](/help/using/features/traits/about-folder-traits.md) como características de conversão. Selecionar uma característica de pasta como característica de conversão resulta em 0 relatórios de agregação e tendência exibidos no teste.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Digite os destinos desejados no campo de pesquisa ou use a seta suspensa. [!UICONTROL Audience Lab] segmentos de teste podem ser enviados para URL, cookie ou destinos de servidor para servidor.
   * Arraste e solte segmentos em destinos.
   * Depois de soltar um segmento em um destino, preencha o **[!UICONTROL Destination Mapping Value]** nas cegas.
   * Você pode enviar o mesmo segmento de teste para vários destinos e pode adicionar vários segmentos de teste a um único destino.
   * Os destinos ficam esmaecidos se não estiverem disponíveis para um determinado segmento de teste com base em [Data Export Controls](../../features/data-export-controls.md).
   * Os usuários só verão os destinos aos quais têm acesso com base no [Grupo de usuários RBAC](../../features/administration/administration-overview.md) ao qual pertencem.
   * Por fim, você deve selecionar uma data de início para seu grupo de teste. Essa data marca o início do período em que seu grupo de teste será publicado nos destinos. Selecione **No End Date** para obter uma comparação indefinida dos segmentos de teste.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] com um perfil autenticado são compatíveis apenas com destinos em tempo real. Se um segmento de teste com uma regra de mesclagem de perfil dessa configuração for enviado para um destino servidor a servidor baseado em arquivo, os públicos-alvo talvez não sejam preenchidos.

   Clique em **[!UICONTROL Next]** para revisar e finalizar o grupo de teste.

1. **[!UICONTROL Summary & Finalize]**

   * Revise as informações adicionadas nas etapas anteriores e selecione **[!UICONTROL Finalize Group]**.
   * Lembre-se de que, depois de finalizar um grupo de teste, ele pode ser duplicado ou excluído, mas não editado.

   >[!NOTE]
   >* Você pode salvar os grupos de teste em qualquer ponto do processo de criação e retornar ao assistente posteriormente. O status do grupo de teste será **[!UICONTROL Draft]** e o grupo de teste não enviará dados para destinos até que você finalize o grupo de teste do segmento.
   >* Para testes de rascunho, você pode voltar e editar os grupos de teste clicando em **[!UICONTROL Edit]** no cartão do grupo de teste na exibição principal [!UICONTROL Audience Lab].


## Editar grupos de teste de segmento {#edit-test-groups}

Em [!UICONTROL Audience Lab], você só pode editar grupos de teste de rascunho. No assistente [!UICONTROL Create Segment Test Group], você pode salvar seu grupo de teste como rascunho e retomar o trabalho nele mais tarde.

1. Navegue até a exibição principal [!UICONTROL Audience Lab].
1. Procure seus grupos de teste de rascunho e selecione o controle **[!UICONTROL Edit]** no cartão de grupo de teste.
1. Retome o assistente [Criar grupo de teste de segmento](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) e selecione **[!UICONTROL Finalize Group]** quando terminar.

## Excluir grupos de teste de segmento {#delete-test-groups}

1. Navegue até a exibição principal [!UICONTROL Audience Lab].
1. Localize o grupo de teste que deseja excluir. Você pode:

   * pressione o controle **[!UICONTROL Delete]** no cartão do grupo de teste, ou
   * pressione o título do grupo de teste no cartão do grupo de teste para ir para a exibição [Informações do grupo de teste](../../features/audience-lab/audience-lab-information-view.md) e pressione o controle **[!UICONTROL Delete]** na barra de título.

1. Para [segmentos de teste concluídos](../../features/audience-lab/audience-lab.md#status), um alerta solicitará o download do arquivo CSV para salvar o relatório, se desejar.
