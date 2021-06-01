---
description: 'Esta página inclui orientações passo a passo sobre como combinar dados de CRM offline com dados comportamentais que você já tem no Audience Manager para criar novos segmentos de público-alvo e, em seguida, enviar esses segmentos de público-alvo para Destinos baseados em pessoas.  '
seo-description: 'Esta página inclui orientações passo a passo sobre como combinar dados de CRM offline com dados comportamentais que você já tem no Audience Manager para criar novos segmentos de público-alvo e, em seguida, enviar esses segmentos de público-alvo para Destinos baseados em pessoas.   '
seo-title: Fluxo de trabalho A - Personalização com base em toda a Atividade online combinada com dados offline
solution: Audience Manager
title: Fluxo de trabalho A - Personalização com base em toda a Atividade online combinada com dados offline
feature: Destinos com base em pessoas
exl-id: 1f906955-8fe7-4cce-95d6-0e4275d523e8
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 7%

---

# Fluxo de trabalho A - Personalização com base em toda a Atividade online combinada com dados offline {#workflow-a}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e uso deste recurso. Nada neste documento é de aconselhamento jurídico. Consulte o seu advogado para obter orientação jurídica.

Esta página inclui orientações passo a passo sobre como combinar dados offline [!DNL CRM] com dados comportamentais que você já tem no Audience Manager para criar novos segmentos de público-alvo e, em seguida, enviar esses segmentos de público-alvo para [!DNL People-Based Destinations].

## Etapa 1 - Definir as configurações da fonte de dados {#configure-data-source-settings}

Dependendo de seus [DPUUIDs](../../reference/ids-in-aam.md) serem endereços de email com hash em letras minúsculas, talvez seja necessário configurar a fonte de dados que armazenará os endereços de email com hash.

 

**Cenário 1: seus  [](../../reference/ids-in-aam.md) DPUUIDs já têm endereços de email com hash em letras minúsculas.**

Nesse caso, é necessário rotular a fonte de dados correspondente como tal:

1. Vá para [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. Encontre a fonte de dados que contém seus [DPUUIDs](../../reference/ids-in-aam.md) e clique nela.
1. No menu suspenso **[!UICONTROL ID Type]**, selecione **[!UICONTROL Cross Device]**.
1. Verifique se a opção [!UICONTROL Cannot be tied to personally identifiable information] está desmarcada.
1. Na seção **[!UICONTROL Data Source Settings]**, selecione as opções **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e habilite a opção **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Use o menu suspenso para selecionar o rótulo **[!UICONTROL Emails(SHA256, lowercased)]** para essa fonte de dados.
   >[!IMPORTANT]
   >
   >Essa opção rotula apenas a fonte de dados como contendo dados com hash com esse algoritmo específico. O Audience Manager não faz hash nos dados desta etapa. Verifique se os endereços de email que você planeja armazenar nessa fonte de dados já estão com hash com o algoritmo [!DNL SHA256]. Caso contrário, você não poderá usá-lo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Salve as configurações da fonte de dados.

 

**Cenário 2: seus  [](../../reference/ids-in-aam.md) DPUUIDs não são endereços de email com hash em letras minúsculas.**

Nesse caso, é necessário criar uma nova fonte de dados entre dispositivos que armazenará seus endereços de email com hash. Veja como fazer isso:

1. Faça logon na sua conta do Audience Manager, vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** e clique em **[!UICONTROL Add New]**.
1. Insira um [!UICONTROL Name] e [!UICONTROL Description] para sua nova fonte de dados.
1. No menu suspenso **[!UICONTROL ID Type]**, selecione **[!UICONTROL Cross Device]**.
1. Na seção **[!UICONTROL Data Source Settings]**, selecione as opções **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e habilite a opção **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Use o menu suspenso para selecionar o rótulo **[!UICONTROL Emails(SHA256, lowercased)]** para essa fonte de dados.
   >[!IMPORTANT]
   >
   >Essa opção rotula apenas a fonte de dados como contendo dados com hash com esse algoritmo específico. O Audience Manager não faz hash nos dados desta etapa. Verifique se os endereços de email que você planeja armazenar nessa fonte de dados já estão com hash com o algoritmo [!DNL SHA256]. Caso contrário, você não poderá usá-lo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Salve as configurações da fonte de dados.

Assista ao vídeo abaixo para obter um tutorial em vídeo sobre como criar uma fonte de dados para [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> Consulte [Integração de dados](people-based-destinations-prerequisites.md#data-onboarding) para obter perguntas frequentes sobre como você deve trazer seus dados offline para o Audience Manager para Destinos baseados em pessoas.

## Etapa 2 - Corresponder DPUUIDs a endereços de email com hash por meio da sincronização de ID baseada em arquivo {#match-ids-emails}

>[!IMPORTANT]
>
> Esta etapa se aplica somente ao [Cenário 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) descrito acima. Se os [DPUUIDs](../../reference/ids-in-aam.md) existentes já tiverem endereços de email com hash, pule para [Etapa 3 - Criar uma regra de mesclagem de perfil para segmentação](people-based-destinations-workflow-combined.md#create-merge-rule).

Considere que você deseja corresponder seus [DPUUIDs](../../reference/ids-in-aam.md) existentes aos endereços de email com hash da tabela abaixo (coluna à direita) e armazenar os endereços de email com hash na nova fonte de dados criada em [Etapa 1 - Configurar as configurações da fonte de dados](people-based-destinations-workflow-combined.md#configure-data-source-settings).

| DPUUID (ID do CRM) | Seu endereço de email | Endereço de email com hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 6807998276567319850405265607456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041 149 |
| 674126820834119957255387043620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 8915902479676034373311707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c975415d2d4862745ff8af00c49b6b4ae6 |

 

Você pode vincular até 10 endereços de email com hash a um único [DPUUID](../../reference/ids-in-aam.md). Para fazer isso, separe os endereços de email com hash por um `<TAB>`, dentro do arquivo de sincronização.

No nosso exemplo, agora você teria duas fontes de dados.

| ID da fonte de dados | Conteúdo da fonte de dados |
| -------------- | -------------------------- |
| 999999 | DPUUIDs existentes (IDs do CRM) |
| 987654 | Endereços de email com hash |

 

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

Depois de criar o arquivo de sincronização de ID, é necessário carregá-lo em um bucket [!DNL Amazon S3]. Para saber como fazer upload de arquivos de sincronização de ID, consulte [Enviar dados em lote para o Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Etapa 3 - Criar uma regra de mesclagem de perfil para segmentação {#create-merge-rule}

A próxima etapa é criar uma nova regra de mesclagem que ajudará você a criar os segmentos de público-alvo para enviar para seus destinos com base em pessoas.

>[!IMPORTANT]
>
> Se você já tiver uma regra definida com as opções [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL Last Authenticated Profiles], poderá pular para [Etapa 4 - Criar segmentos de público-alvo](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Faça logon na sua conta do Audience Manager e acesse **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Clique em **[!UICONTROL Add New Rule]**.
1. Insira uma regra de mesclagem de perfil **[!UICONTROL Name]** e **[!UICONTROL Description]**.
1. Na seção **[!UICONTROL Profile Merge Rule Setup]**, selecione as opções **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**.
1. Na lista **[!UICONTROL Cross-Device Profile Options]**, selecione as fontes de dados nas quais deseja executar a segmentação. Essas devem ser as fontes de dados que contêm seus [DPUUIDs](../../reference/ids-in-aam.md) existentes.

## Etapa 4 - Criar segmentos de público-alvo {#create-audience-segments}

Para criar novos segmentos de público-alvo, use o [Construtor de segmentos](../segments/segment-builder.md). Se você tem segmentos de público-alvo existentes que deseja enviar para [!DNL People-Based Destinations], pule para [Etapa 5 - Configurar a autenticação de plataforma com base em pessoas](people-based-destinations-workflow-combined.md#configure-authentication).

## Etapa 5 - Configurar a autenticação de plataforma com base em pessoas {#configure-authentication}

1. Faça logon na sua conta do Audience Manager e acesse **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se você tiver uma integração configurada anteriormente com uma plataforma social, ela deverá ser exibida nesta página. Caso contrário, a página ficará vazia.
   ![integração com base em pessoas](assets/pbd-config.png)
1. Clique em **[!UICONTROL Add Account]**.
1. Use o menu suspenso **[!UICONTROL People-Based Platform]** para selecionar a plataforma com a qual deseja configurar a integração.
   ![plataforma baseada em pessoas](assets/pbd-add.png)
1. Clique em **[!UICONTROL Confirm]** para ser redirecionado para a página de autenticação da plataforma selecionada.
1. Depois de autenticar na conta da plataforma social, você é redirecionado para o Audience Manager, onde deve ver as contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique em **[!UICONTROL Confirm]**.
1. O Audience Manager exibe uma notificação na parte superior da página para que você saiba se a conta foi adicionada com êxito. A notificação também permite adicionar um endereço de email de contato para receber notificações quando a autenticação da plataforma social estiver prestes a expirar.

>[!IMPORTANT]
>
>Um Audience Manager trata da integração com plataformas sociais por meio de tokens de autenticação que expiram após um determinado período. Consulte Renovação de token de autenticação para obter detalhes sobre como renovar os tokens expirados.

## Etapa 6 - Criar um destino com base em pessoas {#create-destination}

1. Faça logon na sua conta do Audience Manager, vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** e clique em **[!UICONTROL Create Destination]**.
1. Na seção **[!UICONTROL Basic Information]** , digite um **[!UICONTROL Name]** e **[!UICONTROL Description]** para sua nova fonte de dados e use as seguintes configurações:
   * **[!UICONTROL Category]**: Plataformas integradas;
   * **[!UICONTROL Type]**: Baseado em pessoas;
   * **[!UICONTROL Platform]**: selecione a plataforma baseada em pessoas para a qual deseja enviar segmentos de público-alvo;
   * **[!UICONTROL Account]**: selecione a conta do anunciante desejada associada à plataforma selecionada.
      ![create-destination](assets/pbd-create-destination.png)
1. Clique em **[!UICONTROL Next]**.
1. Escolha o **[!UICONTROL Data Export Labels]** que deseja definir para este destino.
1. Na seção **[!UICONTROL Configuration]**, selecione a fonte de dados que contém suas fontes de dados com hash.
1. Na seção **[!UICONTROL Segment Mappings]**, selecione os segmentos que deseja enviar para esse destino. Esses seriam os segmentos criados em [Etapa 4 - Criar segmentos de público-alvo](people-based-destinations-workflow-combined.md#create-audience-segments).
1. Salve o destino.
