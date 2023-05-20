---
description: Esta página ilustra o processo de criação de pixels de Públicos-alvo personalizados (WCA) de sites da Facebook para enviar segmentos de público-alvo Audience Manager baseados na Web para o Facebook, para direcionamento de anúncios online com maior transparência.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Integração WCA com o Facebook
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 8780083474d68717fe3bd4dc632d96da89929122
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 4%

---

# [!DNL Facebook WCA] Integração {#facebook-wca-integration}

Esta página ilustra o processo de criação [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixels para envio com base na Web [!DNL Audience Manager] segmentos de público-alvo para [!DNL Facebook], para direcionamento de anúncios online com mais transparência.

## Visão geral {#overview}

[Públicos-alvo personalizados de sites da facebook (WCA)](https://www.facebook.com/business/help/610516375684216?id=2469097953376494) O permite criar uma lista de pessoas que visitaram determinadas páginas ou executaram ações específicas no site. [!DNL Audience Manager] habilita a ativação no [!DNL WCA] usar [!DNL URL] destinos, com os quais você pode configurar uma integração personalizada baseada em pixel para enviar públicos-alvo baseados na web para o [!DNL Facebook] para direcionamento.

![Integração WCA com o Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Esse recurso exige que você selecione a variável [!UICONTROL Website] público-alvo para a opção de plataformas sociais no [Destinos do URL](/help/using/features/destinations/create-url-destination.md). Plataformas sociais exigem que as informações do referenciador sejam desmascaradas quando enviadas para sua plataforma. Esteja ciente de que isso significa que a plataforma/parceiro de destino poderá visualizar as informações no seu referenciador [!DNL URL].

## Pré-requisitos {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segmentos, prontos para atribuir aos novos [!DNL Facebook] destino. Aqui está [como criar um segmento](/help/using/features/segments/segment-builder.md) no [!DNL Audience Manager] IU.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versão 4.1.0 ou mais recente. Baixe a versão mais recente **[aqui](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versão 9.0 ou mais recente, disponível para download em **[aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Como alternativa, se você usar [Encaminhamento pelo lado do servidor (SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) para importar dados para o [!DNL Audience Manager], você deve usar o AppMeasurement versão 2.12 ou mais recente. Baixar [!DNL AppMeasurement] usando o [Gerenciador de código do Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).

Recomendamos instalar ou atualizar as bibliotecas nas etapas 3 e 4 usando [Tags do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

## Etapa 1 - Criar um [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Criar um novo [!UICONTROL URL Destination] in [!DNL Audience Manager] e nomeie-o [!DNL Facebook Website Custom Audiences]. Use as configurações abaixo ao criar o destino. Você também pode consultar a [Configurar um destino de URL](/help/using/features/destinations/create-url-destination.md) página.

### Informações básicas

* **[!UICONTROL Category]**: Personalizado
* **[!UICONTROL Type]**: [!DNL URL]
* Selecione o **[!UICONTROL Auto-fill Destination Mapping]** e selecione **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Selecione a opção **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Esse rótulo de exportação impede que dados de terceiros e dados derivados de gráficos de dispositivos sejam incluídos nos segmentos.

### Configuração

* **[!UICONTROL URL type]**: Selecionar **[!UICONTROL Website audience for social platforms]**. Selecionando este [!UICONTROL URL Type] opção, [!DNL Audience Manager] não obscurece o referenciador [!DNL URL] informações ao acionar um [!DNL Facebook WCA] pixel.
* **[!UICONTROL Serialize]**: Selecionar **[!UICONTROL Enable]**.
* No **[!UICONTROL Base URL]** e **[!UICONTROL Secure URL]** insira o [!DNL Facebook WCA] pixel.
* **[!UICONTROL Delimiter]**: `,`

Base [!DNL URL] exemplo: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemplo de pixel disparado da página. Este exemplo mostra um usuário que se qualifica para três [!DNL Audience Manager] com as IDs 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parâmetro | Descrição |
|---------|----------|
| `id` | Seu [!DNL Facebook] ID de pixel, que você pode encontrar na variável [!DNL Facebook Ad Manager] ao criar pixels de público. |
| `ev` | Event.     Esse é um valor arbitrário, que aparecerá no campo [!DNL Facebook Ad Manager] assim que o pixel começar a ser acionado no site. Consulte a [!UICONTROL Include] item em [Etapa 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), para obter mais informações. |
| `cd[segID]` | Um parâmetro adicional, que começará a ser preenchido dentro do [!DNL Facebook Ad Manager] assim que o pixel começar a ser acionado no site. `segID` também é arbitrária. |
| `%ALIAS%` | Um [!DNL Audience Manager] macro, que será substituída dinamicamente pela variável [!DNL Audience Manager] [!UICONTROL segment] IDs para as quais o visitante do site se qualifica, delimitadas por vírgula , |

Seu [!UICONTROL URL destination] A configuração do deve parecer com a imagem abaixo:

![Configuração de destino](/help/using/integration/assets/facebook-wca.png)

Salve o [!UICONTROL destination]. Em seguida, você pode prosseguir para a **Mapeamentos de segmentos** etapa.

## Etapa 2 - Mapeamentos de segmentos - Mapear segmento para destino {#step-2-segment-mappings}

No [Configurar destino de URL](/help/using/features/destinations/create-url-destination.md) fluxo de trabalho, mapeie o segmento aplicável para o segmento recém-criado [!UICONTROL destination]. Observe que o valor de mapeamento é preenchido automaticamente com [!DNL Audience Manager] [!UICONTROL segment ID].

Informe uma data final, se aplicável; caso contrário, deixe em branco se não houver uma data final.

## Etapa 3 - Criar um [!UICONTROL Audience] no prazo de [!DNL Facebook Ads Manager] {#step-3-create-audience}

Consulte [Criar um público-alvo personalizado do site](https://www.facebook.com/business/help/666509013483225) no [!DNL Facebook] documentação de ajuda. Selecione o [!UICONTROL Create Audience] opções na tabela abaixo:

| Item | Descrição |
|---------|----------|
| Tráfego no site | Combinação Personalizada |
| Incluir | <ul><li>Selecionar **[!UICONTROL Event]** > Selecionar **[!UICONTROL Adobe-Audience-Manager-Segment]**. Este era o valor de `ev` no pixel de exemplo na etapa 1. Observe que se o pixel ainda não tiver sido acionado, a variável **[!UICONTROL Event]** ou **[!UICONTROL Adobe-Audience-Manager-Segment]** pode não aparecer na variável [!DNL Facebook] interface do usuário.</li><li>Adicionar um parâmetro: Selecionar `segID`.</li><li><p>Selecione o **contém** operador.</p><p>Isso é importante, considerando que os visitantes podem se qualificar para vários segmentos, pode haver vários [!UICONTROL segment IDs] no parâmetro pixel. Uso de &quot;iguais&quot; (`=`) pode não qualificar seus visitantes para o público-alvo e você observará um volume menor.</p></li><li>Adicione um valor: insira o [!DNL Audience Manager] ID do segmento.</li></ul> |
| Adicionar nova condição | Configuração opcional. |
| No último | Configuração opcional. |
| Nome do público | Recomendamos que você use o mesmo [!DNL Audience Manager] nome do segmento para fins de consistência, a menos que você esteja adicionando condições adicionais a este público-alvo. |

## Etapa 4 - Atribuir a [!UICONTROL Audience] para um [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Depois de criar o [!DNL Custom Audience], atribua-o a uma campanha publicitária. Crie uma nova campanha ou edite uma existente e você descobrirá que o público recém-criado está listado na [!DNL Facebook] interface do usuário. Sua campanha publicitária terá como alvo os usuários que viram o pixel disparar em seus navegadores ao visitar seu site, se [!DNL Audience Manager] O os inclui no segmento.

## Resumo {#summary}

Agora que você atribuiu a sua [!DNL Audience Manager] segmento para o [!DNL Facebook WCA] destino, [!DNL Audience Manager] acionará seletivamente o [!DNL Facebook WCA] pixel para usuários de um determinado segmento com a respectiva ID de segmento no pixel para preencher a [!DNL Facebook Audience]. Tal resulta num aumento gradual da [!DNL Facebook Audience] quanto mais a tag for acionada para o público aplicável no site.

>[!NOTE]
>
> Se um usuário sair do estado [!DNL Audience Manager] segmento, no momento, não há como [!DNL Audience Manager] para informar [!DNL Facebook] para remover o usuário do [!DNL Custom Audience].
