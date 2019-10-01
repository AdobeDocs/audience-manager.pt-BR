---
description: 'Esta página inclui orientações passo a passo sobre como criar segmentos de público-alvo a partir de dados de clientes somente offline e enviá-los para Destinos Baseados em Pessoas.  '
seo-description: 'Esta página inclui orientações passo a passo sobre como criar segmentos de público-alvo a partir de dados de clientes somente offline e enviá-los para Destinos Baseados em Pessoas.  '
seo-title: Fluxo de trabalho B - Personalização com base em dados somente offline
solution: Audience Manager
title: Fluxo de trabalho B - Personalização com base em dados somente offline
translation-type: tm+mt
source-git-commit: fb5d9eff3573048d3e8a570b342a97bce3cd8da0

---


# Fluxo de trabalho B - Personalização com base em dados somente offline {#workflow-b}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a guiá-lo pela configuração e uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

Esta página inclui orientações passo a passo sobre como criar segmentos de público-alvo a partir de dados de clientes somente offline e enviá-los para Destinos Baseados em Pessoas.

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

 

**Cenário 1: seus[DPUUIDs](../../reference/ids-in-aam.md)já têm endereços de email com hash em minúsculas.**

Nesse caso, é necessário rotular a fonte de dados correspondente como tal:

1. Vá para **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**.
1. Localize a fonte de dados que contém seus [DPUUIDs](../../reference/ids-in-aam.md)e clique nela.
1. Verifique se a opção **[!UICONTROL Cannot be tied to personally identifiable information]** está desmarcada.
1. Salve as configurações da fonte de dados.

 

**Scenario 2: your DPUUIDs are not lowercase, hashed email addresses.[](../../reference/ids-in-aam.md)**

In this case, you need to create a new cross-device data source that will store your hashed email addresses. Veja como fazer isso:

1. Faça logon em sua conta do Audience Manager, vá para **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]** e clique em **[!UICONTROL Add New]**.
1. Enter a  and  for your new data source.**[!UICONTROL Name]****[!UICONTROL Description]**
1. In the  drop-down menu, select .**[!UICONTROL ID Type]****[!UICONTROL Cross Device]**
1. In the  section, select both the  and  options, and enable the  option.**[!UICONTROL Data Source Settings]****[!UICONTROL Inbound]****[!UICONTROL Outbound]****[!UICONTROL Share associated cross-device IDs in people-based destinations]**
1. Use the drop-down menu to select the **[!UICONTROL Emails(SHA256, lowercased)]** label for this data source.
   >[!IMPORTANT]
   >
   >This option only labels the data source as containing data hashed with that specific algorithm. Audience Manager does not hash the data at this step. Make sure the email addresses that you plan on storing in this data source are already hashed with the [!DNL SHA256] algorithm. Otherwise, you won't be able to use it for [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > See [Data Onboarding](people-based-destinations-prerequisites.md#data-onboarding) for frequently asked questions about how you should bring your offline data into Audience Manager for People-Based Destinations.

## Step 3 - Match DPUUIDs to Hashed Email Addresses via File-Based ID Synchronization {#match-ids-emails}

>[!IMPORTANT]
>
> This step only applies to [Scenario 2](people-based-destinations-workflow-offline.md#configure-data-source-settings) described above. Se seus [DPUUIDs](../../reference/ids-in-aam.md) existentes já tiverem endereços de email com hash, pule para a [Etapa 4 - Criar uma regra de mesclagem de perfil para segmentação](#create-profile-merge-rule).

Let's say you want to match your existing DPUUIDs from the example at Step 1 to the hashed email addresses from the table below (right column), and store the hashed email addresses in the new data source that you created at Step 2 - Configure Data Source Settings.[](../../reference/ids-in-aam.md)[](#configure-data-source-settings)

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

 

Em nosso exemplo, seu arquivo [de sincronização de](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ID teria o seguinte conteúdo:

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

## Step 4 - Create a Profile Merge Rule for Segmentation {#create-profile-merge-rule}

A próxima etapa é criar uma nova regra de mesclagem que ajudará a criar os segmentos de público-alvo a serem enviados para o seu site [!DNL People-Based Destinations].

1. Log in to your Audience Manager account and go to  -&gt; .**[!UICONTROL Audience Data]****[!UICONTROL Profile Merge Rules]**
2. Clique em [!UICONTROL Add New Rule].
3. Insira uma regra de mesclagem de perfil **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. In the  section, select the  rule from the  list.**[!UICONTROL Profile Merge Rule Setup]****[!UICONTROL All Cross-Device Profiles]****[!UICONTROL Cross-Device Options]**
5. In the  list, select the data source that your traits are onboarded against.**[!UICONTROL Cross-Device Profile Options]**
   ![merge-rule-setup](assets/pbd-pmr.png)

## Etapa 5 - Criar segmentos de público-alvo {#create-audience-segments}

Para criar novos segmentos a partir de dados somente offline, use o Construtor [de](../segments/segment-builder.md) segmentos e certifique-se de usar a nova regra de mesclagem de perfil criada na etapa anterior ao criar o segmento.

## Etapa 6 - Configurar a autenticação de plataforma baseada em pessoas {#configure-authentication}

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

## Etapa 7 - Criar um destino baseado em pessoas {#create-destination}

1. Log in to your Audience Manager account, go to  &gt; , and click .**[!UICONTROL Audience Data]****[!UICONTROL Destinations]****[!UICONTROL Create Destination]**
1. In the  section, enter a  and  for your new data source, and use the following settings:**[!UICONTROL Basic Information]****[!UICONTROL Name]****[!UICONTROL Description]**
   * **[!UICONTROL Category]**: Plataformas integradas;
   * **[!UICONTROL Type]**: People-Based;
   * **[!UICONTROL Platform]**: select the people-based platform that you want to send audience segments to;
   * **[!UICONTROL Account]**: select the desired advertiser account associated with the selected platform.
      ![create-destination](assets/pbd-create-destination.png)
1. Clique em **[!UICONTROL Next]**.
1. Choose the  that you want to set for this destination.**[!UICONTROL Data Export Labels]**
1. In the  section, select the data source that contains your hashed data sources.**[!UICONTROL Configuration]**
1. In the  section, select the segments that you want to send to this destination. **[!UICONTROL Segment Mappings]** This would be the segments that you created at Step 5 - Create Audience Segments.[](people-based-destinations-workflow-offline.md#create-audience-segments)
1. Salve o destino.
