---
description: 'Esta página inclui orientações passo a passo sobre como combinar dados do CRM offline com dados comportamentais que você já tem no Audience Manager para criar novos segmentos de audiência e, em seguida, enviar esses segmentos de audiência para Destinos Baseados em Pessoas.  '
seo-description: 'Esta página inclui orientações passo a passo sobre como combinar dados do CRM offline com dados comportamentais que você já tem no Audience Manager para criar novos segmentos de audiência e, em seguida, enviar esses segmentos de audiência para Destinos Baseados em Pessoas.   '
seo-title: Fluxo de trabalho A - Personalização com base em toda a Atividade online combinada com dados offline
solution: Audience Manager
title: Fluxo de trabalho A - Personalização com base em toda a Atividade online combinada com dados offline
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1180'
ht-degree: 7%

---


# Fluxo de trabalho A - Personalização com base em toda a Atividade online combinada com dados offline {#workflow-a}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo durante a configuração e o uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

Esta página inclui orientações passo a passo sobre como combinar dados offline [!DNL CRM] com dados comportamentais que você já tem no Audience Manager para criar novos segmentos de audiência e, em seguida, enviar esses segmentos de audiência para [!DNL People-Based Destinations].

## Etapa 1 - Configurar as configurações da fonte de dados {#configure-data-source-settings}

Dependendo de seus [DPUUIDs](../../reference/ids-in-aam.md) serem endereços de email com hash em minúsculas, talvez seja necessário configurar a fonte de dados que armazenará os endereços de email com hash.

 

**Cenário 1: seus  [](../../reference/ids-in-aam.md) DPUUIDs já têm endereços de email com hash em minúsculas.**

Nesse caso, é necessário rotular a fonte de dados correspondente como tal:

1. Vá para [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. Localize a fonte de dados que contém seus [DPUUIDs](../../reference/ids-in-aam.md) e clique nela.
1. No menu suspenso **[!UICONTROL ID Type]**, selecione **[!UICONTROL Cross Device]**.
1. Verifique se a opção [!UICONTROL Cannot be tied to personally identifiable information] está desmarcada.
1. Na seção **[!UICONTROL Data Source Settings]**, selecione as opções **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e ative a opção **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Use o menu suspenso para selecionar o rótulo **[!UICONTROL Emails(SHA256, lowercased)]** para essa fonte de dados.
   >[!IMPORTANT]
   >
   >Essa opção rotula somente a fonte de dados como contendo dados com hash com esse algoritmo específico. Audience Manager não hash os dados nesta etapa. Verifique se os endereços de email que você planeja armazenar nessa fonte de dados já estão com hash com o algoritmo [!DNL SHA256]. Caso contrário, você não poderá usá-lo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Salve as configurações da fonte de dados.

 

**Cenário 2: seus  [](../../reference/ids-in-aam.md) DPUUIDs não têm endereços de email em hash e minúsculas.**

Nesse caso, é necessário criar uma nova fonte de dados entre dispositivos que armazene seus endereços de email com hash. Veja como fazer isso:

1. Faça logon em sua conta do Audience Manager, vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** e clique em **[!UICONTROL Add New]**.
1. Insira [!UICONTROL Name] e [!UICONTROL Description] para sua nova fonte de dados.
1. No menu suspenso **[!UICONTROL ID Type]**, selecione **[!UICONTROL Cross Device]**.
1. Na seção **[!UICONTROL Data Source Settings]**, selecione as opções **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e ative a opção **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Use o menu suspenso para selecionar o rótulo **[!UICONTROL Emails(SHA256, lowercased)]** para essa fonte de dados.
   >[!IMPORTANT]
   >
   >Essa opção rotula somente a fonte de dados como contendo dados com hash com esse algoritmo específico. Audience Manager não hash os dados nesta etapa. Verifique se os endereços de email que você planeja armazenar nessa fonte de dados já estão com hash com o algoritmo [!DNL SHA256]. Caso contrário, você não poderá usá-lo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Salve as configurações da fonte de dados.

Assista ao vídeo abaixo para ver um tutorial em vídeo sobre como criar uma fonte de dados para [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> Consulte [Integração de dados](people-based-destinations-prerequisites.md#data-onboarding) para obter perguntas frequentes sobre como você deve colocar seus dados offline no Audience Manager para Destinos baseados em pessoas.

## Etapa 2 - Corresponder DPUUIDs a endereços de email com hash via sincronização de ID baseada em arquivo {#match-ids-emails}

>[!IMPORTANT]
>
> Esta etapa se aplica somente ao [Cenário 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) descrito acima. Se os seus [DPUUIDs](../../reference/ids-in-aam.md) existentes já tiverem endereços de email com hash, pule para [Etapa 3 - Criar uma regra de mesclagem de Perfil para segmentação](people-based-destinations-workflow-combined.md#create-merge-rule).

Digamos que você queira corresponder seus [DPUUIDs](../../reference/ids-in-aam.md) existentes aos endereços de email com hash da tabela abaixo (coluna direita) e armazenar os endereços de email com hash na nova fonte de dados que você criou em [Etapa 1 - Configurar as configurações da fonte de dados](people-based-destinations-workflow-combined.md#configure-data-source-settings).

| DPUUID (CRM ID) | Seu endereço de email | Endereço de email com hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 6807998276567319850405265607456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041 149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Você pode vincular até 10 endereços de email com hash a um único [DPUUID](../../reference/ids-in-aam.md). Para fazer isso, separe os endereços de email com hash por vírgula, dentro do arquivo de sincronização.

Em nosso exemplo, você agora teria duas fontes de dados.

| ID da fonte de dados | Conteúdo da fonte de dados |
| -------------- | -------------------------- |
| 999999 | DPUUIDs existentes (IDs CRM) |
| 987654 | Endereços de email em hash |

 

Seu [arquivo de sincronização de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) teria o seguinte conteúdo:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

O [arquivo de sincronização de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) deve seguir esta estrutura de nomenclatura:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

No exemplo acima, o nome do arquivo seria semelhante a:
`c2c_id_999999_987654_1560431657.sync`

[Baixe o arquivo de exemplo aqui](assets/c2c_id_999999_987654_1560431657.sync).

Depois de criar o arquivo de sincronização de ID, é necessário carregá-lo em um bucket [!DNL Amazon S3]. Para saber como carregar arquivos de sincronização de ID, consulte [Enviar dados em lote para Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Etapa 3 - Criar uma regra de união de Perfis para a segmentação {#create-merge-rule}

A próxima etapa é a criação de uma nova regra de mesclagem que ajudará a criar os segmentos de audiência para enviar aos destinos baseados em pessoas.

>[!IMPORTANT]
>
> Se você já tiver uma regra definida com as opções [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL Last Authenticated Profiles], poderá pular para [Etapa 4 - Criar segmentos de Audiência](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Faça logon na sua conta do Audience Manager e vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Clique em **[!UICONTROL Add New Rule]**.
1. Insira uma regra de união de perfis **[!UICONTROL Name]** e **[!UICONTROL Description]**.
1. Na seção **[!UICONTROL Profile Merge Rule Setup]**, selecione as opções **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**.
1. Na lista **[!UICONTROL Cross-Device Profile Options]**, selecione as fontes de dados nas quais deseja executar a segmentação. Essas devem ser as fontes de dados que contêm seus [DPUUIDs](../../reference/ids-in-aam.md) existentes.

## Etapa 4 - Criar segmentos de Audiência {#create-audience-segments}

Para criar novos segmentos de audiência, use o [Construtor de segmentos](../segments/segment-builder.md). Se você tiver segmentos de audiência existentes que deseja enviar para [!DNL People-Based Destinations], pule para [Etapa 5 - Configurar autenticação de plataforma baseada em pessoas](people-based-destinations-workflow-combined.md#configure-authentication).

## Etapa 5 - Configurar a autenticação de plataforma baseada em pessoas {#configure-authentication}

1. Faça logon na sua conta do Audience Manager e vá para **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se você tiver uma integração previamente configurada com uma plataforma social, deverá vê-la listada nesta página. Caso contrário, a página estará vazia.
   ![integração baseada em pessoas](assets/pbd-config.png)
1. Clique em **[!UICONTROL Add Account]**.
1. Use o menu suspenso **[!UICONTROL People-Based Platform]** para selecionar a plataforma com a qual você deseja configurar a integração.
   ![plataforma baseada em pessoas](assets/pbd-add.png)
1. Clique em **[!UICONTROL Confirm]** para ser redirecionado para a página de autenticação da plataforma selecionada.
1. Depois de autenticado em sua conta da plataforma social, você é redirecionado para o Audience Manager onde deve ver suas contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique em **[!UICONTROL Confirm]**.
1. O Audience Manager exibe uma notificação na parte superior da página para informar se a conta foi adicionada com êxito. A notificação também permite que você adicione um endereço de email de contato para receber notificações quando a autenticação da plataforma social estiver prestes a expirar.

>[!IMPORTANT]
>
>Um Audience Manager lida com a integração com plataformas sociais por meio de tokens de autenticação que expiram após um determinado período de tempo. Consulte Renovação de token de autenticação para obter detalhes sobre como renovar os tokens expirados.

## Etapa 6 - Criar um destino baseado em pessoas {#create-destination}

1. Faça logon em sua conta do Audience Manager, vá até **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** e clique em **[!UICONTROL Create Destination]**.
1. Na seção **[!UICONTROL Basic Information]**, insira **[!UICONTROL Name]** e **[!UICONTROL Description]** para sua nova fonte de dados e use as seguintes configurações:
   * **[!UICONTROL Category]**: Plataformas integradas;
   * **[!UICONTROL Type]**: Baseado em pessoas;
   * **[!UICONTROL Platform]**: selecione a plataforma baseada em pessoas para a qual deseja enviar segmentos de audiência;
   * **[!UICONTROL Account]**: selecione a conta do anunciante desejada associada à plataforma selecionada.
      ![create-target](assets/pbd-create-destination.png)
1. Clique em **[!UICONTROL Next]**.
1. Escolha o **[!UICONTROL Data Export Labels]** que deseja definir para este destino.
1. Na seção **[!UICONTROL Configuration]**, selecione a fonte de dados que contém suas fontes de dados com hash.
1. Na seção **[!UICONTROL Segment Mappings]**, selecione os segmentos que deseja enviar para esse destino. Esses seriam os segmentos criados em [Etapa 4 - Criar segmentos de Audiência](people-based-destinations-workflow-combined.md#create-audience-segments).
1. Salve o destino.
