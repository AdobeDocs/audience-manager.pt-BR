---
description: 'Esta página inclui orientação passo a passo sobre como construir segmentos de público-alvo com base em dados de clientes offline e enviá-los para Destinos baseados em pessoas.  '
seo-description: 'Esta página inclui orientação passo a passo sobre como construir segmentos de público-alvo com base em dados de clientes offline e enviá-los para Destinos baseados em pessoas.  '
seo-title: Fluxo de trabalho B - Personalização com base em dados somente offline
solution: Audience Manager
title: Fluxo de trabalho B - Personalização com base em dados somente offline
translation-type: tm+mt
source-git-commit: d0e343e3fbaf527e9b630dc2dbc851d8f8f4c0b2

---


# Fluxo de trabalho B - Personalização com base em dados somente offline {#workflow-b}

Esta página inclui orientação passo a passo sobre como construir segmentos de público-alvo com base em dados de clientes offline e enviá-los para Destinos baseados em pessoas.

## Etapa 1 - Características offline no quadro {#step-1-onboard-traits}

A primeira etapa para criar segmentos de público-alvo neste cenário é trazer os dados do cliente offline para o Audience Manager.

>[!IMPORTANT]
>
> Antes de continuar, verifique se a atividade do cliente que você está prestes a entrar já está definida no Audience Manager com características [integradas correspondentes](../traits/trait-qualification-reference.md).

Independentemente de suas IDs de cliente do Audience Manager ([dpuuids](../../reference/ids-in-aam.md)) já terem sido e-mails com hash ou não, você deve executar a integração traço em relação à fonte de dados que contém suas [dpuuids](../../reference/ids-in-aam.md).

### Exemplo

Você deseja qualificar as IDs do cliente da tabela abaixo para as IDs de característica integradas correspondentes. Considere que suas [dpuuids](../../reference/ids-in-aam.md) são armazenadas em uma fonte de dados com a ID 999999 e sua ID do parceiro do Audience Manager é 123.

| ID do cliente (DPUUID) | ID de característica de onboarded |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />Para qualificar as IDs do cliente no exemplo acima para as características integradas correspondentes, você deve carregar um [arquivo de dados de entrada] (../../integration/send-audience-data/batch-data-transfer-explained/inbound-file-contents. md) com o seguinte conteúdo:

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

O nome do arquivo seria desta forma: `ftp_dpm_999999_123_TIMESTAMP.sync.gz`.
Consulte [Requisitos de nome e tamanho de arquivo do Amazon S 3 para arquivos de dados de entrada](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) para obter informações detalhadas sobre a estrutura do nome do arquivo.

## Etapa 2 - Configurar configurações de fonte de dados {#configure-data-source-settings}

Dependendo de suas [dpuuids](../../reference/ids-in-aam.md) serem em minúsculas, os endereços de email com hash talvez precisem configurar a fonte de dados que armazenará os endereços de email com hash.

 

**Cenário 1: suas[dpuuids](../../reference/ids-in-aam.md)são endereços de email com hash em minúsculas.**

Nesse caso, é necessário rotular a fonte de dados correspondente como tal:

1. Vá para **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**.
1. Encontre a fonte de dados que contém suas [dpuuids](../../reference/ids-in-aam.md)e clique nela.
1. Verifique se a opção **[!UICONTROL Cannot be tied to personally identifiable information]** está desmarcada.
1. Salve as configurações de fonte de dados.

 

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

## Etapa 3 - Corresponder dpuuids a endereços de email com hash por meio da sincronização de ID baseada em arquivo {#match-ids-emails}

>[!IMPORTANT]
>
> Essa etapa aplica-se somente ao [Cenário 2](people-based-destinations-workflow-offline.md#configure-data-source-settings) descrito acima. Se suas dpuuids existentes [já](../../reference/ids-in-aam.md) estiverem em endereços de email com hash, pule para [a Etapa 4 - Crie uma regra de mesclagem de perfil para segmentação](#create-profile-merge-rule).

Suponhamos que você queira corresponder às [dpuuids](../../reference/ids-in-aam.md) existentes do exemplo na Etapa 1 para os endereços de email com hash da tabela abaixo (coluna direita) e armazene os endereços de email com hash na nova fonte de dados criada na [Etapa 2 - Configure as configurações da fonte de dados](#configure-data-source-settings).

Como lembrete, agora você teria duas fontes de dados:

| ID da fonte de dados | Conteúdo da fonte de dados |
| -------------- | -------------------------- |
| 999999 | Dpuuids existentes (IDs de CRM) |
| 987654 | Endereços de email com hash |

| Dpuuids (IDs CRM) | Endereço de email | Endereço de email com hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

O [arquivo](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) de sincronização de ID teria o seguinte conteúdo:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

O arquivo de sincronização [de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) deve seguir esta estrutura de nomenclatura:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

No exemplo acima, o nome do arquivo seria:`c2c_id_999999_987654_1560431657.sync`


[Baixe o arquivo de exemplo aqui](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync).

## Etapa 4 - Criar uma regra de mesclagem de perfil para segmentação {#create-profile-merge-rule}

A próxima etapa está criando uma nova regra de mesclagem que ajudará a criar os segmentos do público-alvo para enviar para o seu [!DNL People-Based Destinations].

1. Faça logon em sua conta do Audience Manager e vá **[!UICONTROL Audience Data]** para -&gt; **[!UICONTROL Profile Merge Rules]**.
2. Clique em [!UICONTROL Add New Rule].
3. Insira uma regra de mesclagem de perfil **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. Na **[!UICONTROL Profile Merge Rule Setup]** seção, selecione a **[!UICONTROL All Cross-Device Profiles]** regra na **[!UICONTROL Cross-Device Options]** lista.
5. Na **[!UICONTROL Cross-Device Profile Options]** lista, selecione a fonte de dados na qual suas características estão vinculadas.
   ![mesclar regras](assets/pbd-pmr.png)

## Etapa 5 - Criar segmentos de público-alvo {#create-audience-segments}

Para criar novos segmentos a partir de dados offline, use o [Construtor](../segments/segment-builder.md) de segmentos e certifique-se de usar a nova regra de mesclagem de perfil criada na etapa anterior ao criar o segmento.

## Etapa 6 - Configurar autenticação de plataforma baseada em pessoas {#configure-authentication}

1. Faça logon em sua conta do Audience Manager e vá **[!UICONTROL Administration]** para &gt; **[!UICONTROL Integrated Accounts]**. Se você tiver uma integração configurada anteriormente com uma plataforma social, deverá vê-la listada nesta página. Caso contrário, a página ficará vazia.
   ![integração baseada em pessoas](assets/pbd-config.png)
1. Clique em **[!UICONTROL Add Account]**.
1. Use o **[!UICONTROL People-Based Platform]** menu suspenso para selecionar a plataforma com a qual você deseja configurar a integração.
   ![plataforma baseada em pessoas](assets/pbd-add.png)
1. Clique **[!UICONTROL Confirm]** para ser redirecionado para a página de autenticação da plataforma selecionada.
1. Após ter sido autenticado na conta da plataforma social, você será redirecionado para o Audience Manager onde você deverá visualizar suas contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique **[!UICONTROL Confirm]** em.
1. O Audience Manager exibe uma notificação na parte superior da página para informar se a conta foi adicionada com êxito. A notificação também permite que você adicione um endereço de email de contato para receber notificações quando a autenticação da plataforma social estiver prestes a expirar.

>[!IMPORTANT]
>
>Um Gerente de udience lida com a integração com plataformas sociais por meio de tokens de autenticação que expiram após um determinado período. Consulte Renovação do token de autenticação para obter detalhes sobre como renovar os tokens expirados.

## Etapa 7 - Criar um destino baseado em pessoas {#create-destination}

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
1. Na **[!UICONTROL Segment Mappings]** seção, selecione os segmentos que deseja enviar para esse destino. Esses seriam os segmentos criados na [Etapa 5 - Criar segmentos de público-alvo](people-based-destinations-workflow-offline.md#create-audience-segments).
1. Salve o destino.
