---
description: Esta página inclui orientação passo a passo sobre como combinar dados do CRM offline com dados comportamentais que você já tem no Audience Manager para criar novos segmentos de público-alvo e, em seguida, enviar esses segmentos de público-alvo para Destinos com base em pessoas.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with behavioral data that you already have in Audience Manager to create new audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow A - Personalization Based on All Online Activity Combined with Offline Data
solution: Audience Manager
title: Fluxo de trabalho A - Personalization com base em toda a atividade online combinada com dados offline
feature: People-based Destinations
exl-id: 1f906955-8fe7-4cce-95d6-0e4275d523e8
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1108'
ht-degree: 0%

---

# Fluxo de trabalho A - Personalization com base em toda a atividade online combinada com dados offline {#workflow-a}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e pelo uso desse recurso. Nada contido aqui é aconselhamento jurídico. Consulte seu próprio serviço jurídico para obter orientação jurídica.

Esta página inclui orientação passo a passo sobre como combinar dados do [!DNL CRM] offline com dados comportamentais que você já tem no Audience Manager para criar novos segmentos de público e, em seguida, enviar esses segmentos de público-alvo para o [!DNL People-Based Destinations].

## Etapa 1 - Definir configurações do Data Source {#configure-data-source-settings}

Se os [DPUUIDs](../../reference/ids-in-aam.md) forem endereços de email com hash e em letras minúsculas, talvez seja necessário configurar a fonte de dados que armazenará os endereços de email com hash.

 

**Cenário 1: seus [DPUUIDs](../../reference/ids-in-aam.md) já são endereços de email com hash e minúsculas.**

Nesse caso, é necessário rotular a fonte de dados correspondente dessa maneira:

1. Vá para [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. Localize a fonte de dados que contém seus [DPUUIDs](../../reference/ids-in-aam.md) e clique nela.
1. No menu suspenso **[!UICONTROL ID Type]**, selecione **[!UICONTROL Cross Device]**.
1. Verifique se a opção [!UICONTROL Cannot be tied to personally identifiable information] está desmarcada.
1. Na seção **[!UICONTROL Data Source Settings]**, selecione as opções **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e habilite a opção **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Use o menu suspenso para selecionar o rótulo **[!UICONTROL Emails(SHA256, lowercased)]** para esta fonte de dados.
   >[!IMPORTANT]
   >
   >Essa opção rotula apenas a fonte de dados como contendo dados com hash com esse algoritmo específico. O Audience Manager não faz o hash dos dados nesta etapa. Verifique se os endereços de email que você planeja armazenar nesta fonte de dados já foram atribuídos a hash com o algoritmo [!DNL SHA256]. Caso contrário, você não poderá usá-lo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Salve as configurações da fonte de dados.

 

**Cenário 2: seus [DPUUIDs](../../reference/ids-in-aam.md) não são endereços de email com hash e em minúsculas.**

Nesse caso, você precisa criar uma nova fonte de dados entre dispositivos que armazenará seus endereços de email com hash. Veja como fazer isso:

1. Faça logon em sua conta Audience Manager, vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** e clique em **[!UICONTROL Add New]**.
1. Insira um [!UICONTROL Name] e [!UICONTROL Description] para sua nova fonte de dados.
1. No menu suspenso **[!UICONTROL ID Type]**, selecione **[!UICONTROL Cross Device]**.
1. Na seção **[!UICONTROL Data Source Settings]**, selecione as opções **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e habilite a opção **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Use o menu suspenso para selecionar o rótulo **[!UICONTROL Emails(SHA256, lowercased)]** para esta fonte de dados.
   >[!IMPORTANT]
   >
   >Essa opção rotula apenas a fonte de dados como contendo dados com hash com esse algoritmo específico. O Audience Manager não faz o hash dos dados nesta etapa. Verifique se os endereços de email que você planeja armazenar nesta fonte de dados já foram atribuídos a hash com o algoritmo [!DNL SHA256]. Caso contrário, você não poderá usá-lo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Salve as configurações da fonte de dados.

Assista ao vídeo abaixo para obter um tutorial em vídeo sobre como criar uma fonte de dados para [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> Consulte [Integração de dados](people-based-destinations-prerequisites.md#data-onboarding) para perguntas frequentes sobre como você deve trazer seus dados offline para o Audience Manager for People-Based Destinations.

## Etapa 2 - Corresponder DPUUIDs a Endereços de email com hash por meio da Sincronização de ID com base em arquivo {#match-ids-emails}

>[!IMPORTANT]
>
> Esta etapa se aplica somente ao [Cenário 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) descrito acima. Se seus [DPUUIDs](../../reference/ids-in-aam.md) já forem endereços de email com hash, pule para [Etapa 3 - Criar uma Regra de Mesclagem de Perfis para Segmentação](people-based-destinations-workflow-combined.md#create-merge-rule).

Digamos que você queira corresponder seus [DPUUIDs](../../reference/ids-in-aam.md) existentes aos endereços de email com hash da tabela abaixo (coluna à direita) e armazenar os endereços de email com hash na nova fonte de dados criada em [Etapa 1 - Definir Configurações de Source de Dados](people-based-destinations-workflow-combined.md#configure-data-source-settings).

| DPUUID (ID DE CRM) | Endereço de email | Endereço de email com hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Você pode vincular até 10 endereços de email com hash a um único [DPUUID](../../reference/ids-in-aam.md). Para fazer isso, separe os endereços de email com hash com um `<TAB>`, dentro do arquivo de sincronização.

No nosso exemplo, agora você teria duas fontes de dados.

| ID da fonte de dados | Conteúdo da fonte de dados |
| -------------- | -------------------------- |
| 999999 | DPUUIDs existentes (IDs de CRM) |
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

[Baixar arquivo de exemplo aqui](assets/c2c_id_999999_987654_1560431657.sync).

Após criar o arquivo de sincronização de ID, é necessário carregá-lo em um bucket [!DNL Amazon S3]. Para saber como carregar arquivos de sincronização de ID, consulte [Enviar dados em lote para o Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Etapa 3 - Criar uma regra de mesclagem de perfis para segmentação {#create-merge-rule}

A próxima etapa é criar uma nova regra de mesclagem que ajudará você a criar os segmentos de público-alvo para enviar aos seus destinos com base em pessoas.

>[!IMPORTANT]
>
> Se você já tiver uma regra definida com as opções [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL Last Authenticated Profiles], pule para [Etapa 4 - Criar segmentos de público-alvo](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Faça logon em sua conta Audience Manager e vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Clique em **[!UICONTROL Add New Rule]**.
1. Insira uma regra de mesclagem de perfis **[!UICONTROL Name]** e **[!UICONTROL Description]**.
1. Na seção **[!UICONTROL Profile Merge Rule Setup]**, selecione as opções **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**.
1. Na lista **[!UICONTROL Cross-Device Profile Options]**, selecione as fontes de dados nas quais deseja executar a segmentação. Estas devem ser as fontes de dados que contêm seus [DPUUIDs](../../reference/ids-in-aam.md) existentes.

## Etapa 4 - Criar segmentos de público {#create-audience-segments}

Para criar novos segmentos de público, use o [Construtor de segmentos](../segments/segment-builder.md). Se você tiver segmentos de público-alvo existentes que deseja enviar para [!DNL People-Based Destinations], pule para [Etapa 5 - Configurar a Autenticação da Plataforma com Base em Pessoas](people-based-destinations-workflow-combined.md#configure-authentication).

## Etapa 5 - Configurar a autenticação da plataforma baseada em pessoas {#configure-authentication}

1. Faça logon em sua conta Audience Manager e vá para **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se você tiver uma integração configurada anteriormente com uma plataforma social, deverá vê-la listada nesta página. Caso contrário, a página ficará vazia.
   ![integração baseada em pessoas](assets/pbd-config.png)
1. Clique em **[!UICONTROL Add Account]**.
1. Use o menu suspenso **[!UICONTROL People-Based Platform]** para selecionar a plataforma com a qual deseja configurar a integração.
   ![plataforma baseada em pessoas](assets/pbd-add.png)
1. Clique em **[!UICONTROL Confirm]** para ser redirecionado para a página de autenticação da plataforma selecionada.
1. Depois de autenticar em sua conta da plataforma social, você é redirecionado para o Audience Manager, onde deve ver suas contas de anunciante associadas. Selecione a conta de anunciante que deseja usar e clique em **[!UICONTROL Confirm]**.
1. O Audience Manager exibe uma notificação na parte superior da página para que você saiba se a conta foi adicionada com êxito. A notificação também permite adicionar um endereço de email de contato para receber notificações quando a autenticação da plataforma social estiver prestes a expirar.

>[!IMPORTANT]
>
>Um Audience Manager lida com a integração com plataformas sociais por meio de tokens de autenticação que expiram após um determinado período. Consulte Renovação do token de autenticação para obter detalhes sobre como renovar os tokens expirados.

## Etapa 6 - Criar um destino com base em pessoas {#create-destination}

1. Faça logon em sua conta Audience Manager, vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** e clique em **[!UICONTROL Create Destination]**.
1. Na seção **[!UICONTROL Basic Information]**, insira um **[!UICONTROL Name]** e **[!UICONTROL Description]** para sua nova fonte de dados e use as seguintes configurações:
   * **[!UICONTROL Category]**: Plataformas Integradas;
   * **[!UICONTROL Type]**: Baseado Em Pessoas;
   * **[!UICONTROL Platform]**: selecione a plataforma com base em pessoas para a qual você deseja enviar segmentos de público-alvo;
   * **[!UICONTROL Account]**: selecione a conta de anunciante desejada associada à plataforma selecionada.

     ![criar-destino](assets/pbd-create-destination.png)
1. Clique em **[!UICONTROL Next]**.
1. Escolha o **[!UICONTROL Data Export Labels]** que deseja definir para este destino.
1. Na seção **[!UICONTROL Configuration]**, selecione a fonte de dados que contém suas fontes de dados com hash.
1. Na seção **[!UICONTROL Segment Mappings]**, selecione os segmentos que deseja enviar para esse destino. Estes são os segmentos que você criou em [Etapa 4 - Criar segmentos de público-alvo](people-based-destinations-workflow-combined.md#create-audience-segments).
1. Salve o destino.
