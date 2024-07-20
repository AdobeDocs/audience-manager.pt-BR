---
description: Esta página inclui orientação passo a passo sobre como criar segmentos de público-alvo a partir de dados de clientes somente offline e enviá-los para Destinos com base em pessoas.
seo-description: This page includes step-by-step guidance on how to build audience segments from offline-only customer data, and send them to People-Based Destinations.
seo-title: Workflow B - Personalization Based on Offline-Only Data
solution: Audience Manager
title: Fluxo de trabalho B - Personalization com base em dados somente offline
feature: People-based Destinations
exl-id: d980de26-3133-4ae3-80c2-8c3bf2480bbd
source-git-commit: 87c3169083f0dc66490e6a8c808e16371f1d78c0
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 1%

---

# Fluxo de trabalho B - Personalization com base em dados somente offline {#workflow-b}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e pelo uso desse recurso. Nada contido aqui é aconselhamento jurídico. Consulte seu próprio serviço jurídico para obter orientação jurídica.

Esta página inclui orientação passo a passo sobre como criar segmentos de público-alvo a partir de dados de clientes somente offline e enviá-los para Destinos com base em pessoas.

## Etapa 1 - Características offline integradas {#step-1-onboard-traits}

A primeira etapa para criar segmentos de público-alvo neste cenário é trazer os dados offline do cliente para o Audience Manager.

>[!IMPORTANT]
>
> Antes de continuar, verifique se a atividade do cliente que você está prestes a integrar já está definida no Audience Manager com as [características integradas](../traits/trait-and-segment-qualification-reference.md) correspondentes.

Independentemente de suas IDs de cliente do Audience Manager existentes ([DPUUIDs](../../reference/ids-in-aam.md)) serem emails com hash ou não, você deve realizar a integração de características na fonte de dados que contém suas [DPUUIDs](../../reference/ids-in-aam.md).

### Exemplo

Você deseja qualificar as IDs do cliente da tabela abaixo para as IDs de característica integradas correspondentes. Considere que seus [DPUUIDs](../../reference/ids-in-aam.md) estão armazenados em uma fonte de dados com a ID 999999 e sua ID de fonte de dados Audience Manager é 123.

| ID do cliente (DPUUID) | ID de característica integrada |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />

Para qualificar as IDs do cliente no exemplo acima para as características integradas correspondentes, você deve carregar um [arquivo de dados de entrada](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) com o seguinte conteúdo:

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

O nome do arquivo seria semelhante a: `ftp_dpm_999999_123_TIMESTAMP.sync.gz`.
Consulte [Requisitos de nome e tamanho de arquivo do Amazon S3 para arquivos de dados de entrada](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) para obter informações detalhadas sobre a estrutura de nome de arquivo.

## Etapa 2 - Definir configurações do Data Source {#configure-data-source-settings}

Se os [DPUUIDs](../../reference/ids-in-aam.md) forem endereços de email com hash e em letras minúsculas, talvez seja necessário configurar a fonte de dados que armazenará os endereços de email com hash.

 

**Cenário 1: seus [DPUUIDs](../../reference/ids-in-aam.md) já são endereços de email com hash e minúsculas.**

Nesse caso, é necessário rotular a fonte de dados correspondente dessa maneira:

1. Vá para **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**.
1. Localize a fonte de dados que contém seus [DPUUIDs](../../reference/ids-in-aam.md) e clique nela.
1. Verifique se a opção **[!UICONTROL Cannot be tied to personally identifiable information]** está desmarcada.
1. Salve as configurações da fonte de dados.

 

**Cenário 2: seus [DPUUIDs](../../reference/ids-in-aam.md) não são endereços de email com hash e em minúsculas.**

Nesse caso, você precisa criar uma nova fonte de dados entre dispositivos que armazenará seus endereços de email com hash. Veja como fazer isso:

1. Faça logon em sua conta do Audience Manager, vá para **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** e clique em **[!UICONTROL Add New]**.
1. Insira um **[!UICONTROL Name]** e **[!UICONTROL Description]** para sua nova fonte de dados.
1. No menu suspenso **[!UICONTROL ID Type]**, selecione **[!UICONTROL Cross Device]**.
1. Na seção **[!UICONTROL Data Source Settings]**, selecione as opções **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e habilite a opção **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Use o menu suspenso para selecionar o rótulo **[!UICONTROL Emails(SHA256, lowercased)]** para esta fonte de dados.
   >[!IMPORTANT]
   >
   >Essa opção rotula apenas a fonte de dados como contendo dados com hash com esse algoritmo específico. O Audience Manager não faz o hash dos dados nesta etapa. Verifique se os endereços de email que você planeja armazenar nesta fonte de dados já foram atribuídos a hash com o algoritmo [!DNL SHA256]. Caso contrário, você não poderá usá-lo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consulte [Integração de dados](people-based-destinations-prerequisites.md#data-onboarding) para perguntas frequentes sobre como você deve trazer seus dados offline para o Audience Manager for People-Based Destinations.

Assista ao vídeo abaixo para obter um tutorial em vídeo sobre como criar uma fonte de dados para [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Etapa 3 - Corresponder DPUUIDs a Endereços de email com hash por meio da Sincronização de ID com base em arquivo {#match-ids-emails}

>[!IMPORTANT]
>
> Esta etapa se aplica somente ao [Cenário 2](people-based-destinations-workflow-offline.md#configure-data-source-settings) descrito acima. Se seus [DPUUIDs](../../reference/ids-in-aam.md) já forem endereços de email com hash, pule para [Etapa 4 - Criar uma Regra de Mesclagem de Perfis para Segmentação](#create-profile-merge-rule).

Digamos que você deseje fazer a correspondência de seus [DPUUIDs](../../reference/ids-in-aam.md) existentes do exemplo na Etapa 1 com os endereços de email com hash da tabela abaixo (coluna à direita) e armazenar os endereços de email com hash na nova fonte de dados criada em [Etapa 2 - Definir Configurações do Data Source](#configure-data-source-settings).

Como lembrete, agora você teria duas fontes de dados:

| ID da fonte de dados | Conteúdo da fonte de dados |
| -------------- | -------------------------- |
| 999999 | DPUUIDs existentes (IDs de CRM) |
| 987654 | Endereços de email com hash |

| DPUUIDs (IDs de CRM) | Endereço de email | Endereço de email com hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Em nosso exemplo, seu [arquivo de sincronização de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) teria o seguinte conteúdo:

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

## Etapa 4 - Criar uma regra de mesclagem de perfis para segmentação {#create-profile-merge-rule}

A próxima etapa é criar uma nova regra de mesclagem que ajudará você a criar os segmentos de público-alvo para enviar ao seu [!DNL People-Based Destinations].

1. Faça logon em sua conta Audience Manager e vá para **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Clique em [!UICONTROL Add New Rule].
3. Insira uma regra de mesclagem de perfis **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. Na seção **[!UICONTROL Profile Merge Rule Setup]**, selecione a regra **[!UICONTROL All Cross-Device Profiles]** na lista **[!UICONTROL Cross-Device Options]**.
5. Na lista **[!UICONTROL Cross-Device Profile Options]**, selecione a fonte de dados na qual suas características são integradas.
   ![configuração-regra-mesclagem](assets/pbd-pmr.png)

## Etapa 5 - Criar segmentos de público-alvo {#create-audience-segments}

Para criar novos segmentos a partir de dados somente offline, use o [Construtor de segmentos](../segments/segment-builder.md) e certifique-se de usar a nova regra de mesclagem de perfis que você criou na etapa anterior ao criar o segmento.

## Etapa 6 - Configurar a autenticação da plataforma baseada em pessoas {#configure-authentication}

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
>O Audience Manager lida com a integração com plataformas sociais por meio de tokens de autenticação que expiram após um determinado período. Consulte Renovação do token de autenticação para obter detalhes sobre como renovar os tokens expirados.

## Etapa 7 - Criar um destino com base em pessoas {#create-destination}

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
1. Na seção **[!UICONTROL Segment Mappings]**, selecione os segmentos que deseja enviar para esse destino. Estes seriam os segmentos que você criou em [Etapa 5 - Criar segmentos de público-alvo](people-based-destinations-workflow-offline.md#create-audience-segments).
1. Salve o destino.
