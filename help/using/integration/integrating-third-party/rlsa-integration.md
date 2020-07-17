---
description: Este procedimento requer uma lista de recomercialização do AdWords, um código de pixel e um destino de URL Audience Manager. Também é conhecida como lista de remarketing para integração de anúncios de pesquisa (RLSA). Aplica-se somente à pesquisa paga.
seo-description: Este procedimento requer uma lista de recomercialização do AdWords, um código de pixel e um destino de URL Audience Manager. Também é conhecida como lista de remarketing para integração de anúncios de pesquisa (RLSA). Aplica-se somente à pesquisa paga.
seo-title: Enviar segmentos para uma Lista de remarketing do Google AdWords
solution: Audience Manager
title: Enviar segmentos para uma Lista de remarketing do Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 5%

---


# Send Segments to a Google Ads Remarketing List {#send-segments-to-a-google-adwords-remarketing-list}

Esse procedimento requer uma lista [!DNL Google Ads] de recomercialização, um código de pixel e um Audience Manager [!DNL URL] [!DNL destination]. Também é conhecida como lista de remarketing para integração de anúncios de pesquisa ([!DNL RLSA]). Aplica-se somente à pesquisa paga.

>[!IMPORTANT]
>Observe que esta não é uma integração produtiva dos dois sistemas.

Para configurar uma lista [!DNL Google Ads] de recomercialização como uma [!DNL Audience Manager] das seguintes opções [!DNL URL destination]:

1. Em sua [!DNL Google Ads] conta, [crie uma lista](https://support.google.com/adwords/answer/2454064?hl=en) de remarketing do site e anote sua ID de conversão.
1. Use o seguinte URL como modelo para o URL básico e o URL seguro. Substitua a seção xxxxxxxx pela ID de conversão.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. No Audience Manager, [crie [!DNL URL destination]](../../features/destinations/create-url-destination.md) ou edite um existente [!DNL destination]. Use as seguintes configurações ao criar o [!DNL destination]:
   * Tipo: URL
   * Serializar: Ativado
   * Delimitador: Ponto-e-vírgula (;)

1. Na [!UICONTROL Segment Mappings] seção de sua [!DNL URL] página [!DNL destination], adicione o código da etapa 2 aos campos [!DNL URL] e [!DNL Secure URL] . Prefixe o código com `http:` e `https:` nos campos [!DNL URL] e [!DNL Secure URL] , respectivamente.

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
   >Se estiver trabalhando com vários segmentos, obtenha um novo pixel para cada segmento que deseja mapear para um [!DNL Google Ads][!DNL destination]. Isso garante que os dados sejam aplicados à lista de recomercialização apropriada.

1. Ao mapear um novo segmento para isso [!DNL destination] no Audience Manager, defina o mapeamento como `aam=segmentID` e substitua `segmentID` pela ID do segmento.
1. Ao definir um bucket em [!DNL Google Ads], crie uma regra que corresponda ao mapeamento definido na etapa 6.

Um mapeamento concluído pode ser semelhante a:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!Destinos DNL]](../../features/destinations/destinations.md)
>* [Criar um [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [Sobre Listas de recomercialização do AdWords](https://support.google.com/adwords/answer/2472738)
>* [Como funciona a recomercialização de AdWords](https://support.google.com/adwords/answer/2454000)

