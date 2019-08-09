---
description: A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da funcionalidade de Opt-in e pelo suporte à Estrutura de transparência e consentimento (TCF) do IAB. Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar tal suporte no Audience Manager.
seo-description: A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da funcionalidade de Opt-in e pelo suporte à Estrutura de transparência e consentimento (TCF) do IAB. Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar tal suporte no Audience Manager.
seo-title: Plug-in do Audience Manager para a Estrutura de consentimento do IAB
solution: Audience Manager
title: Plug-in do Audience Manager para a Estrutura de consentimento do IAB
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Plug-in do Audience Manager para a Estrutura de consentimento do IAB {#aam-iab-plugin}

## Visão geral

Um aspecto importante nas obrigações de privacidade que você tem em relação aos seus usuários é a aquisição e o transporte de opções de usuário sobre como os dados pessoais deles podem ser usados (ou seja, “finalidade”) e por quem (ou seja, “empresas”).

A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da [funcionalidade de Opt-in](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html) e pelo suporte à [Estrutura de transparência e consentimento (TCF) do IAB](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar tal suporte no Audience Manager. O Audience Manager está registrado no IAB TCF com a ID de fornecedor 565.

O plug-in do Audience Manager para IAB TCF utiliza a [funcionalidade de aceitação](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html), que é, por sua vez, parte da biblioteca do Serviço da [Adobe Experience Cloud ID (ECID)](https://marketing.adobe.com/resources/help/en_US/mcvid/) .

## Escopo e limitações {#scope-and-limitations}

Como Publicador ou Anunciante que trabalha com o Audience Manager, você pode transmitir opções de usuário para o Audience Manager como por IAB TCF. Isso oferece uma maneira fácil e consistente de comunicar opções de usuário a todos os parceiros com os quais você trabalha e o Audience Manager pode ajudá-lo a respeitar as opções de privacidade dos usuários.

O suporte para IAB TCF descrito neste artigo representa a primeira fase do suporte planejado do Audience Manager para a estrutura IAB. Atualmente, o Audience Manager não suporta:

* Fluxos de trabalho de dispositivos móveis;
* Gerenciamento de consentimento entre dispositivos;
* Anexar consentimento para urls enviados para [destinos de URL](/help/using/features/destinations/create-url-destination.md);
* Anexar consentimento para segmentos.

## Pré-requisitos {#prerequisites}

Você deve cumprir os seguintes pré-requisitos para usar o IAB TCF com o Audience Manager:

1. Você deve usar o serviço da Experience Cloud ID (ECID) versão 4.1 ou mais recente. [Baixe](https://github.com/Adobe-Marketing-Cloud/id-service/releases) a versão mais recente do ECID.
2. 
   1. Você deve usar a versão 9.0 ou mais recente da Biblioteca de integração de dados do Audience Manager (DIL), baixável [aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases). Leia sobre [o DIL na documentação do Audience Manager](/help/using/dil/dil-overview.md).
   2. Como alternativa, se você usar o Encaminhamento pelo lado do servidor (SSF) para importar dados para o Audience Manager, será necessário atualizar para a versão mais recente do appmeasurement. Baixe o appmeasurement usando o Gerenciador de código [do Analytics](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).
3. Você deve estar usando uma Plataforma de gerenciamento de aprovação (CMP), seja comercialmente ou sua própria, compatível com IAB e estará registrada com o IAB TCF. Consulte a lista [de cmps registrada na estrutura IAB](https://advertisingconsent.eu/cmp-list/).

## Recomendações e como implementar {#recommendations}

Para habilitar o suporte ao IAB TCF no Audience Manager, leia a nossa documentação sobre [como configurar o IAB com Aceitação](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html).

Isso é mais fácil de executar usando [o Adobe Launch](https://docs.adobelaunch.com/) para equiparar a aceitação ECID em suas propriedades. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## Fluxo de trabalho de escolha do usuário ao usar a estrutura IAB {#user-choice-workflow}

Ao visitar uma propriedade da Web, os usuários podem fornecer suas opções relacionadas à forma como seus dados serão usados pelo editor e pelos fornecedores terceirizados com os quais o editor trabalha. Os usuários fornecem suas opções na forma *de objetivos padrão* e permissões para fornecedores *terceirizados* registrados na lista de fornecedores globais. A imagem abaixo representa um exemplo de uma caixa de diálogo CMP, exibida para um visitante pela primeira vez de um site. Lembre-se de que essa caixa de diálogo pode parecer muito diferente, com base na implementação do cliente.

![Caixa de diálogo CMP](/help/using/overview/aam-gdpr/assets/cmp.png)

Os objetivos padrão na estrutura IAB são:

* Armazenamento e acesso de informações
* Personalização
* Seleção, entrega e relatório de anúncio
* Seleção, entrega e relatório de conteúdo
* Medição

Consulte a página de especificação da estrutura [IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) para obter uma descrição dos cinco objetivos padrão.

Os usuários podem conceder seu consentimento para uma combinação de objetivos padrão e fornecedores. Por exemplo, os usuários podem conceder seu consentimento para armazenamento, personalização e medição e conceder seu consentimento a todos os fornecedores de terceiros exibidos pelo CMP. Ou, em outro exemplo, eles podem conceder seu consentimento para todos os cinco objetivos padrão, mas conceder somente consentimento a alguns fornecedores exibidos pelo CMP.

Depois que o usuário seleciona suas opções de privacidade, as opções do usuário são gravadas na string de consentimento do IAB TCF. A sequência de consentimento do IAB TCF armazena a combinação de finalidades e fornecedores aprovados, juntamente com outras informações de metadados (consulte a página [IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) para obter mais informações). Cada fornecedor registrado no IAB TCF avalia a string de consentimento IAB e faz decisões com base nas opções de privacidade dos usuários. Lembre-se de que as opções de privacidade dos usuários são válidas em todos os fornecedores aprovados.

## Objetivos padrão exigidos pelo Audience Manager {#aam-standard-purposes}

O Audience Manager avalia as opções dos usuários armazenadas na string de consentimento IAB TFC para:

* Armazenamento e acesso de informações (ID 1 da lista de fornecedores [global](https://vendorlist.consensu.org/vendorlist.json))
* Personalização (ID da finalidade 2)
* Medição (ID da finalidade 5)
* Consentimento do fornecedor do Audience Manager para armazenar, processar ou ativar em dados para um editor.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## O comportamento do Audience Manager depende de se o usuário concede consentimento {#aam-behavior-consent}

O Audience Manager funciona de forma diferente dependendo se o Audience Manager detecta a sequência de consentimento do IAB TCF que o usuário forneceu para os três fins (armazenamento, personalização, medição) ou não.

| Quando o usuário *fornecer o consentimento*, o Audience Manager: | Quando o usuário *recusa* o consentimento, o Audience Manager: |
|---|---|
| <ul><li>Executa todos os casos de uso do Audience Manager que você solicitou.</li><li>Transmite consentimento para terceiros em sincronizações de ID (passando rgpts = 1 e a sequência de consentimento como giro_ consentimento em chamadas sincronizadas de ID).</li><li>Avalia e aceita o consentimento passado dos pixels do servidor de anúncios.</li><li>Cumpre sincronizações de ID iniciada pelo parceiro.</li></ul> | <ul><li>Não armazena nenhum novo dado de usuário na sua instância. Isso inclui IDs de parceiro, sinais, características ou dados de pixel.</li><li>Não inicia sincronizações de ID de terceiros.</li><li>Não aceita sincronizações de ID iniciada pelo parceiro.</li></ul> |



## Caso de uso do editor {#publisher-use-case}

Ao implementar o IAB TCF, não é necessário manter o código personalizado para o gerenciamento de consentimento nas suas propriedades da Web por meio de um mecanismo diferente com a Adobe ou outros fornecedores de terceiros. O caso de uso é descrito na imagem e nas etapas abaixo. Inicie à esquerda da imagem:

1. Um usuário visita uma das propriedades da Web. Contanto que esteja usando as versões mais recentes das bibliotecas ECID e DIL (consulte [Pré-requisitos](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites)), o fluxo de aceitação é acionado.
2. O Audience Manager verifica se o fluxo do IAB se aplica (`isIabContext=true`). Consulte [Recomendações e como implementar](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations).
3. O Audience Manager verifica se o RGPD se aplica (`gdpr = 1`) e se há um CMP, registrado com IAB, em sua propriedade da Web. Por exemplo, isso se aplica a usuários que visitam a partir da área da União Europeia. Observe que é sua responsabilidade como editor definir o sinalizador RGPD.
4. Se o RGPD for aplicado, o Audience Manager verificará a string de consentimento IAB, transmitida no parâmetro `gdpr_consent`, para as permissões necessárias. O Audience Manager requer permissões para armazenamento, personalização, medição, mais consentimento do fornecedor do Audience Manager, para armazenar, processar ou ativar dados.
5. Se a sequência de consentimento do IAB TCF estiver presente e contiver as permissões necessárias, o Audience Manager transmite a string de consentimento do IAB para nossos [servidores de coleta de dados](/help/using/reference/system-components/components-data-collection.md) (DCS).
6. O Audience Manager responde definindo um [cookie demdex](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) no navegador. O Audience Manager também inicia e respeita sincronizações de ID de terceiros.
7. Como alternativa, se a sequência de consentimento do IAB TCF transmitida na etapa 5 não contiver todas as permissões necessárias, o Audience Manager não coletará, processará ou ativará dados e não seguirá ou iniciará sincronizações de ID.

![Caso de uso do editor](assets/publisher-use-case.png)

## Caso de uso do anunciante {#advertiser-use-case}

O Audience Manager avalia e aceita o consentimento transmitido em [chamadas de pixel](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md), de acordo com o IAB TCF.

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

## Parceiros de ativação compatíveis com o IAB TCF {#aam-activation-partners}

O plug-in do Audience Manager para IAB TCF permite que você encaminhe a string de consentimento IAB para parceiros de ativação respeitando as opções de privacidade dos usuários. Para obter informações sobre quais parceiros de ativação suportam TCF IAB (precisa desde 7 de julho de 2019), consulte a **[planilha do Excel do parceiro](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx)**.

## Teste da implementação do IAB {#test-iab-implementation}

Para testar se implementou corretamente o plug-in do Audience Manager para IAB TCF, leia Caso [de uso 4 em Métodos de validação para implementação de aceitação e IAB](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html).

## IAB e Opt-out no Audience Manager. Ordem de prioridade. {#iab-and-optout}

Outra opção de privacidade da disposição dos usuários é a capacidade de recusar toda a coleta de dados. A Adobe fornece aos usuários os meios para fazer isso na página [Suas Opções](https://www.adobe.com/privacy/opt-out.html#customeruse) de Privacidade.

O Audience Manager aborda o gerenciamento de não participação em um artigo [separado em nossa documentação](/help/using/overview/data-security-and-privacy/opt-out-management.md).

>[!NOTE]
>
>**Ordem de prioridade** - se o usuário optar por fora da coleta de dados usando uma ferramenta de não participação global, conforme descrito no link acima, isso terá precedência sobre as verificações de participação e IAB.

## Recursos adicionais {#additional-resources}

* [Aceitação do serviço da Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB Europe RPTRANSPARENCY e Framework Framework](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe RPR Transparency and Approval Framework Technical](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Plug-plugin IAB TCF - demonstração de vídeo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)