---
description: Esse procedimento requer uma lista de recomercialização do adwords, um código de pixel e um destino de URL do Audience Manager. Também é conhecido como uma lista de recomercialização para a integração de anúncios de pesquisa (RLSA). Aplica-se somente à pesquisa paga.
seo-description: Esse procedimento requer uma lista de recomercialização do adwords, um código de pixel e um destino de URL do Audience Manager. Também é conhecido como uma lista de recomercialização para a integração de anúncios de pesquisa (RLSA). Aplica-se somente à pesquisa paga.
seo-title: Enviar segmentos para uma lista de remarketing do Google adwords
solution: Audience Manager
title: Enviar segmentos para uma lista de remarketing do Google adwords
uuid: 5 ad 821 c 6-48 b 4-42 c 0-b 912-1563331 e 93 a 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Send Segments to a Google Ads Remarketing List {#send-segments-to-a-google-adwords-remarketing-list}

This procedure requires a [!DNL Google Ads] remarketing list, pixel code, and an Audience Manager [!DNL URL] destination. It is also known as a remarketing list for search ads ([!DNL RLSA]) integration. Aplica-se somente à pesquisa paga.

>[!IMPORTANT]
>Observe que esta não é uma integração productizada dos dois sistemas.

To set up a [!DNL Google Ads] remarketing list as an [!DNL Audience Manager] URL destination:

1. In your [!DNL Google Ads] account, [create a website re-marketing list](https://support.google.com/adwords/answer/2454064?hl=en) and write down your conversion ID.
1. Use o URL a seguir como modelo para URL base e URL seguro. Substitua a seção xxxxxxxx pela ID de conversão.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager, [Create a URL destination](../../features/destinations/manage-destinations.md#configure-url-destination) or edit an existing destination. Use as seguintes configurações ao criar o destino:
   * Tipo: URL
   * Serializar: Ativado
   * Delimitador: Ponto e vírgula (;)

1. In the [!UICONTROL Segment Mappings] section of your [!DNL URL] destination, add the code from step 2 to the [!DNL URL] and [!DNL Secure URL] fields. Prefix the code with `http:` and `https:` in the [!DNL URL] and [!DNL Secure URL] fields, respectively.

   >[!IMPORTANT]
   >
   >Replace encoded ampersands `&` with un-encoded ampersands `&`

   Unsecure [!DNL URL] code:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Secure [!DNL URL] code:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Clique em **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Se estiver trabalhando com vários segmentos, obtenha um novo pixel para cada segmento que deseja mapear para um destino de anúncios do Google. Isso garante que os dados sejam aplicados à lista de recomercialização apropriada.

1. When mapping a new segment to this destination in Audience Manager, define the mapping as `aam=segmentID` and replace `segmentID` with the ID of your segment.
1. When defining a bucket in [!DNL Google Ads], create a rule that matches the mapping defined at step 6.

Um mapeamento concluído pode ser semelhante a:

![](../assets/rlsa_mapping.png)

>[!MORE_ LIKE_ THIS]
>
>* [Destinos](../../features/destinations/destinations.md)
>* [Criar um destino de URL](../../features/destinations/manage-destinations.md#configure-url-destination)
>* [Sobre listas de remarketing adwords](https://support.google.com/adwords/answer/2472738)
>* [Como o adwords Remarketing funciona](https://support.google.com/adwords/answer/2454000)

