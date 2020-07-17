---
description: Esta página ilustra o processo de criação de pixels de Audiências personalizadas (WCA) do site do Facebook para fins de envio de segmentos de audiência de Audience Manager baseados na Web para o Facebook, para direcionamento de anúncios online com maior transparência.
seo-description: Esta página ilustra o processo de criação de pixels de Audiências personalizadas (WCA) do site do Facebook para fins de envio de segmentos de audiência de Audience Manager baseados na Web para o Facebook, para direcionamento de anúncios online com maior transparência.
seo-title: Integração WCA com o Facebook
solution: Audience Manager
title: Integração WCA com o Facebook
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 6%

---


# [!DNL Facebook WCA] Integração {#facebook-wca-integration}

Esta página ilustra o processo de criação de [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixels para fins de envio de segmentos de [!DNL Audience Manager] audiência baseados na Web para [!DNL Facebook], para direcionamento de anúncios online com maior transparência.

## Visão geral {#overview}

[As Audiências personalizadas do site do Facebook (WCA)](https://www.facebook.com/business/help/449542958510885) permitem que você crie uma lista de pessoas que visitaram determinadas páginas ou realizaram ações específicas em seu site. [!DNL Audience Manager] permite a ativação em [!DNL WCA] destinos [!DNL URL] , com os quais você pode configurar uma integração personalizada baseada em pixels para enviar audiências baseadas na Web [!DNL Facebook] para direcionamento.

![Integração WCA com o Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Esse recurso exige que você selecione a opção [!UICONTROL Website] audiência para plataformas sociais em destinos [de](/help/using/features/destinations/create-url-destination.md)URL. As plataformas sociais exigem que as informações de quem indicou sejam desmascaradas quando enviadas para a plataforma. Esteja ciente de que isso significa que a plataforma/parceiro de destino poderá ver informações na sua quem indicou [!DNL URL].

## Pré-requisitos {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segmentos, prontos para atribuir ao seu novo [!DNL Facebook] destino. Veja [como criar um segmento](/help/using/features/segments/segment-builder.md) na [!DNL Audience Manager] interface do usuário.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versão 4.1.0 ou mais recente. Baixe a versão mais recente **[aqui](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versão 9.0 ou mais recente, disponível para download **[aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Como alternativa, se você usar o[Server-Side Forwarding (SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)para importar dados para[!DNL Audience Manager], deverá usar o AppMeasurement versão 2.12 ou mais recente. Download[!DNL AppMeasurement]using the[Analytics Code Manager](https://docs.adobe.com/content/help/pt-BR/analytics/admin/admin-tools/code-manager-admin.html).

Recomendamos que você instale ou atualize as bibliotecas nas etapas 3 e 4 usando o [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) ou o Gerenciamento [dinâmico de tags da](https://docs.adobe.com/content/help/pt-BR/dtm/using/dtm-home.html)Adobe.

## Etapa 1 - Criar um [!UICONTROL Facebook Destination] em [!DNL Audience Manager] {#step-1-create-facebook-destination}

Crie um novo [!UICONTROL URL Destination] em [!DNL Audience Manager] e nomeie-o [!DNL Facebook Website Custom Audiences]. Use as configurações abaixo ao criar o destino. Você também pode consultar a página [Configurar um destino](/help/using/features/destinations/create-url-destination.md) de URL.

### Informações básicas

* **[!UICONTROL Category]**: Personalizado
* **[!UICONTROL Type]**: [!DNL URL]
* Marque a caixa de **[!UICONTROL Auto-fill Destination Mapping]** seleção e selecione **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Selecione a opção **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Esse rótulo de exportação impede que dados de terceiros e dados derivados de gráficos de dispositivos sejam incluídos nos segmentos.

### Configuração

* **[!UICONTROL URL type]**: Selecionar **[!UICONTROL Website audience for social platforms]**. Ao selecionar essa [!UICONTROL URL Type] opção, [!DNL Audience Manager] não obscurece as [!DNL URL] informações de quem indicou ao acionar um [!DNL Facebook WCA] pixel.
* **[!UICONTROL Serialize]**: Selecionar **[!UICONTROL Enable]**.
* No campo **[!UICONTROL Base URL]** e **[!UICONTROL Secure URL]** , insira o [!DNL Facebook WCA] pixel.
* **[!UICONTROL Delimiter]**: `,`

Exemplo [!DNL URL] básico: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemplo de pixel disparado da página. Este exemplo mostra um usuário que se qualifica para três [!DNL Audience Manager] segmentos, com as IDs 3401321, 2993399 e 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parâmetro | Descrição |
---------|----------|
| `id` | Sua ID de [!DNL Facebook] pixel, que pode ser encontrada na interface do [!DNL Facebook Ad Manager] usuário ao criar pixels de audiência. |
| `ev` | Event.     Esse é um valor arbitrário, que aparecerá na interface do [!DNL Facebook Ad Manager] usuário assim que o pixel começar a ser acionado no site. Consulte o [!UICONTROL Include] item na [Etapa 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)para obter mais informações. |
| `cd[segID]` | Um parâmetro adicional, que começará a ser preenchido na interface do [!DNL Facebook Ad Manager] usuário quando o pixel começar a ser acionado no site. `segID` também é arbitrário. |
| `%ALIAS%` | Uma [!DNL Audience Manager] macro, que será substituída dinamicamente pelas [!DNL Audience Manager] [!UICONTROL segment] IDs para as quais o visitante do site se qualifica, delimitadas por vírgula, |

Sua [!UICONTROL URL destination] configuração deve ser semelhante na imagem abaixo:

![Configuração de destino](/help/using/integration/assets/facebook-wca.png)

Salve o [!UICONTROL destination]. Em seguida, você pode prosseguir para a etapa Mapeamentos **de** segmentos.

## Etapa 2 - Mapeamentos de segmento - Mapear segmento para destino {#step-2-segment-mappings}

No fluxo de trabalho [Configurar destino](/help/using/features/destinations/create-url-destination.md) de URL, mapeie o segmento aplicável para o recém-criado [!UICONTROL destination]. Observe que o valor de mapeamento é preenchido automaticamente com o [!DNL Audience Manager][!UICONTROL segment ID].

Informe uma data de término, se aplicável, caso contrário, deixe em branco sem data de término.

## Etapa 3 - Criar um [!UICONTROL Audience] em [!DNL Facebook Ads Manager] {#step-3-create-audience}

Consulte [Criar uma Audiência](https://www.facebook.com/business/help/666509013483225) personalizada do site na documentação de [!DNL Facebook] ajuda. Selecione as [!UICONTROL Create Audience] opções na tabela abaixo:

| Item | Descrição |
---------|----------|
| Tráfego do site | Combinação personalizada |
| Incluir | <ul><li>Selecione **[!UICONTROL Event]** > Selecionar **[!UICONTROL Adobe-Audience-Manager-Segment]**. Esse era o valor do `ev` parâmetro no pixel exemplo na etapa 1. Observe que, se o pixel ainda não for acionado, a **[!UICONTROL Event]** opção ou **[!UICONTROL Adobe-Audience-Manager-Segment]** talvez não apareça na interface do [!DNL Facebook] usuário.</li><li>Adicione um parâmetro: Selecione `segID`.</li><li><p>Selecione o operador **contém** .</p><p>Isso é importante, considerando que os visitantes podem se qualificar para vários segmentos, pode haver vários [!UICONTROL segment IDs] no parâmetro de pixel. O uso do operador igual (`=`) pode não qualificar seus visitantes para a audiência e você observará um volume menor.</p></li><li>Adicione um valor: Insira a ID do [!DNL Audience Manager] segmento.</li></ul> |
| Adicionar nova condição | Configuração opcional. |
| No último | Configuração opcional. |
| Nome da Audiência | Recomendamos que você use o mesmo nome de [!DNL Audience Manager] segmento para fins de consistência, a menos que esteja adicionando condições adicionais a essa Audiência. |

## Etapa 4 - Atribuir o [!UICONTROL Audience] a um [!UICONTROL Campaign] em [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Depois de criar o [!DNL Custom Audience], atribua-o a uma campanha de anúncio. Crie uma nova campanha ou edite uma existente e você encontrará sua audiência recém-criada listada na interface do [!DNL Facebook] usuário. Sua campanha de publicidade público alvo os usuários que viram o pixel disparar no navegador ao visitar seu site, se [!DNL Audience Manager] incluí-los no segmento.

## Resumo {#summary}

Agora que você atribuiu seu [!DNL Audience Manager] segmento ao [!DNL Facebook WCA] destino, [!DNL Audience Manager] disparará seletivamente o [!DNL Facebook WCA] pixel para os usuários de um determinado segmento com a respectiva ID de segmento no pixel para preencher o [!DNL Facebook Audience]. Isso resulta em um aumento gradual na quantidade de vezes maior [!DNL Facebook Audience] o disparo da tag para a audiência aplicável no site.

>[!NOTE]
>
> Se um usuário sair do [!DNL Audience Manager] segmento, não há como [!DNL Audience Manager] informar [!DNL Facebook] para remover o usuário do [!DNL Custom Audience].

