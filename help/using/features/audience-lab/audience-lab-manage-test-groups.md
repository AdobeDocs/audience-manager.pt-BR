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
ht-degree: 1%

---

# Gerenciar grupos de teste {#manage-test-groups}

Este procedimento o guiará pelas etapas necessárias para criar, editar ou excluir um grupo de teste no [!UICONTROL Audience Lab].

## Criar grupos de teste de segmento {#create-test-groups}

### Pré-requisitos

<!-- create-test-group.xml -->

* Você precisa ter pelo menos um **característica de conversão** configurar. É possível configurar características de conversão na [Construtor de características](../../features/traits/create-onboarded-rule-based-traits.md), selecionando **conversão** como o tipo de evento. Para obter mais informações sobre o que são características de conversão e como configurá-las, preparamos um [vídeo](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) para você.

   >[!IMPORTANT]
   >
   >[Características de pasta](../../features/traits/about-folder-traits.md) são **não suportado** por [!UICONTROL Audience Lab]. Definição de [Tipo de evento](../../features/traits/create-onboarded-rule-based-traits.md) de uma característica de pasta para **conversão** não gerará dados no [!UICONTROL Audience Lab] para essa característica de pasta específica.

* Para empresas que usam [Controle de acesso baseado em função](../../features/administration/administration-overview.md): atribua a [!UICONTROL Audience Lab] [permissão curinga](../../features/administration/administration-overview.md#wild-card-permissions) para **[!UICONTROL User Groups]** para fornecer acesso. Essa permissão possibilita que o usuário crie e visualize os resultados de um teste. Um usuário só poderá usar segmentos de uma fonte de dados que tenha **ler** e **mapear para destino** privilégios para. O usuário só poderá usar características de conversão de uma fonte de dados para a qual tenha **&quot;ler&quot;** permissões. Um usuário também só poderá ver os destinos aos quais tem acesso. Portanto, antes de adicionar a variável [!DNL Audience Lab] permissão curinga para um grupo, verifique se o grupo tem:
   * acesso à leitura de características de conversão relevantes;
   * acesso à leitura e ao mapeamento de segmentos relevantes para testes;
   * acesso aos destinos pertinentes.

Para criar um novo [!UICONTROL Segment Test Group]:

1. Selecionar **[!UICONTROL Create New Test Group]** no [!UICONTROL Audience Lab] painel para iniciar o assistente.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Preencher um **[!UICONTROL Test Group Name]** e uma **[!UICONTROL Description]**.
   * Escolha o **[!UICONTROL Base Segment]** navegando no navegador de arquivos ou digitando na barra de pesquisa, confirme pressionando **[!UICONTROL Choose Segment.]**
   * Você pode salvar o grupo de teste como rascunho e retomar o trabalho nele posteriormente.
   * Um alerta será exibido caso o segmento base selecionado já esteja sendo usado em outros grupos de teste. O uso do segmento base duas vezes pode distorcer os resultados da conversão para ambos os testes.

1. **[!UICONTROL Allocate Test Segments]**

   * Você pode criar **até 15 segmentos de teste** e divida a porcentagem de dispositivos conforme desejar.
   * Você pode editar o nome dos segmentos de teste clicando neles.
   * As porcentagens são divididas automaticamente de forma uniforme em 100% quando novos segmentos de teste são alocados. É possível editar as porcentagens manualmente. Clique na caixa de seleção após editar as porcentagens e verifique se elas adicionam até 100%; caso contrário, você não poderá prosseguir para a próxima etapa.

1. **[!UICONTROL Set a Control Segment]**

   * Selecione um segmento de controle se quiser separar uma determinada parte do segmento a ser usada como um grupo de controle. Grupos de controle permitem que você veja o impacto dos segmentos de teste criados em comparação a um referencial.
   * Você pode selecionar um segmento de teste como segmento de controle na lista suspensa ou escolher **[!UICONTROL None]** para nenhum controle.
   * Clique em **[!UICONTROL Next]** quando terminar.

1. **[!UICONTROL Select Conversion Traits]**

   * Adicione características de conversão digitando na janela de características de conversão. Este é um **obrigatório** e não poderá prosseguir para a próxima etapa, a menos que adicione pelo menos uma característica de conversão.
   * Você pode adicionar até 5 características de conversão, se desejar.
   * Um alerta será exibido caso você selecione uma característica de conversão já usada para outros grupos de teste.
   * Observe que o Audience Manager não suporta o uso de [características da pasta](/help/using/features/traits/about-folder-traits.md) como características de conversão. Selecionar uma característica de pasta como característica de conversão resultará em 0 agregação e relatório de tendência exibidos no teste.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Digite os destinos desejados no campo de pesquisa ou use a seta suspensa. [!UICONTROL Audience Lab] os segmentos de teste podem ser enviados para URL, cookie ou destinos de servidor para servidor.
   * Arraste e solte segmentos para destinos.
   * Depois de soltar um segmento em um destino, preencha o **[!UICONTROL Destination Mapping Value]** cegos.
   * Você pode enviar o mesmo segmento de teste para vários destinos e adicionar vários segmentos de teste a um único destino.
   * Os destinos ficam esmaecidos se não estiverem disponíveis para um determinado segmento de teste com base em [Controles da exportação de dados](../../features/data-export-controls.md).
   * Os usuários só verão os destinos aos quais têm acesso com base no [Grupo de usuários RBAC](../../features/administration/administration-overview.md) eles pertencem a.
   * Por fim, é necessário selecionar uma data de início para o grupo de teste. Essa data marca o início do período em que seu grupo de teste será publicado nos destinos. Selecionar **Sem data final** para uma comparação indefinida dos segmentos de teste.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] com um perfil autenticado só são compatíveis com destinos em tempo real. Se um segmento de teste com uma regra de mesclagem de perfis dessa configuração for enviado para um destino de servidor para servidor baseado em arquivo, os públicos-alvo talvez não sejam preenchidos.

   Clique em **[!UICONTROL Next]** para revisar e finalizar seu grupo de teste.

1. **[!UICONTROL Summary & Finalize]**

   * Revise as informações adicionadas nas etapas anteriores e selecione **[!UICONTROL Finalize Group]**.
   * Lembre-se de que, uma vez finalizado um grupo de teste, ele poderá ser duplicado ou excluído, mas não editado.

   >[!NOTE]
   >* Você pode salvar os grupos de teste em qualquer ponto do processo de criação e retornar ao assistente posteriormente. O status do grupo de teste será **[!UICONTROL Draft]** e o grupo de teste não enviará dados para destinos até você finalizar o grupo de teste de segmento.
   >* Para testes de rascunho, você pode voltar e editar os grupos de teste clicando em **[!UICONTROL Edit]** no cartão do grupo de teste no campo principal [!UICONTROL Audience Lab] exibição.


## Editar grupos de teste de segmento {#edit-test-groups}

Entrada [!UICONTROL Audience Lab], você só poderá editar grupos de teste de rascunho. No [!UICONTROL Create Segment Test Group] assistente, você pode salvar seu grupo de teste como rascunho e continuar trabalhando nele posteriormente.

1. Navegue até a [!UICONTROL Audience Lab] visualização principal.
1. Procure os grupos de teste de rascunho e selecione o **[!UICONTROL Edit]** no cartão do grupo de teste.
1. Retomar o [Criar grupo de teste de segmento](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) e selecione **[!UICONTROL Finalize Group]** quando terminar.

## Excluir grupos de teste do segmento {#delete-test-groups}

1. Navegue até a [!UICONTROL Audience Lab] visualização principal.
1. Localize o grupo de teste que deseja excluir. Você pode:

   * pressione a **[!UICONTROL Delete]** controlo no cartão do grupo de ensaio, ou
   * pressione o título do grupo de teste no cartão do grupo de teste para ir para o [Testar informações do grupo](../../features/audience-lab/audience-lab-information-view.md) exiba e pressione a &lt;barra de espaço> **[!UICONTROL Delete]** controle na barra de título.

1. Para [segmentos de teste concluídos](../../features/audience-lab/audience-lab.md#status), um alerta solicitará que você baixe o arquivo CSV para salvar o relatório, se desejar.
