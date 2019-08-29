---
description: Este artigo explica como configurar Públicos-alvo personalizados do Twitter para integrações novas e existentes.
seo-description: Este artigo explica como configurar Públicos-alvo personalizados do Twitter para integrações novas e existentes.
seo-title: Configurar públicos-alvo adaptados do Twitter como destino baseado em dispositivo autoatendimento
solution: Audience Manager
title: Configurar públicos-alvo adaptados do Twitter como destino baseado em dispositivo autoatendimento
translation-type: tm+mt
source-git-commit: 2ca6ed86922af2dbdfd268551f101e58c8356579

---


# Configurar [!DNL Twitter Tailored Audiences] como destino baseado em dispositivo autoatendimento {#configure-twitter}

Este artigo explica como configurar [Públicos-alvo personalizados do Twitter](https://business.twitter.com/en/targeting/tailored-audiences.html) para integrações novas e existentes.

## Pré-requisitos {#prerequisites}

Antes de configurar o [!DNL Twitter Tailored Audiences] destino, verifique os seguintes pré-requisitos do Twitter que você precisa atender.

1. Sua [!DNL Twitter Ads] conta deve ser qualificada para publicidade. As novas [!DNL Twitter Ads] contas não são elegíveis para publicidade nas primeiras 2 semanas após a criação.
2. Sua conta de usuário do Twitter de acesso autorizado no Audience Manager deve ter a permissão do Gerenciador de público [-alvo](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) do parceiro habilitada.
3. Se [você estiver atualizando sua integração existente do Twitter para a administração de autoatendimento](#update-existing-twitter-integrations), sua conta de usuário do Twitter deve ter a [permissão Gerente](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) de publicidade ativada.

## Adicionar um novo [!DNL Twitter Tailored Audiences] destino {#add-new-twitter-destination}

Esta seção descreve as etapas que você precisa seguir ao configurar um novo destino com base em dispositivo. [!DNL Twitter Tailored Audiences] Este cenário pressupõe que você não tem um destino existente [!DNL Twitter Tailored Audiences] configurado por meio do consultor da Adobe ou do Atendimento ao cliente.

### Etapa 1. Autenticar com [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

Antes de adicionar o destino baseado no dispositivo, você precisa vincular o Audience Manager e sua [!DNL Twitter Tailored Audiences] conta. Veja como fazer isso:

1. Faça logon em sua conta do Audience Manager e vá **[!DNL Administration > Integrated Accounts]** para. Se você tiver uma integração configurada anteriormente com uma plataforma de destino, deverá vê-la listada nesta página. Caso contrário, a página ficará vazia.
2. Clique em **[!DNL Add Account]**.
3. Selecione [!DNL Twitter Tailored Audiences] e clique **[!DNL Confirm]** para ser redirecionado para a página de autenticação. ![plataformas integradas](assets/dbd-integrated-platforms.png)
4. Depois de autenticado, você será redirecionado para o Audience Manager onde você deverá ver suas contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique **[!DNL Confirm]** em.

### Etapa 2: Criar um novo destino baseado em dispositivo {#step2-create-new-destination}

Depois de vincular o Audience Manager e seu [!DNL Twitter Tailored Audiences], você pode criar o novo destino. Veja como fazer isso:

>[!NOTE]
>
>Não é possível alterar o nome de um destino existente baseado em dispositivo. Certifique-se de fornecer um nome que ajudará a identificar o destino corretamente.

1. Faça logon na conta do Audience Manager, vá para **[!DNL Audience Data > Destinations]** e clique **[!DNL Create Destination]** em.
2. Na **[!DNL Basic Information]** seção, digite a **[!DNL Name]** e **[!DNL Description]** para o novo destino e use as configurações abaixo: ![configuração](assets/dbd-new-basic.png)
3. Clique em **[!DNL Next]**.
4. Escolha [os Rótulos](/help/using/features/data-export-controls.md#controls-labels) de exportação de dados que você deseja definir para esse destino.
5. Clique em **[!DNL Save]**.
6. Na **[!DNL Segment Mappings]** seção, selecione os segmentos do público-alvo que você deseja enviar para este destino.
7. Salve o destino.

## Atualizar integrações existentes do Twitter para administração de autoatendimento {#update-existing-twitter-integrations}

Para melhorar a experiência do usuário e simplificar o processo de configuração, estamos atualizando a [!DNL Twitter Tailored Audiences] integração para um modelo de autoatendimento, onde você pode realizar a própria configuração, na interface do usuário do Audience Manager. Esta seção descreve as etapas que você precisa executar para atualizar sua integração existente do Twitter.

>[!IMPORTANT]
>
>As etapas descritas abaixo só se aplicam se você tiver uma integração existente com [!DNL Twitter Tailored Audiences], configurada por um consultor do Audience Manager ou pelo Atendimento ao cliente. O processo completo de atualização do destino para o modelo de autoatendimento pode levar até 5 dias úteis. Por enquanto, seu destino ainda está ativo e o Audience Manager continua a enviar públicos-alvo para ele.
> Consulte o número 3 em [Pré-requisitos](#prerequisites) antes de migrar para [!DNL Twitter Tailored Audiences] o modelo de autoatendimento.

Siga as etapas abaixo para migrar seu destino existente [!DNL Twitter Tailored Audiences] para o modelo de autoatendimento.

1. Faça logon em sua conta do Audience Manager e vá **[!DNL Administration > Integrated Accounts]** para.
1. Clique em **[!DNL Add Account]**.
1. Selecione [!DNL Twitter Tailored Audiences] e clique **[!DNL Confirm]** para ser redirecionado para a página de autenticação. ![plataformas integradas](assets/dbd-integrated-platforms.png)
1. Após ter sido autenticado com a [!DNL Twitter] sua conta, você será redirecionado para o Audience Manager onde você deverá visualizar suas contas de anunciante associadas. Selecione a conta do anunciante que deseja usar e clique **[!DNL Confirm]** em.
1. Vá **[!UICONTROL Audience Data]** para &gt; **[!UICONTROL Destinations]** e clique no destino do Twitter que você precisa configurar.
1. Clique em **[!UICONTROL Edit]**. Na **[!UICONTROL Basic Information]** seção, clique no menu **[!UICONTROL Integrated Account]** suspenso e selecione a [!DNL Twitter] conta com a qual você está autenticada na Etapa 4.
1. **[!UICONTROL Save]** o destino.

## Validando a migração para a administração de autoatendimento {#migration-validation}

A migração completa de integrações existentes [!DNL Twitter] para administração de autoatendimento pode levar até 7 dias. Quando a migração for concluída, o Audience Manager mostrará uma notificação na interface do usuário.

Você também verá um novo grupo de públicos-alvo na [!DNL Twitter] sua conta, com os nomes prefixos por [[!DNL Adobe DMP Audience]]. Aguarde até 7 dias para que a população do público-alvo seja totalmente preenchida. Após a conclusão da migração, você deve usar esses novos públicos em vez dos antigos.

## Considerações sobre mapeamento de segmento {#segment-mapping-considerations}

Ao mapear segmentos de público-alvo para o Twitter, certifique-se de cumprir os seguintes requisitos de nomenclatura de segmento:

* Forneça nomes de mapeamento de segmento legíveis. Recomendamos usar o mesmo nome que você usou para os segmentos do Audience Manager.
* Não use vírgulas em nomes de mapeamento de segmento e segmento.

### Exemplo

* Corrigir o segmento ou o nome do mapeamento: " US and European Shoppers ";
* Segmento incorreto ou nome do mapeamento: " US, Europeu 5 h 0 rs rs ".

>[!IMPORTANT]
>
>Não é possível alterar os nomes dos segmentos já mapeados. O Audience Manager usa os nomes de segmento para identificar corretamente os segmentos na integração.
