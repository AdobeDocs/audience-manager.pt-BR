---
description: Esta página inclui orientação passo a passo sobre como combinar dados do CRM offline com dados comportamentais em tempo real para usuários autenticados criarem segmentos de público-alvo e, em seguida, enviar esses segmentos de público-alvo para Destinos com base em pessoas.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with real-time behavioral data for authenticated users to create audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow C - Personalization Based on Authenticated Activity Combined with Offline Data
solution: Audience Manager
title: Fluxo de trabalho C - Personalization com base na Atividade autenticada combinada com dados offline
feature: People-based Destinations
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 1%

---

# Fluxo de trabalho C - Personalization com base na Atividade autenticada combinada com dados offline {#workflow-c}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e pelo uso desse recurso. Nada contido aqui é aconselhamento jurídico. Consulte seu próprio serviço jurídico para obter orientação jurídica.

Esta página inclui orientação passo a passo sobre como combinar dados do [!DNL CRM] offline com dados comportamentais em tempo real para usuários autenticados criarem segmentos de público-alvo e, em seguida, enviar esses segmentos de público-alvo para o [!DNL People-Based Destinations].

## Etapa 1 - Definir configurações do Data Source {#configure-data-source-settings}

Se os [DPUUIDs](../../reference/ids-in-aam.md) forem endereços de email com hash e em letras minúsculas, talvez seja necessário configurar a fonte de dados que armazenará os endereços de email com hash.

 

**Cenário 1: seus [DPUUIDs](../../reference/ids-in-aam.md) já são endereços de email com hash e minúsculas.**

Neste caso, pule para [Etapa 5 - Configurar a Autenticação da Plataforma Baseada em Pessoas](#configure-authentication).

 

**Cenário 2: seus [DPUUIDs](../../reference/ids-in-aam.md) não são endereços de email com hash e em minúsculas.**

Nesse caso, você precisa criar uma nova fonte de dados entre dispositivos que armazenará seus endereços de email com hash. Veja como fazer isso:

1. Faça logon em sua conta da Audience Manager, vá para **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** e clique em **[!UICONTROL Add New]**.
1. Insira um **[!UICONTROL Name]** e **[!UICONTROL Description]** para sua nova fonte de dados.
1. No menu suspenso **[!UICONTROL ID Type]**, selecione **[!UICONTROL Cross Device]**.
1. Na seção **[!UICONTROL Data Source Settings]**, selecione as opções **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e habilite a opção **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Use o menu suspenso para selecionar o rótulo **[!UICONTROL Emails(SHA256, lowercased)]** para esta fonte de dados.
   >[!IMPORTANT]
   >
   >Essa opção rotula apenas a fonte de dados como contendo dados com hash com esse algoritmo específico. A Audience Manager não faz o hash dos dados nesta etapa. Verifique se os endereços de email que você planeja armazenar nesta fonte de dados já foram atribuídos a hash com o algoritmo [!DNL SHA256]. Caso contrário, você não poderá usá-lo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consulte [Integração de dados](people-based-destinations-prerequisites.md#data-onboarding) para perguntas frequentes sobre como você deve trazer seus dados offline para o Audience Manager for People-Based Destinations.

Assista ao vídeo abaixo para obter um tutorial em vídeo sobre como criar uma fonte de dados para [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Etapa 2 - Usar IDs declaradas para corresponder DPUUIDs a endereços de email com hash por meio de chamadas HTTP em tempo real {#match-email-addresses}

Para qualificar usuários autenticados para características baseadas em regras, você precisa enviar a qualificação de característica por meio de [IDs declaradas](../declared-ids.md).

### Exemplo

Digamos que você tenha criado as duas fontes de dados a seguir.

| ID da fonte de dados | Conteúdo da fonte de dados |
| -------------- | -------------------------- |
| 999999 | DPUUIDs existentes (IDs de CRM) |
| 987654 | Endereços de email com hash |

 

Em seguida, qualifique as IDs do CRM abaixo para a característica na tabela.

| DPUUID (ID DE CRM) | Endereço de email | Endereço de email com hash | Características |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | local = EUA |

 

Sua ID declarada deve seguir esta sintaxe:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

No exemplo acima, a chamada de ID declarada deve ter esta aparência:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Etapa 3 - Criar uma regra de mesclagem de perfis para segmentação {#create-profile-merge-rule-segmentation}

A próxima etapa é criar uma nova regra de mesclagem que ajudará você a criar os segmentos de público-alvo para enviar ao seu [!DNL People-Based Destinations].

>[!IMPORTANT]
>
>Se você já tiver uma regra definida com as opções **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**, pule para [Etapa 4 - Criar segmentos de público-alvo](#create-audience-segments).

1. Faça logon em sua conta da Audience Manager e vá para **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Clique em **[!UICONTROL Add New Rule]**.
3. Insira uma regra de mesclagem de perfis **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. Na seção **[!UICONTROL Profile Merge Rule Setup]**, selecione a regra **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]** na lista **[!UICONTROL Cross-Device Options]**.
5. Na lista **[!UICONTROL Cross-Device Profile Options]**, selecione as fontes de dados nas quais deseja executar a segmentação. Essas devem ser as fontes de dados que contêm seus DPUUIDs existentes.
   ![configuração-regra-mesclagem](assets/pbd-pmr-combined.png)

## Etapa 4 - Criar segmentos de público {#create-audience-segments}

Para criar novos segmentos, use o [Construtor de segmentos](../segments/segment-builder.md). Se você tiver segmentos de público-alvo existentes que deseja enviar para [!DNL People-Based Destinations], pule para [Etapa 5 - Configurar a Autenticação da Plataforma com Base em Pessoas](#configure-authentication).

## Etapa 5 - Configurar a autenticação da plataforma baseada em pessoas {#configure-authentication}

1. Faça logon em sua conta do Audience Manager e vá para **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se você tiver uma integração configurada anteriormente com uma plataforma social, deverá vê-la listada nesta página. Caso contrário, a página ficará vazia.
   ![integração baseada em pessoas](assets/pbd-config.png)
2. Clique em **[!UICONTROL Add Account]**.
3. Use o menu suspenso **[!UICONTROL People-Based Platform]** para selecionar a plataforma com a qual deseja configurar a integração.
   ![plataforma baseada em pessoas](assets/pbd-add.png)
4. Clique em **[!UICONTROL Confirm]** para ser redirecionado para a página de autenticação da plataforma selecionada.
5. Depois de autenticar em sua conta da plataforma social, você é redirecionado para o Audience Manager, onde deve ver suas contas de anunciante associadas. Selecione a conta de anunciante que deseja usar e clique em **[!UICONTROL Confirm]**.
6. O Audience Manager exibe uma notificação na parte superior da página para que você saiba se a conta foi adicionada com êxito. A notificação também permite adicionar um endereço de email de contato para receber notificações quando a autenticação da plataforma social estiver prestes a expirar.

>[!IMPORTANT]
>
>O Audience Manager lida com a integração com plataformas sociais por meio de tokens de autenticação que expiram após um determinado período. Consulte Renovação do token de autenticação para obter detalhes sobre como renovar os tokens expirados.

## Etapa 6 - Criar um destino com base em pessoas {#create-destination}

1. Faça logon em sua conta do Audience Manager, vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** e clique em **[!UICONTROL Create Destination]**.
1. Na seção **[!UICONTROL Basic Information]**, insira um **[!UICONTROL Name]** e **[!UICONTROL Description]** para sua nova fonte de dados e use as seguintes configurações:
   * **[!UICONTROL Category]**: Plataformas Integradas;
   * **[!UICONTROL Type]**: Baseado Em Pessoas;
   * **[!UICONTROL Platform]**: selecione a plataforma com base em pessoas para a qual você deseja enviar segmentos de público-alvo;
   * **[!UICONTROL Account]**: selecione a conta de anunciante desejada associada à plataforma selecionada.
     ![criar-destino](assets/pbd-create-destination.png)
1. Clique em **[!UICONTROL Next]**.
1. Escolha o **[!UICONTROL Data Export Labels]** que deseja definir para este destino.
1. Na seção **[!UICONTROL Configuration]**, selecione a fonte de dados que contém suas fontes de dados com hash.
1. Na seção **[!UICONTROL Segment Mappings]**, selecione os segmentos que deseja enviar para esse destino. Estes são os segmentos que você criou em [Etapa 4 - Criar segmentos de público-alvo](#create-audience-segments).
1. Salve o destino.
