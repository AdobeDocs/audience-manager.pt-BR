---
description: A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da funcionalidade de aceitação e pelo suporte à Estrutura de transparência e consentimento (TCF) do IAB. Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar o suporte no Audience Manager.
seo-description: A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da funcionalidade de aceitação e pelo suporte à Estrutura de transparência e consentimento (TCF) do IAB. Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar o suporte no Audience Manager.
seo-title: Plug-in do Audience Manager para a TCF do IAB
solution: Audience Manager
title: Plug-in do Audience Manager para a TCF do IAB
feature: Governança e privacidade de dados
exl-id: aa6bc415-e52b-4900-951d-ccf51d907aa2
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '2421'
ht-degree: 36%

---

# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## Visão geral

Um aspecto importante nas obrigações de privacidade que você pode ter em relação aos seus usuários é a aquisição e o transporte de opções do usuário sobre como seus dados pessoais podem ser usados (ou seja, &quot;finalidade&quot;) e por quem (ou seja, &quot;empresas&quot;).

A Adobe fornece o meio de gerenciar e comunicar as opções de privacidade de seus usuários por meio da [funcionalidade de aceitação](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html) e pelo suporte à [Estrutura de transparência e consentimento (TCF) do IAB](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

Este artigo descreve os casos de uso do Audience Manager que oferecem suporte à TCF do IAB e como implementar o suporte no Audience Manager.

>[!IMPORTANT]
>
>O Audience Manager é registrado no [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) com a ID de fornecedor 565.

O Plug-in do Audience Manager para a TCF do IAB utiliza a [Funcionalidade de aceitação](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html), que, por sua vez, faz parte da biblioteca do [ Experience Platform Identity Service (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html).

## Escopo e limitações {#scope-and-limitations}

Como Editor ou Anunciante trabalhando com o Audience Manager, você pode transmitir as opções do usuário ao Audience Manager de acordo com a TCF do IAB.

>[!IMPORTANT]
>
>Os regulamentos IAB TCF aplicam-se apenas aos visitantes localizados no Espaço Econômico Europeu.

O Audience Manager ajuda você a respeitar as opções de privacidade dos usuários e também fornece uma maneira fácil de comunicar essas opções a todos os parceiros com os quais você trabalha.

Atualmente, o Audience Manager não oferece suporte a/à:

* fluxos de trabalho para dispositivos móveis;
* Anexação de consentimento às exportações de segmento.

## Atualizando para [!DNL IAB TCF v2.0] {#upgrading}

Os clientes que estiverem atualizando sua implementação [!DNL Audience Manager Plug-in for IAB TCF] de [!DNL IAB TCF] v1.1 para [!DNL IAB TCF] v2.0 ou ativando [!DNL IAB TCF] v2.0 pela primeira vez devem seguir as mesmas diretrizes sobre pré-requisitos e implementação, conforme descrito abaixo.

## Pré-requisitos {#prerequisites}

>[!IMPORTANT]
>
>O Audience Manager é compatível com IAB TCF v2.0.
>
>O suporte à TCF do IAB v1.1 terminará em 15 de agosto de 2020.
>
> Os clientes que desejam continuar usando o Plug-in do Audience Manager para TCF do IAB para gerenciamento de consentimento devem atualizar para a versão mais recente de [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) para continuar o suporte.
>
> Depois de atualizar para a versão mais recente [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases), as cadeias de consentimento do IAB TCF v1.1 não serão mais suportadas, portanto, atualize seu CMP antes de atualizar para a versão mais recente do ECID.

Você deve atender aos seguintes pré-requisitos para usar o Plug-in do Audience Manager para a TCF do IAB com o Audience Manager:

1. Você deve usar o Adobe Experience Platform Identity Service (ECID) versão 5 ou mais recente. [Baixe](https://github.com/Adobe-Marketing-Cloud/id-service/releases) a versão mais recente do ECID.
2. Você deve estar usando o Audience Manager [!DNL Data Integration Library] (DIL) versão 9.0 ou mais recente, disponível para download em [aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases). Leia sobre a [DIL na documentação do Audience Manager](../../dil/dil-overview.md). Recomendamos usar [Adobe Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html) para a implementação DIL mais fácil para o Audience Manager.
3. Como alternativa, se você usar [!DNL Server-Side Forwarding] (SSF) para importar dados para o Audience Manager, será necessário atualizar para a versão mais recente do AppMeasurement. Baixe o AppMeasurement usando o [Gerenciador de código do Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).
4. Você deve usar uma Plataforma de gerenciamento de consentimento (CMP), comercial ou própria, integrada ao IAB TCF v2.0 e registrada junto à TCF do IAB. Consulte a lista de [CMPs registradas junto à estrutura do IAB](https://iabeurope.eu/cmp-list/).

>[!WARNING]
>
>Se estiver usando uma Plataforma de gerenciamento de consentimento (CMP) que não é compatível com a TCF do IAB v.2.0, o Audience Manager enviará automaticamente o parâmetro `gdpr=0` em sincronizações de ID, mesmo se os visitantes estiverem na União Europeia. Para determinar se a validação do GDPR está ativa, recomendamos que você confirme com sua Plataforma de gerenciamento de consentimento (CMP) que ela suporta a TCF do IAB v2.0.

## Recomendações e como implementar {#recommendations}

Para ativar o suporte à TCF do IAB no Audience Manager, leia nossa documentação sobre [como configurar o IAB com a opção de aceitação](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html).

A maneira mais fácil de fazer isso é usando [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html?lang=en) para adicionar [!DNL ECID Opt-in] em suas propriedades. Leia a documentação da [extensão de aceitação da ECID](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html) para saber como configurar a extensão do Launch.

## Fluxo de trabalho escolhido pelo usuário ao usar a estrutura do IAB {#user-choice-workflow}

Ao visitar uma propriedade da Web, os usuários podem dizer como querem que seus dados devem ser usados pelo editor e pelos fornecedores de terceiros com quem o editor trabalha.

Os usuários informam suas opções na forma de *consentimento* e *interesse legítimo* para os fins do IAB para *fornecedores de terceiros* registrados na lista global de fornecedores.

A imagem abaixo representa um exemplo de uma caixa de diálogo da CMP, exibida em um visitante novo de um site. Lembre-se de que essa caixa de diálogo pode variar bastante de acordo com a implementação do cliente.

![Caixa de diálogo da CMP](assets/cmp-example.png)

Detalhes sobre as várias finalidades e permissões incluídas na TCF do IAB v2.0 são abordados nas [Políticas de Estrutura de Transparência e Consentimento da Europa do IAB](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Os usuários podem consentir ou interessar legitimamente (se disponível) com uma combinação de finalidades e fornecedores. Por exemplo, os usuários podem consentir com o armazenamento de informações em um dispositivo, o desenvolvimento e o aprimoramento de produtos e consentir com todos os fornecedores de terceiros exibidos pela CMP.

Ou, em outro exemplo, eles poderiam consentir ou ter interesse legítimo para todos os fins, mas apenas consentir ou ter interesse legítimo em alguns dos fornecedores exibidos pela CMP.

Depois que o usuário seleciona suas opções de privacidade, as opções do usuário são registradas na sequência IAB TC. A string IAB TC armazena a combinação de finalidades e fornecedores aprovados, juntamente com outras informações de metadados (consulte a [página IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) para obter mais informações).

Todos os fornecedores registrados na TCF do IAB avaliam a string do IAB TC e tomam decisões com base nas opções de privacidade dos usuários. Lembre-se de que as opções de privacidade dos usuários são válidas para todos os fornecedores registrados com a TCF do IAB.

## Finalidades exigidas pelo Audience Manager {#aam-standard-purposes}

O Audience Manager avalia as opções dos usuários armazenadas na string IAB TC para os seguintes fins, definidos nas [Políticas de estrutura de transparência e consentimento do IAB Europe](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Appendix_A_Purposes_and_Features_Definitions).

* **Finalidade 1**: Armazenar e/ou acessar informações num dispositivo;
* **Finalidade 10**: Desenvolver e melhorar os produtos;
* **Finalidade especial 1**: Garanta a segurança, evite fraudes e depure.

>[!IMPORTANT]
>
>O Audience Manager precisa de consentimento para Finalidade 1 e Finalidade 10, além do consentimento do fornecedor, para implantar cookies e iniciar ou honrar as sincronizações de ID.
>
>De acordo com [regulamentos IAB](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_), o Especial Finalidade 1 (Garantir a segurança, evitar fraudes e depurar) é sempre consentido e os usuários não podem se opor a ele.

## O comportamento do Audience Manager depende do consentimento do usuário {#aam-behavior-consent}

O Audience Manager funciona de forma diferente dependendo se a cadeia de caracteres TC do IAB inclui o consentimento do usuário para as duas finalidades (armazenamento e/ou acesso às informações em um dispositivo e desenvolvimento e melhoria dos produtos) ou não.

Também verificamos o consentimento do usuário para todos os destinos com os quais você trabalha no Audience Manager, desde que esses destinos estejam registrados na TCF do IAB.

| Quando o usuário *consente*, o Audience Manager: | Quando o usuário *não consente*, o Audience Manager: |
|---|---|
| <ul><li>Executa todos os casos de uso do Audience Manager solicitados.</li><li>Transmite o consentimento a terceiros em sincronizações de ID (transmitindo `gdpr = 1` e a cadeia de consentimento como `gdpr_consent` em chamadas de sincronização de ID).</li><li>Avalia e respeita o consentimento passado dos pixels do servidor de publicidade.</li><li>Respeita sincronizações de ID iniciadas pelo parceiro.</li></ul> | <ul><li>Não armazena dados novos do usuário na sua instância, inclusive IDs de parceiros, sinais, características ou dados de pixel.</li><li>Não inicia sincronizações de ID de terceiros.</li><li>Não respeita sincronizações de ID iniciadas pelo parceiro.</li><li>Opta por recusar a coleta de dados.</li></ul> |

## Caso de uso do editor {#publisher-use-case}

Ao implementar o Plug-in do Audience Manager para a TCF do IAB, você não é obrigado a manter o código personalizado para gerenciamento de consentimento em suas propriedades da Web por meio de um mecanismo diferente com o Adobe ou outros fornecedores de terceiros. O caso de uso é descrito na imagem e nas etapas abaixo. Início à esquerda da imagem:

1. Um usuário visita uma de suas propriedades da Web. Desde que você esteja usando as versões mais recentes da ECID e bibliotecas DIL (consulte [Pré-requisitos](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), o fluxo de aceitação é acionado.
2. O Audience Manager verifica se o fluxo do IAB se aplica (`isIabContext=true`). Consulte [Recomendações e como implementar](aam-iab-plugin.md#recommendations).
3. O Audience Manager verifica se o GDPR se aplica (`gdpr = 1`) e se há uma CMP, registrada junto à TCF do IAB, na propriedade da Web. Por exemplo, isso se aplicaria aos usuários que visitam a União Europeia. Observe que, como editor, é sua responsabilidade definir o sinalizador do GDPR.
4. Se o GDPR for aplicado, o Audience Manager verifica a string TC IAB, transmitida no parâmetro `gdpr_consent`, para obter o consentimento necessário. O Audience Manager precisa de consentimento para armazenar e/ou acessar informações em um dispositivo ([IAB TCF purpose 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), desenvolver e melhorar produtos ([IAB TCF purpose 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), além do consentimento do fornecedor de Audience Manager para armazenar, processar ou ativar dados.
5. Se a string IAB TC estiver presente e tiver o consentimento necessário, o Audience Manager transmitirá a string IAB TC para nossos [servidores de coleta de dados](../../reference/system-components/components-data-collection.md) (DCS).
6. O Audience Manager responde definindo um [cookie demdex](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html) no navegador e inicia e respeita sincronizações de ID de terceiros.
7. Como alternativa, se a cadeia de caracteres TC IAB transmitida na etapa 4 não contiver todas as permissões necessárias, o Audience Manager não coletará, processará ou ativará quaisquer dados do usuário e não honrará ou iniciará sincronizações de ID. Além disso, ele recusa o usuário dos destinos com os quais você trabalha.

>[!IMPORTANT]
>
>Se você estiver trabalhando com parceiros de destino Audience Manager que exigem parâmetros TCF do IAB, mas não tem uma CMP compatível com IAB TCF no seu site, o Audience Manager envia `gdpr=0` em sincronizações de ID. Isso significa que o GDPR não se aplica a esses usuários.
>
> Se isso não for desejado, você deve ativar a funcionalidade TCF do IAB no Audience Manager para enviar as strings TC do IAB apropriadas para os parceiros de destino.



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

1. O usuário recebe uma impressão por meio de um servidor de anúncios. Isso se transforma em uma [chamada de pixel](../../integration/media-data-integration/impression-data-pixels.md) para nossos Servidores de coleta de dados (DCS).
2. O Audience Manager verifica se o sinalizador de GDPR se aplica. Caso contrário, o Audience Manager armazena os dados transmitidos nas variáveis `gdpr` e `gdpr_consent` em chamadas de pixel.
3. Se a string IAB TC estiver presente e tiver as permissões necessárias, o Audience Manager armazenará os dados transmitidos nas variáveis `gdpr` e `gdpr_consent` em chamadas de pixel.
4. Se a string IAB TC estiver ausente ou não tiver as permissões necessárias, o Audience Manager ignorará os dados transmitidos nas variáveis `gdpr` e `gdpr_consent` em chamadas de pixel.

![Caso de uso do anunciante](assets/advertiser-use-case.png)

## Parceiros de ativação que oferecem suporte à IAB do TCF {#aam-activation-partners}

O Plug-in do Audience Manager para a TCF do IAB permite encaminhar a cadeia de caracteres TC do IAB para parceiros de ativação, respeitando as opções de privacidade dos usuários. Para obter informações sobre quais parceiros de ativações oferecem suporte à TCF do IAB, consulte nossa [lista de destinos com base em dispositivos](/help/using/features/destinations/device-based-destinations-list.md).

## Anexação do consentimento aos URLs enviados aos destinos do URL

A integração do Audience Manager com a TCF do IAB v2.0 oferece suporte ao anexo do consentimento para informações enviadas para [destinos de URL](../../features/destinations/create-url-destination.md) que são integrados com a TCF do IAB v2.0. No entanto, esse processo não é feito automaticamente pelo Audience Manager para evitar a quebra de formatos de URL específicos.

Os clientes que desejam anexar o consentimento aos dados enviados para [!DNL URL destinations] devem adicionar manualmente as macros `${GDPR}` e `${GDPR_CONSENT_XXXX}` ao formato do URL, substituindo `XXXX` pela ID do parceiro de destino.

Exemplo: `https://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Consulte [Macros de destino definidas](../../features/destinations/destination-macros.md) para obter mais detalhes sobre as macros de destino suportadas.

## Gerenciamento de consentimento entre dispositivos

O Plug-in do Audience Manager para a TCF do IAB recusa automaticamente as IDs presentes em uma solicitação, quando os visitantes do site não fornecem as permissões apropriadas. Se a solicitação contiver uma [ID entre dispositivos (ID do CRM)](../../reference/ids-in-aam.md), o Audience Manager rejeitará a ID, juntamente com o último dispositivo vinculado a essa [ID entre dispositivos (ID do CRM)](../../reference/ids-in-aam.md).

## Testar a implementação do IAB {#test-iab-implementation}

Para testar se você implementou corretamente o Plug-in do Audience Manager para a TCF do IAB, leia [Caso de uso 4 em Validando o serviço de Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## IAB e opção de recusa no Audience Manager. Ordem de precedência. {#iab-and-optout}

Outra opção de privacidade à disposição dos usuários é a capacidade de recusar toda a coleta de dados. A Adobe fornece aos usuários essa opção na página [Suas escolhas de privacidade](https://www.adobe.com/br/privacy/opt-out.html#customeruse).

O Audience Manager aborda as solicitações de recusa em um [artigo separado da documentação](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Os usuários que recusarem a coleta de dados depois de recusar o consentimento não poderão receber a recusa.

>[!NOTE]
>
>**Ordem de precedência** - Se o usuário recusar a coleta de dados usando uma ferramenta de recusa global, conforme descrito no link acima, essa ação terá precedência sobre as verificações de aceitação e IAB.

## Recursos adicionais {#additional-resources}

* [Aceitação do Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* [Estrutura de transparência e consentimento do GDPR do IAB Europe](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Especificações técnicas da estrutura de transparência e consentimento do GDPR do IAB Europe](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Plug-in da TCF do IAB - demonstração em vídeo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
