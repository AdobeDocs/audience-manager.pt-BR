---
description: Configure Abrir servidor de publicidade como destino e envie os dados do Audience Manager para essa plataforma.
seo-description: Configure Abrir servidor de publicidade como destino e envie os dados do Audience Manager para essa plataforma.
seo-title: OAS como um destino do Audience Manager
solution: Audience Manager
title: OAS como um destino do Audience Manager
uuid: 5891 a 063-5 a 4 b -4 ea 7-865 f-b 24 e 17 ca 735 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# OAS as an Audience Manager Destination {#oas-as-an-audience-manager-destination}

Set up [!DNL Open Ad Server] as a destination and send Audience Manager data to that platform.

## OAS Destination Requirements {#oas-requirements}

Standards for code placement, supported key-value formats, reports, and the type of segment data sent to [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Esse tipo de destino exige o seguinte:

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library] deve ser implantado em seu inventário. [!UICONTROL DIL] ajuda a eliminar a necessidade de gravar código especial para coleta de dados, integração, leitura de valores de cookies e recuperar dados da página.
* **`get_aamCookie`Função:** Código que captura a ID de usuário do Audience Manager e os dados do cookie. Place [this code](../../features/destinations/get-aam-cookie-code.md) on the top of the page or inside the `<head>` codeblock.
* **Enviar logs de entrega para o Audience Manager:** Se desejar um relatório de entrega de segmento (opcional), forneça ao Audience Manager um log diário que contenha dados de entrega de nível de impressão. The data can be in a raw format, but each record must contain the Audience Manager [!UICONTROL UUID]. Audience Manager can pick up or receive these via [!DNL FTP].

### Formato do cookie e dados de valor-chave

O Audience Manager pode enviar dados de segmento para um cookie do navegador da seguinte maneira:

* Single keys (`x=1&x=2`);
* Multiple keys (`x=1&x=2&y=3&y=4`);
* Serialized values (`x=1,2,3`);
* Um delimitador de valor padrão usado para separar pares de valores chave individuais.

### Somente os segmentos qualificados são enviados para OAS

The amount data passed in to [!DNL OAS] depends on how many segments a particular user qualifies for. Por exemplo, digamos que você configure os segmentos de Gerenciamento de público-alvo 100. Se um visitante do site se qualificar para cinco deles, somente esses cinco segmentos serão enviados para OAS (nem todos os 100).

>[!MORE_ LIKE_ THIS]
>
>* [código get_ aamcookie](../../features/destinations/get-aam-cookie-code.md)
>* [Pares de valores chave explicados](../../reference/key-value-pairs-explained.md)


## Create an OAS Destination {#oas-dest-setup}

Create a cookie-based destination for [!DNL OAS] in Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) que deseja compartilhar dados. [!UICONTROL Destination Builder] fornece as ferramentas que permitem criar e gerenciar esses processos de entrega de dados. Audience Manager destination features are located in *Audience Data &gt; Destinations*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

### Etapa 1: Informações básicas

To complete the [!UICONTROL Basic Information] section:

1. Dê um nome ao destino.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Save]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

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

## OAS Setup {#oas-code-setup}

Modify [!DNL OAS] settings to work with Audience Manager segment data.

<!-- aam-oas-code.xml -->

To set up [!DNL OAS]

* Install [!UICONTROL DIL] code across your site.
* Crie OAS como destino de cookie no Audience Manager.
* Place the `get_aamCookie` function at the top of the page, ideally within the `<head>` codeblock. The `get_aamCookie` code is available [here](../../features/destinations/get-aam-cookie-code.md).
* Modify your ad tag to call the `get_aamCookie` function and include the cookie name you provided when setting up the [!DNL OAS] destination. For example, if you named the cookie `test_cookie`, then the ad tag should call `get_aamCookie` and reference the cookie name.
* Sua tag de publicidade pode ser semelhante ao exemplo abaixo.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Remember to include the `u=` variable. It holds the actual unique user ID ([!UICONTROL UUID]) passed in during an ad call.
