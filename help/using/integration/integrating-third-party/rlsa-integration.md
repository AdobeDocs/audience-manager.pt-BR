---
description: Este procedimento requer uma lista de remarketing do AdWords, um código de pixel e um destino de URL de Audience Manager. Também é conhecida como uma lista de remarketing para integração de anúncios de pesquisa (RLSA). Aplica-se somente à pesquisa paga.
seo-description: Este procedimento requer uma lista de remarketing do AdWords, um código de pixel e um destino de URL de Audience Manager. Também é conhecida como uma lista de remarketing para integração de anúncios de pesquisa (RLSA). Aplica-se somente à pesquisa paga.
seo-title: Enviar segmentos para uma Lista de remarketing do Google AdWords
solution: Audience Manager
title: Enviar segmentos para uma Lista de remarketing do Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third-party Integration
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 5%

---

# Enviar segmentos para uma Lista de remarketing do Google Ads {#send-segments-to-a-google-adwords-remarketing-list}

Este procedimento requer uma [!DNL Google Ads] lista de remarketing, código de pixel e um Audience Manager [!DNL URL] [!DNL destination]. Também é conhecida como uma lista de remarketing para integração de anúncios de pesquisa ([!DNL RLSA]). Aplica-se somente à pesquisa paga.

>[!IMPORTANT]
>Observe que não se trata de uma integração produzida dos dois sistemas.

Para configurar uma lista de remarketing [!DNL Google Ads] como um [!DNL Audience Manager] [!DNL URL destination]:

1. Em sua conta [!DNL Google Ads], [crie uma lista de remarketing do site](https://support.google.com/adwords/answer/2454064?hl=en) e anote sua ID de conversão.
1. Use o seguinte URL como modelo para o URL básico e o URL seguro. Substitua a seção xxxxxxxx pela ID de conversão.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. No Audience Manager, [Crie um [!DNL URL destination]](../../features/destinations/create-url-destination.md) ou edite um [!DNL destination] existente. Use as seguintes configurações ao criar o [!DNL destination]:
   * Tipo: URL
   * Serializar: Ativado
   * Delimitador: Ponto e vírgula (;)

1. Na seção [!UICONTROL Segment Mappings] de [!DNL URL] [!DNL destination], adicione o código da etapa 2 aos campos [!DNL URL] e [!DNL Secure URL]. Coloque o prefixo `http:` e `https:` nos campos [!DNL URL] e [!DNL Secure URL], respectivamente.

   >[!IMPORTANT]
   >
   >Substitua os &quot;E&quot; comercial (&amp;) codificados `&` por &quot;E&quot; comercial (&amp;) não codificado `&`

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
   >Se estiver trabalhando com vários segmentos, obtenha um novo pixel para cada segmento que deseja mapear para um [!DNL Google Ads] [!DNL destination]. Isso garante que os dados sejam aplicados à lista de remarketing apropriada.

1. Ao mapear um novo segmento para esse [!DNL destination] no Audience Manager, defina o mapeamento como `aam=segmentID` e substitua `segmentID` pela ID do segmento.
1. Ao definir um bucket em [!DNL Google Ads], crie uma regra que corresponda ao mapeamento definido na etapa 6.

Um mapeamento concluído pode ser semelhante a:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [Criar um [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [Sobre as listas de remarketing do AdWords](https://support.google.com/adwords/answer/2472738)
>* [Como a recomercialização do AdWords funciona](https://support.google.com/adwords/answer/2454000)

