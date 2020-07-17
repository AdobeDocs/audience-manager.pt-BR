---
description: Este procedimento o orienta pelas etapas necessárias para criar, editar ou excluir um grupo de teste no Audiência Lab
seo-description: Este procedimento o orienta pelas etapas necessárias para criar, editar ou excluir um grupo de teste no Audiência Lab
seo-title: Gerenciar grupos de teste
solution: Audience Manager
title: Gerenciar grupos de teste
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 1%

---


# Gerenciar grupos de teste {#manage-test-groups}

Este procedimento o orienta pelas etapas necessárias para criar, editar ou excluir um grupo de teste no [!UICONTROL Audience Lab].

## Criar grupos de teste de segmento {#create-test-groups}

### Pré-requisitos

<!-- create-test-group.xml -->

* É necessário ter pelo menos uma característica **de** conversão configurada. Você pode configurar características de conversão no Construtor de [características](../../features/traits/create-onboarded-rule-based-traits.md)selecionando a **conversão** como o tipo de evento. Para obter mais informações sobre quais características de conversão são e como configurá-las, preparamos um [vídeo](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) para você.

   >[!IMPORTANT]
   >
   >[As características](../../features/traits/about-folder-traits.md) da pasta **não são suportadas** por [!UICONTROL Audience Lab]. Definir o [Tipo de evento](../../features/traits/create-onboarded-rule-based-traits.md) de uma característica de pasta como **conversão** não gerará dados [!UICONTROL Audience Lab] para essa característica específica de pasta.

* Para empresas usando Controle de acesso [baseado em](../../features/administration/administration-overview.md)função: Atribua a permissão [!UICONTROL Audience Lab] [curinga para](../../features/administration/administration-overview.md#wild-card-permissions) **[!UICONTROL User Groups]** fornecer acesso. Essa permissão permite que o usuário crie e visualização os resultados de um teste. Um usuário só poderá usar segmentos de uma fonte de dados para a qual tenha **lido** e **mapeado para privilégios de destino** . O usuário só poderá usar características de conversão de uma fonte de dados para a qual tenha permissões de **&quot;leitura&quot;** . Um usuário só poderá ver os destinos aos quais ele tem acesso. Portanto, antes de adicionar a permissão [!DNL Audience Lab] curinga a um grupo, verifique se o grupo tem:
   * Acesso a características de conversão relevantes;
   * acesso a segmentos relevantes de leitura e de mapa para testes;
   * acesso aos destinos relevantes.

To create a new [!UICONTROL Segment Test Group]:

1. Selecione **[!UICONTROL Create New Test Group]** no [!UICONTROL Audience Lab] painel para start do assistente.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Preencha um **[!UICONTROL Test Group Name]** e um **[!UICONTROL Description]**.
   * Escolha o arquivo navegando **[!UICONTROL Base Segment]** no navegador de arquivos ou digitando na barra de pesquisa, confirme pressionando **[!UICONTROL Choose Segment.]**
   * Você pode salvar o grupo de teste como um rascunho e continuar trabalhando nele posteriormente.
   * Um alerta será exibido caso o segmento base selecionado já esteja sendo usado em outros grupos de teste. O uso do segmento base duas vezes pode distorcer os resultados de conversão para ambos os testes.

1. **[!UICONTROL Allocate Test Segments]**

   * Você pode criar **até 15 segmentos** de teste e dividir a porcentagem de dispositivos conforme desejar.
   * Você pode editar o nome dos segmentos de teste clicando neles.
   * As porcentagens dividem-se automaticamente em 100% quando novos segmentos de teste são alocados. Em seguida, é possível editar as porcentagens manualmente. Clique na caixa de seleção após editar as porcentagens e verifique se elas somam até 100%; caso contrário, você não poderá prosseguir para a próxima etapa.

1. **[!UICONTROL Set a Control Segment]**

   * Selecione um segmento de controle se desejar reservar uma parte específica do segmento para ser usado como um grupo de controle. Grupos de controle permitem que você veja o impacto dos segmentos de teste criados em comparação a um benchmark.
   * Você pode selecionar um segmento de teste como segmento de controle na lista suspensa ou pode escolher sem controle **[!UICONTROL None]** .
   * Clique **[!UICONTROL Next]** quando terminar.

1. **[!UICONTROL Select Conversion Traits]**

   * Adicione características de conversão digitando na janela de características de conversão. Esta é uma etapa **obrigatória** e não é possível prosseguir para a próxima etapa, a menos que você adicione pelo menos uma característica de conversão.
   * Se desejar, você pode adicionar até 5 características de conversão.
   * Um alerta será exibido caso você selecione uma característica de conversão já usada para outros grupos de teste.
   * Observe que o Audience Manager não suporta o uso de características [de](/help/using/features/traits/about-folder-traits.md) pasta como características de conversão. Selecionar uma característica de pasta como característica de conversão resulta em 0 agregação e relatórios de tendência exibidos no teste.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Digite os destinos desejados no campo de pesquisa ou use a seta suspensa. [!UICONTROL Audience Lab] segmentos de teste podem ser enviados para destinos de URL, cookie ou servidor para servidor.
   * Arraste e solte segmentos para destinos.
   * Depois de soltar um segmento em um destino, preencha o segmento **[!UICONTROL Destination Mapping Value]** no cego.
   * Você pode enviar o mesmo segmento de teste para vários destinos e pode adicionar vários segmentos de teste a um único destino.
   * Os destinos ficam acinzentados se não estiverem disponíveis para um determinado segmento de teste com base em Controles [de exportação de](../../features/data-export-controls.md)dados.
   * Os usuários só verão os destinos aos quais têm acesso com base no Grupo [de usuários](../../features/administration/administration-overview.md) RBAC ao qual pertencem.
   * Por fim, é necessário selecionar uma data de start para o seu grupo de teste. Essa data marca o start do período em que seu grupo de teste será publicado nos destinos. Selecione **Sem data** final para uma comparação indefinida dos segmentos de teste.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] com um perfil autenticado são suportados apenas em destinos em tempo real. Se um segmento de teste com uma regra de união de perfis dessa configuração for enviado para um destino servidor para servidor baseado em arquivo, o audiência talvez não seja preenchido.

   Clique **[!UICONTROL Next]** para revisar e finalizar seu grupo de teste.

1. **[!UICONTROL Summary & Finalize]**

   * Revise as informações adicionadas nas etapas anteriores e selecione **[!UICONTROL Finalize Group]**.
   * Lembre-se de que, uma vez finalizado, um grupo de teste pode ser duplicado ou excluído, mas não editado.

   >[!NOTE]
   >* Você pode salvar os grupos de teste em qualquer momento do processo de criação e retornar ao assistente posteriormente. O status do grupo de teste será exibido **[!UICONTROL Draft]** e o grupo de teste não enviará dados para destinos até que você conclua o grupo de teste do segmento.
   >* Para testes de rascunho, você pode voltar e editar os grupos de teste clicando **[!UICONTROL Edit]** no cartão do grupo de teste na [!UICONTROL Audience Lab] visualização principal.


## Editar grupos de teste de segmento {#edit-test-groups}

Em [!UICONTROL Audience Lab], você só pode editar grupos de teste de rascunho. No [!UICONTROL Create Segment Test Group] assistente, você pode salvar seu grupo de teste como um rascunho e continuar trabalhando nele mais tarde.

1. Navegue até a visualização [!UICONTROL Audience Lab] principal.
1. Procure seus grupos de teste de rascunho e selecione o **[!UICONTROL Edit]** controle na placa do grupo de teste.
1. Reinicie o assistente [Criar grupo](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) de teste de segmento e selecione **[!UICONTROL Finalize Group]** quando terminar.

## Excluir grupos de teste de segmento {#delete-test-groups}

1. Navegue até a visualização [!UICONTROL Audience Lab] principal.
1. Encontre o grupo de teste que deseja excluir. Você pode:

   * pressione o **[!UICONTROL Delete]** controle na placa do grupo de teste, ou
   * pressione o título do grupo de teste na placa do grupo de teste para acessar a visualização [Test Group Information (Informações](../../features/audience-lab/audience-lab-information-view.md) **[!UICONTROL Delete]** do grupo de teste) e pressione o controle na barra de título.

1. Para segmentos [de teste](../../features/audience-lab/audience-lab.md#status)concluídos, um alerta solicitará que você baixe o arquivo CSV para salvar o relatórios, se desejar.
