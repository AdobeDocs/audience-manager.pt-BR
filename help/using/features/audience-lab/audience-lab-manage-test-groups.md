---
description: Este procedimento percorre as etapas necessárias para criar, editar ou excluir um grupo de teste no Audience Lab
seo-description: This procedure walks you through the steps needed to create, edit, or delete a test group in Audience Lab
seo-title: Manage Test Groups
solution: Audience Manager
title: Gerenciar grupos de teste
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 0%

---

# Gerenciar grupos de teste {#manage-test-groups}

Este procedimento o guiará pelas etapas necessárias para criar, editar ou excluir um grupo de teste no [!UICONTROL Audience Lab].

## Criar grupos de teste de segmento {#create-test-groups}

### Pré-requisitos

<!-- create-test-group.xml -->

* Você precisa ter pelo menos uma **característica de conversão** configurada. Você pode configurar características de conversão no [Construtor de características](../../features/traits/create-onboarded-rule-based-traits.md), selecionando **conversão** como o tipo de evento. Para obter mais informações sobre o que são características de conversão e como configurá-las, preparamos um [vídeo](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) para você.

  >[!IMPORTANT]
  >
  >[As **características da pasta](../../features/traits/about-folder-traits.md) não têm suporte** por [!UICONTROL Audience Lab]. Definir o [Tipo de Evento](../../features/traits/create-onboarded-rule-based-traits.md) de uma característica de pasta como **conversão** não gerará dados em [!UICONTROL Audience Lab] para essa característica de pasta específica.

* Para empresas que usam o [Controle de Acesso Baseado em Função](../../features/administration/administration-overview.md): atribua a [!UICONTROL Audience Lab] [permissão curinga](../../features/administration/administration-overview.md#wild-card-permissions) a **[!UICONTROL User Groups]** para fornecer acesso. Essa permissão possibilita que o usuário crie e visualize os resultados de um teste. Um usuário só poderá usar segmentos de uma fonte de dados para a qual tenha privilégios de **leitura** e **mapeamento para destino**. O usuário só poderá usar características de conversão de uma fonte de dados para a qual tenha permissões de **&quot;leitura&quot;**. Um usuário também só poderá ver os destinos aos quais tem acesso. Portanto, antes de adicionar a permissão curinga [!DNL Audience Lab] a um grupo, verifique se o grupo tem:
   * acesso à leitura de características de conversão relevantes;
   * acesso à leitura e ao mapeamento de segmentos relevantes para testes;
   * acesso aos destinos pertinentes.

Para criar um novo [!UICONTROL Segment Test Group]:

1. Selecione **[!UICONTROL Create New Test Group]** no painel [!UICONTROL Audience Lab] para iniciar o assistente.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Preencha um **[!UICONTROL Test Group Name]** e um **[!UICONTROL Description]**.
   * Escolha o **[!UICONTROL Base Segment]** navegando no navegador de arquivos ou digitando na barra de pesquisa, confirme pressionando **[!UICONTROL Choose Segment.]**
   * Você pode salvar o grupo de teste como rascunho e retomar o trabalho nele posteriormente.
   * Um alerta será exibido caso o segmento base selecionado já esteja sendo usado em outros grupos de teste. O uso do segmento base duas vezes pode distorcer os resultados da conversão para ambos os testes.

1. **[!UICONTROL Allocate Test Segments]**

   * Você pode criar **até 15 segmentos de teste** e dividir a porcentagem de dispositivos conforme desejar.
   * Você pode editar o nome dos segmentos de teste clicando neles.
   * As porcentagens são divididas automaticamente de forma uniforme em 100% quando novos segmentos de teste são alocados. É possível editar as porcentagens manualmente. Clique na caixa de seleção após editar as porcentagens e verifique se elas adicionam até 100%; caso contrário, você não poderá prosseguir para a próxima etapa.

1. **[!UICONTROL Set a Control Segment]**

   * Selecione um segmento de controle se quiser separar uma determinada parte do segmento a ser usada como um grupo de controle. Grupos de controle permitem que você veja o impacto dos segmentos de teste criados em comparação a um referencial.
   * Você pode selecionar um segmento de teste como segmento de controle na lista suspensa, ou pode escolher **[!UICONTROL None]** para nenhum controle.
   * Clique em **[!UICONTROL Next]** quando terminar.

1. **[!UICONTROL Select Conversion Traits]**

   * Adicione características de conversão digitando na janela de características de conversão. Esta é uma etapa **obrigatória** e você não pode prosseguir para a próxima etapa a menos que adicione pelo menos uma característica de conversão.
   * Você pode adicionar até 5 características de conversão, se desejar.
   * Um alerta será exibido caso você selecione uma característica de conversão já usada para outros grupos de teste.
   * Observe que o Audience Manager não oferece suporte ao uso de [características da pasta](/help/using/features/traits/about-folder-traits.md) como características de conversão. Selecionar uma característica de pasta como característica de conversão resultará em 0 agregação e relatório de tendência exibidos no teste.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Digite os destinos desejados no campo de pesquisa ou use a seta suspensa. [!UICONTROL Audience Lab] segmentos de teste podem ser enviados para URL, cookie ou destinos de servidor para servidor.
   * Arraste e solte segmentos para destinos.
   * Depois de soltar um segmento em um destino, preencha o **[!UICONTROL Destination Mapping Value]** às cegas.
   * Você pode enviar o mesmo segmento de teste para vários destinos e adicionar vários segmentos de teste a um único destino.
   * Os destinos estarão esmaecidos se não estiverem disponíveis para um determinado segmento de teste com base em [Controles de exportação de dados](../../features/data-export-controls.md).
   * Os usuários só verão os destinos aos quais têm acesso com base no [Grupo de usuários RBAC](../../features/administration/administration-overview.md) ao qual pertencem.
   * Por fim, é necessário selecionar uma data de início para o grupo de teste. Essa data marca o início do período em que seu grupo de teste será publicado nos destinos. Selecione **Sem Data Final** para uma comparação indefinida dos segmentos de teste.

   >[!NOTE]
   >
   >Só há suporte para [!UICONTROL Profile Merge Rules] com um perfil autenticado em destinos em tempo real. Se um segmento de teste com uma regra de mesclagem de perfis dessa configuração for enviado para um destino de servidor para servidor baseado em arquivo, os públicos-alvo talvez não sejam preenchidos.

   Clique em **[!UICONTROL Next]** para revisar e finalizar seu grupo de teste.

1. **[!UICONTROL Summary & Finalize]**

   * Revise as informações adicionadas nas etapas anteriores e selecione **[!UICONTROL Finalize Group]**.
   * Lembre-se de que, uma vez finalizado um grupo de teste, ele poderá ser duplicado ou excluído, mas não editado.

   >[!NOTE]
   >* Você pode salvar os grupos de teste em qualquer ponto do processo de criação e retornar ao assistente posteriormente. O status do grupo de teste será **[!UICONTROL Draft]** e o grupo de teste não enviará dados para destinos até você finalizar o grupo de teste de segmento.
   >* Para testes de rascunho, você pode voltar e editar os grupos de teste clicando em **[!UICONTROL Edit]** no cartão de grupo de teste na visualização principal [!UICONTROL Audience Lab].

## Editar grupos de teste de segmento {#edit-test-groups}

Em [!UICONTROL Audience Lab], você só pode editar grupos de teste de rascunho. No assistente [!UICONTROL Create Segment Test Group], você pode salvar seu grupo de teste como rascunho e continuar trabalhando nele posteriormente.

1. Navegue até a exibição principal [!UICONTROL Audience Lab].
1. Pesquise os grupos de teste de rascunho e selecione o controle **[!UICONTROL Edit]** no cartão do grupo de teste.
1. Retome o assistente [Criar Grupo de Teste de Segmento](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) e selecione **[!UICONTROL Finalize Group]** quando terminar.

## Excluir grupos de teste do segmento {#delete-test-groups}

1. Navegue até a exibição principal [!UICONTROL Audience Lab].
1. Localize o grupo de teste que deseja excluir. Você pode:

   * pressione o controle **[!UICONTROL Delete]** no cartão do grupo de teste, ou
   * pressione o título do grupo de teste no cartão do grupo de teste para ir para a exibição [Informações do Grupo de Teste](../../features/audience-lab/audience-lab-information-view.md) e pressione o controle **[!UICONTROL Delete]** na barra de título.

1. Para [segmentos de teste concluídos](../../features/audience-lab/audience-lab.md#status), um alerta solicitará que você baixe o arquivo CSV para salvar os relatórios, se desejar.
