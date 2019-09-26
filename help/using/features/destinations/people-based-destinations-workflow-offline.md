---
description: 'Esta página inclui orientações passo a passo sobre como criar segmentos de público-alvo a partir de dados de clientes somente offline e enviá-los para Destinos Baseados em Pessoas.  '
seo-description: 'Esta página inclui orientações passo a passo sobre como criar segmentos de público-alvo a partir de dados de clientes somente offline e enviá-los para Destinos Baseados em Pessoas.  '
seo-title: Fluxo de trabalho B - Personalização com base em dados somente offline
solution: Audience Manager
title: Fluxo de trabalho B - Personalização com base em dados somente offline
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# Fluxo de trabalho B - Personalização com base em dados somente offline {#workflow-b}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a guiá-lo pela configuração e uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

This page includes step-by-step guidance on how to build audience segments from offline-only customer data, and send them to People-Based Destinations.

## Etapa 1 - Características off-line integradas {#step-1-onboard-traits}

A primeira etapa para criar segmentos de público-alvo neste cenário é trazer seus dados de cliente offline para o Audience Manager.

>[!IMPORTANT]
>
> Antes de continuar, verifique se a atividade do cliente que você está prestes a integrar já está definida no Audience Manager com as características [integradas correspondentes](../traits/trait-qualification-reference.md).

Independentemente de suas IDs de cliente ([DPUUIDs](../../reference/ids-in-aam.md)) existentes do Audience Manager serem ou não emails com hash, você deve executar a característica de integração em relação à fonte de dados que contém seus [DPUUIDs](../../reference/ids-in-aam.md).

### Exemplo

Você deseja qualificar as IDs do cliente da tabela abaixo para as IDs de características integradas correspondentes. Considere que seus [DPUUIDs](../../reference/ids-in-aam.md) são armazenados em uma fonte de dados com a ID 999999, e sua ID de parceiro do Audience Manager é 123.

| ID do cliente (DPUUID) | ID de característica integrada |
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

 

**Scenario 1: your[DPUUIDs](../../reference/ids-in-aam.md)are already lowercase, hashed email addresses.**

Nesse caso, é necessário rotular a fonte de dados correspondente como tal:

1. Go to  -&gt; .**[!UICONTROL Audience Data]****[!UICONTROL Data Sources]**
1. Find the data source that contains your DPUUIDs, and click it.[](../../reference/ids-in-aam.md)
1. Make sure the option  is unchecked.**[!UICONTROL Cannot be tied to personally identifiable information]**
1. Save the data source settings.

 

**Scenario 2: your DPUUIDs are not lowercase, hashed email addresses.[](../../reference/ids-in-aam.md)**

In this case, you need to create a new cross-device data source that will store your hashed email addresses. Here's how to do this:

1. Log in to your Audience Manager account and go to  -&gt; , and click .**[!UICONTROL Audience Data]****[!UICONTROL Data Sources]****[!UICONTROL Add New]**
1. Enter a  and  for your new data source.**[!UICONTROL Name]****[!UICONTROL Description]**
1. In the  drop-down menu, select .**[!UICONTROL ID Type]****[!UICONTROL Cross Device]**
1. In the  section, select both the  and  options, and enable the  option.**[!UICONTROL Data Source Settings]****[!UICONTROL Inbound]****[!UICONTROL Outbound]****[!UICONTROL Share associated cross-device IDs in people-based destinations]**
1. Use o menu suspenso para selecionar o **[!UICONTROL Emails(SHA256, lowercased)]** rótulo dessa fonte de dados.
   >[!IMPORTANT]
   >
   >This option only labels the data source as containing data hashed with that specific algorithm. Audience Manager does not hash the data at this step. Verifique se os endereços de email que você planeja armazenar nessa fonte de dados já estão com hash com o [!DNL SHA256] algoritmo. Caso contrário, você não poderá usá-lo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consulte Integração de [dados](people-based-destinations-prerequisites.md#data-onboarding) para obter perguntas frequentes sobre como você deve colocar seus dados offline no Audience Manager para destinos baseados em pessoas.

## Etapa 3 - Corresponder DPUUIDs a endereços de email com hash via sincronização de ID baseada em arquivo {#match-ids-emails}

>[!IMPORTANT]
>
> Esta etapa se aplica somente ao [Cenário 2](people-based-destinations-workflow-offline.md#configure-data-source-settings) descrito acima. Se seus [DPUUIDs](../../reference/ids-in-aam.md) existentes já tiverem endereços de email com hash, pule para a [Etapa 4 - Criar uma regra de mesclagem de perfil para segmentação](#create-profile-merge-rule).

Digamos que você queira corresponder seus [DPUUIDs](../../reference/ids-in-aam.md) existentes do exemplo na Etapa 1 aos endereços de email com hash da tabela abaixo (coluna direita) e armazenar os endereços de email com hash na nova fonte de dados criada na [Etapa 2 - Definir configurações](#configure-data-source-settings)da fonte de dados.

Como lembrete, agora você tem duas fontes de dados:

| ID da fonte de dados | Conteúdo da fonte de dados |
| -------------- | -------------------------- |
| 999999 | DPUUIDs existentes (IDs CRM) |
| 987654 | Endereços de email em hash |

| DPUUIDs (CRM IDs) | Endereço de email | Endereço de email com hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

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

## Etapa 4 - Criar uma regra de mesclagem de perfil para segmentação {#create-profile-merge-rule}

A próxima etapa é criar uma nova regra de mesclagem que ajudará a criar os segmentos de público-alvo a serem enviados para o seu site [!DNL People-Based Destinations].

1. Faça logon em sua conta do Audience Manager e vá para **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Profile Merge Rules]**.
2. Clique em [!UICONTROL Add New Rule].
3. Insira uma regra de mesclagem de perfil **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. Na **[!UICONTROL Profile Merge Rule Setup]** seção, selecione a **[!UICONTROL All Cross-Device Profiles]** regra na **[!UICONTROL Cross-Device Options]** lista.
5. Na **[!UICONTROL Cross-Device Profile Options]** lista, selecione a fonte de dados em que suas características estão integradas.
   ![merge-rule-setup](assets/pbd-pmr.png)

## Etapa 5 - Criar segmentos de público-alvo {#create-audience-segments}

Para criar novos segmentos a partir de dados somente offline, use o Construtor [de](../segments/segment-builder.md) segmentos e certifique-se de usar a nova regra de mesclagem de perfil criada na etapa anterior ao criar o segmento.

## Etapa 6 - Configurar a autenticação de plataforma baseada em pessoas {#configure-authentication}

1. Log in to your Audience Manager account and go to  &gt; . **[!UICONTROL Administration]****[!UICONTROL Integrated Accounts]** If you have a previously configured integration with a social platform, you should see it listed in this page. Otherwise, the page is empty.
   ![people-based-integration](assets/pbd-config.png)
1. Clique em **[!UICONTROL Add Account]**.
1. Use the  drop-down menu to select the platform that you want to configure the integration with.**[!UICONTROL People-Based Platform]**
   ![people-based-platform](assets/pbd-add.png)
1. Click  to be redirected to the authentication page of the selected platform.**[!UICONTROL Confirm]**
1. Once you've authenticated to your social platform account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click .**[!UICONTROL Confirm]**
1. Audience Manager displays a notification at the top of the page to let you know whether the account was successfully added. The notification also allows you to add a contact email address to receive notifications when the social platform authentication is about to expire.

>[!IMPORTANT]
>
>A udience Manager handles the integration with social platforms through authentication tokens that expire after a certain amount of time. Consulte Renovação de token de autenticação para obter detalhes sobre como renovar os tokens expirados.

## Step 7 - Create a People-Based Destination {#create-destination}

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
1. Na **[!UICONTROL Segment Mappings]** seção, selecione os segmentos que deseja enviar para esse destino. Esses seriam os segmentos criados na [Etapa 5 - Criar segmentos](people-based-destinations-workflow-offline.md#create-audience-segments)de público-alvo.
1. Salve o destino.
