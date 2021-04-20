---
description: Configure o Open Ad Server como destino e envie dados de Audience Manager para essa plataforma.
seo-description: Configure o Open Ad Server como destino e envie dados de Audience Manager para essa plataforma.
seo-title: OAS como um destino do Audience Manager
solution: Audience Manager
title: OAS como um destino do Audience Manager
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third-party Integration
exl-id: cf919c27-691f-424b-be83-040f03e34455
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 4%

---

# OAS como um destino do Audience Manager {#oas-as-an-audience-manager-destination}

Configure [!DNL Open Ad Server] como destino e envie dados de Audience Manager para essa plataforma.

## Requisitos de destino do OAS {#oas-requirements}

Padrões para posicionamento de código, formatos de valor-chave suportados, relatórios e o tipo de dados de segmento enviados para [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Esse tipo de destino requer o seguinte:

* **[!UICONTROL DIL]: o código do** [!UICONTROL Data Integration Library]  deve ser implantado em seu inventário. [!UICONTROL DIL] ajuda a eliminar a necessidade de gravar um código especial para coleta de dados, integração, leitura de valores de cookies e recuperação de dados da página.
* **`get_aamCookie`Função:** código que captura a ID de usuário do Audience Manager e os dados de cookie. Coloque [este código](../../features/destinations/get-aam-cookie-code.md) na parte superior da página ou dentro do codeblock `<head>`.
* **Enviar logs de delivery para o Audience Manager:** se quiser um relatório de delivery de segmento (opcional), forneça ao Audience Manager um log diário que contenha dados de delivery de nível de impressão. Os dados podem estar em um formato bruto, mas cada registro deve conter o Audience Manager [!UICONTROL UUID]. O Audience Manager pode coletá-los ou recebê-los via [!DNL FTP].

### Formato do cookie e dados de valor-chave

O Audience Manager pode enviar dados de segmento para um cookie de navegador da seguinte maneira:

* Chaves únicas (`x=1&x=2`);
* Múltiplas chaves (`x=1&x=2&y=3&y=4`);
* Valores serializados (`x=1,2,3`);
* Um delimitador de valor padrão usado para separar pares de valores-chave individuais.

### Somente os segmentos qualificados são enviados para OAS

A quantidade de dados passada para [!DNL OAS] depende de quantos segmentos um usuário específico se qualifica. Por exemplo, digamos que você tenha configurado 100 segmentos de Audience Manager. Se um visitante do site se qualificar para cinco deles, então apenas esses cinco segmentos serão enviados para o OAS (não todos os 100).

>[!MORELIKETHIS]
>
>* [Código get_aamCookie](../../features/destinations/get-aam-cookie-code.md)
>* [Explicação dos pares de valor-chave](../../reference/key-value-pairs-explained.md)


## Criar um Destino OAS {#oas-dest-setup}

Crie um destino baseado em cookies para [!DNL OAS] no Audience Manager.

<!-- aam-oas-destination-setup.xml -->

No Audience Manager, um *destino* é qualquer outro sistema (servidor de anúncios, [!DNL DSP], rede de anúncios etc.) com o qual você deseja compartilhar dados. [!UICONTROL Destination Builder] O fornece as ferramentas que permitem criar e gerenciar esses processos de entrega de dados. Os recursos de destino do Audience Manager estão localizados em *Dados do público-alvo > Destinos*. Para começar, clique em **[!UICONTROL Add New Destination]** e siga as etapas abaixo.

### Etapa 1: Informações básicas

Para concluir a seção [!UICONTROL Basic Information]:

1. Nomeie o destino.
1. Selecione **[!UICONTROL "Cookie"]** na lista suspensa [!UICONTROL Type].
1. Clique em **[!UICONTROL Save]** e vá para as seções [!UICONTROL Configuration] e [!UICONTROL Segment Mappings].

### Etapa 2: Informações de configuração

Para concluir a seção [!UICONTROL Configuration]:

1. **Nome do cookie:** forneça um nome curto e descritivo para o cookie.
1. **Domínio de cookie:** deixe em branco para definir um cookie no domínio da página atual do usuário. Se quiser especificar um domínio, coloque o nome com um ponto como este, `.mydomain.com` no prefixo.
1. Escolha uma opção de chave na seção [!UICONTROL Data Format] .
1. Se as chaves usam dados com valores serializados, selecione o controle **[!UICONTROL Serialize]** e especifique o delimitador de série (o caractere que separa os valores serializados).
1. Clique em **[!UICONTROL Save]** e expanda a seção [!UICONTROL Segment Mappings].

### Etapa 3: Mapeamentos de segmento

Para adicionar um segmento a um destino de cookie:

1. **Localizar segmentos:** A  [!UICONTROL Segment Mappings] seção fornece duas ferramentas de pesquisa para ajudar a localizar segmentos. Para localizar um segmento:
   * Opção 1: Comece digitando um nome de segmento no campo de pesquisa. O campo é atualizado automaticamente com base no texto. Clique em **[!UICONTROL Add]** depois de encontrar o segmento que deseja usar.
   * Opção 2: Clique em **[!UICONTROL Browse All Segments]** para abrir uma janela que permite procurar segmentos por nome ou local de armazenamento. Clique em **[!UICONTROL Add Selected Segments]** quando terminar.
1. **Adicionar mapeamentos:** no pop-up mapeamentos, insira a ID do segmento no campo mapeamentos e clique em  **[!UICONTROL Save]**.
1. Clique em **[!UICONTROL Done]**.

## Configuração do OAS {#oas-code-setup}

Modifique as configurações [!DNL OAS] para funcionar com os dados do segmento Audience Manager.

<!-- aam-oas-code.xml -->

Para configurar [!DNL OAS]

* Instale o código [!UICONTROL DIL] em todo o site.
* Crie o OAS como destino de cookie no Audience Manager.
* Coloque a função `get_aamCookie` na parte superior da página, idealmente dentro do codeblock `<head>`. O código `get_aamCookie` está disponível [aqui](../../features/destinations/get-aam-cookie-code.md).
* Modifique a tag do anúncio para chamar a função `get_aamCookie` e inclua o nome do cookie fornecido ao configurar o destino [!DNL OAS]. Por exemplo, se você nomeou o cookie como `test_cookie`, a tag do anúncio deve chamar `get_aamCookie` e fazer referência ao nome do cookie.
* Sua tag de publicidade pode ser semelhante ao exemplo abaixo.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Lembre-se de incluir a variável `u=` . Ele contém a ID de usuário exclusiva real ([!UICONTROL UUID]) transmitida durante uma chamada de anúncio.
