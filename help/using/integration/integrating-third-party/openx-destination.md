---
description: Configure o OpenX como destino e envie dados de segmento do Audience Manager para essa plataforma.
seo-description: Configure o OpenX como destino e envie dados de segmento do Audience Manager para essa plataforma.
seo-title: OpenX como um destino do Audience Manager
solution: Audience Manager
title: OpenX como um destino do Audience Manager
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# OpenX como um destino do Audience Manager{#openx-as-an-audience-manager-destination}

Configure [!DNL OpenX] como destino e envie dados de segmento do Audience Manager para essa plataforma.

>[!NOTE]
>
>Somente para direcionamento de servidor de anúncios no site.

## Requisitos de destino do OpenX {#openx-requirements}

Padrões para o posicionamento de código, formatos de valor-chave suportados, relatórios e o tipo de dados de segmento enviados para [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Revise o seguinte antes de configurar [!DNL OpenX] como um destino do Audience Manager:

* **[!UICONTROL DIL]** : O [!UICONTROL Data Integration Library] código deve ser implantado em seu site. [!UICONTROL DIL] ajuda a eliminar a necessidade de gravar código especial para coleta de dados, integração, leitura de valores de cookies e recuperação de dados da página.
* **`get_aamCookie`** Função: Código que captura a ID de usuário e os dados de cookie do Audience Manager. Coloque [esse código](../../features/destinations/get-aam-cookie-code.md) na parte superior da página ou dentro do `<head>` bloco de código.
* **** Enviar registros de entrega ao Audience Manager: Se desejar um relatório de entrega de segmento (opcional), forneça ao Audience Manager um registro diário que contenha dados de entrega em nível de impressão. Os dados podem estar em um formato bruto, mas cada registro deve conter o Audience Manager `UUID`. O Audience Manager pode coletar ou receber isso via [!DNL FTP].

### Dados de valor-chave: Requisitos de formato

O Audience Manager envia dados na forma de pares de valores chave. Crie pares de valores chave de acordo com as seguintes especificações:

* Teclas prefáticas com `c.` (por exemplo, `c.color` ou `c.price`).
* Separe os valores serializados anexados a uma única chave com uma vírgula (por exemplo, `c.color = red, green, blue`).
* Separe vários pares de valores chave com um E comercial (por exemplo, `c.color=red & c.price = 100 & c.condition = new`).
* Os nomes de teclas não devem conter caracteres especiais, como acentos e sinais de pontuação ou outros símbolos.

### Somente segmentos qualificados são enviados para o OpenX

A quantidade de dados transmitida depende [!DNL OpenX] de quantos segmentos um usuário específico se qualifica. Por exemplo, digamos que você tenha configurado 100 segmentos de Gerenciamento de público-alvo. Se um visitante do site se qualificar para cinco deles, somente esses cinco segmentos serão enviados para [!DNL OpenX] (não todos os 100).

## Criar um destino OpenX {#openx-destination}

Crie um destino de cookie para [!DNL OpenX] o no Gerenciamento de público-alvo.

<!-- aam-openx-destination.xml -->

No Audience Manager, um *destino* é qualquer outro sistema (servidor de anúncios, rede de anúncios [!DNL DSP], etc.) com os quais você deseja compartilhar dados. [!UICONTROL Destination Builder] fornece as ferramentas que permitem criar e gerenciar esses processos de entrega de dados. Os recursos de destino do Audience Manager estão localizados em Dados de *público-alvo &gt; Destinos*. Para começar, clique **[!UICONTROL Add New Destination]** e siga as etapas abaixo.

### Etapa 1: Informações básicas

Para concluir a [!UICONTROL Basic Information] seção:

1. Nomeie o destino.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Clique **[!UICONTROL Next]** e vá para as seções [!UICONTROL Configuration] e [!UICONTROL Segment Mappings] .

### Etapa 2: Informações de configuração

Para concluir a [!UICONTROL Configuration] seção:

1. **** Nome do cookie: Forneça um nome curto e descritivo para seu cookie.
1. **** Domínio do cookie: Deixe em branco para definir um cookie no domínio da página atual do usuário. Se você quiser especificar um domínio, coloque o nome no prefixo com um ponto como esse `.mydomain.com`.
1. Escolha uma opção principal na [!UICONTROL Data Format] seção.
1. Se as chaves usarem dados com valores serializados, selecione o **[!UICONTROL Serialize]** controle e especifique o delimitador serial (o caractere que separa os valores serializados).
1. Clique **[!UICONTROL Save]** e expanda a [!UICONTROL Segment Mappings] seção.

### Etapa 3: Mapeamentos de segmentos

Para adicionar um segmento a um destino de cookie:

1. **** Localizar segmentos: A [!UICONTROL Segment Mappings] seção fornece duas ferramentas de pesquisa para ajudar a localizar segmentos. Para localizar um segmento:
   * Opção 1: Comece digitando um nome de segmento no campo de pesquisa. O campo é atualizado automaticamente com base no texto. Clique **[!UICONTROL Add]** quando encontrar o segmento que deseja usar.
   * Opção 2: Clique **[!UICONTROL Browse All Segments]** para abrir uma janela que permite procurar segmentos por nome ou local de armazenamento. Click **[!UICONTROL Add Selected Segments]** when done.
1. **** Adicionar mapeamentos: No pop-up de mapeamentos, insira a ID do segmento no campo de mapeamentos e clique em **[!UICONTROL Save]**.
1. Clique em **[!UICONTROL Done]**.

## Configuração do OpenX {#openx-code-setup}

Modifique [!DNL OpenX] as configurações para trabalhar com os dados de segmento do Audience Manager.

<!-- aam-openx-code.xml -->

Para configurar [!DNL OpenX]:

* Instale o [!UICONTROL DIL] código no site.
* Crie [!DNL OpenX] como um destino de cookie no Audience Manager.
* Coloque a `get_aamCookie` função na parte superior da página, idealmente dentro do `<head>` bloco de controle. O `get_aamCookie` código está disponível [aqui](../../features/destinations/get-aam-cookie-code.md).
* Modifique sua tag de publicidade para chamar a `get_aamCookie` função e incluir o nome do cookie fornecido ao configurar o [!DNL OpenX] destino. Por exemplo, se você nomeou o cookie `test_cookie`, a tag do anúncio deve chamar `get_aamCookie` e referenciar o nome do cookie.
* Sua tag de publicidade pode ser semelhante ao exemplo abaixo.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Lembre-se de incluir `xid=` . Ele contém a ID de usuário exclusiva ([!UICONTROL UUID]) passada durante uma chamada de anúncio.

A chamada de anúncio totalmente formada pode ser semelhante a esta:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
