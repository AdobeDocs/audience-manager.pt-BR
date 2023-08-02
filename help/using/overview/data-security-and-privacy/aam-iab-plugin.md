---
description: A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da funcionalidade de aceitação e pelo suporte à Estrutura de transparência e consentimento (TCF) do IAB. Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar o suporte no Audience Manager.
seo-description: Adobe provides you with the means to manage and communicate your users' privacy choices through the Opt-in functionality and through IAB Transparency and Consent Framework (TCF) support. This article describes the Audience Manager use cases that support the IAB TCF and how to implement IAB TCF support in Audience Manager.
seo-title: Audience Manager Plug-in for IAB TCF
solution: Audience Manager
title: Plug-in do Audience Manager para a TCF do IAB
feature: Data Governance & Privacy
exl-id: aa6bc415-e52b-4900-951d-ccf51d907aa2
source-git-commit: 8b370a64d80b40124abee91351cbef09711243d4
workflow-type: tm+mt
source-wordcount: '2353'
ht-degree: 34%

---

# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## Visão geral

Um aspecto importante nas obrigações de privacidade que você pode ter em relação aos seus usuários é a aquisição e o transporte de opções de usuário sobre como os dados pessoais deles podem ser usados (ou seja, &quot;finalidade&quot;) e por quem (ou seja, &quot;empresas&quot;).

A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da [funcionalidade de aceitação](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html) e pelo suporte à [Estrutura de transparência e consentimento (TCF) do IAB](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar o suporte no Audience Manager.

>[!IMPORTANT]
>
>Audience Manager está registrado na [TCF do IAB](https://iabeurope.eu/tcf-for-vendors/) com a ID de fornecedor 565.

O Plug-in do Audience Manager para a TCF do IAB utiliza a [Funcionalidade de aceitação](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html), que, por sua vez, faz parte da biblioteca do [ Experience Platform Identity Service (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html).

## Escopo e limitações {#scope-and-limitations}

Como Editor ou Anunciante trabalhando com o Audience Manager, você pode transmitir as opções do usuário ao Audience Manager de acordo com a TCF do IAB.

>[!IMPORTANT]
>
>Os regulamentos da TCF do IAB se aplicam apenas aos visitantes localizados no Espaço Econômico Europeu.

O Audience Manager ajuda você a respeitar as opções de privacidade dos usuários e também oferece uma maneira fácil de comunicar essas opções a todos os parceiros com quem você trabalha.

Atualmente, o Audience Manager não oferece suporte a/à:

* fluxos de trabalho para dispositivos móveis;
* Anexação de consentimento às exportações de segmento.

## Atualizando para [!DNL IAB TCF v2.2] {#upgrading}

Clientes que estão atualizando seus [!DNL Audience Manager Plug-in for IAB TCF] implementação de [!DNL IAB TCF] v1.1 para [!DNL IAB TCF] v2.2 ou ativando [!DNL IAB TCF] A v2.2 pela primeira vez deve seguir as mesmas diretrizes de pré-requisitos e implementação descritas abaixo.

## Pré-requisitos {#prerequisites}

>[!IMPORTANT]
>
>O Audience Manager suporta IAB TCF v2.2.
>
>O suporte à IAB TCF v1.1 terminará em 15 de agosto de 2020.
>
> Os clientes que desejam continuar usando o plug-in do Audience Manager para a TCF do IAB para gerenciamento de consentimento devem atualizar para a versão mais recente do [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) para suporte contínuo.
>
> Depois de atualizar para a versão mais recente [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) da versão, as cadeias de consentimento da TCF do IAB v1.1 não serão mais compatíveis, portanto, atualize seu CMP antes de atualizar para a versão mais recente do ECID.

Você deve atender aos seguintes pré-requisitos para usar o Plug-in do Audience Manager para TCF do IAB com o Audience Manager:

1. Você deve usar o Adobe Experience Platform Identity Service (ECID) versão 5 ou mais recente. [Baixe](https://github.com/Adobe-Marketing-Cloud/id-service/releases) a versão mais recente do ECID.
2. Você deve usar o Audience Manager [!DNL Data Integration Library] (DIL) versão 9.0 ou mais recente, disponível para download em [aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases). Leia sobre a [DIL na documentação do Audience Manager](../../dil/dil-overview.md). Recomendamos usar o [Extensão de tag do Adobe Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) para a implementação mais fácil de DIL do Audience Manager.
3. Como alternativa, se você usar [!DNL Server-Side Forwarding] (SSF) para importar dados para o Audience Manager, você deve atualizar para a versão mais recente do AppMeasurement. Baixe o AppMeasurement usando o [Gerenciador de código do Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).
4. Você deve usar uma Plataforma de gerenciamento de consentimento (CMP), comercial ou própria, integrada à TCF do IAB v2.2 e registrada junto à TCF do IAB. Consulte a lista de [CMPs registradas junto à estrutura do IAB](https://iabeurope.eu/cmp-list/).

>[!WARNING]
>
>Se você estiver usando uma Plataforma de gerenciamento de consentimento (CMP) que não seja compatível com IAB TCF v2.2, o Audience Manager enviará automaticamente a `gdpr=0` nas sincronizações de ID, mesmo se os visitantes estiverem na União Europeia. Para determinar se a validação do GDPR está ativa, recomendamos que você confirme com sua Plataforma de gerenciamento de consentimento (CMP) se ela é compatível com a TCF do IAB v2.2.

## Recomendações e como implementar {#recommendations}

Para ativar o suporte à TCF do IAB no Audience Manager, leia nossa documentação sobre [como configurar o IAB com a opção de aceitação](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html).

A maneira mais fácil de fazer isso é usando [Tags do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) para adicionar [!DNL ECID Opt-in] em suas propriedades. Leia a documentação do [Extensão de Opt-in ECID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html) para saber como configurar a extensão Tags.

## Fluxo de trabalho escolhido pelo usuário ao usar a estrutura do IAB {#user-choice-workflow}

Ao visitar uma propriedade da Web, os usuários podem dizer como querem que seus dados devem ser usados pelo editor e pelos fornecedores de terceiros com quem o editor trabalha.

Os usuários informam suas opções na forma de *consentimento* para efeitos do CAI, *fornecedores de terceiros* registrado na lista global de fornecedores.

A imagem abaixo representa um exemplo de uma caixa de diálogo da CMP, exibida em um visitante novo de um site. Lembre-se de que essa caixa de diálogo pode variar bastante de acordo com a implementação do cliente.

![Caixa de diálogo da CMP](assets/cmp-example.png)

Detalhes sobre as várias finalidades e permissões incluídas no IAB TCF v2.2 são abordados na [Políticas da Estrutura de transparência e consentimento do IAB Europa](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Os usuários podem consentir com uma combinação de finalidades e fornecedores. Por exemplo, os usuários podem consentir com o armazenamento de informações em um dispositivo, o desenvolvimento e o aprimoramento de produtos e consentir com todos os fornecedores de terceiros exibidos pela CMP.

Ou, em outro exemplo, eles poderiam consentir com todas as finalidades, mas apenas consentir com alguns dos fornecedores exibidos pela CMP.

Depois que o usuário seleciona suas opções de privacidade, elas são registradas na cadeia de caracteres TC do IAB. A cadeia de caracteres IAB TC armazena a combinação de finalidades e fornecedores aprovados, juntamente com outras informações de metadados (consulte a [página IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) para obter mais informações).

Todos os fornecedores registrados na TCF do IAB avaliam a cadeia de caracteres da TC do IAB e tomam decisões com base nas opções de privacidade dos usuários. Lembre-se de que as opções de privacidade dos usuários são válidas para todos os fornecedores registrados na TCF do IAB.

## Finalidades exigidas pelo Audience Manager {#aam-standard-purposes}

O Audience Manager avalia as opções dos usuários armazenadas na string TC do IAB para as seguintes finalidades, definidas no [Políticas da Estrutura de transparência e consentimento do IAB Europa](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Appendix_A_Purposes_and_Features_Definitions).

* **Finalidade 1**: armazenar e/ou acessar informações em um dispositivo;
* **Finalidade 10**: desenvolver e melhorar os produtos;
* **Propósito Especial 1**: garanta a segurança, evite fraudes e depure.

>[!IMPORTANT]
>
>O Audience Manager exige consentimento para Finalidade 1 e Finalidade 10 além do consentimento do fornecedor para implantar cookies e iniciar ou honrar as sincronizações de ID.
>
>Por [Regulamentos do IAB](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_), Special Purpose 1 (Verifique a segurança, evite fraudes e depure) é sempre aceito e os usuários não podem se opor a isso.

## O comportamento do Audience Manager depende do consentimento do usuário {#aam-behavior-consent}

O Audience Manager funciona de forma diferente se a string IAB TC incluir o consentimento do usuário para as duas finalidades (armazenar e/ou acessar informações em um dispositivo e desenvolver e melhorar produtos) ou não.

Também verificamos o consentimento do usuário para todos os destinos com os quais você trabalha no Audience Manager, desde que esses destinos estejam registrados com a TCF do IAB.

| Quando o usuário *consente*, o Audience Manager: | Quando o usuário *não consente*, o Audience Manager: |
|---|---|
| <ul><li>Executa todos os casos de uso do Audience Manager solicitados.</li><li>Transmite o consentimento a terceiros em sincronizações de ID (transmitindo `gdpr = 1` e a sequência de consentimento como `gdpr_consent` em chamadas de sincronização de ID).</li><li>Avalia e respeita o consentimento passado dos pixels do servidor de publicidade.</li><li>Respeita sincronizações de ID iniciadas pelo parceiro.</li></ul> | <ul><li>Não armazena dados novos do usuário na sua instância, inclusive IDs de parceiros, sinais, características ou dados de pixel.</li><li>Não inicia sincronizações de ID de terceiros.</li><li>Não respeita sincronizações de ID iniciadas pelo parceiro.</li><li>Exclui o usuário da coleta de dados adicional.</li></ul> |

## Caso de uso do editor {#publisher-use-case}

Ao implementar o Plug-in do Audience Manager para a TCF do IAB, você não é obrigado a manter o código personalizado para gerenciamento de consentimento nas suas propriedades da Web por meio de um mecanismo diferente com o Adobe ou outros fornecedores de terceiros. O caso de uso é descrito na imagem e nas etapas abaixo. Início à esquerda da imagem:

1. Um usuário visita uma de suas propriedades da Web. Desde que você esteja usando as versões mais recentes da ECID e bibliotecas DIL (consulte [Pré-requisitos](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), o fluxo de aceitação é acionado.
2. O Audience Manager verifica se o fluxo do IAB se aplica (`isIabContext=true`). Consulte [Recomendações e como implementar](aam-iab-plugin.md#recommendations).
3. O Audience Manager verifica se o GDPR se aplica (`gdpr = 1`) e se há uma CMP, registrada junto à TCF do IAB, na propriedade da Web. Por exemplo, isso se aplicaria a usuários que visitam a União Europeia. Observe que, como editor, você é responsável pela definição do sinalizador do GDPR.
4. Se o GDPR se aplicar, o Audience Manager verificará a cadeia de caracteres TC do IAB, transmitida no `gdpr_consent` parâmetro, para o consentimento necessário. O Audience Manager precisa de consentimento para armazenar e/ou acessar informações em um dispositivo ([IAB TCF finalidade 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), desenvolvimento e melhoria dos produtos ([Finalidade 10 da TCF do IAB](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), além do consentimento do fornecedor Audience Manager para armazenar, processar ou ativar dados.
5. Se a string IAB TC estiver presente e tiver o consentimento necessário, o Audience Manager transmitirá a string IAB TC para o nosso [servidores de coleção de dados](../../reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager responde definindo um [cookie demdex](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html) no navegador, e inicia e respeita sincronizações de ID de terceiros.
7. Como alternativa, se a cadeia de caracteres IAB TC transmitida na etapa 4 não tiver todas as permissões necessárias, o Audience Manager não coletará, processará ou ativará dados do usuário e não respeitará ou iniciará sincronizações de ID. Além disso, ele exclui o usuário dos destinos com os quais você trabalha.

>[!IMPORTANT]
>
>Se você estiver trabalhando com parceiros de destino de Audience Manager que exigem parâmetros da TCF do IAB, mas não tiver uma CMP compatível com a TCF do IAB em seu site, o Audience Manager enviará `gdpr=0` em sincronizações de ID. Isso significa que o GDPR não se aplica a esses usuários.
>
> Se isso não for desejado, você deve ativar a funcionalidade da TCF do IAB no Audience Manager para enviar as strings da TC do IAB apropriadas para os parceiros de destino.



![Caso de uso do editor](assets/publisher-use-case.png)

## Caso de uso do anunciante {#advertiser-use-case}

O Audience Manager avalia e respeita o consentimento transmitido em [chamadas de pixel](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md), de acordo com a TCF do IAB.

Os pixels podem ser colocados por clientes do Audience Manager em suas páginas de parceiros ou em servidores de anúncios para inclusão na resposta do anúncio. No primeiro caso, o parceiro deve recuperar programaticamente o parâmetro de consentimento e adicioná-lo ao pixel antes de disparar. No segundo caso, que é mais comum e é descrito detalhadamente abaixo, os servidores de anúncios anexam os parâmetros de consentimento que recebem da Plataforma do lado do suprimento (SSP) ou dos servidores de anúncios do editor a todos os pixels.

O Audience Manager usa dois parâmetros para transmitir o consentimento do usuário em chamadas de pixel:

* `gdpr` pode ser 0 (o GDPR não se aplica) ou 1 (o GDPR se aplica);
* `gdpr_consent` é a cadeia de consentimento do GDPR com codificação base64 segura para URL (consulte a [especificação](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Uma amostra de chamada para um pixel de impressão, com os dois parâmetros, pode ser a seguinte:

```
https://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

O caso de uso é descrito na imagem e nas etapas abaixo. Início à esquerda da imagem:

1. O usuário recebe uma impressão por meio de um servidor de anúncios. Isso se traduz em uma [chamada de pixel](../../integration/media-data-integration/impression-data-pixels.md) aos nossos Servidores de coleta de dados (DCS).
2. O Audience Manager verifica se o sinalizador de GDPR se aplica. Caso contrário, o Audience Manager armazena os dados transmitidos na variável `gdpr` e `gdpr_consent` variáveis em chamadas de pixel.
3. Se a string IAB TC estiver presente e tiver as permissões necessárias, o Audience Manager armazenará os dados transmitidos na variável `gdpr` e `gdpr_consent` variáveis em chamadas de pixel.
4. Se a cadeia de caracteres IAB TC estiver ausente ou não tiver as permissões necessárias, o Audience Manager descartará os dados transmitidos no `gdpr` e `gdpr_consent` variáveis em chamadas de pixel.

![Caso de uso do anunciante](assets/advertiser-use-case.png)

## Parceiros de ativação que oferecem suporte à IAB do TCF {#aam-activation-partners}

O Plug-in do Audience Manager para a TCF do IAB permite encaminhar a string do TC do IAB para parceiros de ativação, respeitando as opções de privacidade dos usuários. Para obter informações sobre quais parceiros de ativações oferecem suporte à TCF do IAB, consulte nossa [lista de destinos com base em dispositivos](/help/using/features/destinations/device-based-destinations-list.md).

## Anexação de consentimento aos URLs enviados aos destinos de URL

A integração do Audience Manager com a TCF do IAB v2.2 oferece suporte à anexação de consentimento às informações enviadas para o [Destinos do URL](../../features/destinations/create-url-destination.md) que estão integrados ao IAB TCF v2.2. No entanto, esse processo não é feito automaticamente pelo Audience Manager, para evitar a quebra de formatos específicos de URL.

Os clientes que quiserem anexar consentimentos aos dados enviados ao [!DNL URL destinations] deve adicionar manualmente o `${GDPR}` e `${GDPR_CONSENT_XXXX}` macros para o formato de URL deles, substituindo `XXXX` com a ID do parceiro de destino.

Exemplo: `https://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Consulte [Macros de destino definidas](../../features/destinations/destination-macros.md) para obter mais detalhes sobre as macros de destino compatíveis.

## Gerenciamento de consentimento entre dispositivos

O Plug-in do Audience Manager para a TCF do IAB recusa automaticamente as IDs presentes em uma solicitação, quando os visitantes do site não fornecem as permissões apropriadas. Se o pedido contiver uma [ID entre dispositivos (ID de CRM)](../../reference/ids-in-aam.md), o Audience Manager cancela a ID, junto com o último dispositivo vinculado a ela [ID entre dispositivos (ID de CRM)](../../reference/ids-in-aam.md).

## Testar a implementação do IAB {#test-iab-implementation}

Para testar se você implementou corretamente o Plug-in do Audience Manager para a TCF do IAB, leia [Caso de uso 4 na validação do serviço de Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## IAB e opção de recusa no Audience Manager. Ordem de precedência. {#iab-and-optout}

Outra opção de privacidade à disposição dos usuários é a capacidade de recusar toda a coleta de dados. A Adobe fornece aos usuários essa opção na página [Suas escolhas de privacidade](https://www.adobe.com/br/privacy/opt-out.html#customeruse).

O Audience Manager aborda as solicitações de recusa em um [artigo separado da documentação](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Os usuários que optam por não participar de toda a coleta de dados após recusarem o consentimento não podem voltar a participar.

>[!NOTE]
>
>**Ordem de precedência** - Se o usuário recusar a coleta de dados usando uma ferramenta de recusa global, conforme descrito no link acima, essa ação terá precedência sobre as verificações de aceitação e IAB.

## Recursos adicionais {#additional-resources}

* [Aceitação do Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* [Estrutura de transparência e consentimento do GDPR do IAB Europe](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Especificações técnicas da estrutura de transparência e consentimento do GDPR do IAB Europe](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Plug-in da TCF do IAB - demonstração em vídeo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
