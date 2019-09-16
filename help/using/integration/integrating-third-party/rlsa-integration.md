---
description: Este procedimento requer uma lista de recomercialização do AdWords, um código de pixels e um destino de URL do Audience Manager. Também é conhecida como uma lista de remarketing para integração de anúncios de pesquisa (RLSA). Aplica-se somente à pesquisa paga.
seo-description: Este procedimento requer uma lista de recomercialização do AdWords, um código de pixels e um destino de URL do Audience Manager. Também é conhecida como uma lista de remarketing para integração de anúncios de pesquisa (RLSA). Aplica-se somente à pesquisa paga.
seo-title: Enviar segmentos para uma lista de recomercialização do Google AdWords
solution: Audience Manager
title: Enviar segmentos para uma lista de recomercialização do Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-156333e93a2
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Enviar segmentos para uma lista de comentários do Google Ads {#send-segments-to-a-google-adwords-remarketing-list}

Este procedimento requer uma lista de [!DNL Google Ads] recomercialização, um código de pixels e um [!DNL URL] destino do Audience Manager. Também é conhecida como uma lista de remarketing para integração de anúncios de pesquisa ([!DNL RLSA]). Aplica-se somente à pesquisa paga.

>[!IMPORTANT]
>Observe que esta não é uma integração produtiva dos dois sistemas.

Para configurar uma lista de [!DNL Google Ads] remarketing como um destino de [!DNL Audience Manager] URL:

1. Na sua [!DNL Google Ads] conta, [crie uma lista](https://support.google.com/adwords/answer/2454064?hl=en) de remarketing do site e anote sua ID de conversão.
1. Use o seguinte URL como modelo para o URL básico e o URL seguro. Substitua a seção xxxxxxxx pela ID de conversão.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. No Audience Manager, [crie um destino](../../features/destinations/create-url-destination.md) de URL ou edite um destino existente. Use as seguintes configurações ao criar o destino:
   * Tipo: URL
   * Serializar: Ativado
   * Delimitador: Ponto-e-vírgula (;)

1. Na [!UICONTROL Segment Mappings] seção do seu [!DNL URL] destino, adicione o código da etapa 2 aos campos [!DNL URL] e [!DNL Secure URL] . Prefixe o código com `http:` e `https:` nos campos [!DNL URL] e [!DNL Secure URL] , respectivamente.

   >[!IMPORTANT]
   >
   >Substitua os E-mails codificados `&` por E-mails não codificados `&`

   Código [!DNL URL] não seguro:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Código [!DNL URL] seguro:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Clique em **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Se estiver trabalhando com vários segmentos, obtenha um novo pixel para cada segmento que deseja mapear para um destino do Google Ads. Isso garante que os dados sejam aplicados à lista de recomercialização apropriada.

1. Ao mapear um novo segmento para esse destino no Audience Manager, defina o mapeamento como `aam=segmentID` e substitua `segmentID` pela ID do segmento.
1. Ao definir um bucket em [!DNL Google Ads], crie uma regra que corresponda ao mapeamento definido na etapa 6.

Um mapeamento concluído pode ser semelhante a:

![](../assets/rlsa_mapping.png)

>[!MORE_LIKE_THIS]
>
>* [Destinos](../../features/destinations/destinations.md)
>* [Criar um destino de URL](../../features/destinations/create-url-destination.md)
>* [Sobre as Listas de Recomercialização do AdWords](https://support.google.com/adwords/answer/2472738)
>* [Como funciona a recomercialização de AdWords](https://support.google.com/adwords/answer/2454000)

