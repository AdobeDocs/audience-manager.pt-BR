---
description: Configure o OpenX como destino e envie dados de segmento de Audience Manager para essa plataforma.
seo-description: Configure o OpenX como destino e envie dados de segmento de Audience Manager para essa plataforma.
seo-title: OpenX como um destino do Audience Manager
solution: Audience Manager
title: OpenX como um destino do Audience Manager
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 3%

---


# OpenX como um destino do Audience Manager{#openx-as-an-audience-manager-destination}

Configure [!DNL OpenX] como destino e envie dados de segmento de Audience Manager para essa plataforma.

>[!NOTE]
>
>Somente para direcionamento de servidor de anúncios no site.

## Requisitos de Destino OpenX {#openx-requirements}

Padrões para posicionamento de código, formatos de valor-chave suportados, relatórios e o tipo de dados de segmento enviados para [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Revise o seguinte antes de configurar [!DNL OpenX] como um destino Audience Manager:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] código deve ser implantado em seu site. [!UICONTROL DIL] ajuda a eliminar a necessidade de gravar um código especial para coleta de dados, integração, leitura de valores de cookies e recuperação de dados da página.
* **`get_aamCookie`Função:** Código que captura a ID de usuário do Audience Manager e os dados do cookie. Coloque [este código](../../features/destinations/get-aam-cookie-code.md) na parte superior da página ou dentro do bloco de códigos `<head>`.
* **Enviar Logs do delivery Audience Manager:** se quiser um relatório de delivery de segmento (opcional), forneça ao Audience Manager um registro diário que contenha dados de delivery de nível de impressão. Os dados podem estar em um formato bruto, mas cada registro deve conter o Audience Manager `UUID`. O Audience Manager pode coletar ou receber esses itens por meio de [!DNL FTP].

### Dados de valor-chave: Requisitos de formato

Audience Manager envia dados na forma de pares de valores chave. Crie pares de valores chave de acordo com as seguintes especificações:

* Teclas prefáticas com `c.` (por exemplo, `c.color` ou `c.price`).
* Separe os valores serializados anexados a uma única chave com uma vírgula (por exemplo, `c.color = red, green, blue`).
* Separe vários pares de valores chave com um E comercial (por exemplo, `c.color=red & c.price = 100 & c.condition = new`).
* Os nomes de teclas não devem conter caracteres especiais, como acentos e sinais de pontuação ou outros símbolos.

### Somente segmentos qualificados são enviados para o OpenX

A quantidade de dados transmitida para [!DNL OpenX] depende de quantos segmentos um usuário específico se qualifica. Por exemplo, considere configurar 100 segmentos de Audience Manager. Se um visitante de site se qualificar para cinco deles, então apenas esses cinco segmentos serão enviados para [!DNL OpenX] (não todos os 100).

## Criar um Destino OpenX {#openx-destination}

Crie um destino de cookie para [!DNL OpenX] no Audience Manager.

<!-- aam-openx-destination.xml -->

No Audience Manager, um *destino* é qualquer outro sistema (servidor de anúncios, [!DNL DSP], rede de anúncios, etc.) com o qual você deseja compartilhar dados. [!UICONTROL Destination Builder] fornece as ferramentas que permitem criar e gerenciar esses processos de delivery de dados. Os recursos de destino de Audience Manager estão localizados em *Dados de Audiência > Destinos*. Para começar, clique em **[!UICONTROL Add New Destination]** e siga as etapas abaixo.

### Etapa 1: Informações básicas

Para concluir a seção [!UICONTROL Basic Information]:

1. Nomeie o destino.
1. Selecione **[!UICONTROL "Cookie"]** na lista suspensa [!UICONTROL Type].
1. Clique em **[!UICONTROL Next]** e vá para as seções [!UICONTROL Configuration] e [!UICONTROL Segment Mappings].

### Etapa 2: Informações de configuração

Para concluir a seção [!UICONTROL Configuration]:

1. **Nome do cookie:** forneça um nome curto e descritivo para o cookie.
1. **Domínio do cookie:** deixe em branco para definir um cookie no domínio da página atual do usuário. Se você quiser especificar um domínio, coloque um prefixo no nome com um ponto como este, `.mydomain.com`.
1. Escolha uma opção de chave na seção [!UICONTROL Data Format].
1. Se as chaves usarem dados com valores serializados, selecione o controle **[!UICONTROL Serialize]** e especifique o delimitador serial (o caractere que separa os valores serializados).
1. Clique em **[!UICONTROL Save]** e expanda a seção [!UICONTROL Segment Mappings].

### Etapa 3: Mapeamentos de segmentos

Para adicionar um segmento a um destino de cookie:

1. **Localizar segmentos:** A  [!UICONTROL Segment Mappings] seção fornece duas ferramentas de pesquisa para ajudar a localizar segmentos. Para localizar um segmento:
   * Opção 1: Start que digita um nome de segmento no campo de pesquisa. O campo é atualizado automaticamente com base no texto. Clique em **[!UICONTROL Add]** depois de encontrar o segmento que deseja usar.
   * Opção 2: Clique em **[!UICONTROL Browse All Segments]** para abrir uma janela que permite procurar segmentos por nome ou local do armazenamento. Clique em **[!UICONTROL Add Selected Segments]** quando terminar.
1. **Adicionar mapeamentos:** no pop-up mapeamentos, insira a ID do segmento no campo mapeamentos e clique em  **[!UICONTROL Save]**.
1. Clique em **[!UICONTROL Done]**.

## Configuração do OpenX {#openx-code-setup}

Modifique as configurações [!DNL OpenX] para trabalhar com dados de segmento de Audience Manager.

<!-- aam-openx-code.xml -->

Para configurar [!DNL OpenX]:

* Instale o código [!UICONTROL DIL] no seu site.
* Crie [!DNL OpenX] como um destino de cookie no Audience Manager.
* Coloque a função `get_aamCookie` na parte superior da página, idealmente dentro do bloco `<head>`. O código `get_aamCookie` está disponível [aqui](../../features/destinations/get-aam-cookie-code.md).
* Modifique sua tag de publicidade para chamar a função `get_aamCookie` e inclua o nome do cookie fornecido ao configurar o destino [!DNL OpenX]. Por exemplo, se você nomeou o cookie `test_cookie`, a tag de anúncio deve chamar `get_aamCookie` e fazer referência ao nome do cookie.
* Sua tag de publicidade pode ser semelhante ao exemplo abaixo.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Lembre-se de incluir `xid=`. Ele contém a ID de usuário exclusiva real ([!UICONTROL UUID]) transmitida durante uma chamada de anúncio.

A chamada de anúncio totalmente formada pode ser semelhante a esta:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
