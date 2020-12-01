---
description: A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da funcionalidade de aceitação e pelo suporte à Estrutura de transparência e consentimento (TCF) do IAB. Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar o suporte no Audience Manager.
seo-description: A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da funcionalidade de aceitação e pelo suporte à Estrutura de transparência e consentimento (TCF) do IAB. Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar o suporte no Audience Manager.
seo-title: Plug-in do Audience Manager para a TCF do IAB
solution: Audience Manager
title: Plug-in do Audience Manager para a TCF do IAB
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '2449'
ht-degree: 40%

---


# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## Visão geral

Um aspecto importante das obrigações de privacidade que você pode ter para com seus usuários é a aquisição e a transmissão de escolhas do usuário sobre como seus dados pessoais podem ser usados (ou seja, &quot;fins&quot;) e por quem (ou seja, &quot;empresas&quot;).

A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da [funcionalidade de aceitação](https://docs.adobe.com/content/help/pt-BR/id-service/using/implementation/opt-in-service/optin-overview.html) e pelo suporte à [Estrutura de transparência e consentimento (TCF) do IAB](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar o suporte no Audience Manager.

>[!IMPORTANT]
>
>O Audience Manager está registrado no [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) com a ID do fornecedor 565.

O Plug-in do Audience Manager para a TCF do IAB utiliza a [Funcionalidade de aceitação](https://docs.adobe.com/content/help/pt-BR/id-service/using/implementation/opt-in-service/iab.html), que, por sua vez, faz parte da biblioteca do [ Experience Platform Identity Service (ECID)](https://docs.adobe.com/content/help/pt-BR/id-service/using/home.html).

## Escopo e limitações {#scope-and-limitations}

Como Editor ou Anunciante trabalhando com o Audience Manager, você pode transmitir as opções do usuário ao Audience Manager de acordo com a TCF do IAB.

>[!IMPORTANT]
>
>Os regulamentos relativos ao TCF da IAB aplicam-se apenas aos visitantes localizados no Espaço Econômico Europeu.

O Audience Manager ajuda você a respeitar as opções de privacidade dos usuários e também fornece uma maneira fácil de comunicar essas opções a todos os parceiros com os quais você trabalha.

Atualmente, o Audience Manager não oferece suporte a/à:

* fluxos de trabalho para dispositivos móveis;
* Anexar consentimento às exportações de segmento.

## Atualizando para [!DNL IAB TCF v2.0] {#upgrading}

Os clientes que estão atualizando sua implementação [!DNL Audience Manager Plug-in for IAB TCF] de [!DNL IAB TCF] v1.1 para [!DNL IAB TCF] v2.0, ou ativando [!DNL IAB TCF] v2.0 pela primeira vez, devem seguir as mesmas diretrizes sobre pré-requisitos e implementação, conforme descrito abaixo.

## Pré-requisitos {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager suporta IAB TCF v2.0.
>
>O suporte ao IAB TCF v1.1 terminará em 15 de agosto de 2020.
>
> Os clientes que desejarem continuar usando o Plug-in Audience Manager para IAB TCF para gerenciamento de consentimento devem atualizar para a versão mais recente do [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) para suporte contínuo.
>
> Depois de atualizar para a versão mais recente do [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases), as cadeias de caracteres de consentimento do IAB TCF v1.1 não serão mais suportadas, portanto, atualize seu CMP antes de atualizar para a versão mais recente do ECID.

Você deve atender aos seguintes pré-requisitos para usar o Plug-in Audience Manager para IAB TCF com Audience Manager:

1. Você deve usar o Adobe Experience Platform Identity Service (ECID) versão 5 ou mais recente. [Baixe](https://github.com/Adobe-Marketing-Cloud/id-service/releases) a versão mais recente do ECID.
2. Você deve estar usando a versão 9.0 do Audience Manager [!DNL Data Integration Library] (DIL) ou mais recente, disponível para download de [aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases). Leia sobre a [DIL na documentação do Audience Manager](../..//dil/dil-overview.md). Recomendamos usar [Adobe Launch](https://docs.adobe.com/content/help/pt-BR/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html) para a implementação mais fácil do DIL para Audience Manager.
3. Como alternativa, se você usar [!DNL Server-Side Forwarding] (SSF) para importar dados para o Audience Manager, será necessário atualizar para a versão mais recente do AppMeasurement. Baixe o AppMeasurement usando o [Gerenciador de código do Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/admin/admin-tools/code-manager-admin.html).
4. Você deve estar usando uma Plataforma de Gerenciamento de Consentimento (CMP), comercial ou própria, integrada ao IAB TCF v2.0 e registrada no IAB TCF. Consulte a lista de [CMPs registradas junto à estrutura do IAB](https://iabeurope.eu/cmp-list/).

>[!WARNING]
>
>Se você estiver usando uma plataforma de gerenciamento de consentimento (CMP) que não suporta IAB TCF v.2.0, o Audience Manager enviará automaticamente o parâmetro `gdpr=0` em sincronizações de ID, mesmo se os visitantes estiverem na União europeia. Para determinar se sua validação do RGPD está ativa, recomendamos que você confirme com sua Plataforma de Gerenciamento de Consentimento (CMP) que eles suportam o IAB TCF v2.0.

## Recomendações e como implementar {#recommendations}

Para ativar o suporte à TCF do IAB no Audience Manager, leia nossa documentação sobre [como configurar o IAB com a opção de aceitação](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html).

A maneira mais fácil de fazer isso é usando [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) para adicionar [!DNL ECID Opt-in] às suas propriedades. Leia a documentação da [extensão de aceitação da ECID](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html) para saber como configurar a extensão do Launch.

## Fluxo de trabalho escolhido pelo usuário ao usar a estrutura do IAB {#user-choice-workflow}

Ao visitar uma propriedade da Web, os usuários podem dizer como querem que seus dados devem ser usados pelo editor e pelos fornecedores de terceiros com quem o editor trabalha.

Os usuários fornecem suas opções na forma de *consentimento* e *interesse legítimo* para os fins do IAB para *fornecedores de terceiros* registrados na lista do fornecedor global.

A imagem abaixo representa um exemplo de uma caixa de diálogo da CMP, exibida em um visitante novo de um site. Lembre-se de que essa caixa de diálogo pode variar bastante de acordo com a implementação do cliente.

![Caixa de diálogo da CMP](assets/cmp-example.png)

Os detalhes sobre os vários propósitos e permissões incluídos no IAB TCF v2.0 são abordados nas [Políticas IAB Europe Transparency &amp; Consent Framework](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Os usuários podem conceder seu consentimento ou interesse legítimo (se disponível) para uma combinação de finalidades e fornecedores. Por exemplo, os usuários podem conceder seu consentimento para armazenar informações em um dispositivo, desenvolver e melhorar produtos e conceder seu consentimento a todos os fornecedores de terceiros exibidos pelo CMP.

Ou, num outro exemplo, poderiam conceder o seu consentimento ou o seu interesse legítimo para todos os fins, mas apenas conceder o consentimento ou o interesse legítimo a alguns dos fornecedores expostos pelo CMP.

Depois que o usuário seleciona suas opções de privacidade, as opções do usuário são registradas na string IAB TC. A string IAB TC armazena a combinação de finalidades e fornecedores aprovados, juntamente com outras informações de metadados (consulte a [página IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) para obter mais informações).

Todos os fornecedores registrados no IAB TCF avaliam a sequência de caracteres IAB TC e tomam decisões com base nas opções de privacidade dos usuários. Lembre-se de que as opções de privacidade dos usuários são válidas em todos os fornecedores registrados com IAB TCF.

## Finalidades exigidas por Audience Manager {#aam-standard-purposes}

O Audience Manager avalia as opções dos usuários armazenadas na string IAB TC para os seguintes fins, definidos em [IAB Europe Transparency &amp; Consent Framework Policies](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes). Além disso, você também pode encontrar os propósitos na [lista do fornecedor global](https://vendorlist.consensu.org/vendorlist.json).

* **Finalidade 1**: Armazenar e/ou aceder a informações num dispositivo;
* **Finalidade 10**: Desenvolver e melhorar os produtos;
* **Finalidade especial 1**: Garanta a segurança, evite fraudes e depure.

>[!IMPORTANT]
>
>A Audience Manager precisa de consentimento para o Objetivo 1 e o Objetivo 10, além do consentimento do fornecedor, para implantar cookies e iniciar ou honrar sincronizações de ID.
>
>De acordo com [regulamentos IAB](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_), o Objetivo Especial 1 (Garantir a segurança, impedir fraudes e depurar) é sempre aceito e os usuários não podem se opor a ele.

## O comportamento do Audience Manager depende do consentimento do usuário {#aam-behavior-consent}

O Audience Manager funciona de forma diferente dependendo se a sequência de caracteres IAB TC inclui o consentimento do usuário para os dois fins (armazenar e/ou acessar informações em um dispositivo e desenvolver e melhorar produtos) ou não.

Também verificamos o consentimento do usuário para todos os destinos com os quais você trabalha no Audience Manager, desde que esses destinos estejam registrados no IAB TCF.

| Quando o usuário *consente*, o Audience Manager: | Quando o usuário *não consente*, o Audience Manager: |
|---|---|
| <ul><li>Executa todos os casos de uso do Audience Manager solicitados.</li><li>Transmite o consentimento a terceiros em sincronizações de ID (transmitindo `gdpr = 1` e a cadeia de caracteres de consentimento como `gdpr_consent` em chamadas de sincronização de ID).</li><li>Avalia e respeita o consentimento passado dos pixels do servidor de publicidade.</li><li>Respeita sincronizações de ID iniciadas pelo parceiro.</li></ul> | <ul><li>Não armazena dados novos do usuário na sua instância, inclusive IDs de parceiros, sinais, características ou dados de pixel.</li><li>Não inicia sincronizações de ID de terceiros.</li><li>Não respeita sincronizações de ID iniciadas pelo parceiro.</li><li>Opt out o usuário de mais coleta de dados.</li></ul> |

## Caso de uso do editor {#publisher-use-case}

Ao implementar o Plug-in de Audience Manager para IAB TCF, você não é obrigado a manter o código personalizado para gerenciamento de consentimento em suas propriedades da Web por meio de um mecanismo diferente com o Adobe ou outros fornecedores de terceiros. O caso de uso é descrito na imagem e nas etapas abaixo. Início à esquerda da imagem:

1. Um usuário visita uma de suas propriedades da Web. Desde que você esteja usando as versões mais recentes da ECID e bibliotecas DIL (consulte [Pré-requisitos](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), o fluxo de aceitação é acionado.
2. O Audience Manager verifica se o fluxo do IAB se aplica (`isIabContext=true`). Consulte [Recomendações e como implementar](aam-iab-plugin.md#recommendations).
3. O Audience Manager verifica se o RGPD se aplica (`gdpr = 1`) e se existe um CMP, registrado com o IAB TCF, na propriedade da Web. Por exemplo, tal aplicar-se-ia aos utilizadores que visitam a União europeia. Observe que é sua responsabilidade, como editor, definir o sinalizador do RGPD.
4. Se o GDPR for aplicado, o Audience Manager verifica a string IAB TC, transmitida no parâmetro `gdpr_consent`, para obter o consentimento necessário. O Audience Manager precisa de consentimento para armazenar e/ou acessar informações em um dispositivo ([IAB TCF objetivo 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), desenvolver e melhorar produtos ([IAB TCF objetivo 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), além do consentimento do fornecedor do Audience Manager para armazenar, processar ou ativar dados.
5. Se a sequência de caracteres TC IAB estiver presente e contiver o consentimento necessário, o Audience Manager passará a sequência de caracteres TC IAB para nossos [servidores de coleta de dados](../../reference/system-components/components-data-collection.md) (DCS).
6. O Audience Manager responde definindo um [cookie demdex](https://docs.adobe.com/content/help/pt-BR/core-services/interface/ec-cookies/cookies-am.html) no navegador e inicia e honra sincronizações de ID de terceiros.
7. Como alternativa, se a sequência de caracteres TC IAB transmitida na etapa 4 não contiver todas as permissões necessárias, o Audience Manager não coletará, processará ou ativará quaisquer dados do usuário e não honrará ou iniciará sincronizações de ID. Além disso, ele opt out o usuário dos destinos com os quais você trabalha.

>[!IMPORTANT]
>
>Se você estiver trabalhando com parceiros de destino de Audience Manager que exigem parâmetros TCF da IAB, mas não tiver um CMP compatível com TCF da IAB em seu site, o Audience Manager enviará `gdpr=0` em sincronizações de ID. Isso significa que o RGPD não se aplica a esses usuários.
>
> Se isso não for desejado, ative a funcionalidade TCF IAB no Audience Manager para enviar as strings TC IAB apropriadas aos parceiros de destino.



![Caso de uso do editor](assets/publisher-use-case.png)

## Caso de uso do anunciante {#advertiser-use-case}

O Audience Manager avalia e respeita o consentimento transmitido em [chamadas de pixel](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md), de acordo com a TCF do IAB.

Os pixels podem ser colocados pelos clientes do Audience Manager em suas páginas de parceiros ou são colocados nos servidores de anúncios para inclusão na resposta do anúncio. No primeiro caso, o parceiro deve recuperar programaticamente o parâmetro de consentimento e adicioná-lo ao pixel antes de disparar. No segundo caso, que é mais comum e é descrito detalhadamente abaixo, os servidores de anúncios anexam os parâmetros de consentimento que recebem da Plataforma do lado do suprimento (SSP) ou dos servidores de anúncios do editor a todos os pixels.

O Audience Manager usa dois parâmetros para transmitir o consentimento do usuário em chamadas de pixel:

* `gdpr` pode ser 0 (o GDPR não se aplica) ou 1 (o GDPR se aplica);
* `gdpr_consent` é a cadeia de consentimento do GDPR com codificação base64 segura para URL (consulte a [especificação](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Uma amostra de chamada para um pixel de impressão, com os dois parâmetros, pode ser a seguinte:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

O caso de uso é descrito na imagem e nas etapas abaixo. Início à esquerda da imagem:

1. O usuário recebe uma impressão por meio de um servidor de anúncios. Isso se traduz em uma chamada de [pixel](../../integration/media-data-integration/impression-data-pixels.md) para nossos servidores de coleta de dados (DCS).
2. O Audience Manager verifica se o sinalizador de GDPR se aplica. Caso contrário, o Audience Manager armazena os dados transmitidos nas variáveis `gdpr` e `gdpr_consent` em chamadas de pixel.
3. Se a string IAB TC estiver presente e contiver as permissões necessárias, o Audience Manager armazenará os dados transmitidos nas variáveis `gdpr` e `gdpr_consent` em chamadas de pixel.
4. Se a sequência de caracteres TC IAB estiver ausente ou não tiver as permissões necessárias, o Audience Manager ignorará os dados transmitidos nas variáveis `gdpr` e `gdpr_consent` em chamadas de pixel.

![Caso de uso do anunciante](assets/advertiser-use-case.png)

## Parceiros de ativação que oferecem suporte à IAB do TCF {#aam-activation-partners}

O Plug-in de Audience Manager para IAB TCF permite encaminhar a sequência de caracteres IAB TC para parceiros de ativação respeitando as opções de privacidade dos usuários. Para obter informações sobre quais parceiros de ativações oferecem suporte à TCF do IAB, consulte nossa [lista de destinos com base em dispositivos](/help/using/features/destinations/device-based-destinations-list.md).

## Acrescentar consentimento a URLs enviados para destinos de URL

A integração do Audience Manager com o IAB TCF v2.0 suporta o anexo de consentimento às informações enviadas para [destinos de URL](../../features/destinations/create-url-destination.md) que estão integrados com o IAB TCF v2.0. No entanto, esse processo não é feito automaticamente por Audience Manager, para evitar a quebra de formatos de URL específicos.

Os clientes que desejam anexar o consentimento aos dados enviados para [!DNL URL destinations] devem adicionar manualmente as macros `${GDPR}` e `${GDPR_CONSENT_XXXX}` ao formato do URL, substituindo `XXXX` pela ID do parceiro de destino.

Exemplo: `http://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Consulte [Macros de destino definidas](../../features/destinations/destination-macros.md) para obter mais detalhes sobre as macros de destino suportadas.

## Gerenciamento de consentimento entre dispositivos

O Plug-in de Audience Manager para IAB TCF opt out automaticamente as IDs presentes em uma solicitação, quando os visitantes do site não fornecem as permissões apropriadas. Se a solicitação contiver uma [ID de dispositivo cruzado (ID CRM)](../../reference/ids-in-aam.md), o Audience Manager opt out a ID, juntamente com o último dispositivo vinculado a essa [ID de dispositivo cruzado (ID CRM)](../../reference/ids-in-aam.md).

## Testar a implementação do IAB {#test-iab-implementation}

Para testar se você implementou corretamente o Plug-in de Audience Manager para IAB TCF, leia [Caso de uso 4 em Validação do serviço de aceitação](https://docs.adobe.com/content/help/pt-BR/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## IAB e opção de recusa no Audience Manager. Ordem de precedência. {#iab-and-optout}

Outra opção de privacidade à disposição dos usuários é a capacidade de recusar toda a coleta de dados. A Adobe fornece aos usuários essa opção na página [Suas escolhas de privacidade](https://www.adobe.com/br/privacy/opt-out.html#customeruse
).

O Audience Manager aborda as solicitações de recusa em um [artigo separado da documentação](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Os usuários que forem opt out de toda a coleta de dados depois que recusarem o consentimento, não poderão ser aceitos novamente.

>[!NOTE]
>
>**Ordem de precedência** - Se o usuário recusar a coleta de dados usando uma ferramenta de recusa global, conforme descrito no link acima, essa ação terá precedência sobre as verificações de aceitação e IAB.

## Recursos adicionais {#additional-resources}

* [Aceitação do Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [Estrutura de transparência e consentimento do GDPR do IAB Europe](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Especificações técnicas da estrutura de transparência e consentimento do GDPR do IAB Europe](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Plug-in da TCF do IAB - demonstração em vídeo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)