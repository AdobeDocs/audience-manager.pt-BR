---
description: Configure o Open Ad Server como destino e envie dados de Audience Manager para essa plataforma.
seo-description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-title: OAS as an Audience Manager Destination
solution: Audience Manager
title: OAS como um destino de Audience Manager
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third-party Integration
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 2%

---

# OAS como um destino de Audience Manager {#oas-as-an-audience-manager-destination}

Configure [!DNL Open Ad Server] como destino e envie dados de Audience Manager para essa plataforma.

## Requisitos de Destino OAS {#oas-requirements}

Padrões para posicionamento de código, formatos de valores-chave com suporte, relatórios e o tipo de dados de segmento enviados para [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Este tipo de destino requer o seguinte:

* **[!UICONTROL DIL]:** O código [!UICONTROL Data Integration Library] deve ser implantado em seu inventário. O [!UICONTROL DIL] ajuda a eliminar a necessidade de gravar código especial para coleta de dados, integração, leitura de valores de cookie e recuperação de dados de página.
* **`get_aamCookie`Função:** Código que captura a ID de usuário Audience Manager e os dados do cookie. Coloque [este código](../../features/destinations/get-aam-cookie-code.md) na parte superior da página ou dentro do bloco de código `<head>`.
* **Enviar logs de entrega para Audience Manager:** Se desejar um relatório de entrega de segmento (opcional), forneça ao Audience Manager um log diário que contenha dados de entrega no nível de impressão. Os dados podem estar em um formato bruto, mas cada registro deve conter o Audience Manager [!UICONTROL UUID]. O Audience Manager pode recebê-los via [!DNL FTP].

### Formato do cookie e dados de valor-chave

O Audience Manager pode enviar dados de segmento para um cookie do navegador da seguinte maneira:

* Chaves simples (`x=1&x=2`);
* Várias chaves (`x=1&x=2&y=3&y=4`);
* Valores serializados (`x=1,2,3`);
* Um delimitador de valor padrão usado para separar pares de valores chave individuais.

### Somente os segmentos qualificados são enviados para o OAS

A quantidade de dados transmitida para [!DNL OAS] depende de quantos segmentos um usuário específico se qualifica. Por exemplo, digamos que você configure segmentos de 100 Audience Manager. Se um visitante do site se qualificar para cinco deles, então somente esses cinco segmentos serão enviados para o OAS (não todos os 100).

>[!MORELIKETHIS]
>
>* [Código get_aamCookie](../../features/destinations/get-aam-cookie-code.md)
>* [Explicação dos pares de valor-chave](../../reference/key-value-pairs-explained.md)

## Criar um Destino OAS {#oas-dest-setup}

Crie um destino baseado em cookie para [!DNL OAS] no Audience Manager.

<!-- aam-oas-destination-setup.xml -->

No Audience Manager, um *destino* é qualquer outro sistema (servidor de anúncios, [!DNL DSP], rede de anúncios etc.) com o qual você deseja compartilhar dados. O [!UICONTROL Destination Builder] fornece as ferramentas que permitem criar e gerenciar esses processos de entrega de dados. Os recursos de destino do Audience Manager estão localizados em *Dados de público-alvo > Destinos*. Para começar, clique em **[!UICONTROL Add New Destination]** e siga as etapas abaixo.

### Etapa 1: Informações Básicas

Para concluir a seção [!UICONTROL Basic Information]:

1. Nomeie o destino.
1. Selecione **[!UICONTROL "Cookie"]** na lista suspensa [!UICONTROL Type].
1. Clique em **[!UICONTROL Save]** e vá para as seções [!UICONTROL Configuration] e [!UICONTROL Segment Mappings].

### Etapa 2: Informações de Configuração

Para concluir a seção [!UICONTROL Configuration]:

1. **Nome do cookie:** forneça um nome curto e descritivo para o cookie.
1. **Domínio do cookie:** Deixe em branco para definir um cookie no domínio da página atual do usuário. Se você quiser especificar um domínio, adicione um ponto como este ao nome, `.mydomain.com`.
1. Escolha uma opção de chave na seção [!UICONTROL Data Format].
1. Se suas chaves usarem dados com valores serializados, selecione o controle **[!UICONTROL Serialize]** e especifique o delimitador serial (o caractere que separa os valores serializados).
1. Clique em **[!UICONTROL Save]** e expanda a seção [!UICONTROL Segment Mappings].

### Etapa 3: Mapeamentos de Segmento

Para adicionar um segmento a um destino de cookie:

1. **Localizar segmentos:** A seção [!UICONTROL Segment Mappings] fornece duas ferramentas de pesquisa para ajudar a localizar segmentos. Para localizar um segmento:
   * Opção 1: comece digitando um nome de segmento no campo de pesquisa. O campo é atualizado automaticamente com base no texto. Clique em **[!UICONTROL Add]** depois de encontrar o segmento que deseja usar.
   * Opção 2: clique em **[!UICONTROL Browse All Segments]** para abrir uma janela que permite procurar segmentos por nome ou local de armazenamento. Clique em **[!UICONTROL Add Selected Segments]** quando terminar.
1. **Adicionar mapeamentos:** no pop de mapeamentos, insira a ID do segmento no campo mapeamentos e clique em **[!UICONTROL Save]**.
1. Clique em **[!UICONTROL Done]**.

## Configuração do OAS {#oas-code-setup}

Modifique as configurações [!DNL OAS] para trabalhar com dados de segmento de Audience Manager.

<!-- aam-oas-code.xml -->

Para configurar [!DNL OAS]

* Instale o código [!UICONTROL DIL] em todo o site.
* Crie o OAS como um destino de cookie no Audience Manager.
* Coloque a função `get_aamCookie` na parte superior da página, idealmente dentro do bloco de código `<head>`. O código `get_aamCookie` está disponível [aqui](../../features/destinations/get-aam-cookie-code.md).
* Modifique a tag de publicidade para chamar a função `get_aamCookie` e incluir o nome do cookie fornecido ao configurar o destino [!DNL OAS]. Por exemplo, se você nomeou o cookie `test_cookie`, a marca de anúncio deve chamar `get_aamCookie` e fazer referência ao nome do cookie.
* A tag do anúncio pode ser semelhante ao exemplo abaixo.

  ```js
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&u=" + get_aamCookie('aam_uuid')
  ```

Lembre-se de incluir a variável `u=`. Ele contém a ID de usuário exclusiva real ([!UICONTROL UUID]) transmitida durante uma chamada de anúncio.
