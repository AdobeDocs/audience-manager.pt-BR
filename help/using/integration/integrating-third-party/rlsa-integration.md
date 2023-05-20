---
description: Esse procedimento requer uma lista de remarketing do AdWords, um código de pixel e um destino de URL Audience Manager. Também é conhecida como lista de remarketing para integração de anúncios de pesquisa (RLSA). Aplica-se somente à pesquisa paga.
seo-description: This procedure requires an AdWords remarketing list, pixel code, and an Audience Manager URL destination. It is also known as a remarketing list for search ads (RLSA) integration. Applies to paid search only.
seo-title: Send Segments to a Google AdWords Remarketing List
solution: Audience Manager
title: Enviar segmentos para uma Lista de remarketing do Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third-party Integration
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
source-git-commit: b8d65ef8c27100d174a997eb24a75f37b4e75d40
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 3%

---

# Enviar segmentos para uma Lista de remarketing do Google Ads {#send-segments-to-a-google-adwords-remarketing-list}

Este procedimento requer um [!DNL Google Ads] lista de remarketing, código de pixel e um Audience Manager [!DNL URL] [!DNL destination]. Também é conhecida como lista de remarketing para anúncios de pesquisa ([!DNL RLSA]). Aplica-se somente à pesquisa paga.

>[!IMPORTANT]
>Observe que essa não é uma integração produzida dos dois sistemas.

Para configurar um [!DNL Google Ads] lista de remarketing como um [!DNL Audience Manager] [!DNL URL destination]:

1. No seu [!DNL Google Ads] conta, [criar uma lista de remarketing do site](https://support.google.com/tagmanager/answer/6106960?hl=en) e anote o ID de conversão.
1. Use o seguinte URL como modelo para o URL básico e o URL seguro. Substitua a seção xxxxxxxx pelo seu ID de conversão.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. No Audience Manager, [Criar um [!DNL URL destination]](../../features/destinations/create-url-destination.md) ou editar um existente [!DNL destination]. Use as seguintes configurações ao criar o [!DNL destination]:
   * Tipo: URL
   * Serialização: ativada
   * Delimitador: ponto e vírgula ( &amp;semi; )

1. No [!UICONTROL Segment Mappings] seção do seu [!DNL URL] [!DNL destination], adicione o código da etapa 2 à variável [!DNL URL] e [!DNL Secure URL] campos. Coloque o prefixo no código `http:` e `https:` no [!DNL URL] e [!DNL Secure URL] campos, respectivamente.

   >[!IMPORTANT]
   >
   >Substituir &quot;E&quot; comercial codificado `&` com &quot;E&quot; comercial não codificado `&`

   Não seguro [!DNL URL] código:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Seguro [!DNL URL] código:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Clique em **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Se estiver trabalhando com vários segmentos, obtenha um novo pixel para cada segmento que deseja mapear para um [!DNL Google Ads] [!DNL destination]. Isso garante que os dados sejam aplicados à lista de remarketing apropriada.

1. Ao mapear um novo segmento para esta [!DNL destination] no Audience Manager, defina o mapeamento como `aam=segmentID` e substituir `segmentID` com a ID do seu segmento.
1. Ao definir um intervalo no [!DNL Google Ads], crie uma regra que corresponda ao mapeamento definido na etapa 6.

Um mapeamento concluído pode ser semelhante a este:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [Criar um [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [Sobre as listas de remarketing do AdWords](https://support.google.com/adwords/answer/2472738)
>* [Como funciona o remarketing do AdWords](https://support.google.com/adwords/answer/2454000)

