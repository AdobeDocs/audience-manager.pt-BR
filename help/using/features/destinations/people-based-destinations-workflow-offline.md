---
description: 'Esta página inclui orientações passo a passo sobre como criar segmentos de público-alvo a partir de dados de clientes somente offline e enviá-los para Destinos Baseados em Pessoas.  '
seo-description: 'Esta página inclui orientações passo a passo sobre como criar segmentos de público-alvo a partir de dados de clientes somente offline e enviá-los para Destinos Baseados em Pessoas.  '
seo-title: Fluxo de trabalho B - Personalização com base em dados somente offline
solution: Audience Manager
title: Fluxo de trabalho B - Personalização com base em dados somente offline
translation-type: tm+mt
source-git-commit: ad9c077f538759e195a83d47e0ef36ccffa25c7e

---


# Workflow B - Personalization Based on Offline-Only Data {#workflow-b}

>[!IMPORTANT]
>This article contains product documentation meant to guide you through the setup and usage of this feature. Nada aqui contido é aconselhamento jurídico. Please consult your own legal counsel for legal guidance.

This page includes step-by-step guidance on how to build audience segments from offline-only customer data, and send them to People-Based Destinations.

## Step 1 - Onboard Offline Traits {#step-1-onboard-traits}

The first step creating audience segments in this scenario is to bring your offline customer data into Audience Manager.

>[!IMPORTANT]
>
> Before continuing, make sure that the customer activity that you are about to onboard is already defined in Audience Manager with corresponding onboarded traits.[](../traits/trait-qualification-reference.md)

Regardless of whether your existing Audience Manager customer IDs (DPUUIDs) are hashed emails or not, you must perform the trait onboarding against the data source that contains your DPUUIDs.[](../../reference/ids-in-aam.md)[](../../reference/ids-in-aam.md)

### Exemplo

You want to qualify the customer IDs from the table below for the corresponding onboarded trait IDs. Let's consider that your DPUUIDs are stored in a data source with the ID 999999, and your Audience Manager Partner ID is 123.[](../../reference/ids-in-aam.md)

| ID do cliente (DPUUID) | Onboarded Trait ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />
Para qualificar as IDs do cliente no exemplo acima para as características integradas correspondentes, faça upload de um [arquivo de dados de entrada](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) com o seguinte conteúdo:

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

O nome do arquivo seria semelhante a: `ftp_dpm_999999_123_TIMESTAMP.sync.gz`.
Consulte Requisitos de nome e tamanho de arquivo do [Amazon S3 para arquivos](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) de dados de entrada para obter informações detalhadas sobre a estrutura do nome do arquivo.

## Etapa 2 - Definir configurações da fonte de dados {#configure-data-source-settings}

Dependendo de seus [DPUUIDs](../../reference/ids-in-aam.md) serem endereços de email com hash e minúsculas, talvez seja necessário configurar a fonte de dados que armazenará os endereços de email com hash.

 

**Scenario 1: your DPUUIDs are already lowercase, hashed email addresses.[](../../reference/ids-in-aam.md)**

In this case, you need to need to label the corresponding data source as such:

1. Vá para **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**.
1. Find the data source that contains your DPUUIDs, and click it.[](../../reference/ids-in-aam.md)
1. Verifique se a opção **[!UICONTROL Cannot be tied to personally identifiable information]** está desmarcada.
1. Salve as configurações da fonte de dados.

 

**Cenário 2: seus[DPUUIDs](../../reference/ids-in-aam.md)não são endereços de email com hash em minúsculas.**

Nesse caso, é necessário criar uma nova fonte de dados entre dispositivos que armazene seus endereços de email com hash. Veja como fazer isso:

1. Faça logon em sua conta do Audience Manager, vá para **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]** e clique em **[!UICONTROL Add New]**.
1. Insira um **[!UICONTROL Name]** e **[!UICONTROL Description]** para sua nova fonte de dados.
1. No menu **[!UICONTROL ID Type]** suspenso, selecione **[!UICONTROL Cross Device]**.
1. Na **[!UICONTROL Data Source Settings]** seção, selecione as opções **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e ative a **[!UICONTROL Share associated cross-device IDs in people-based destinations]** .
1. Use o menu suspenso para selecionar o **[!UICONTROL Emails(SHA256, lowercased)]** rótulo dessa fonte de dados.
   >[!IMPORTANT]
   >
   >Essa opção rotula somente a fonte de dados como contendo dados com hash com esse algoritmo específico. O Audience Manager não hash os dados nesta etapa. Verifique se os endereços de email que você planeja armazenar nessa fonte de dados já estão com hash com o [!DNL SHA256] algoritmo. Caso contrário, você não poderá usá-lo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > See Data Onboarding for frequently asked questions about how you should bring your offline data into Audience Manager for People-Based Destinations.[](people-based-destinations-prerequisites.md#data-onboarding)

## Etapa 3 - Corresponder DPUUIDs a endereços de email com hash via sincronização de ID baseada em arquivo {#match-ids-emails}

>[!IMPORTANT]
>
> Esta etapa se aplica somente ao [Cenário 2](people-based-destinations-workflow-offline.md#configure-data-source-settings) descrito acima. Se seus [DPUUIDs](../../reference/ids-in-aam.md) existentes já tiverem endereços de email com hash, pule para a [Etapa 4 - Criar uma regra de mesclagem de perfil para segmentação](#create-profile-merge-rule).

Digamos que você queira corresponder seus [DPUUIDs](../../reference/ids-in-aam.md) existentes do exemplo na Etapa 1 aos endereços de email com hash da tabela abaixo (coluna direita) e armazenar os endereços de email com hash na nova fonte de dados criada na [Etapa 2 - Definir configurações](#configure-data-source-settings)da fonte de dados.

Como lembrete, agora você tem duas fontes de dados:

| ID da fonte de dados | Conteúdo da fonte de dados |
| -------------- | -------------------------- |
| 999999 | Existing DPUUIDs (CRM IDs) |
| 987654 | Endereços de email em hash |

| DPUUIDs (CRM IDs) | Endereço de email | Hashed email address |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

In our example, your ID synchronization file would have the following contents:[](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

The ID synchronization file must follow this naming structure:[](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

In the example above, the file name would look like this:
`c2c_id_999999_987654_1560431657.sync`

[Download example file here.](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync)

Once you've created your ID synchronization file, you need to upload it to an  bucket. [!DNL Amazon S3] To learn how to upload ID synchronization files, see Send Batch Data to Audience Manager.[](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)

## Etapa 4 - Criar uma regra de mesclagem de perfil para segmentação {#create-profile-merge-rule}

The next step is creating a new merge rule that will help you create the audience segments to send to your .[!DNL People-Based Destinations]

1. Log in to your Audience Manager account and go to  -&gt; .**[!UICONTROL Audience Data]****[!UICONTROL Profile Merge Rules]**
2. Clique em [!UICONTROL Add New Rule].
3. Insira uma regra de mesclagem de perfil **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. Na **[!UICONTROL Profile Merge Rule Setup]** seção, selecione a **[!UICONTROL All Cross-Device Profiles]** regra na **[!UICONTROL Cross-Device Options]** lista.
5. Na **[!UICONTROL Cross-Device Profile Options]** lista, selecione a fonte de dados em que suas características estão integradas.
   ![merge-rule-setup](assets/pbd-pmr.png)

## Etapa 5 - Criar segmentos de público-alvo {#create-audience-segments}

Para criar novos segmentos a partir de dados somente offline, use o Construtor [de](../segments/segment-builder.md) segmentos e certifique-se de usar a nova regra de mesclagem de perfil criada na etapa anterior ao criar o segmento.

## Step 6 - Configure People-Based Platform Authentication {#configure-authentication}

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
>O Audience Manager lida com a integração com plataformas sociais por meio de tokens de autenticação que expiram após um determinado período de tempo. Consulte Renovação de token de autenticação para obter detalhes sobre como renovar os tokens expirados.

## Step 7 - Create a People-Based Destination {#create-destination}

1. Faça logon em sua conta do Audience Manager, vá para **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** e clique em **[!UICONTROL Create Destination]**.
1. Na **[!UICONTROL Basic Information]** seção, digite um **[!UICONTROL Name]** e **[!UICONTROL Description]** para sua nova fonte de dados e use as seguintes configurações:
   * **[!UICONTROL Category]**: Plataformas integradas;
   * **[!UICONTROL Type]**: Baseado em pessoas;
   * **[!UICONTROL Platform]**: selecione a plataforma baseada em pessoas para a qual deseja enviar segmentos de público-alvo;
   * **[!UICONTROL Account]**: selecione a conta do anunciante desejada associada à plataforma selecionada.
      ![create-target](assets/pbd-create-destination.png)
1. Clique em **[!UICONTROL Next]**.
1. Escolha o destino **[!UICONTROL Data Export Labels]** que deseja definir.
1. Na **[!UICONTROL Configuration]** seção, selecione a fonte de dados que contém suas fontes de dados com hash.
1. Na **[!UICONTROL Segment Mappings]** seção, selecione os segmentos que deseja enviar para esse destino. This would be the segments that you created at Step 5 - Create Audience Segments.[](people-based-destinations-workflow-offline.md#create-audience-segments)
1. Save the destination.
