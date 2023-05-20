---
description: Configure o OpenX como destino e envie dados de segmento do Audience Manager para essa plataforma.
seo-description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-title: OpenX as an Audience Manager Destination
solution: Audience Manager
title: OpenX como um destino do Audience Manager
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third-party Integration
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 2%

---

# OpenX como um destino do Audience Manager{#openx-as-an-audience-manager-destination}

Configurar [!DNL OpenX] como destino e enviar dados de segmento de Audience Manager para essa plataforma.

>[!NOTE]
>
>Somente para direcionamento no site e no servidor.

## Requisitos de destino do OpenX {#openx-requirements}

Padrões para inserção de código, formatos de valores-chave compatíveis, relatórios e o tipo de dados de segmento enviados ao [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Analise o seguinte antes de configurar [!DNL OpenX] como destino Audience Manager:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] o código deve ser implantado no site. [!UICONTROL DIL] O ajuda a eliminar a necessidade de gravar código especial para coleta de dados, integração, leitura de valores de cookie e recuperação de dados de página.
* **`get_aamCookie`Função:** Código que captura a ID de usuário do Audience Manager e os dados do cookie. Local [este código](../../features/destinations/get-aam-cookie-code.md) na parte superior da página ou dentro da `<head>` codeblock.
* **Enviar logs de entrega para o Audience Manager:** Se quiser um relatório de delivery de segmento (opcional), forneça ao Audience Manager um log diário que contenha dados de delivery no nível de impressão. Os dados podem estar em um formato bruto, mas cada registro deve conter o Audience Manager `UUID`. O Audience Manager pode recebê-los via [!DNL FTP].

### Dados de valor-chave: requisitos de formato

O Audience Manager envia dados na forma de pares de valores chave. Crie pares de valores chave de acordo com as seguintes especificações:

* Teclas de prefácio com `c.` (por exemplo, `c.color` ou `c.price`).
* Separe os valores serializados anexados a uma única chave com uma vírgula (por exemplo, `c.color = red, green, blue`).
* Separe vários pares de valores-chave com um E comercial (por exemplo, `c.color=red & c.price = 100 & c.condition = new`).
* Os nomes das teclas não devem conter caracteres especiais como acentos, sinais de pontuação ou outros símbolos.

### Somente os segmentos qualificados são enviados para OpenX

A quantidade de dados transmitida para [!DNL OpenX] depende de para quantos segmentos um usuário específico se qualifica. Por exemplo, digamos que você configure segmentos de 100 Audience Manager. Se um visitante do site se qualificar para cinco deles, então somente esses cinco segmentos serão enviados para o [!DNL OpenX] (nem todos os 100).

## Criar um destino OpenX {#openx-destination}

Criar um destino de cookie para [!DNL OpenX] em Audience Manager.

<!-- aam-openx-destination.xml -->

No Audience Manager, um *destino* é qualquer outro sistema (servidor de anúncios, [!DNL DSP], rede de anúncios etc.) com o qual você deseja compartilhar dados. [!UICONTROL Destination Builder] O fornece as ferramentas que permitem criar e gerenciar esses processos de delivery de dados. Os recursos de destino do Audience Manager estão localizados em *Dados de público-alvo > Destinos*. Para começar, clique em **[!UICONTROL Add New Destination]** e siga as etapas abaixo.

### Etapa 1: Informações Básicas

Para concluir o [!UICONTROL Basic Information] seção:

1. Nomeie o destino.
1. Selecionar **[!UICONTROL "Cookie"]** do [!UICONTROL Type] lista suspensa.
1. Clique em **[!UICONTROL Next]** e vá para a página [!UICONTROL Configuration] e [!UICONTROL Segment Mappings] seções.

### Etapa 2: Informações de Configuração

Para concluir o [!UICONTROL Configuration] seção:

1. **Nome do cookie:** Forneça um nome curto e descritivo para o cookie.
1. **Domínio do cookie:** Deixe em branco para definir um cookie no domínio da página atual do usuário. Se quiser especificar um domínio, adicione um ponto como este ao nome, `.mydomain.com`.
1. Escolha uma opção de chave na caixa [!UICONTROL Data Format] seção.
1. Se suas chaves usarem dados com valores serializados, selecione a variável **[!UICONTROL Serialize]** controlar e especificar o delimitador de série (o caractere que separa os valores serializados).
1. Clique em **[!UICONTROL Save]** e expanda a variável [!UICONTROL Segment Mappings] seção.

### Etapa 3: Mapeamentos de Segmento

Para adicionar um segmento a um destino de cookie:

1. **Localizar segmentos:** A variável [!UICONTROL Segment Mappings] A seção fornece duas ferramentas de pesquisa para ajudar a localizar segmentos. Para localizar um segmento:
   * Opção 1: comece digitando um nome de segmento no campo de pesquisa. O campo é atualizado automaticamente com base no texto. Clique em **[!UICONTROL Add]** depois de encontrar o segmento que deseja usar.
   * Opção 2: clique em **[!UICONTROL Browse All Segments]** para abrir uma janela que permite procurar segmentos por nome ou local de armazenamento. Clique em **[!UICONTROL Add Selected Segments]** quando terminar.
1. **Adicionar Mapeamentos:** No pop de mapeamentos, insira a ID do segmento no campo mapeamentos e clique em **[!UICONTROL Save]**.
1. Clique em **[!UICONTROL Done]**.

## Configuração do OpenX {#openx-code-setup}

Modificar [!DNL OpenX] configurações para trabalhar com dados de segmento Audience Manager.

<!-- aam-openx-code.xml -->

Para configurar [!DNL OpenX]:

* Instalar [!UICONTROL DIL] em todo o site.
* Criar [!DNL OpenX] como um destino de cookie no Audience Manager.
* Coloque o `get_aamCookie` na parte superior da página, idealmente dentro do `<head>` codeblock. A variável `get_aamCookie` o código está disponível [aqui](../../features/destinations/get-aam-cookie-code.md).
* Modifique sua tag de publicidade para chamar a `get_aamCookie` e inclua o nome do cookie fornecido ao configurar a função [!DNL OpenX] destino. Por exemplo, se você nomeou o cookie `test_cookie`, a tag do anúncio deverá chamar `get_aamCookie` e referencie o nome do cookie.
* A tag do anúncio pode ser semelhante ao exemplo abaixo.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Lembre-se de incluir `xid=` . Ele contém a ID de usuário exclusiva real ([!UICONTROL UUID]) transmitidos durante uma chamada de publicidade.

A chamada de anúncio totalmente formada pode ser semelhante a:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
