---
description: Esta página ilustra o processo de criação de pixels de público-alvo personalizado (WCA) para o site da Facebook com o objetivo de enviar segmentos de público-alvo de Audience Manager com base na Web para o Facebook, para segmentação de anúncios online com transparência aprimorada.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Integração WCA com o Facebook
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 4%

---

# [!DNL Facebook WCA] Integração {#facebook-wca-integration}

Esta página ilustra o processo de criação [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixels para fins de envio com base na Web [!DNL Audience Manager] segmentos de público-alvo para [!DNL Facebook], para segmentação de anúncios online com transparência aprimorada.

## Visão geral {#overview}

[Públicos-alvo personalizados do site da facebook (WCA)](https://www.facebook.com/business/help/449542958510885) O permite criar uma lista de pessoas que visitaram determinadas páginas ou realizaram ações específicas no seu site. [!DNL Audience Manager] habilita a ativação no [!DNL WCA] usar [!DNL URL] destinos , com os quais você pode configurar uma integração personalizada baseada em pixels para enviar públicos baseados na Web para o [!DNL Facebook] para direcionamento.

![Integração WCA com o Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Esse recurso exige que você selecione a variável [!UICONTROL Website] opção público-alvo para plataformas sociais em [Destinos de URL](/help/using/features/destinations/create-url-destination.md). As plataformas sociais exigem que as informações do referenciador sejam desmascaradas quando enviadas para a plataforma. Esteja ciente de que isso significa que a plataforma/parceiro de destino poderá ver informações em seu referenciador [!DNL URL].

## Pré-requisitos {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segmentos prontos para serem atribuídos aos novos [!DNL Facebook] destino. Aqui está [como criar um segmento](/help/using/features/segments/segment-builder.md) no [!DNL Audience Manager] IU.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versão 4.1.0 ou mais recente. Baixe a versão mais recente **[aqui](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versão 9.0 ou mais recente, disponível para download em **[here](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Como alternativa, se você usar [Encaminhamento pelo lado do servidor (SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) para importar dados para [!DNL Audience Manager], você deve usar o AppMeasurement versão 2.12 ou mais recente. Baixar [!DNL AppMeasurement] usando o [Gerenciador de código do Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).

Recomendamos que você instale ou atualize as bibliotecas nas etapas 3 e 4 usando [Tags do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

## Etapa 1 - Criar um [!UICONTROL Facebook Destination] em [!DNL Audience Manager] {#step-1-create-facebook-destination}

Crie um novo [!UICONTROL URL Destination] em [!DNL Audience Manager] e nomeá-lo [!DNL Facebook Website Custom Audiences]. Use as configurações abaixo ao criar o destino. Também é possível fazer referência à variável [Configurar um destino de URL](/help/using/features/destinations/create-url-destination.md) página.

### Informações básicas

* **[!UICONTROL Category]**: Personalizado
* **[!UICONTROL Type]**: [!DNL URL]
* Selecione o **[!UICONTROL Auto-fill Destination Mapping]** caixa de seleção, em seguida, selecione **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Selecione a opção **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Esse rótulo de exportação impede que dados de terceiros e dados derivados de gráficos de dispositivos sejam incluídos nos segmentos.

### Configuração

* **[!UICONTROL URL type]**: Selecionar **[!UICONTROL Website audience for social platforms]**. Ao selecionar essa opção [!UICONTROL URL Type] , [!DNL Audience Manager] não obscurece o referenciador [!DNL URL] informações ao acionar um [!DNL Facebook WCA] pixel.
* **[!UICONTROL Serialize]**: Selecionar **[!UICONTROL Enable]**.
* No **[!UICONTROL Base URL]** e **[!UICONTROL Secure URL]** , insira o [!DNL Facebook WCA] pixel.
* **[!UICONTROL Delimiter]**: `,`

Base [!DNL URL] exemplo: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemplo de pixel acionado a partir da página. Este exemplo mostra um usuário que se qualificou para três [!DNL Audience Manager] segmentos, com as IDs 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parâmetro | Descrição |
|---------|----------|
| `id` | Seu [!DNL Facebook] ID de pixel, que pode ser encontrada na variável [!DNL Facebook Ad Manager] interface do usuário ao criar pixels de público-alvo. |
| `ev` | Event.     Esse é um valor arbitrário, que aparecerá no [!DNL Facebook Ad Manager] interface do usuário assim que o pixel começar a disparar no site. Consulte a [!UICONTROL Include] item em [Etapa 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), para obter mais informações. |
| `cd[segID]` | Um parâmetro adicional, que começará a ser preenchido na variável [!DNL Facebook Ad Manager] interface do usuário assim que o pixel começar a disparar no site. `segID` é também arbitrária. |
| `%ALIAS%` | Um [!DNL Audience Manager] macro , que será substituída dinamicamente pela variável [!DNL Audience Manager] [!UICONTROL segment] IDs para as quais o visitante do site se qualifica, delimitadas por vírgula , |

Seu [!UICONTROL URL destination] a configuração deve ser semelhante na imagem abaixo:

![Configuração de destino](/help/using/integration/assets/facebook-wca.png)

Salve as [!UICONTROL destination]. Em seguida, você pode prosseguir para a **Mapeamentos de segmento** etapa.

## Etapa 2 - Mapeamentos de segmento - Mapear segmento para destino {#step-2-segment-mappings}

No [Configurar destino do URL](/help/using/features/destinations/create-url-destination.md) , mapeie o segmento aplicável para o recém-criado [!UICONTROL destination]. Observe que o valor de mapeamento é preenchido automaticamente com a variável [!DNL Audience Manager] [!UICONTROL segment ID].

Insira uma data final, se aplicável, caso contrário, deixe em branco sem data final.

## Etapa 3 - Criar um [!UICONTROL Audience] within [!DNL Facebook Ads Manager] {#step-3-create-audience}

Consulte [Criar um público-alvo personalizado do site](https://www.facebook.com/business/help/666509013483225) no [!DNL Facebook] documentação de ajuda. Selecione o [!UICONTROL Create Audience] opções na tabela abaixo:

| Item | Descrição |
|---------|----------|
| Tráfego do site | Combinação personalizada |
| Incluir | <ul><li>Selecionar **[!UICONTROL Event]** > Selecionar **[!UICONTROL Adobe-Audience-Manager-Segment]**. Esse era o valor da variável `ev` no pixel de exemplo na etapa 1. Observe que, se o pixel ainda não for acionado, a variável **[!UICONTROL Event]** ou **[!UICONTROL Adobe-Audience-Manager-Segment]** pode não aparecer no [!DNL Facebook] interface do usuário.</li><li>Adicione um parâmetro: Selecionar `segID`.</li><li><p>Selecione o **contém** operador.</p><p>Isso é importante, considerando que os visitantes podem se qualificar para vários segmentos, pode haver vários [!UICONTROL segment IDs] no parâmetro pixel. Usar o igual (`=`) pode não qualificar seus visitantes para o público-alvo e você observará um volume menor.</p></li><li>Adicione um valor: Insira o [!DNL Audience Manager] ID do segmento.</li></ul> |
| Adicionar nova condição | Configuração opcional. |
| No último | Configuração opcional. |
| Nome do público-alvo | Recomendamos que você use o mesmo [!DNL Audience Manager] nome do segmento para fins de consistência, a menos que você esteja adicionando condições adicionais a esse público-alvo. |

## Etapa 4 - Atribuir a variável [!UICONTROL Audience] para [!UICONTROL Campaign] em [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Depois de criar o [!DNL Custom Audience], atribua-a a uma campanha publicitária. Crie uma nova campanha ou edite uma existente e você encontrará seu público recém-criado listado na variável [!DNL Facebook] interface do usuário. Sua campanha publicitária terá como alvo usuários que viram o pixel disparar em seu navegador ao visitar seu site, se [!DNL Audience Manager] inclui no segmento.

## Resumo {#summary}

Agora que você atribuiu seu [!DNL Audience Manager] para [!DNL Facebook WCA] destino, [!DNL Audience Manager] disparará seletivamente a variável [!DNL Facebook WCA] pixel para usuários de um determinado segmento com a respectiva ID de segmento no pixel para preencher a variável [!DNL Facebook Audience]. Isto resulta num aumento gradual da [!DNL Facebook Audience] quanto mais a tag for acionada para o público-alvo aplicável em seu site.

>[!NOTE]
>
> Se um usuário sair de [!DNL Audience Manager] no momento, não há como [!DNL Audience Manager] informar [!DNL Facebook] para remover o usuário do [!DNL Custom Audience].
