---
description: 'Esta página inclui orientação passo a passo sobre como combinar dados de CRM offline com dados comportamentais em tempo real para usuários autenticados para criar segmentos do público-alvo e, em seguida, enviar esses segmentos do público para Destinos baseados em pessoas. '
seo-description: 'Esta página inclui orientação passo a passo sobre como combinar dados de CRM offline com dados comportamentais em tempo real para usuários autenticados para criar segmentos do público-alvo e, em seguida, enviar esses segmentos do público para Destinos baseados em pessoas.  '
seo-title: Fluxo de trabalho C - Personalização baseada em atividade autenticada combinada com dados offline
solution: Audience Manager
title: Fluxo de trabalho C - Personalização baseada em atividade autenticada combinada com dados offline
translation-type: tm+mt
source-git-commit: d0e343e3fbaf527e9b630dc2dbc851d8f8f4c0b2

---


# Fluxo de trabalho C - Personalização baseada em atividade autenticada combinada com dados offline {#workflow-c}

Esta página inclui orientação passo a passo sobre como combinar dados offline [!DNL CRM] com dados comportamentais em tempo real para usuários autenticados para criar segmentos do público-alvo e, em seguida, enviar estes segmentos do público para [!DNL People-Based Destinations].

## Etapa 1 - Configurar configurações de fonte de dados {#configure-data-source-settings}

Dependendo de suas [dpuuids](../../reference/ids-in-aam.md) serem em minúsculas, os endereços de email com hash talvez precisem configurar a fonte de dados que armazenará os endereços de email com hash.

 

**Cenário 1: suas[dpuuids](../../reference/ids-in-aam.md)são endereços de email com hash em minúsculas.**

Nesse caso, pule para [a Etapa 5 - Configurar autenticação de plataforma baseada em pessoas](#configure-authentication).

 

**Cenário 2: suas[dpuuids](../../reference/ids-in-aam.md)não são minúsculas e endereços de email com hash.**

Nesse caso, é necessário criar uma nova fonte de dados entre dispositivos que armazene seus endereços de email com hash. Veja como fazer isso:

1. Faça logon em sua conta do Audience Manager e vá **[!UICONTROL Audience Data]** para -&gt; **[!UICONTROL Data Sources]** e clique **[!UICONTROL Add New]** em.
1. Digite a **[!UICONTROL Name]** e **[!UICONTROL Description]** para a nova fonte de dados.
1. No menu **[!UICONTROL ID Type]** suspenso, selecione **[!UICONTROL Cross Device]**.
1. Na **[!UICONTROL Data Source Settings]** seção, selecione as opções **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** as opções e ative a **[!UICONTROL Share associated cross-device IDs in people-based destinations]** opção.
1. Use o menu suspenso para selecionar **[!UICONTROL Emails(SHA256, lowercased)]** o rótulo dessa fonte de dados.
   >[!IMPORTANT]
   >
   >Essa opção apenas rotula a fonte de dados como contendo os dados com hash do algoritmo específico. O Audience Manager não faz hash os dados nesta etapa. Verifique se os endereços de email que você planeja armazenar nessa fonte de dados já estão com hash com o [!DNL SHA256] algoritmo. Caso contrário, não será possível usá-lo [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consulte [Onboard](people-based-destinations-prerequisites.md#data-onboarding) de dados para perguntas frequentes sobre como colocar seus dados offline no Audience Manager para destinos baseados em pessoas.

## Etapa 2 - Usar IDs declaradas para corresponder dpuuids a endereços de email com hash por meio de chamadas HTTP em tempo real {#match-email-addresses}

Para qualificar usuários autenticados para características baseadas em regras, é necessário enviar a qualificação de característica por meio [de IDs declaradas](../declared-ids.md).

### Exemplo

Considere que você criou as duas fontes de dados a seguir.

| ID da fonte de dados | Conteúdo da fonte de dados |
| -------------- | -------------------------- |
| 999999 | Dpuuids existentes (IDs de CRM) |
| 987654 | Endereços de email com hash |

 

Em seguida, você deseja qualificar as IDs do CRM abaixo para a característica na tabela.

| DPUUID (ID de CRM) | Endereço de email | Endereço de email com hash | Características |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location = US |

 

A ID declarada deve seguir esta sintaxe:

`https://yourDomain.demdex.net/event?d_cid_ic=myHashedEmailDataSourceID%01myHashedEmail&d_cid_ic=myCrmDataSourceID%01myCRMID&key=value`

 

No exemplo acima, a chamada de ID declarada deve ser semelhante a:

`https://yourDomain.demdex.net/event?d_cid_ic=987654%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=999999%0168079982765673198504052656074456196039&location=US`

## Etapa 3 - Criar uma regra de mesclagem de perfil para segmentação {#create-profile-merge-rule-segmentation}

A próxima etapa está criando uma nova regra de mesclagem que ajudará a criar os segmentos do público-alvo para enviar para o seu [!DNL People-Based Destinations].

>[!IMPORTANT]
>
>Se você já tiver uma regra definida com as **[!UICONTROL Current Authenticated Profiles]****[!UICONTROL Last Authenticated Profiles]** opções, poderá pular para [a Etapa 4 - Criar segmentos de público-alvo](#create-audience-segments).

1. Faça logon em sua conta do Audience Manager e vá **[!UICONTROL Audience Data]** para -&gt; **[!UICONTROL Profile Merge Rules]**.
2. Clique em **[!UICONTROL Add New Rule]**.
3. Insira uma regra de mesclagem de perfil **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. Na **[!UICONTROL Profile Merge Rule Setup]** seção, selecione a **[!UICONTROL All Cross-Device Profiles]** regra na **[!UICONTROL Cross-Device Options]** lista.
5. Na **[!UICONTROL Cross-Device Profile Options]** lista, selecione as fontes de dados em que deseja executar a segmentação. Essas devem ser as fontes de dados que contêm suas dpuuids existentes.
   ![mesclar regras](assets/pbd-pmr-combined.png)

## Etapa 4 - Criar segmentos de público-alvo {#create-audience-segments}

Para criar novos segmentos, use o [Construtor de segmentos](../segments/segment-builder.md). Se você possui segmentos de público-alvo existentes que deseja enviar [!DNL People-Based Destinations], pule para [a Etapa 5 - Configurar autenticação de plataforma baseada em pessoas](#configure-authentication).

## Etapa 5 - Configurar autenticação de plataforma baseada em pessoas {#configure-authentication}

1. Faça logon em sua conta do Audience Manager e vá **[!UICONTROL Administration]** para &gt; **[!UICONTROL Integrated Accounts]**. Se você tiver uma integração configurada anteriormente com uma plataforma social, deverá vê-la listada nesta página. Caso contrário, a página ficará vazia.
   ![integração baseada em pessoas](assets/pbd-config.png)
2. Clique em **[!UICONTROL Add Account]**.
3. Use o **[!UICONTROL People-Based Platform]** menu suspenso para selecionar a plataforma com a qual você deseja configurar a integração.
   ![plataforma baseada em pessoas](assets/pbd-add.png)
4. Clique **[!UICONTROL Confirm]** para ser redirecionado para a página de autenticação da plataforma selecionada.
5. Após ter sido autenticado na conta da plataforma social, você será redirecionado para o Audience Manager onde você deverá visualizar suas contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique **[!UICONTROL Confirm]** em.
6. O Audience Manager exibe uma notificação na parte superior da página para informar se a conta foi adicionada com êxito. A notificação também permite que você adicione um endereço de email de contato para receber notificações quando a autenticação da plataforma social estiver prestes a expirar.

>[!IMPORTANT]
>
>Um Gerente de udience lida com a integração com plataformas sociais por meio de tokens de autenticação que expiram após um determinado período. Consulte Renovação do token de autenticação para obter detalhes sobre como renovar os tokens expirados.

## Etapa 6 - Criar um destino baseado em pessoas {#create-destination}

1. Faça logon em sua conta do Audience Manager, vá **[!UICONTROL Audience Data]** para &gt; **[!UICONTROL Destinations]** e clique **[!UICONTROL Create Destination]** em.
1. Na **[!UICONTROL Basic Information]** seção, digite a **[!UICONTROL Name]** e **[!UICONTROL Description]** para a nova fonte de dados e use as seguintes configurações:
   * **[!UICONTROL Category]**: Plataformas integradas;
   * **[!UICONTROL Type]**: Baseada em pessoas;
   * **[!UICONTROL Platform]**: selecione a plataforma baseada em pessoas para a qual você deseja enviar segmentos de público-alvo;
   * **[!UICONTROL Account]**: selecione a conta de anunciante desejada associada à plataforma selecionada.
      ![criar destino](assets/pbd-create-destination.png)
1. Clique em **[!UICONTROL Next]**.
1. Escolha o **[!UICONTROL Data Export Labels]** que deseja definir para este destino.
1. Na **[!UICONTROL Configuration]** seção, selecione a fonte de dados que contém suas fontes de dados com hash.
1. Na **[!UICONTROL Segment Mappings]** seção, selecione os segmentos que deseja enviar para esse destino. Esses seriam os segmentos criados na [Etapa 4 - Criar segmentos de público-alvo](#create-audience-segments).
1. Salve o destino.
