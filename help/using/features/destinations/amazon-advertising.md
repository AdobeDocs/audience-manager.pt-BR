---
description: Este artigo explica como configurar o Amazon Advertising para integrações novas e existentes.
solution: Audience Manager
title: Configurar o Amazon Advertising como um destino baseado em dispositivo de autoatendimento
exl-id: 049af52a-b425-493d-9e77-9ced7ba6d168
source-git-commit: bac3167927af0957e7081e1ea653464101affcb8
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 0%

---

# Configurar [!DNL Amazon Advertising] como um Destino Baseado em Dispositivo de Autoatendimento {#configure-amazon}

Este artigo explica como configurar uma integração com o [Amazon Advertising](https://advertising.amazon.com/API/docs/en-us).

## Pré-requisitos {#prerequisites}

Antes de configurar o destino do [!DNL Amazon Advertising], verifique se você atende aos seguintes pré-requisitos.

* Sua conta [!DNL Amazon] deve ser qualificada para publicidade.
* Ao criar o primeiro destino [!DNL Amazon Advertising] na sua instância do Audience Manager, entre em contato com a Adobe Consulting ou com o Atendimento ao cliente para habilitar a sincronização de ID [!DNL Amazon] (Data Source ID = 139200) para sua conta. Isso é necessário para a sincronização correta entre Audience Manager e [!DNL Amazon].
* Depois que os novos públicos do provedor de dados forem criados, você deverá [atualizar seus metadados](https://advertising.amazon.com/API/docs/en-us/data-provider/openapi#tag/Metadata/paths/~1v2~1dp~1audiencemetadata~1%7BaudienceId%7D/put) e adicionar o **[!DNL audience fees]**. Para esta operação, você pode usar a [API do Amazon Ads](https://advertising.amazon.com/API/docs/en-us/guides/onboarding/apply-for-access) ou a [Interface do usuário do Amazon Advertising](https://advertising.amazon.com/).

## Adicionar um novo destino [!DNL Amazon Advertising] {#add-new-amazon-destination}

Esta seção descreve as etapas que devem ser seguidas ao configurar um novo destino baseado em dispositivo para [!DNL Amazon Advertising]. Este cenário pressupõe que você não tenha nenhum destino [!DNL Amazon Advertising] existente configurado por meio de seu consultor de Adobe ou do Atendimento ao cliente.

### Etapa 1. Autenticar com [!DNL Amazon Advertising] {#step1-authenticate-with-amazon}

Antes de adicionar o destino baseado em dispositivo, é necessário vincular o Audience Manager e sua conta do [!DNL Amazon Advertising]. Veja como fazer isso:

1. Faça logon em sua conta Audience Manager e vá para **[!UICONTROL Administration > Integrated Accounts]**. Se você tiver uma integração configurada anteriormente com uma plataforma de destino, deverá vê-la listada nesta página. Caso contrário, a página ficará vazia.
1. Selecione **[!UICONTROL Add Account]**.
1. Selecione [!UICONTROL Amazon Data Provider].

   ![plataformas integradas](assets/dbd-amazon-without-options.png)

1. Selecione uma das opções de **[!UICONTROL Amazon Data Provider]**, dependendo da região em que sua conta do [!DNL Amazon Ads] foi criada (América do Norte, Europa ou Extremo Oriente), e clique em **[!DNL Confirm]** para ser redirecionado à página de autenticação.

   ![plataformas integradas](assets/dbd-amazon-with-options.png)

1. Após a autenticação, você é redirecionado para o Audience Manager, onde deve ver suas contas de anunciante associadas. Selecione a conta de anunciante que deseja usar e clique em **[!UICONTROL Confirm]**. Ao fazer isso, você autorizou o acesso do Audience Manager para enviar atualizações para seus públicos.

### Etapa 2: Criar um novo destino com base em dispositivo {#step2-create-new-destination}

Depois de vincular o Audience Manager e sua conta do [!DNL Amazon Advertising], você poderá criar o novo destino. Veja como fazer isso:

>[!NOTE]
>
>Não é possível alterar o nome de um destino existente baseado em dispositivo. Forneça um nome que ajudará a identificar o destino corretamente.

1. Faça logon em sua conta Audience Manager, vá para **[!UICONTROL Audience Data > Destinations]** e selecione **[!UICONTROL Create Destination]**.
1. Na seção **[!UICONTROL Basic Information]**, digite um **[!UICONTROL Name]** e **[!UICONTROL Description]** para o novo destino e use as configurações abaixo:

   ![configuração](assets/dbd-new-account-amazon.png)

1. Selecione **[!UICONTROL Next]**.
1. Escolha os [Rótulos de Exportação de Dados](/help/using/features/data-export-controls.md#controls-labels) que você deseja definir para este destino.
1. Selecione **[!UICONTROL Save]**.
1. Na seção **[!UICONTROL Segment Mappings]**, selecione os segmentos de público-alvo que você deseja enviar para esse destino.
1. Salve o destino.

## Considerações sobre taxas de correspondência {#match-rates-considerations}

A integração entre o Audience Manager e o [!DNL Amazon Advertising] dá suporte a preenchimentos retroativos de público-alvo histórico. Todas as qualificações de segmento são enviadas para [!DNL Amazon] quando você cria o destino.

## Solução de problemas {#troubleshooting}

Ao configurar ou enviar dados para o destino [!DNL Amazon Advertising], você pode encontrar os erros descritos abaixo. Esta seção explica o que pode causar os erros e como corrigi-los.

| Mensagem de erro | Ocorrência / Motivo | Resolução |
|---|---|---|
| `Internal server error` | Esta mensagem de erro é exibida na interface do usuário do Audience Manager ao tentar adicionar uma nova conta do [!DNL Amazon] usando uma versão desatualizada da API do Amazon. | Entre em contato com o Atendimento ao cliente da Adobe. |
| `Amazon Error: Account XXXXXXXXX was not found` | Essa mensagem de erro é exibida na interface do usuário do Audience Manager quando as credenciais configuradas para o destino não estão autorizadas a acessar a conta do Amazon Ads correspondente. | <ul><li>Verifique se as credenciais de conta que você está usando atendem aos [pré-requisitos](#prerequisites).</li><li>Navegue até a interface do usuário do Amazon Ads usando as mesmas credenciais e verifique se os públicos-alvo corretos são exibidos na conta correspondente. </li></ul> |
