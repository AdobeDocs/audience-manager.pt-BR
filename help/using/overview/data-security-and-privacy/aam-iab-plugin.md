---
description: A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da funcionalidade de Opt-in e pelo suporte à Estrutura de transparência e consentimento (TCF) do IAB. Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar tal suporte no Audience Manager.
seo-description: A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da funcionalidade de Opt-in e pelo suporte à Estrutura de transparência e consentimento (TCF) do IAB. Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar tal suporte no Audience Manager.
seo-title: Plug-in do Audience Manager para a Estrutura de consentimento do IAB
solution: Audience Manager
title: Plug-in do Audience Manager para a Estrutura de consentimento do IAB
translation-type: tm+mt
source-git-commit: 40e30379f051398a5f6c8ee7db49b6c5c5e146cd
workflow-type: tm+mt
source-wordcount: '2449'
ht-degree: 7%

---


# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## Visão geral

Um aspecto importante das obrigações de privacidade que você pode ter para com seus usuários é a aquisição e a transmissão de escolhas do usuário sobre como seus dados pessoais podem ser usados (ou seja, &quot;fins&quot;) e por quem (ou seja, &quot;empresas&quot;).

A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da [funcionalidade de Opt-in](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) e pelo suporte à [Estrutura de transparência e consentimento (TCF) do IAB](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar tal suporte no Audience Manager.

>[!IMPORTANT]
>
>O Audience Manager está registrado no TCF [IAB](https://iabeurope.eu/tcf-for-vendors/) com a ID do fornecedor 565.

O Plug-in de Audience Manager para IAB TCF utiliza a funcionalidade [de](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html)aceitação, que, por sua vez, faz parte da biblioteca do [Adobe Experience Platform Identity Service (ECID)](https://docs.adobe.com/content/help/en/id-service/using/home.html) .

## Âmbito e limitações {#scope-and-limitations}

Como um Editor ou Anunciante trabalhando com o Audience Manager, você pode transmitir as opções do usuário para o Audience Manager de acordo com o TCF da IAB.

>[!IMPORTANT]
>
>Os regulamentos relativos ao TCF da IAB aplicam-se apenas aos visitantes localizados no Espaço Econômico Europeu.

O Audience Manager ajuda você a respeitar as opções de privacidade dos usuários e também fornece uma maneira fácil de comunicar essas opções a todos os parceiros com os quais você trabalha.

Atualmente, o Audience Manager não suporta:

* workflows para dispositivos móveis;
* Anexar consentimento às exportações de segmento.

## Atualizando para [!DNL IAB TCF v2.0] {#upgrading}

Os clientes que estão atualizando sua [!DNL Audience Manager Plug-in for IAB TCF] implementação da [!DNL IAB TCF] v1.1 para a [!DNL IAB TCF] v2.0 ou ativando a [!DNL IAB TCF] v2.0 pela primeira vez devem seguir as mesmas diretrizes sobre pré-requisitos e implementação, conforme descrito abaixo.

## Pré-requisitos {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager suporta IAB TCF v2.0.
>
>O suporte ao IAB TCF v1.1 terminará em 15 de agosto de 2020.
>
> Os clientes que desejarem continuar usando o Plug-in Audience Manager para IAB TCF para gerenciamento de consentimento devem atualizar para a versão mais recente do [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) para suporte contínuo.
>
> Após a atualização para a versão [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) mais recente, as sequências de caracteres de consentimento IAB TCF v1.1 não serão mais suportadas, portanto, atualize seu CMP antes de atualizar para a versão mais recente do ECID.

Você deve atender aos seguintes pré-requisitos para usar o Plug-in Audience Manager para IAB TCF com Audience Manager:

1. Você deve usar o Adobe Experience Platform Identity Service (ECID) versão 5 ou mais recente. [Baixe](https://github.com/Adobe-Marketing-Cloud/id-service/releases) nossa versão mais recente do ECID.
2. Você deve estar usando o Audience Manager [!DNL Data Integration Library] (DIL) versão 9.0 ou mais recente, disponível para download [aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases). Leia sobre o [DIL na documentação](../..//dil/dil-overview.md)do Audience Manager. Recomendamos usar o [Adobe Launch](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html) para a implementação mais fácil do DIL para o Audience Manager.
3. Como alternativa, se você usar [!DNL Server-Side Forwarding] (SSF) para importar dados para o Audience Manager, precisará atualizar para a versão mais recente do AppMeasurement. Baixe o AppMeasurement usando o Gerenciador [de código da](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)Analytics.
4. Você deve usar um Platform de gerenciamento de consentimento (CMP), comercial ou próprio, integrado ao IAB TCF v2.0 e registrado no IAB TCF. Consulte a lista de [CMPs registrados na estrutura](https://iabeurope.eu/cmp-list/)IAB.

>[!WARNING]
>
>Se você estiver usando um Platform de Gerenciamento de Consentimento (CMP) que não suporta IAB TCF v.2.0, o Audience Manager enviará automaticamente o `gdpr=0` parâmetro em sincronizações de ID, mesmo se os visitantes estiverem na União europeia. Para determinar se sua validação do RGPD está ativa, recomendamos que você confirme com seu Platform de gerenciamento de consentimento (CMP) que eles suportam o IAB TCF v2.0.

## Recomendações e como implementar {#recommendations}

Para ativar o suporte ao TCF IAB no Audience Manager, leia a nossa documentação sobre [como configurar o IAB com a opção de participação](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html).

A maneira mais fácil de fazer isso é usando o [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) para adicionar [!DNL ECID Opt-in] suas propriedades. Read the documentation for the [ECID Opt-in extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html) to learn how to set up the Launch extension.

## Fluxo de trabalho de escolha do usuário ao usar a estrutura IAB {#user-choice-workflow}

Ao visitar uma propriedade da Web, os usuários podem fornecer suas opções sobre como seus dados devem ser usados pelo editor e pelos fornecedores de terceiros com os quais o editor trabalha.

Os usuários fornecem suas opções na forma de *consentimento* e interesse ** legítimo para os fins IAB a fornecedores ** terceiros registrados na lista do fornecedor global.

A imagem abaixo representa um exemplo de uma caixa de diálogo CMP, exibida em um visitante pela primeira vez de um site. Lembre-se de que essa caixa de diálogo pode parecer muito diferente, com base na implementação do cliente.

![Caixa de diálogo CMP](assets/cmp-example.png)

Os detalhes sobre os vários objetivos e permissões incluídos no IAB TCF v2.0 são abordados nas Políticas [](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)IAB Europe Transparency &amp; Consent Framework.

Os usuários podem conceder seu consentimento ou interesse legítimo (se disponível) para uma combinação de finalidades e fornecedores. Por exemplo, os usuários podem conceder seu consentimento para armazenar informações em um dispositivo, desenvolver e melhorar produtos e conceder seu consentimento a todos os fornecedores de terceiros exibidos pelo CMP.

Ou, num outro exemplo, poderiam conceder o seu consentimento ou o seu interesse legítimo para todos os fins, mas apenas conceder o consentimento ou o interesse legítimo a alguns dos fornecedores expostos pelo CMP.

Depois que o usuário seleciona suas opções de privacidade, as opções do usuário são registradas na string IAB TC. A string IAB TC armazena a combinação de finalidades e fornecedores aprovados, juntamente com outras informações de metadados (consulte a página [](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) IAB para obter mais informações).

Todos os fornecedores registrados no IAB TCF avaliam a sequência de caracteres IAB TC e tomam decisões com base nas opções de privacidade dos usuários. Lembre-se de que as opções de privacidade dos usuários são válidas em todos os fornecedores registrados com IAB TCF.

## Finalidades exigidas pelo Audience Manager {#aam-standard-purposes}

O Audience Manager avalia as opções dos usuários armazenadas na sequência de caracteres IAB TC para os seguintes fins, definidos nas Políticas [](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)IAB Europe Transparency &amp; Consent Framework. Além disso, você também pode encontrar os propósitos na lista [do fornecedor](https://vendorlist.consensu.org/vendorlist.json)global.

* **Finalidade 1**: Armazenar e/ou aceder a informações num dispositivo;
* **Finalidade 10**: Desenvolver e melhorar os produtos;
* **Finalidade especial 1**: Garanta a segurança, evite fraudes e depure.

>[!IMPORTANT]
>
>A Audience Manager precisa de consentimento para o Objetivo 1 e o Objetivo 10, além do consentimento do fornecedor, para implantar cookies e iniciar ou honrar sincronizações de ID.
>
>De acordo com os regulamentos [da](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_)IAB, o Especial 1 (Garanta a segurança, previne fraudes e depura) é sempre aceito e os usuários não podem se opor a isso.

## O comportamento de Audience Manager depende se o usuário concede consentimento {#aam-behavior-consent}

O Audience Manager funciona de forma diferente dependendo se a sequência de caracteres IAB TC inclui o consentimento do usuário para os dois fins (armazenar e/ou acessar informações em um dispositivo e desenvolver e melhorar produtos) ou não.

Também verificamos o consentimento do usuário para todos os destinos com os quais você trabalha no Audience Manager, desde que esses destinos estejam registrados no IAB TCF.

| Quando seu usuário *fornece consentimento*, Audience Manager: | Quando o usuário *recusar* o consentimento, Audience Manager: |
|---|---|
| <ul><li>Executa todos os casos de Audience Manager que você solicitou.</li><li>Transmite o consentimento a terceiros em sincronizações de ID (passando `gdpr = 1` e a sequência de caracteres de consentimento como `gdpr_consent` em chamadas de sincronização de ID).</li><li>Avalia e respeita o consentimento passado dos pixels do servidor de publicidade.</li><li>Honra sincronizações de ID iniciadas pelo parceiro.</li></ul> | <ul><li>Não armazena dados novos do usuário na sua instância. Isso inclui IDs de parceiros, sinais, características ou dados de pixel.</li><li>Não inicia sincronizações de ID de terceiros.</li><li>Não aceita sincronizações de ID iniciadas pelo parceiro.</li><li>Opt out o usuário de mais coleta de dados.</li></ul> |

## Caso de uso do editor {#publisher-use-case}

Ao implementar o Plug-in de Audience Manager para IAB TCF, você não é obrigado a manter o código personalizado para gerenciamento de consentimento em suas propriedades da Web por meio de um mecanismo diferente com a Adobe ou outros fornecedores de terceiros. O caso de uso é descrito na imagem e nas etapas abaixo. Start à esquerda da imagem:

1. Um usuário visita uma de suas propriedades da Web. Desde que você esteja usando as versões mais recentes das bibliotecas ECID e DIL (consulte [Pré-requisitos](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), o fluxo de aceitação é acionado.
2. O Audience Manager verifica se o fluxo IAB se aplica (`isIabContext=true`). Consulte [Recomendações e como implementar](aam-iab-plugin.md#recommendations).
3. A Audience Manager verifica se o RGPD se aplica (`gdpr = 1`) e se existe um CMP, registrado com o IAB TCF, na propriedade da Web. Por exemplo, tal aplicar-se-ia aos utilizadores que visitam a União europeia. Observe que é sua responsabilidade, como editor, definir o sinalizador do RGPD.
4. Se o RGPD for aplicado, o Audience Manager verifica a string IAB TC, transmitida no `gdpr_consent` parâmetro, para obter o consentimento necessário. O Audience Manager precisa de consentimento para armazenar e/ou acessar informações em um dispositivo (finalidade 1[do TCF da](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)IAB), desenvolver e melhorar produtos (finalidade 10[do TCF da](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)IAB), além do consentimento do fornecedor do Audience Manager para armazenar, processar ou ativar dados.
5. Se a sequência de caracteres TC IAB estiver presente e contiver o consentimento necessário, o Audience Manager passará a sequência de caracteres TC IAB para nossos servidores [de coleta de](../../reference/system-components/components-data-collection.md) dados (DCS).
6. O Audience Manager responde configurando um cookie [](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) demdex no navegador e inicia e honra sincronizações de ID de terceiros.
7. Como alternativa, se a sequência de caracteres TC IAB transmitida na etapa 4 não contiver todas as permissões necessárias, o Audience Manager não coletará, processará ou ativará quaisquer dados do usuário e não honrará ou iniciará sincronizações de ID. Além disso, ele opt out o usuário dos destinos com os quais você trabalha.

>[!IMPORTANT]
>
>Se você estiver trabalhando com parceiros de destino de Audience Manager que exigem parâmetros TCF da IAB, mas você não tiver um CMP compatível com IAB TCF em seu site, o Audience Manager enviará `gdpr=0` sincronizações de ID. Isso significa que o RGPD não se aplica a esses usuários.
>
> Se isso não for desejado, ative a funcionalidade TCF IAB no Audience Manager para enviar as strings TC IAB apropriadas aos parceiros de destino.



![Caso de uso do editor](assets/publisher-use-case.png)

## Caso de uso do anunciante {#advertiser-use-case}

A Audience Manager avalia e honra o consentimento passado em chamadas [de](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)pixel, de acordo com o TCF da IAB.

Os pixels podem ser colocados pelos clientes do Audience Manager em suas páginas de parceiros ou são colocados nos servidores de anúncios para inclusão na resposta do anúncio. No primeiro caso, seu parceiro deve recuperar programaticamente o parâmetro de consentimento e adicioná-lo ao pixel antes de disparar. No segundo caso, que é mais comum e é descrito detalhadamente abaixo, os servidores de publicidade anexam os parâmetros de consentimento que recebem do Supply-Side Platform (SSP) ou dos servidores de anúncios do editor a todos os pixels.

O Audience Manager usa dois parâmetros para passar o consentimento do usuário em chamadas de pixel:

* `gdpr` pode ser 0 (RGPD não se aplica) ou 1 (RGPD se aplica);
* `gdpr_consent` é a sequência de caracteres de consentimento do RGPD com codificação base64 segura para URL (consulte a [especificação](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Uma amostra de chamada para um pixel de impressão, com os dois parâmetros, pode ser a seguinte:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

O caso de uso é descrito na imagem e nas etapas abaixo. Start à esquerda da imagem:

1. Seu usuário recebe uma impressão por meio de um servidor de anúncios. Isso se traduz em uma chamada [de](../../integration/media-data-integration/impression-data-pixels.md) pixel para nossos servidores de coleta de dados (DCS).
2. Audience Manager verifica se o indicador do RGPD se aplica. Caso contrário, o Audience Manager armazena os dados transmitidos nas variáveis `gdpr` e `gdpr_consent` em chamadas de pixel.
3. Se a string IAB TC estiver presente e contiver as permissões necessárias, o Audience Manager armazenará os dados transmitidos nas variáveis `gdpr` e `gdpr_consent` nas chamadas de pixel.
4. Se a sequência de caracteres TC IAB estiver ausente ou não tiver as permissões necessárias, o Audience Manager ignorará os dados transmitidos nas variáveis `gdpr` e `gdpr_consent` nas chamadas de pixel.

![Caso de uso do anunciante](assets/advertiser-use-case.png)

## Parceiros Ativações que oferecem suporte ao IAB TCF {#aam-activation-partners}

O Plug-in de Audience Manager para IAB TCF permite encaminhar a sequência de caracteres IAB TC para parceiros de ativação respeitando as opções de privacidade dos usuários. Para obter informações sobre quais parceiros de ativações suportam o TCF da IAB, consulte nossa [lista de destinos](/help/using/features/destinations/device-based-destinations-list.md)baseados em dispositivos.

## Acrescentar consentimento a URLs enviados para destinos de URL

A integração do Audience Manager com o IAB TCF v2.0 suporta o anexo de consentimento às informações enviadas para destinos [de](../../features/destinations/create-url-destination.md) URL que são integrados com o IAB TCF v2.0. No entanto, esse processo não é feito automaticamente por Audience Manager, para evitar a quebra de formatos de URL específicos.

Os clientes que desejam anexar o consentimento aos dados enviados [!DNL URL destinations] devem adicionar manualmente as macros `${GDPR}` e `${GDPR_CONSENT_XXXX}` macros ao formato do URL, substituindo `XXXX` pela ID do parceiro de destino.

Exemplo: `http://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Consulte Macros de [destino definidas](../../features/destinations/destination-macros.md) para obter mais detalhes sobre as macros de destino suportadas.

## Gerenciamento de consentimento entre dispositivos

O Plug-in de Audience Manager para IAB TCF opt out automaticamente as IDs presentes em uma solicitação, quando os visitantes do site não fornecem as permissões apropriadas. Se a solicitação contiver uma ID de dispositivo [cruzado (ID CRM)](../../reference/ids-in-aam.md), o Audience Manager opt out a ID, juntamente com o último dispositivo vinculado a essa ID de dispositivo [cruzado (ID CRM)](../../reference/ids-in-aam.md).

## Testar sua implementação IAB {#test-iab-implementation}

Para testar se você implementou corretamente o Plug-in de Audience Manager para IAB TCF, leia [Caso de uso 4 em Validação do serviço](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88)de aceitação.

## IAB e opção de não participação no Audience Manager. Ordem de precedência. {#iab-and-optout}

Outra opção de privacidade à disposição dos usuários é a capacidade de opt out toda a coleta de dados. A Adobe fornece aos usuários os meios para fazer isso na página [Suas escolhas](https://www.adobe.com/privacy/opt-out.html#customeruse) de privacidade.

O Audience Manager atende às solicitações de recusa em um artigo [separado em nossa documentação](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Os usuários que forem opt out de toda a coleta de dados depois que recusarem o consentimento, não poderão ser aceitos novamente.

>[!NOTE]
>
>**Ordem de precedência** - Se o usuário opt out da coleta de dados usando uma ferramenta de opção de não participação global, conforme descrito no link acima, isso terá precedência sobre as verificações de aceitação e IAB.

## Recursos adicionais {#additional-resources}

* [Aceitação do serviço de identidade do Adobe Experience Platform](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [Estrutura de Transparência e Consentimento do RGPD da Europa IAB](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Especificações técnicas do IAB Europe RGPD Transparência e Estrutura de Consentimento](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Plug-in IAB TCF - demonstração de vídeo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)