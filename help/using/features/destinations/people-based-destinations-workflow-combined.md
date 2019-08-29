---
description: 'Esta página inclui orientação passo a passo sobre como combinar dados de CRM offline com dados comportamentais que você já tem no Audience Manager para criar novos segmentos do público-alvo e, em seguida, enviar esses segmentos do público para Destinos baseados em pessoas.  '
seo-description: 'Esta página inclui orientação passo a passo sobre como combinar dados de CRM offline com dados comportamentais que você já tem no Audience Manager para criar novos segmentos do público-alvo e, em seguida, enviar esses segmentos do público para Destinos baseados em pessoas.   '
seo-title: Fluxo de trabalho A - Personalização com base em todas as atividades online combinadas com dados offline
solution: Audience Manager
title: Fluxo de trabalho A - Personalização com base em todas as atividades online combinadas com dados offline
translation-type: tm+mt
source-git-commit: f3f47db944d9f771cbd55058f6652188cda0e147

---


# Fluxo de trabalho A - Personalização com base em todas as atividades online combinadas com dados offline {#workflow-a}

Esta página inclui orientação passo a passo sobre como combinar dados offline [!DNL CRM] com dados comportamentais que você já tem no Audience Manager para criar novos segmentos do público-alvo e, em seguida, enviar estes segmentos do público para [!DNL People-Based Destinations].

## Etapa 1 - Configurar configurações de fonte de dados {#configure-data-source-settings}

Dependendo de suas [dpuuids](../../reference/ids-in-aam.md) serem em minúsculas, os endereços de email com hash talvez precisem configurar a fonte de dados que armazenará os endereços de email com hash.

**Cenário 1: suas[dpuuids](../../reference/ids-in-aam.md)são endereços de email com hash em minúsculas.**

Nesse caso, é necessário rotular a fonte de dados correspondente como tal:

1. Vá para [!UICONTROL Audience Data] -&gt; [!UICONTROL Data Sources].
1. Encontre a fonte de dados que contém suas [dpuuids](../../reference/ids-in-aam.md)e clique nela.
1. Verifique se a opção [!UICONTROL Cannot be tied to personally identifiable information] está desmarcada.
1. Salve as configurações de fonte de dados.

**Cenário 2: suas[dpuuids](../../reference/ids-in-aam.md)não são minúsculas e endereços de email com hash.**

Nesse caso, é necessário criar uma nova fonte de dados entre dispositivos que armazene seus endereços de email com hash. Veja como fazer isso:

1. Faça logon em sua conta do Audience Manager e vá **[!UICONTROL Audience Data]** para &gt; **[!UICONTROL Data Sources]** e clique **[!UICONTROL Add New]** em.
1. Digite a [!UICONTROL Name] e [!UICONTROL Description] para a nova fonte de dados.
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

## Etapa 2 - Corresponder dpuuids a endereços de email com hash por meio da sincronização de ID baseada em arquivo {#match-ids-emails}

>[!IMPORTANT]
>
> Essa etapa aplica-se somente ao [Cenário 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) descrito acima. Se suas dpuuids existentes [já](../../reference/ids-in-aam.md) estiverem em endereços de email com hash, pule para [a Etapa 3 - Crie uma regra de mesclagem de perfil para segmentação](people-based-destinations-workflow-combined.md#create-merge-rule).

Considere que você deseja corresponder [suas dpuuids](../../reference/ids-in-aam.md) existentes aos endereços de email com hash da tabela abaixo (coluna direita) e armazenar os endereços de email com hash na nova fonte de dados criada na [Etapa 1 - Configurar configurações de fonte de dados](people-based-destinations-workflow-combined.md#configure-data-source-settings).

| DPUUID (ID de CRM) | Endereço de email | Endereço de email com hash |
| --- | --- | --- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

Você pode vincular até 10 endereços de email com hash a uma única [DPUUID](../../reference/ids-in-aam.md). Para fazer isso, separe os endereços de email com hash de uma vírgula, dentro do arquivo de sincronização.

Em nosso exemplo, agora você teria duas fontes de dados.

| ID da fonte de dados | Conteúdo da fonte de dados |
| --- | --- |
| 999999 | Dpuuids existentes (IDs de CRM) |
| 987654 | Endereços de email com hash |

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

## Etapa 3 - Criar uma regra de mesclagem de perfil para segmentação {#create-merge-rule}

A próxima etapa está criando uma nova regra de mesclagem que ajudará a criar os segmentos do público-alvo para enviar para seus destinos baseados em pessoas.

>[!IMPORTANT]
>
> Se você já tiver uma regra definida com as [!UICONTROL Current Authenticated Profiles][!UICONTROL Last Authenticated Profiles] opções, poderá pular para [a Etapa 4 - Criar segmentos de público-alvo](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Faça logon em sua conta do Audience Manager e vá **[!UICONTROL Audience Data]** para &gt; **[!UICONTROL Profile Merge Rules]**.
1. Clique em **[!UICONTROL Add New Rule]**.
1. Insira uma regra de mesclagem de perfil **[!UICONTROL Name]** e **[!UICONTROL Description]**.
1. Na **[!UICONTROL Profile Merge Rule Setup]** seção, selecione as opções **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]** opções.
1. Na **[!UICONTROL Cross-Device Profile Options]** lista, selecione as fontes de dados em que deseja executar a segmentação. Essas devem ser as fontes de dados que contêm suas [dpuuids existentes](../../reference/ids-in-aam.md).

## Etapa 4 - Criar segmentos de público-alvo {#create-audience-segments}

Para criar novos segmentos do público-alvo, use o [Construtor de segmentos](../segments/segment-builder.md). Se você possui segmentos de público-alvo existentes que deseja enviar [!DNL People-Based Destinations], pule para [a Etapa 5 - Configurar autenticação de plataforma baseada em pessoas](people-based-destinations-workflow-combined.md#configure-authentication).

## Etapa 5 - Configurar autenticação de plataforma baseada em pessoas {#configure-authentication}

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
1. Na **[!UICONTROL Segment Mappings]** seção, selecione os segmentos que deseja enviar para esse destino. Esses seriam os segmentos criados na [Etapa 4 - Criar segmentos de público-alvo](people-based-destinations-workflow-combined.md#create-audience-segments).
1. Salve o destino.
