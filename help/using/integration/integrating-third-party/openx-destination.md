---
description: Configure openx como destino e envie os dados de segmento do Audience Manager para essa plataforma.
seo-description: Configure openx como destino e envie os dados de segmento do Audience Manager para essa plataforma.
seo-title: Openx como Destino do Audience Manager
solution: Audience Manager
title: Openx como Destino do Audience Manager
uuid: 5 e 86 ba 73-281 c -403 b-af 06-64 a 1 d 427526 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# OpenX as an Audience Manager Destination{#openx-as-an-audience-manager-destination}

Set up [!DNL OpenX] as a destination and send Audience Manager segment data to that platform.

>[!NOTE]
>
>Somente para direcionamento do servidor de publicidade no site.

## OpenX Destination Requirements {#openx-requirements}

Standards for code placement, supported key-value formats, reports, and the type of segment data sent to [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Review the following before setting up [!DNL OpenX] as an Audience Manager destination:

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library] deve ser implantado em seu site. [!UICONTROL DIL] ajuda a eliminar a necessidade de gravar código especial para coleta de dados, integração, leitura de valores de cookies e recuperar dados da página.
* **`get_aamCookie`Função:** Código que captura a ID de usuário do Audience Manager e os dados do cookie. Place [this code](../../features/destinations/get-aam-cookie-code.md) on the top of the page or inside the `<head>` codeblock.
* **Enviar logs de entrega para o Audience Manager:** Se desejar um relatório de entrega de segmento (opcional), forneça ao Audience Manager um log diário que contenha dados de entrega de nível de impressão. The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager can pick up or receive these via [!DNL FTP].

### Dados de chave-valor: Requisitos de formato

O Audience Manager envia dados na forma de pares de valor chave. Crie pares de valor chave de acordo com as seguintes especificações:

* Preface keys with `c.` (e.g., `c.color` or `c.price`).
* Separate serialized values attached to a single key with a comma (e.g., `c.color = red, green, blue`).
* Separate multiple key-value pairs with an ampersand (e.g., `c.color=red & c.price = 100 & c.condition = new`).
* Os nomes de teclas não devem conter caracteres especiais, como marcas de acento e pontuação ou outros símbolos.

### Somente os segmentos qualificados são enviados para openx

The amount data passed in to [!DNL OpenX] depends on how many segments a particular user qualifies for. Por exemplo, digamos que você configure os segmentos de Gerenciamento de público-alvo 100. If a site visitor qualifies for five of them, then only those five segments get sent to [!DNL OpenX] (not all 100).

## Create an OpenX Destination {#openx-destination}

Create a cookie destination for [!DNL OpenX] in Audience Management.

<!-- aam-openx-destination.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) que deseja compartilhar dados. [!UICONTROL Destination Builder] fornece as ferramentas que permitem criar e gerenciar esses processos de entrega de dados. Audience Manager destination features are located in *Audience Data &gt; Destinations*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

### Etapa 1: Informações básicas

To complete the [!UICONTROL Basic Information] section:

1. Dê um nome ao destino.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

### Etapa 2: Informações de configuração

To complete the [!UICONTROL Configuration] section:

1. **Nome do cookie:** Forneça um nome curto e descritivo para o seu cookie.
1. **Domínio do cookie:** Deixe em branco para definir um cookie no domínio da página atual do usuário. If you want to specify a domain, prefix the name with a period like this, `.mydomain.com`.
1. Choose a key option in the [!UICONTROL Data Format] section.
1. If your keys use data with serialized values, select the **[!UICONTROL Serialize]** control and specify the serial delimiter (the character that separates the serialized values).
1. Click **[!UICONTROL Save]** and expand the [!UICONTROL Segment Mappings] section.

### Etapa 3: Mapeamentos de segmento

Para adicionar um segmento a um destino de cookie:

1. **Localizar segmentos:** [!UICONTROL Segment Mappings] A seção fornece duas ferramentas de pesquisa para ajudar a localizar segmentos. Para encontrar um segmento:
   * Opção 1: Comece a digitar um nome de segmento no campo de pesquisa. O campo é atualizado automaticamente com base no texto. Click **[!UICONTROL Add]** once you find the segment you want to use.
   * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.
1. **Adicionar mapeamentos:** Nos pop-ups, insira a ID do segmento no campo de mapeamentos e clique **[!UICONTROL Save]** em.
1. Clique em **[!UICONTROL Done]**.

## OpenX Setup {#openx-code-setup}

Modify [!DNL OpenX] settings to work with Audience Manager segment data.

<!-- aam-openx-code.xml -->

To set up [!DNL OpenX]:

* Install [!UICONTROL DIL] code across your site.
* Create [!DNL OpenX] as a cookie destination in Audience Manager.
* Place the `get_aamCookie` function at the top of the page, ideally within the `<head>` codeblock. The `get_aamCookie` code is available [here](../../features/destinations/get-aam-cookie-code.md).
* Modify your ad tag to call the `get_aamCookie` function and include the cookie name you provided when setting up the [!DNL OpenX] destination. For example, if you named the cookie `test_cookie`, then the ad tag should call `get_aamCookie` and reference the cookie name.
* Sua tag de publicidade pode ser semelhante ao exemplo abaixo.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Remember to include `xid=` . It holds the actual unique user ID ([!UICONTROL UUID]) passed in during an ad call.

A chamada de anúncio completamente formada pode ser semelhante a:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
