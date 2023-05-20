---
description: Esta página inclui orientação passo a passo sobre como combinar dados do CRM offline com dados comportamentais em tempo real para usuários autenticados criarem segmentos de público-alvo e, em seguida, enviar esses segmentos de público-alvo para Destinos com base em pessoas.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with real-time behavioral data for authenticated users to create audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow C - Personalization Based on Authenticated Activity Combined with Offline Data
solution: Audience Manager
title: Fluxo de trabalho C - Personalização baseada na Atividade autenticada combinada com dados offline
feature: People-based Destinations
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 5%

---

# Fluxo de trabalho C - Personalização baseada na Atividade autenticada combinada com dados offline {#workflow-c}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e pelo uso desse recurso. Nada contido aqui é aconselhamento jurídico. Consulte seu próprio serviço jurídico para obter orientação jurídica.

Esta página inclui orientação passo a passo sobre como combinar offline [!DNL CRM] dados com dados comportamentais em tempo real para usuários autenticados criarem segmentos de público-alvo, em seguida, enviar esses segmentos de público para [!DNL People-Based Destinations].

## Etapa 1 - Definir configurações da fonte de dados {#configure-data-source-settings}

Dependendo se o seu [DPUUIDs](../../reference/ids-in-aam.md) são endereços de email com hash e em letras minúsculas, talvez seja necessário configurar a fonte de dados que armazenará os endereços de email com hash.

 

**Cenário 1: seu [DPUUIDs](../../reference/ids-in-aam.md) já são endereços de email em letras minúsculas e com hash.**

Nesse caso, pule para [Etapa 5 - Configurar a autenticação da plataforma baseada em pessoas](#configure-authentication).

 

**Cenário 2: seu [DPUUIDs](../../reference/ids-in-aam.md) não são endereços de email em letras minúsculas e com hash.**

Nesse caso, você precisa criar uma nova fonte de dados entre dispositivos que armazenará seus endereços de email com hash. Veja como fazer isso:

1. Faça logon na sua conta Audience Manager e acesse **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** e clique em **[!UICONTROL Add New]**.
1. Insira um **[!UICONTROL Name]** e **[!UICONTROL Description]** para sua nova fonte de dados.
1. No **[!UICONTROL ID Type]** selecione **[!UICONTROL Cross Device]**.
1. No **[!UICONTROL Data Source Settings]** selecione a opção **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e habilite a opção **[!UICONTROL Share associated cross-device IDs in people-based destinations]** opção.
1. Use o menu suspenso para selecionar o **[!UICONTROL Emails(SHA256, lowercased)]** rótulo para esta fonte de dados.
   >[!IMPORTANT]
   >
   >Essa opção rotula apenas a fonte de dados como contendo dados com hash com esse algoritmo específico. O Audience Manager não faz o hash dos dados nesta etapa. Verifique se os endereços de email que você planeja armazenar nessa fonte de dados já estão com o hash [!DNL SHA256] algoritmo. Caso contrário, você não poderá usá-lo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consulte [Integração de dados](people-based-destinations-prerequisites.md#data-onboarding) para perguntas frequentes sobre como você deve trazer seus dados offline para o Audience Manager para destinos com base em pessoas.

Assista ao vídeo abaixo para obter um tutorial em vídeo sobre como criar uma fonte de dados para o [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Etapa 2 - Usar IDs declaradas para corresponder DPUUIDs a endereços de email com hash por meio de chamadas HTTP em tempo real {#match-email-addresses}

Para qualificar usuários autenticados para características baseadas em regras, é necessário enviar a qualificação de característica por meio do [IDs declaradas](../declared-ids.md).

### Exemplo

Digamos que você tenha criado as duas fontes de dados a seguir.

| ID da fonte de dados | Conteúdo da fonte de dados |
| -------------- | -------------------------- |
| 999999 | DPUUIDs existentes (IDs de CRM) |
| 987654 | Endereços de email com hash |

 

Em seguida, qualifique as IDs do CRM abaixo para a característica na tabela.

| DPUUID (ID DE CRM) | Seu endereço de email | Endereço de email com hash | Característica |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | local = EUA |

 

Sua ID declarada deve seguir esta sintaxe:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

No exemplo acima, a chamada de ID declarada deve ter esta aparência:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Etapa 3 - Criar uma regra de mesclagem de perfis para segmentação {#create-profile-merge-rule-segmentation}

A próxima etapa é criar uma nova regra de mesclagem que ajudará você a criar os segmentos de público-alvo a serem enviados para o seu [!DNL People-Based Destinations].

>[!IMPORTANT]
>
>Se você já tiver uma regra definida com o **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]** opções, você pode pular para [Etapa 4 - Criar segmentos de público](#create-audience-segments).

1. Faça logon na sua conta Audience Manager e acesse **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Clique em **[!UICONTROL Add New Rule]**.
3. Inserir uma regra de mesclagem de perfis **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. No **[!UICONTROL Profile Merge Rule Setup]** , selecione a **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]** regra do **[!UICONTROL Cross-Device Options]** lista.
5. No **[!UICONTROL Cross-Device Profile Options]** selecione as fontes de dados nas quais deseja executar a segmentação. Essas devem ser as fontes de dados que contêm seus DPUUIDs existentes.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Etapa 4 - Criar segmentos de público {#create-audience-segments}

Para criar novos segmentos, use o [Construtor de segmentos](../segments/segment-builder.md). Se você tiver segmentos de público-alvo existentes para os quais deseja enviar [!DNL People-Based Destinations], saltar para [Etapa 5 - Configurar a autenticação da plataforma baseada em pessoas](#configure-authentication).

## Etapa 5 - Configurar a autenticação da plataforma baseada em pessoas {#configure-authentication}

1. Faça logon na sua conta Audience Manager e acesse **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se você tiver uma integração configurada anteriormente com uma plataforma social, deverá vê-la listada nesta página. Caso contrário, a página ficará vazia.
   ![integração baseada em pessoas](assets/pbd-config.png)
2. Clique em **[!UICONTROL Add Account]**.
3. Use o **[!UICONTROL People-Based Platform]** para selecionar a plataforma com a qual deseja configurar a integração.
   ![plataforma baseada em pessoas](assets/pbd-add.png)
4. Clique em **[!UICONTROL Confirm]** para ser redirecionado à página de autenticação da plataforma selecionada.
5. Depois de autenticar em sua conta da plataforma social, você é redirecionado para o Audience Manager, onde deve ver suas contas de anunciante associadas. Selecione a conta de anunciante que deseja usar e clique em **[!UICONTROL Confirm]**.
6. O Audience Manager exibe uma notificação na parte superior da página para que você saiba se a conta foi adicionada com êxito. A notificação também permite adicionar um endereço de email de contato para receber notificações quando a autenticação da plataforma social estiver prestes a expirar.

>[!IMPORTANT]
>
>O Audience Manager lida com a integração com plataformas sociais por meio de tokens de autenticação que expiram após um determinado período. Consulte Renovação do token de autenticação para obter detalhes sobre como renovar os tokens expirados.

## Etapa 6 - Criar um destino com base em pessoas {#create-destination}

1. Faça logon em sua conta Audience Manager, acesse **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** e clique em **[!UICONTROL Create Destination]**.
1. No **[!UICONTROL Basic Information]** , insira um **[!UICONTROL Name]** e **[!UICONTROL Description]** para sua nova fonte de dados e use as seguintes configurações:
   * **[!UICONTROL Category]**: plataformas integradas;
   * **[!UICONTROL Type]**: Com Base Em Pessoas;
   * **[!UICONTROL Platform]**: selecione a plataforma com base em pessoas para a qual você deseja enviar segmentos de público-alvo;
   * **[!UICONTROL Account]**: selecione a conta de anunciante desejada associada à plataforma selecionada.
      ![create-destination](assets/pbd-create-destination.png)
1. Clique em **[!UICONTROL Next]**.
1. Escolha o **[!UICONTROL Data Export Labels]** que deseja definir para este destino.
1. No **[!UICONTROL Configuration]** selecione a fonte de dados que contém suas fontes de dados com hash.
1. No **[!UICONTROL Segment Mappings]** selecione os segmentos que deseja enviar para esse destino. Esses seriam os segmentos criados em [Etapa 4 - Criar segmentos de público](#create-audience-segments).
1. Salve o destino.
