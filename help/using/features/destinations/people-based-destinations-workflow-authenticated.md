---
description: 'Esta página inclui orientações passo a passo sobre como combinar dados de CRM offline com dados comportamentais em tempo real para usuários autenticados criar segmentos de público-alvo e, em seguida, enviar esses segmentos de público-alvo para Destinos baseados em pessoas. '
seo-description: 'Esta página inclui orientações passo a passo sobre como combinar dados de CRM offline com dados comportamentais em tempo real para usuários autenticados criar segmentos de público-alvo e, em seguida, enviar esses segmentos de público-alvo para Destinos baseados em pessoas.  '
seo-title: Fluxo de trabalho C - Personalização baseada na Atividade autenticada combinada com dados offline
solution: Audience Manager
title: Fluxo de trabalho C - Personalização baseada na Atividade autenticada combinada com dados offline
feature: Destinos com base em pessoas
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 5%

---

# Fluxo de trabalho C - Personalização baseada na Atividade autenticada combinada com dados offline {#workflow-c}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e uso deste recurso. Nada neste documento é de aconselhamento jurídico. Consulte o seu advogado para obter orientação jurídica.

Esta página inclui orientações passo a passo sobre como combinar dados offline [!DNL CRM] com dados comportamentais em tempo real para usuários autenticados criar segmentos de público-alvo e, em seguida, enviar esses segmentos de público-alvo para [!DNL People-Based Destinations].

## Etapa 1 - Definir as configurações da fonte de dados {#configure-data-source-settings}

Dependendo de seus [DPUUIDs](../../reference/ids-in-aam.md) serem endereços de email com hash em letras minúsculas, talvez seja necessário configurar a fonte de dados que armazenará os endereços de email com hash.

 

**Cenário 1: seus  [](../../reference/ids-in-aam.md) DPUUIDs já têm endereços de email com hash em letras minúsculas.**

Nesse caso, pule para [Step 5 - Configure People-Based Platform Authentication](#configure-authentication).

 

**Cenário 2: seus  [](../../reference/ids-in-aam.md) DPUUIDs não são endereços de email com hash em letras minúsculas.**

Nesse caso, é necessário criar uma nova fonte de dados entre dispositivos que armazenará seus endereços de email com hash. Veja como fazer isso:

1. Faça logon na sua conta do Audience Manager, vá para **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** e clique em **[!UICONTROL Add New]**.
1. Insira um **[!UICONTROL Name]** e **[!UICONTROL Description]** para sua nova fonte de dados.
1. No menu suspenso **[!UICONTROL ID Type]**, selecione **[!UICONTROL Cross Device]**.
1. Na seção **[!UICONTROL Data Source Settings]**, selecione as opções **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e habilite a opção **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Use o menu suspenso para selecionar o rótulo **[!UICONTROL Emails(SHA256, lowercased)]** para essa fonte de dados.
   >[!IMPORTANT]
   >
   >Essa opção rotula apenas a fonte de dados como contendo dados com hash com esse algoritmo específico. O Audience Manager não faz hash nos dados desta etapa. Verifique se os endereços de email que você planeja armazenar nessa fonte de dados já estão com hash com o algoritmo [!DNL SHA256]. Caso contrário, você não poderá usá-lo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consulte [Integração de dados](people-based-destinations-prerequisites.md#data-onboarding) para obter perguntas frequentes sobre como você deve trazer seus dados offline para o Audience Manager para Destinos baseados em pessoas.

Assista ao vídeo abaixo para obter um tutorial em vídeo sobre como criar uma fonte de dados para [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Etapa 2 - Usar IDs declaradas para corresponder DPUUIDs a endereços de email com hash por meio de chamadas HTTP em tempo real {#match-email-addresses}

Para qualificar usuários autenticados para características com base em regras, é necessário enviar a qualificação de característica por meio de [IDs declaradas](../declared-ids.md).

### Exemplo

Digamos que você criou as duas fontes de dados a seguir.

| ID da fonte de dados | Conteúdo da fonte de dados |
| -------------- | -------------------------- |
| 999999 | DPUUIDs existentes (IDs do CRM) |
| 987654 | Endereços de email com hash |

 

Em seguida, você deseja qualificar as IDs de CRM abaixo para a característica na tabela.

| DPUUID (ID do CRM) | Seu endereço de email | Endereço de email com hash | Característica |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 6807998276567319850405265607456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041 149 | localização = US |

 

Sua ID declarada deve seguir esta sintaxe:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

No exemplo acima, a chamada de ID declarada deve ser semelhante a:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Etapa 3 - Criar uma regra de mesclagem de perfil para segmentação {#create-profile-merge-rule-segmentation}

A próxima etapa é criar uma nova regra de mesclagem que ajudará você a criar os segmentos de público-alvo para enviar para seu [!DNL People-Based Destinations].

>[!IMPORTANT]
>
>Se você já tiver uma regra definida com as opções **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**, poderá pular para [Etapa 4 - Criar segmentos de público-alvo](#create-audience-segments).

1. Faça logon na sua conta do Audience Manager e vá para **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Clique em **[!UICONTROL Add New Rule]**.
3. Insira uma regra de mesclagem de perfil **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. Na seção **[!UICONTROL Profile Merge Rule Setup]**, selecione a regra **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]** na lista **[!UICONTROL Cross-Device Options]**.
5. Na lista **[!UICONTROL Cross-Device Profile Options]**, selecione as fontes de dados nas quais deseja executar a segmentação. Essas devem ser as fontes de dados que contêm seus DPUUIDs existentes.
   ![mesclar configuração de regra](assets/pbd-pmr-combined.png)

## Etapa 4 - Criar segmentos de público-alvo {#create-audience-segments}

Para criar novos segmentos, use o [Construtor de segmentos](../segments/segment-builder.md). Se você tem segmentos de público-alvo existentes que deseja enviar para [!DNL People-Based Destinations], pule para [Etapa 5 - Configurar a autenticação de plataforma com base em pessoas](#configure-authentication).

## Etapa 5 - Configurar a autenticação de plataforma com base em pessoas {#configure-authentication}

1. Faça logon na sua conta do Audience Manager e acesse **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se você tiver uma integração configurada anteriormente com uma plataforma social, ela deverá ser exibida nesta página. Caso contrário, a página ficará vazia.
   ![integração com base em pessoas](assets/pbd-config.png)
2. Clique em **[!UICONTROL Add Account]**.
3. Use o menu suspenso **[!UICONTROL People-Based Platform]** para selecionar a plataforma com a qual deseja configurar a integração.
   ![plataforma baseada em pessoas](assets/pbd-add.png)
4. Clique em **[!UICONTROL Confirm]** para ser redirecionado para a página de autenticação da plataforma selecionada.
5. Depois de autenticar na conta da plataforma social, você é redirecionado para o Audience Manager, onde deve ver as contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique em **[!UICONTROL Confirm]**.
6. O Audience Manager exibe uma notificação na parte superior da página para que você saiba se a conta foi adicionada com êxito. A notificação também permite adicionar um endereço de email de contato para receber notificações quando a autenticação da plataforma social estiver prestes a expirar.

>[!IMPORTANT]
>
>O Audience Manager lida com a integração com plataformas sociais por meio de tokens de autenticação que expiram após um determinado período. Consulte Renovação de token de autenticação para obter detalhes sobre como renovar os tokens expirados.

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
1. Na seção **[!UICONTROL Segment Mappings]**, selecione os segmentos que deseja enviar para esse destino. Esses seriam os segmentos criados em [Etapa 4 - Criar segmentos de público-alvo](#create-audience-segments).
1. Salve o destino.
