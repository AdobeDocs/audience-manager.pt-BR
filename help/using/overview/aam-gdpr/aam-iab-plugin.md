---
description: A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da funcionalidade de Opt-in e pelo suporte à Estrutura de transparência e consentimento (TCF) do IAB. Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar tal suporte no Audience Manager.
seo-description: A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da funcionalidade de Opt-in e pelo suporte à Estrutura de transparência e consentimento (TCF) do IAB. Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar tal suporte no Audience Manager.
seo-title: Plug-in do Audience Manager para a Estrutura de consentimento do IAB
solution: Audience Manager
title: Plug-in do Audience Manager para a Estrutura de consentimento do IAB
translation-type: tm+mt
source-git-commit: c238a37e1a72edb0679f657d0178e04b8d848ec2

---


# Plug-in do Audience Manager para a Estrutura de consentimento do IAB {#aam-iab-plugin}

## Visão geral

Um aspecto importante nas obrigações de privacidade que você tem em relação aos seus usuários é a aquisição e o transporte de opções de usuário sobre como os dados pessoais deles podem ser usados (ou seja, “finalidade”) e por quem (ou seja, “empresas”).

A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da [funcionalidade de Opt-in](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html) e pelo suporte à [Estrutura de transparência e consentimento (TCF) do IAB](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar tal suporte no Audience Manager. Audience Manager is registered in the IAB TCF with the vendor ID 565.

The Audience Manager Plug-in for IAB TCF utilizes the Opt-in functionality, which is, in turn, part of the Adobe Experience Cloud ID Service (ECID) library.[](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)[](https://marketing.adobe.com/resources/help/en_US/mcvid/)

## Scope and Limitations {#scope-and-limitations}

As a Publisher or Advertiser working with Audience Manager, you are able to convey user choices to Audience Manager as per IAB TCF. Isso fornece uma maneira fácil e consistente de comunicar as opções de usuários a todos os parceiros com os quais você trabalha e o Audience Manager pode ajudá-lo a respeitar as opções de privacidade dos usuários.

O suporte ao TCF do IAB descrito neste artigo representa a primeira fase do suporte planejado do Audience Manager ao quadro do IAB. Atualmente, o Audience Manager não oferece suporte a:

* Fluxos de trabalho do dispositivo móvel;
* Gestão do consentimento entre dispositivos;
* Acrescentar consentimento aos URLs enviados para destinos [](/help/using/features/destinations/create-url-destination.md)URL;
* Anexar consentimento aos segmentos.

## Pré-requisitos {#prerequisites}

Você deve atender aos seguintes pré-requisitos para usar o TCF IAB com o Audience Manager:

1. Você deve estar usando a versão 4.1 ou mais recente do Serviço da Experience Cloud ID (ECID). [Baixe](https://github.com/Adobe-Marketing-Cloud/id-service/releases) nossa versão mais recente do ECID.
2. 
   1. Você deve estar usando a Biblioteca de integração de dados (DIL) do Audience Manager versão 9.0 ou mais recente, disponível para download [aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases). Leia sobre o [DIL na documentação](/help/using/dil/dil-overview.md)do Audience Manager.
   2. Como alternativa, se você usar o encaminhamento pelo lado do servidor (SSF) para importar dados para o Audience Manager, será necessário atualizar para a versão mais recente do AppMeasurement. Baixe o AppMeasurement usando o Gerenciador [de código do](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)Analytics.
3. Você deve estar usando uma Plataforma de Gerenciamento de Consentimento (CMP), comercial ou própria, compatível com a IAB, e está registrada no IAB TCF. Consulte a lista de [CMPs registrados na estrutura](https://advertisingconsent.eu/cmp-list/)IAB.

## Recomendações e como implementar {#recommendations}

Para habilitar o suporte ao TCF IAB no Audience Manager, leia nossa documentação sobre [como configurar o IAB com aceitação](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html).

Isso é mais fácil de ser feito usando o [Adobe Launch](https://docs.adobelaunch.com/) para instrumentar a opção ECID nas suas propriedades. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## Fluxo de trabalho de escolha do usuário ao usar a estrutura IAB {#user-choice-workflow}

Ao visitar uma propriedade da Web, os usuários podem fornecer suas opções sobre como seus dados devem ser usados pelo editor e pelos fornecedores de terceiros com os quais o editor trabalha. Os usuários fornecem suas opções na forma de finalidades *e permissões* padrão para fornecedores ** terceiros registrados na lista global de fornecedores. A imagem abaixo representa um exemplo de uma caixa de diálogo CMP, exibida para um visitante pela primeira vez de um site. Lembre-se de que essa caixa de diálogo pode parecer muito diferente, com base na implementação do cliente.

![Caixa de diálogo CMP](/help/using/overview/aam-gdpr/assets/cmp.png)

Os objetivos padrão do quadro IAB são:

* Armazenamento e acesso à informação
* Personalização
* Seleção de anúncios, entrega e relatório
* Seleção de conteúdo, entrega e relatório
* Medição

Refer to the IAB framework specification page for a description of the five standard purposes.[](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features)

Users may grant their consent for a combination of standard purposes and vendors. Por exemplo, os usuários podem conceder seu consentimento para armazenamento, personalização e medição e conceder seu consentimento a todos os fornecedores de terceiros exibidos pelo CMP. Or, in another example, they could grant their consent for all five standard purposes but only grant consent to a few of the vendors displayed by the CMP.

Once the user selects their privacy choices, the user choice(s) are recorded in the IAB TCF consent string. The IAB TCF consent string stores the combination of approved purposes and vendors, along with other metadata information (see the IAB page for more information). [](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) Every vendor registered in the IAB TCF evaluates the IAB TCF consent string and makes decisions based on the users' privacy choices. Keep in mind that the users' privacy choices are valid across all approved vendors.

## Standard purposes needed by Audience Manager {#aam-standard-purposes}

Audience Manager evaluates the users' choices stored in the IAB TFC consent string for:

* Information storage and access (purpose ID 1 in the global vendor list)[](https://vendorlist.consensu.org/vendorlist.json)
* Personalização (ID de objetivo 2)
* Measurement (purpose ID 5)
* Audience Manager vendor consent to store, process, or activate on data for a publisher.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Audience Manager behavior depends on whether the user grants consent {#aam-behavior-consent}

Audience Manager works differently depending on whether Audience Manager detects in the IAB TCF consent string that the user has provided consent for the three purposes (storage, personalization, measurement) or not.

| When your user provides consent, Audience Manager:** | Quando o usuário *recusar* o consentimento, o Audience Manager: |
|---|---|
| <ul><li>Executa todos os casos de uso do Audience Manager solicitados.</li><li>Transmite o consentimento a terceiros em sincronizações de ID (transmitindo gdpr = 1 e a sequência de caracteres de consentimento como gdpr_Consentimento em chamadas de sincronização de ID).</li><li>Avalia e respeita o consentimento passado dos pixels do servidor de publicidade.</li><li>Honra sincronizações de ID iniciadas pelo parceiro.</li></ul> | <ul><li>Não armazena dados novos do usuário na sua instância. Isso inclui IDs de parceiros, sinais, características ou dados de pixel.</li><li>Não inicia sincronizações de ID de terceiros.</li><li>Não aceita sincronizações de ID iniciadas pelo parceiro.</li></ul> |



## Caso de uso do editor {#publisher-use-case}

Ao implementar o TCF da IAB, você não é obrigado a manter o código personalizado para gerenciamento de consentimento nas suas propriedades da Web por meio de um mecanismo diferente com a Adobe ou outros fornecedores de terceiros. O caso de uso é descrito na imagem e nas etapas abaixo. Comece a partir da esquerda da imagem:

1. Um usuário visita uma de suas propriedades da Web. Desde que você esteja usando as versões mais recentes das bibliotecas ECID e DIL (consulte [Pré-requisitos](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites)), o fluxo de aceitação é acionado.
2. O Audience Manager verifica se o fluxo IAB se aplica (`isIabContext=true`). Consulte [Recomendações e como implementar](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations).
3. O Audience Manager verifica se o RGPD se aplica (`gdpr = 1`) e se há um CMP, registrado com o IAB, na propriedade da Web. Tal aplicar-se-ia, por exemplo, aos utilizadores que visitam o espaço da União Europeia. Observe que é sua responsabilidade como editor definir o sinalizador do RGPD.
4. Se o GDPR for aplicado, o Audience Manager verificará a string de consentimento do TCF IAB, transmitida no parâmetro `gdpr_consent`, para obter as permissões necessárias. O Audience Manager precisa de permissões para armazenamento, personalização, medição, além do consentimento do fornecedor do Audience Manager, para armazenar, processar ou ativar dados.
5. Se a sequência de caracteres de consentimento TCF do IAB estiver presente e contiver as permissões necessárias, o Audience Manager transmitirá a sequência de caracteres de consentimento TCF do IAB aos nossos servidores [de coleta de](/help/using/reference/system-components/components-data-collection.md) dados (DCS).
6. O Audience Manager responde definindo um cookie [](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) demdex no navegador. Audience Manager also initiates and honors 3rd party ID syncs.
7. Como alternativa, se a sequência de caracteres de consentimento TCF IAB transmitida na etapa 5 não contiver todas as permissões necessárias, o Audience Manager não coletará, processará ou ativará dados e não honrará ou iniciará sincronizações de ID.

![Publisher Use Case](assets/publisher-use-case.png)

## Advertiser Use Case {#advertiser-use-case}

O Audience Manager avalia e honra o consentimento passado em chamadas [de](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)pixel, de acordo com o TCF do IAB.

Os pixels são geralmente colocados por clientes do Audience Manager em suas páginas de parceiros ou são colocados em servidores de anúncios para inclusão na resposta do anúncio. In the first case, your partner must programmatically retrieve the consent parameter and add it to the pixel before firing. No segundo caso, que é mais comum e é descrito detalhadamente abaixo, os servidores de anúncios anexam os parâmetros de consentimento que recebem da Plataforma do lado do suprimento (SSP) ou dos servidores de anúncios do editor a todos os pixels.

O Audience Manager usa dois parâmetros para transmitir o consentimento do usuário em chamadas de pixel:

* `gdpr` pode ser 0 (RGPD não se aplica) ou 1 (RGPD se aplica);
* `gdpr_consent` é a sequência de caracteres de consentimento do RGPD com codificação base64 segura para URL (consulte a [especificação](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)). Uma amostra de chamada para um pixel de impressão, com os dois parâmetros, pode ser a seguinte:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

O caso de uso é descrito na imagem e nas etapas abaixo. Comece a partir da esquerda da imagem:

1. Seu usuário recebe uma impressão por meio de um servidor de anúncios. Isso se traduz em uma chamada de pixel para nossos servidores de coleta de dados (DCS).
1. O Audience Manager verifica se o sinalizador do RGPD se aplica. Caso contrário, o Audience Manager armazena os dados transmitidos nas variáveis de macro em chamadas de pixel.
1. Se a string de consentimento estiver presente e contiver as permissões necessárias, o Audience Manager armazenará os dados transmitidos nas variáveis de macro em chamadas de pixel.
1. Se a sequência de caracteres de consentimento estiver ausente ou não tiver as permissões necessárias, o Audience Manager soltará os dados transmitidos nas variáveis de macro em chamadas de pixel.

![Caso de uso do anunciante](assets/advertiser-use-case.png)

## Parceiros de ativação que oferecem suporte ao IAB TCF {#aam-activation-partners}

O Plug-in do Audience Manager para IAB TCF permite encaminhar a sequência de caracteres de consentimento TCF do IAB para parceiros de ativação, respeitando ao mesmo tempo as opções de privacidade dos usuários. Para obter informações sobre quais parceiros de ativação suportam o IAB TCF (preciso a partir de 7 de julho de 2019), consulte nossa folha **[Excel do](/help/using/overview/aam-gdpr/assets/AAM-Partners-October2019.xlsx)** Parceiro.

## Testar sua implementação IAB {#test-iab-implementation}

Para testar se você implementou corretamente o Plug-in do Audience Manager para IAB TCF, leia [Caso de uso 4 em Métodos de validação para aceitação e implementação](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html)IAB.

## IAB e cancelamento no Audience Manager. Ordem de precedência. {#iab-and-optout}

Outra opção de privacidade à disposição dos usuários é a capacidade de recusar toda a coleta de dados. Adobe provides users with the means to do so within the Your Privacy Choices page.[](https://www.adobe.com/privacy/opt-out.html#customeruse)

O Audience Manager aborda o gerenciamento de não participação em um artigo [separado em nossa documentação](/help/using/overview/data-security-and-privacy/opt-out-management.md).

>[!NOTE]
>
>**Ordem de precedência** - Se o usuário optar por não participar da coleta de dados usando uma ferramenta de opção global, conforme descrito no link acima, isso terá precedência sobre as verificações de aceitação e IAB.

## Recursos adicionais {#additional-resources}

* [Experience Cloud ID Service Opt-in](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [Estrutura de Transparência e Consentimento do RGPD da Europa IAB](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Especificações técnicas do IAB Europe RGPD Transparência e Estrutura de Consentimento](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF plugin - video demonstration](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)