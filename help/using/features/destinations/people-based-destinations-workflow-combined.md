---
description: 'Esta página inclui orientações passo a passo sobre como combinar dados do CRM offline com dados comportamentais que você já tem no Audience Manager para criar novos segmentos de público-alvo e, em seguida, enviar esses segmentos de público-alvo para Destinos baseados em pessoas.  '
seo-description: 'Esta página inclui orientações passo a passo sobre como combinar dados do CRM offline com dados comportamentais que você já tem no Audience Manager para criar novos segmentos de público-alvo e, em seguida, enviar esses segmentos de público-alvo para Destinos baseados em pessoas.   '
seo-title: Fluxo de trabalho A - Personalização com base em toda a atividade online combinada com dados offline
solution: Audience Manager
title: Fluxo de trabalho A - Personalização com base em toda a atividade online combinada com dados offline
translation-type: tm+mt
source-git-commit: fb5d9eff3573048d3e8a570b342a97bce3cd8da0

---


# Fluxo de trabalho A - Personalização com base em toda a atividade online combinada com dados offline {#workflow-a}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a guiá-lo pela configuração e uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

Esta página inclui orientações passo a passo sobre como combinar dados offline [!DNL CRM] com dados comportamentais que você já tem no Audience Manager para criar novos segmentos de público-alvo e, em seguida, enviar esses segmentos de público-alvo para [!DNL People-Based Destinations].

## Etapa 1 - Definir configurações da fonte de dados {#configure-data-source-settings}

Dependendo de seus [DPUUIDs](../../reference/ids-in-aam.md) serem endereços de email com hash e minúsculas, talvez seja necessário configurar a fonte de dados que armazenará os endereços de email com hash.

 

**Cenário 1: seus[DPUUIDs](../../reference/ids-in-aam.md)já têm endereços de email com hash em minúsculas.**

Nesse caso, é necessário rotular a fonte de dados correspondente como tal:

1. Vá para [!UICONTROL Audience Data] -&gt; [!UICONTROL Data Sources].
1. Localize a fonte de dados que contém seus [DPUUIDs](../../reference/ids-in-aam.md)e clique nela.
1. In the  drop-down menu, select .**[!UICONTROL ID Type]****[!UICONTROL Cross Device]**
1. Make sure the option  is unchecked.[!UICONTROL Cannot be tied to personally identifiable information]
1. In the  section, select both the  and  options, and enable the  option.**[!UICONTROL Data Source Settings]****[!UICONTROL Inbound]****[!UICONTROL Outbound]****[!UICONTROL Share associated cross-device IDs in people-based destinations]**
1. Use the drop-down menu to select the  label for this data source.**[!UICONTROL Emails(SHA256, lowercased)]**
   >[!IMPORTANT]
   >
   >This option only labels the data source as containing data hashed with that specific algorithm. Audience Manager does not hash the data at this step. Make sure the email addresses that you plan on storing in this data source are already hashed with the  algorithm. [!DNL SHA256] Otherwise, you won't be able to use it for .[!DNL People-Based Destinations]

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Save the data source settings.

 

**Cenário 2: seus[DPUUIDs](../../reference/ids-in-aam.md)não são endereços de email com hash em minúsculas.**

In this case, you need to create a new cross-device data source that will store your hashed email addresses. Veja como fazer isso:

1. Faça logon em sua conta do Audience Manager, vá para **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]** e clique em **[!UICONTROL Add New]**.
1. Insira um [!UICONTROL Name] e [!UICONTROL Description] para sua nova fonte de dados.
1. No menu **[!UICONTROL ID Type]** suspenso, selecione **[!UICONTROL Cross Device]**.
1. Na **[!UICONTROL Data Source Settings]** seção, selecione as opções **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e ative a **[!UICONTROL Share associated cross-device IDs in people-based destinations]** .
1. Use o menu suspenso para selecionar o **[!UICONTROL Emails(SHA256, lowercased)]** rótulo dessa fonte de dados.
   >[!IMPORTANT]
   >
   >Essa opção rotula somente a fonte de dados como contendo dados com hash com esse algoritmo específico. O Audience Manager não hash os dados nesta etapa. Verifique se os endereços de email que você planeja armazenar nessa fonte de dados já estão com hash com o [!DNL SHA256] algoritmo. Caso contrário, você não poderá usá-lo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Salve as configurações da fonte de dados.

>[!NOTE]
>
> Consulte Integração de [dados](people-based-destinations-prerequisites.md#data-onboarding) para obter perguntas frequentes sobre como você deve colocar seus dados offline no Audience Manager para destinos baseados em pessoas.

## Etapa 2 - Corresponder DPUUIDs a endereços de email com hash via sincronização de ID baseada em arquivo {#match-ids-emails}

>[!IMPORTANT]
>
> Esta etapa se aplica somente ao [Cenário 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) descrito acima. Se seus [DPUUIDs](../../reference/ids-in-aam.md) existentes já tiverem endereços de email com hash, pule para a [Etapa 3 - Criar uma regra de mesclagem de perfil para segmentação](people-based-destinations-workflow-combined.md#create-merge-rule).

Digamos que você queira corresponder seus [DPUUIDs](../../reference/ids-in-aam.md) existentes aos endereços de email com hash da tabela abaixo (coluna direita) e armazenar os endereços de email com hash na nova fonte de dados criada na [Etapa 1 - Definir configurações](people-based-destinations-workflow-combined.md#configure-data-source-settings)da fonte de dados.

| DPUUID (CRM ID) | Endereço de email | Endereço de email com hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Você pode vincular até 10 endereços de email com hash a uma única [DPUUID](../../reference/ids-in-aam.md). Para fazer isso, separe os endereços de email com hash por vírgula, dentro do arquivo de sincronização.

Em nosso exemplo, você agora teria duas fontes de dados.

| ID da fonte de dados | Conteúdo da fonte de dados |
| -------------- | -------------------------- |
| 999999 | DPUUIDs existentes (IDs CRM) |
| 987654 | Endereços de email em hash |

 

Seu arquivo [de sincronização de](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ID teria o seguinte conteúdo:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

O arquivo [de sincronização de](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ID deve seguir esta estrutura de nomenclatura:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

No exemplo acima, o nome do arquivo seria semelhante a:
`c2c_id_999999_987654_1560431657.sync`

[Baixe o arquivo de exemplo aqui](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync).

Depois de criar o arquivo de sincronização de ID, é necessário carregá-lo em um [!DNL Amazon S3] bucket. Para saber como carregar arquivos de sincronização de ID, consulte [Enviar dados em lote para o Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Etapa 3 - Criar uma regra de mesclagem de perfil para segmentação {#create-merge-rule}

A próxima etapa é criar uma nova regra de mesclagem que ajudará a criar os segmentos de público-alvo para enviar para seus destinos baseados em pessoas.

>[!IMPORTANT]
>
> Se você já tiver uma regra definida com as opções [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL Last Authenticated Profiles] , poderá pular para a [Etapa 4 - Criar segmentos](people-based-destinations-workflow-combined.md#create-audience-segments)de público-alvo.

1. Faça logon em sua conta do Audience Manager e vá para **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Profile Merge Rules]**.
1. Clique em **[!UICONTROL Add New Rule]**.
1. Insira uma regra de mesclagem de perfil **[!UICONTROL Name]** e **[!UICONTROL Description]**.
1. Na **[!UICONTROL Profile Merge Rule Setup]** seção, selecione as **[!UICONTROL Current Authenticated Profiles]** opções ou **[!UICONTROL Last Authenticated Profiles]** .
1. In the  list, select the data sources that you want to run the segmentation on. **[!UICONTROL Cross-Device Profile Options]** These should be the data sources containing your existing DPUUIDs.[](../../reference/ids-in-aam.md)

## Etapa 4 - Criar segmentos de público-alvo {#create-audience-segments}

To create new audience segments, use the Segment Builder. [](../segments/segment-builder.md) If you have existing audience segments that you want to send to , skip to Step 5 - Configure People-Based Platform Authentication.[!DNL People-Based Destinations][](people-based-destinations-workflow-combined.md#configure-authentication)

## Step 5 - Configure People-Based Platform Authentication {#configure-authentication}

1. Faça logon em sua conta do Audience Manager e vá para **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Se você tiver uma integração previamente configurada com uma plataforma social, deverá vê-la listada nesta página. Caso contrário, a página estará vazia.
   ![integração baseada em pessoas](assets/pbd-config.png)
1. Clique em **[!UICONTROL Add Account]**.
1. Use o menu **[!UICONTROL People-Based Platform]** suspenso para selecionar a plataforma com a qual deseja configurar a integração.
   ![plataforma baseada em pessoas](assets/pbd-add.png)
1. Clique em **[!UICONTROL Confirm]** para ser redirecionado para a página de autenticação da plataforma selecionada.
1. Depois de autenticar em sua conta da plataforma social, você será redirecionado para o Audience Manager, onde deverá ver suas contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique em **[!UICONTROL Confirm]**.
1. O Audience Manager exibe uma notificação na parte superior da página para informá-lo se a conta foi adicionada com êxito. A notificação também permite que você adicione um endereço de email de contato para receber notificações quando a autenticação da plataforma social estiver prestes a expirar.

>[!IMPORTANT]
>
>Um Audience Manager lida com a integração com plataformas sociais por meio de tokens de autenticação que expiram após um determinado período de tempo. Consulte Renovação de token de autenticação para obter detalhes sobre como renovar os tokens expirados.

## Etapa 6 - Criar um destino baseado em pessoas {#create-destination}

1. Log in to your Audience Manager account, go to  &gt; , and click .**[!UICONTROL Audience Data]****[!UICONTROL Destinations]****[!UICONTROL Create Destination]**
1. Na **[!UICONTROL Basic Information]** seção, digite um **[!UICONTROL Name]** e **[!UICONTROL Description]** para sua nova fonte de dados e use as seguintes configurações:
   * **[!UICONTROL Category]**: Plataformas integradas;
   * **[!UICONTROL Type]**: Baseado em pessoas;
   * **[!UICONTROL Platform]**: selecione a plataforma baseada em pessoas para a qual deseja enviar segmentos de público-alvo;
   * **[!UICONTROL Account]**: selecione a conta do anunciante desejada associada à plataforma selecionada.
      ![create-target](assets/pbd-create-destination.png)
1. Clique em **[!UICONTROL Next]**.
1. Escolha o destino **[!UICONTROL Data Export Labels]** que deseja definir.
1. Na **[!UICONTROL Configuration]** seção, selecione a fonte de dados que contém suas fontes de dados com hash.
1. Na **[!UICONTROL Segment Mappings]** seção, selecione os segmentos que deseja enviar para esse destino. Esses seriam os segmentos criados na [Etapa 4 - Criar segmentos](people-based-destinations-workflow-combined.md#create-audience-segments)de público-alvo.
1. Salve o destino.
