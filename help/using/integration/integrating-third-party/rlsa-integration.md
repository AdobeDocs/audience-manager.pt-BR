---
description: Esse procedimento requer uma lista de remarketing do AdWords, um código de pixel e um destino de URL do Audience Manager. Também é conhecida como lista de remarketing para integração de anúncios de pesquisa (RLSA). Aplica-se somente à pesquisa paga.
seo-description: This procedure requires an AdWords remarketing list, pixel code, and an Audience Manager URL destination. It is also known as a remarketing list for search ads (RLSA) integration. Applies to paid search only.
seo-title: Send Segments to a Google AdWords Remarketing List
solution: Audience Manager
title: Enviar segmentos para uma Lista de remarketing do Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third-party Integration
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
TQID: https://experienceleague.adobe.com/BxJ9n5RLQwR8i9Sgu1cgeaijSCrKLltsAXdm0eQBqxY
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: c814092e-2730-45e8-a12d-e084529f52cb
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 284
ht-degree: 0%

---

# Enviar segmentos para uma Lista de remarketing do Google Ads {#send-segments-to-a-google-adwords-remarketing-list}

Este procedimento requer uma lista de remarketing [!DNL Google Ads], um código de pixel e um Audience Manager [!DNL URL] [!DNL destination]. Também é conhecida como lista de remarketing para integração de anúncios de pesquisa ([!DNL RLSA]). Aplica-se somente à pesquisa paga.

>[!IMPORTANT]
>Observe que essa não é uma integração produzida dos dois sistemas.

Para configurar uma lista de remarketing [!DNL Google Ads] como um [!DNL Audience Manager] [!DNL URL destination]:

1. Na sua conta do [!DNL Google Ads], [crie uma lista de remarketing para sites](https://support.google.com/tagmanager/answer/6106960?hl=en) e anote sua ID de conversão.
1. Use o seguinte URL como modelo para o URL básico e o URL seguro. Substitua a seção xxxxxxxx pelo seu ID de conversão.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. No Audience Manager, [Crie um  [!DNL URL destination]](../../features/destinations/create-url-destination.md) ou edite um [!DNL destination] existente. Usar as seguintes configurações ao criar o [!DNL destination]:
   * Tipo: URL
   * Serialização: ativada
   * Delimitador: ponto e vírgula ( &semi; )

1. Na seção [!UICONTROL Segment Mappings] do [!DNL URL] [!DNL destination], adicione o código da etapa 2 aos campos [!DNL URL] e [!DNL Secure URL]. Prefixe o código com `http:` e `https:` nos campos [!DNL URL] e [!DNL Secure URL], respectivamente.

   >[!IMPORTANT]
   >
   >Substituir &quot;E&quot; comercial codificado `&` por &quot;E&quot; comercial não codificado `&`

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

1. Ao mapear um novo segmento para este [!DNL destination] no Audience Manager, defina o mapeamento como `aam=segmentID` e substitua `segmentID` pela ID do seu segmento.
1. Ao definir um bucket no [!DNL Google Ads], crie uma regra que corresponda ao mapeamento definido na etapa 6.

Um mapeamento concluído pode ser semelhante a este:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [Criar um [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [Sobre Listas de Remarketing do AdWords](https://support.google.com/adwords/answer/2472738)
>* [Como funciona o remarketing do AdWords](https://support.google.com/adwords/answer/2454000)
