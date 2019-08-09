---
description: Esse procedimento requer uma lista de recomercialização do adwords, um código de pixel e um destino de URL do Audience Manager. Também é conhecido como uma lista de recomercialização para a integração de anúncios de pesquisa (RLSA). Aplica-se somente à pesquisa paga.
seo-description: Esse procedimento requer uma lista de recomercialização do adwords, um código de pixel e um destino de URL do Audience Manager. Também é conhecido como uma lista de recomercialização para a integração de anúncios de pesquisa (RLSA). Aplica-se somente à pesquisa paga.
seo-title: Enviar segmentos para uma lista de remarketing do Google adwords
solution: Audience Manager
title: Enviar segmentos para uma lista de remarketing do Google adwords
uuid: 5 ad 821 c 6-48 b 4-42 c 0-b 912-1563331 e 93 a 2
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Enviar segmentos para uma lista de remarketing do Google Ads {#send-segments-to-a-google-adwords-remarketing-list}

Esse procedimento requer uma lista [!DNL Google Ads] de recomercialização, um código de pixel e [!DNL URL] um destino do Audience Manager. Também é conhecido como uma lista de recomercialização para anúncios de pesquisa ([!DNL RLSA]). Aplica-se somente à pesquisa paga.

>[!IMPORTANT]
>Observe que esta não é uma integração productizada dos dois sistemas.

Para configurar uma lista [!DNL Google Ads] de recomercialização como destino [!DNL Audience Manager] de URL:

1. Em sua [!DNL Google Ads] conta [, crie uma lista](https://support.google.com/adwords/answer/2454064?hl=en) de recomercialização e anote a ID de conversão.
1. Use o URL a seguir como modelo para URL base e URL seguro. Substitua a seção xxxxxxxx pela ID de conversão.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. No Audience Manager, [crie um destino de URL](../../features/destinations/create-url-destination.md) ou edite um destino existente. Use as seguintes configurações ao criar o destino:
   * Tipo: URL
   * Serializar: Ativado
   * Delimitador: Ponto e vírgula (;)

1. Na [!UICONTROL Segment Mappings] seção do [!DNL URL] destino, adicione o código da etapa 2 aos [!DNL URL][!DNL Secure URL] campos. Prefixe o código com `http:` e `https:` nos [!DNL URL][!DNL Secure URL] campos, respectivamente.

   >[!IMPORTANT]
   >
   >Substituir os Ampersands codificados `&` por Ampersands não codificados `&`

   Código não seguro [!DNL URL] :

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Código seguro [!DNL URL] :

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Clique em **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Se estiver trabalhando com vários segmentos, obtenha um novo pixel para cada segmento que deseja mapear para um destino de anúncios do Google. Isso garante que os dados sejam aplicados à lista de recomercialização apropriada.

1. Ao mapear um novo segmento para esse destino no Audience Manager, defina o mapeamento como `aam=segmentID` e substitua `segmentID` pela ID do segmento.
1. Ao definir um compartimento em [!DNL Google Ads], crie uma regra que corresponda ao mapeamento definido na etapa 6.

Um mapeamento concluído pode ser semelhante a:

![](../assets/rlsa_mapping.png)

>[!MORE_ LIKE_ THIS]
>
>* [Destinos](../../features/destinations/destinations.md)
>* [Criar um destino de URL](../../features/destinations/create-url-destination.md)
>* [Sobre listas de remarketing adwords](https://support.google.com/adwords/answer/2472738)
>* [Como o adwords Remarketing funciona](https://support.google.com/adwords/answer/2454000)

