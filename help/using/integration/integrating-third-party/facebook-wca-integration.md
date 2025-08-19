---
description: Esta página ilustra o processo de criação de pixels de Públicos-alvo personalizados (WCA) de sites do Facebook para enviar segmentos de público-alvo do Audience Manager baseados na Web para o Facebook, para direcionamento de anúncios online com mais transparência.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Integração WCA com o Facebook
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 6dc931b88666515cf51ab89ce1a54bbcf9995679
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 1%

---

# Integração do [!DNL Facebook WCA] {#facebook-wca-integration}

Esta página ilustra o processo de criação de [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixels para enviar segmentos de público-alvo [!DNL Audience Manager] baseados na Web para [!DNL Facebook], para direcionamento de anúncios online com transparência aprimorada.

>[!IMPORTANT]
>
>Essa não é uma integração produzida entre o Audience Manager e o Facebook.

## Visão geral {#overview}

[O WCA (Públicos-alvo personalizados do site) do Facebook](https://www.facebook.com/business/help/610516375684216?id=2469097953376494) permite criar uma lista de pessoas que visitaram determinadas páginas ou realizaram ações específicas no seu site. O [!DNL Audience Manager] habilita a ativação no [!DNL WCA] usando destinos do [!DNL URL], com os quais você pode configurar uma integração personalizada baseada em pixels para enviar públicos baseados na Web para o [!DNL Facebook] para direcionamento.

![Integração WCA com o Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Esse recurso exige que você selecione a opção [!UICONTROL Website] público-alvo para plataformas sociais em [destinos de URL](/help/using/features/destinations/create-url-destination.md). Plataformas sociais exigem que as informações do referenciador sejam desmascaradas quando enviadas para sua plataforma. Esteja ciente de que isso significa que a plataforma/parceiro de destino poderá visualizar informações no referenciador [!DNL URL].

## Pré-requisitos {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segmentos, prontos para atribuir ao seu novo destino [!DNL Facebook]. Veja [como criar um segmento](/help/using/features/segments/segment-builder.md) na interface do usuário do [!DNL Audience Manager].
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versão 4.1.0 ou mais recente. Baixe a última versão **[aqui](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versão 9.0 ou mais recente, disponível para download de **[aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Como alternativa, se você usar o [Encaminhamento pelo Lado do Servidor (SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) para importar dados para o [!DNL Audience Manager], deverá usar a versão 2.12 ou mais recente do AppMeasurement. Baixe [!DNL AppMeasurement] usando o [Analytics Code Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).

Recomendamos instalar ou atualizar as bibliotecas nas etapas 3 e 4 usando as [Tags do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

## Etapa 1 - Criar um [!UICONTROL Facebook Destination] em [!DNL Audience Manager] {#step-1-create-facebook-destination}

Crie um novo [!UICONTROL URL Destination] em [!DNL Audience Manager] e nomeie-o [!DNL Facebook Website Custom Audiences]. Use as configurações abaixo ao criar o destino. Você também pode consultar a página [Configurar um destino de URL](/help/using/features/destinations/create-url-destination.md).

### Informações básicas

* **[!UICONTROL Category]**: Personalizado
* **[!UICONTROL Type]**: [!DNL URL]
* Marque a caixa de seleção **[!UICONTROL Auto-fill Destination Mapping]** e selecione **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Selecione a opção **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Esse rótulo de exportação impede que dados de terceiros e dados derivados de gráficos de dispositivos sejam incluídos nos segmentos.

### Configuração

* **[!UICONTROL URL type]**: Selecione **[!UICONTROL Website audience for social platforms]**. Ao selecionar esta opção [!UICONTROL URL Type], [!DNL Audience Manager] não obscurece as informações do referenciador [!DNL URL] ao disparar um pixel [!DNL Facebook WCA].
* **[!UICONTROL Serialize]**: Selecione **[!UICONTROL Enable]**.
* Nos campos **[!UICONTROL Base URL]** e **[!UICONTROL Secure URL]**, insira o pixel [!DNL Facebook WCA].
* **[!UICONTROL Delimiter]**: `,`

Exemplo de base [!DNL URL]: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemplo de pixel disparado da página. Este exemplo mostra um usuário que se qualifica para três [!DNL Audience Manager] segmentos, com as IDs 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parâmetro | Descrição |
|---------|----------|
| `id` | Sua ID de [!DNL Facebook] pixels, que você pode encontrar na interface do usuário [!DNL Facebook Ad Manager] ao criar pixels de público. |
| `ev` | Evento. Este é um valor arbitrário, que aparecerá na interface do usuário do [!DNL Facebook Ad Manager] quando o pixel começar a ser acionado no site. Consulte o item [!UICONTROL Include] em [Etapa 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), para obter mais informações. |
| `cd[segID]` | Um parâmetro adicional, que começará a ser preenchido na interface do usuário do [!DNL Facebook Ad Manager] quando o pixel começar a ser acionado no site. `segID` também é arbitrário. |
| `%ALIAS%` | Uma macro [!DNL Audience Manager], que será substituída dinamicamente pelas IDs [!DNL Audience Manager] [!UICONTROL segment] para as quais o visitante do site se qualifica, delimitadas por vírgula , |

A configuração do [!UICONTROL URL destination] deve ser semelhante à imagem abaixo:

![Configuração de destino](/help/using/integration/assets/facebook-wca.png)

Salve o [!UICONTROL destination]. Em seguida, você pode prosseguir para a etapa **Mapeamentos de segmentos**.

## Etapa 2 - Mapeamentos de segmentos - Mapear segmento para destino {#step-2-segment-mappings}

No fluxo de trabalho [Configurar destino da URL](/help/using/features/destinations/create-url-destination.md), mapeie o segmento aplicável para o [!UICONTROL destination] recém-criado. Observe que o valor de mapeamento é preenchido automaticamente com o [!DNL Audience Manager] [!UICONTROL segment ID].

Informe uma data final, se aplicável; caso contrário, deixe em branco se não houver uma data final.

## Etapa 3 - Criar um [!UICONTROL Audience] em [!DNL Facebook Ads Manager] {#step-3-create-audience}

Consulte [Criar um público-alvo personalizado do site](https://www.facebook.com/business/help/666509013483225) na documentação de ajuda do [!DNL Facebook]. Selecione as opções de [!UICONTROL Create Audience] na tabela abaixo:

| Item | Descrição |
|---------|----------|
| Tráfego no site | Combinação Personalizada |
| Incluir | <ul><li>Selecione **[!UICONTROL Event]** > Selecionar **[!UICONTROL Adobe-Audience-Manager-Segment]**. Este era o valor do parâmetro `ev` no pixel de exemplo na etapa 1. Observe que, se o pixel ainda não for acionado, a opção **[!UICONTROL Event]** ou **[!UICONTROL Adobe-Audience-Manager-Segment]** pode não aparecer na interface do usuário [!DNL Facebook].</li><li>Adicionar um parâmetro: Selecione `segID`.</li><li><p>Selecione o operador **contains**.</p><p>Isso é importante, considerando que os visitantes podem se qualificar para vários segmentos, pode haver vários [!UICONTROL segment IDs] no parâmetro de pixel. O uso do operador equals (`=`) pode não qualificar seus visitantes para o público-alvo, e você observará um volume menor.</p></li><li>Adicionar um valor: insira a ID de segmento [!DNL Audience Manager].</li></ul> |
| Adicionar nova condição | Configuração opcional. |
| No último | Configuração opcional. |
| Nome do público | Recomendamos usar o mesmo nome de segmento [!DNL Audience Manager] para consistência, a menos que você esteja adicionando condições adicionais a esse público-alvo. |

## Etapa 4 - Atribuir o [!UICONTROL Audience] a um [!UICONTROL Campaign] em [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Depois de criar o [!DNL Custom Audience], atribua-o a uma campanha publicitária. Crie uma nova campanha ou edite uma existente e você descobrirá que o público recém-criado está listado na interface do usuário do [!DNL Facebook]. Sua campanha publicitária será direcionada aos usuários que viram o pixel disparar em seus navegadores ao visitar seu site, se [!DNL Audience Manager] incluí-los no segmento.

## Resumo {#summary}

Agora que você atribuiu o segmento [!DNL Audience Manager] ao destino [!DNL Facebook WCA], o [!DNL Audience Manager] acionará seletivamente o pixel [!DNL Facebook WCA] para os usuários de um determinado segmento com a respectiva ID de segmento no pixel para preencher o [!DNL Facebook Audience]. Isso resulta em um aumento gradual no [!DNL Facebook Audience], quanto mais a tag é acionada para o público aplicável no site.

>[!NOTE]
>
> Se um usuário cai fora do segmento [!DNL Audience Manager], atualmente não há como [!DNL Audience Manager] informar [!DNL Facebook] para remover o usuário do [!DNL Custom Audience].
>
