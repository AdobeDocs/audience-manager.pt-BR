---
description: A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da funcionalidade de Opt-in e pelo suporte à Estrutura de transparência e consentimento (TCF) do IAB. Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar tal suporte no Audience Manager.
seo-description: A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da funcionalidade de Opt-in e pelo suporte à Estrutura de transparência e consentimento (TCF) do IAB. Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar tal suporte no Audience Manager.
seo-title: Plug-in do Audience Manager para a Estrutura de consentimento do IAB
solution: Audience Manager
title: Plug-in do Audience Manager para a Estrutura de consentimento do IAB
translation-type: tm+mt
source-git-commit: 0e32fcaee617e7f18ce4223ffacc39708fb32786

---


# Plug-in do Audience Manager para a Estrutura de consentimento do IAB {#aam-iab-plugin}

## Visão geral

Um aspecto importante nas obrigações de privacidade que você tem em relação aos seus usuários é a aquisição e o transporte de opções de usuário sobre como os dados pessoais deles podem ser usados (ou seja, “finalidade”) e por quem (ou seja, “empresas”).

A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da [funcionalidade de Opt-in](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html) e pelo suporte à [Estrutura de transparência e consentimento (TCF) do IAB](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar tal suporte no Audience Manager. O Audience Manager está registrado no IAB TCF com a ID de fornecedor 565.

The Audience Manager Plug-in for IAB TCF utilizes the [Opt-in functionality](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html), which is, in turn, part of the Adobe [Experience Cloud ID Service (ECID)](https://marketing.adobe.com/resources/help/en_US/mcvid/) library.

## Scope and Limitations {#scope-and-limitations}

Como Publicador ou Anunciante que trabalha com o Audience Manager, você pode transmitir opções de usuário para o Audience Manager como por IAB TCF. Isso oferece uma maneira fácil e consistente de comunicar opções de usuário a todos os parceiros com os quais você trabalha e o Audience Manager pode ajudá-lo a respeitar as opções de privacidade dos usuários.

O suporte para IAB TCF descrito neste artigo representa a primeira fase do suporte planejado do Audience Manager para a estrutura IAB. Atualmente, o Audience Manager não suporta:

* Fluxos de trabalho de dispositivos móveis;
* Gerenciamento de consentimento entre dispositivos;
* Appending consent to URLs sent to [URL destinations](/help/using/features/destinations/manage-destinations.md#configure-url-destination);
* Anexar consentimento para segmentos.

## Pré-requisitos {#prerequisites}

Você deve cumprir os seguintes pré-requisitos para usar o IAB TCF com o Audience Manager:

1. Você deve usar o serviço da Experience Cloud ID (ECID) versão 4.1 ou mais recente. [Baixe](https://github.com/Adobe-Marketing-Cloud/id-service/releases) a versão mais recente do ECID.
2. 
   1. You must be using Audience Manager Data Integration Library (DIL) version 9.0 or newer, downloadable from [here](https://github.com/Adobe-Marketing-Cloud/dil/releases). Read about [DIL in the Audience Manager documentation](/help/using/dil/dil-overview.md).
   2. Como alternativa, se você usar o Encaminhamento pelo lado do servidor (SSF) para importar dados para o Audience Manager, será necessário atualizar para a versão mais recente do appmeasurement. Download AppMeasurement using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).
3. Você deve estar usando uma Plataforma de gerenciamento de aprovação (CMP), seja comercialmente ou sua própria, compatível com IAB e estará registrada com o IAB TCF. See the list of [CMPs registered within the IAB framework](https://advertisingconsent.eu/cmp-list/).

## Recommendations and how to implement {#recommendations}

To enable the IAB TCF support in Audience Manager, read our documentation on [how to set up IAB with Opt-in](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html).

This is easiest done by using [Adobe Launch](https://docs.adobelaunch.com/) to instrument ECID Opt-in on your properties. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## User choice workflow when using the IAB framework {#user-choice-workflow}

Ao visitar uma propriedade da Web, os usuários podem fornecer suas opções relacionadas à forma como seus dados serão usados pelo editor e pelos fornecedores terceirizados com os quais o editor trabalha. Users provide their choices in the form of *standard purposes* and permissions to *third-party vendors* registered in the global vendor list. A imagem abaixo representa um exemplo de uma caixa de diálogo CMP, exibida para um visitante pela primeira vez de um site. Lembre-se de que essa caixa de diálogo pode parecer muito diferente, com base na implementação do cliente.

![Caixa de diálogo CMP](/help/using/overview/aam-gdpr/assets/cmp.png)

Os objetivos padrão na estrutura IAB são:

* Armazenamento e acesso de informações
* Personalização
* Seleção, entrega e relatório de anúncio
* Seleção, entrega e relatório de conteúdo
* Medição

Refer to the [IAB framework specification page](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) for a description of the five standard purposes.

Os usuários podem conceder seu consentimento para uma combinação de objetivos padrão e fornecedores. Por exemplo, os usuários podem conceder seu consentimento para armazenamento, personalização e medição e conceder seu consentimento a todos os fornecedores de terceiros exibidos pelo CMP. Ou, em outro exemplo, eles podem conceder seu consentimento para todos os cinco objetivos padrão, mas conceder somente consentimento a alguns fornecedores exibidos pelo CMP.

Depois que o usuário seleciona suas opções de privacidade, as opções do usuário são gravadas na string de consentimento do IAB TCF. The IAB TCF consent string stores the combination of approved purposes and vendors, along with other metadata information (see the [IAB page](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) for more information). Cada fornecedor registrado no IAB TCF avalia a string de consentimento IAB e faz decisões com base nas opções de privacidade dos usuários. Lembre-se de que as opções de privacidade dos usuários são válidas em todos os fornecedores aprovados.

## Standard purposes needed by Audience Manager {#aam-standard-purposes}

O Audience Manager avalia as opções dos usuários armazenadas na string de consentimento IAB TFC para:

* Information storage and access (purpose ID 1 in the [global vendor list](https://vendorlist.consensu.org/vendorlist.json))
* Personalização (ID da finalidade 2)
* Medição (ID da finalidade 5)
* Consentimento do fornecedor do Audience Manager para armazenar, processar ou ativar em dados para um editor.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Audience Manager behavior depends on whether the user grants consent {#aam-behavior-consent}

O Audience Manager funciona de forma diferente dependendo se o Audience Manager detecta a sequência de consentimento do IAB TCF que o usuário forneceu para os três fins (armazenamento, personalização, medição) ou não.

| When your user *provides consent*, Audience Manager: | When your user *declines* consent, Audience Manager: |
|---|---|
| <ul><li>Executa todos os casos de uso do Audience Manager que você solicitou.</li><li>Transmite consentimento para terceiros em sincronizações de ID (passando rgpts = 1 e a sequência de consentimento como giro_ consentimento em chamadas sincronizadas de ID).</li><li>Avalia e aceita o consentimento passado dos pixels do servidor de anúncios.</li><li>Cumpre sincronizações de ID iniciada pelo parceiro.</li></ul> | <ul><li>Não armazena nenhum novo dado de usuário na sua instância. Isso inclui IDs de parceiro, sinais, características ou dados de pixel.</li><li>Não inicia sincronizações de ID de terceiros.</li><li>Não aceita sincronizações de ID iniciada pelo parceiro.</li></ul> |



## Publisher Use Case {#publisher-use-case}

Ao implementar o IAB TCF, não é necessário manter o código personalizado para o gerenciamento de consentimento nas suas propriedades da Web por meio de um mecanismo diferente com a Adobe ou outros fornecedores de terceiros. O caso de uso é descrito na imagem e nas etapas abaixo. Inicie à esquerda da imagem:

1. Um usuário visita uma das propriedades da Web. As long as you are using the latest versions of the ECID and DIL libraries (see [Prerequisites](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites)), the opt-in flow is triggered.
2. Audience Manager checks whether the IAB flow applies (`isIabContext=true`). See [Recommendations and how to implement](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations).
3. Audience Manager checks whether GDPR applies (`gdpr = 1`) and whether there is a CMP, registered with IAB, on your web property. Por exemplo, isso se aplica a usuários que visitam a partir da área da União Europeia. Observe que é sua responsabilidade como editor definir o sinalizador RGPD.
4. If GDPR applies, Audience Manager checks the IAB TCF consent string, passed in the parameter `gdpr_consent`, for the needed permissions. O Audience Manager requer permissões para armazenamento, personalização, medição, mais consentimento do fornecedor do Audience Manager, para armazenar, processar ou ativar dados.
5. If the IAB TCF consent string is present and it contains the required permissions, Audience Manager passes the IAB TCF consent string on to our [data collection servers](/help/using/reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager responds by setting a [demdex cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) on the browser. O Audience Manager também inicia e respeita sincronizações de ID de terceiros.
7. Como alternativa, se a sequência de consentimento do IAB TCF transmitida na etapa 5 não contiver todas as permissões necessárias, o Audience Manager não coletará, processará ou ativará dados e não seguirá ou iniciará sincronizações de ID.

![Caso de uso do editor](assets/publisher-use-case.png)

## Advertiser Use Case {#advertiser-use-case}

Audience Manager evaluates and honors consent passed in [pixel calls](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md), in accordance with the IAB TCF.

Os pixels normalmente são colocados pelos clientes do Audience Manager nas páginas de parceiros ou são colocados em servidores de publicidade a serem incluídos na resposta do anúncio. No primeiro caso, seu parceiro deve recuperar programaticamente o parâmetro de consentimento e adicioná-lo ao pixel antes de acionar. No segundo caso, que é mais comum e descrito detalhadamente abaixo, os servidores de publicidade anexam os parâmetros de consentimento que recebem dos servidores de plataforma de disponibilização (SSP) ou do editor de anúncios a todos os pixels.

O Audience Manager usa dois parâmetros para transmitir o consentimento do usuário em chamadas de pixel:

* `gdpr` pode ser 0 (RGPD não se aplica) ou 1 (o RGPD se aplica);
* `gdpr_consent` é a string de consentimento do RGPD com base em URL segura para URL (consulte [a especificação](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)). Uma chamada de amostra para um pixel de impressão, com os dois parâmetros abaixo:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

O caso de uso é descrito na imagem e nas etapas abaixo. Inicie à esquerda da imagem:

1. O usuário recebe uma impressão por meio de um servidor de publicidade. Isso traduz-se em uma chamada de pixel para nossos Servidores de coleta de dados (DCS).
1. O Audience Manager verifica se o sinalizador do RGPD se aplica. Se não for o caso, o Audience Manager armazena os dados transmitidos em variáveis macro em chamadas de pixel.
1. Se a string de consentimento estiver presente e contiver as permissões necessárias, o Audience Manager armazenará os dados transmitidos em variáveis macro em chamadas de pixel.
1. Se a sequência de consentimento estiver ausente ou não tiver as permissões necessárias, o Audience Manager irá ignorar os dados passados em variáveis macro em chamadas de pixel.

![Caso de uso do anunciante](assets/advertiser-use-case.png)

## Activation partners that support IAB TCF {#aam-activation-partners}

O plug-in do Audience Manager para IAB TCF permite que você encaminhe a string de consentimento IAB para parceiros de ativação respeitando as opções de privacidade dos usuários. For information on which activation partners support IAB TCF (accurate as of July 7th, 2019), refer to our **[Partner Excel sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx)**.

## Test your IAB implementation {#test-iab-implementation}

To test that you have correctly implemented the Audience Manager Plug-in for IAB TCF, read [Use Case 4 in Validation Methods for Opt-in and IAB implementation](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html).

## IAB e Opt-out no Audience Manager. Order of precedence. {#iab-and-optout}

Outra opção de privacidade da disposição dos usuários é a capacidade de recusar toda a coleta de dados. Adobe provides users with the means to do so within the [Your Privacy Choices](https://www.adobe.com/privacy/opt-out.html#customeruse) page.

Audience Manager addresses opt-out management in a [separate article in our documentation](/help/using/overview/data-security-and-privacy/opt-out-management.md).

>[!NOTE]
>
>**Ordem de prioridade** - se o usuário optar por fora da coleta de dados usando uma ferramenta de não participação global, conforme descrito no link acima, isso terá precedência sobre as verificações de participação e IAB.

## Recursos adicionais {#additional-resources}

* [Aceitação do serviço da Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB Europe RPTRANSPARENCY e Framework Framework](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe RPR Transparency and Approval Framework Technical](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Plug-plugin IAB TCF - demonstração de vídeo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)