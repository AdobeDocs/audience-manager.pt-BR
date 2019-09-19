---
description: Configure o Open Ad Server como destino e envie dados do Audience Manager para essa plataforma.
seo-description: Configure o Open Ad Server como destino e envie dados do Audience Manager para essa plataforma.
seo-title: OAS como destino do Audience Manager
solution: Audience Manager
title: OAS como destino do Audience Manager
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
translation-type: tm+mt
source-git-commit: 78a0a0e461ea3a74d0dbb0370a841db274a6f9be

---


# OAS como destino do Audience Manager {#oas-as-an-audience-manager-destination}

Configure [!DNL Open Ad Server] como destino e envie dados do Audience Manager para essa plataforma.

## Requisitos de destino do OAS {#oas-requirements}

Padrões para o posicionamento de código, formatos de valor-chave suportados, relatórios e o tipo de dados de segmento enviados para [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Esse tipo de destino requer o seguinte:

* **[!UICONTROL DIL]** : O [!UICONTROL Data Integration Library] código deve ser implantado no seu inventário. [!UICONTROL DIL] ajuda a eliminar a necessidade de gravar código especial para coleta de dados, integração, leitura de valores de cookies e recuperação de dados da página.
* **`get_aamCookie`** Função: Código que captura a ID de usuário e os dados de cookie do Audience Manager. Coloque [esse código](../../features/destinations/get-aam-cookie-code.md) na parte superior da página ou dentro do `<head>` bloco de código.
* **** Enviar registros de entrega ao Audience Manager: Se desejar um relatório de entrega de segmento (opcional), forneça ao Audience Manager um registro diário que contenha dados de entrega em nível de impressão. Os dados podem estar em um formato bruto, mas cada registro deve conter o Audience Manager [!UICONTROL UUID]. O Audience Manager pode coletar ou receber isso via [!DNL FTP].

### Formato de cookie e dados de valor-chave

O Audience Manager pode enviar dados de segmento para um cookie do navegador da seguinte maneira:

* Teclas simples (`x=1&x=2`);
* Teclas múltiplas (`x=1&x=2&y=3&y=4`);
* Valores serializados (`x=1,2,3`);
* Um delimitador de valor padrão usado para separar pares de valores chave individuais.

### Somente segmentos qualificados são enviados para OAS

A quantidade de dados transmitida depende [!DNL OAS] de quantos segmentos um usuário específico se qualifica. Por exemplo, considere configurar 100 segmentos do Audience Manager. Se um visitante do site se qualificar para cinco deles, somente esses cinco segmentos serão enviados para o OAS (não todos os 100).

>[!MORE_LIKE_THIS]
>
>* [get_aamCookie Code](../../features/destinations/get-aam-cookie-code.md)
>* [Explicação dos pares de valor-chave](../../reference/key-value-pairs-explained.md)


## Criar um destino OAS {#oas-dest-setup}

Crie um destino baseado em cookies para [!DNL OAS] o no Audience Manager.

<!-- aam-oas-destination-setup.xml -->

No Audience Manager, um *destino* é qualquer outro sistema (servidor de anúncios, rede de anúncios [!DNL DSP], etc.) com os quais você deseja compartilhar dados. [!UICONTROL Destination Builder] fornece as ferramentas que permitem criar e gerenciar esses processos de entrega de dados. Os recursos de destino do Audience Manager estão localizados em Dados de *público-alvo &gt; Destinos*. Para começar, clique **[!UICONTROL Add New Destination]** e siga as etapas abaixo.

### Etapa 1: Informações básicas

Para concluir a [!UICONTROL Basic Information] seção:

1. Nomeie o destino.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Clique **[!UICONTROL Save]** e vá para as seções [!UICONTROL Configuration] e [!UICONTROL Segment Mappings] .

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

## Configuração do OAS {#oas-code-setup}

Modifique [!DNL OAS] as configurações para trabalhar com os dados de segmento do Audience Manager.

<!-- aam-oas-code.xml -->

Para configurar [!DNL OAS]

* Instale o [!UICONTROL DIL] código no site.
* Crie o OAS como um destino de cookie no Audience Manager.
* Coloque a `get_aamCookie` função na parte superior da página, idealmente dentro do `<head>` bloco de controle. O `get_aamCookie` código está disponível [aqui](../../features/destinations/get-aam-cookie-code.md).
* Modifique sua tag de publicidade para chamar a `get_aamCookie` função e incluir o nome do cookie fornecido ao configurar o [!DNL OAS] destino. Por exemplo, se você nomeou o cookie `test_cookie`, a tag do anúncio deve chamar `get_aamCookie` e referenciar o nome do cookie.
* Sua tag de publicidade pode ser semelhante ao exemplo abaixo.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Lembre-se de incluir a `u=` variável. Ele contém a ID de usuário exclusiva ([!UICONTROL UUID]) passada durante uma chamada de anúncio.
