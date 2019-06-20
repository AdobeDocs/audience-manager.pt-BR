---
description: Perguntas frequentes sobre coleta de dados e integração.
seo-description: Perguntas frequentes sobre coleta de dados e integração.
seo-title: Perguntas frequentes sobre coleção de dados e integração do produto
solution: Audience Manager
title: Perguntas frequentes sobre coleção de dados e integração do produto
uuid: fa 8 e 79 f 4-99 cb -41 fd -8 a 85-d 4 f 92 d 03 c 7 a 5
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# Data Collection and Product Integration FAQ{#data-collection-and-product-integration-faq}

Perguntas frequentes sobre coleta de dados e integração.

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**Como diferenciar tráfego de entrada do[!UICONTROL DCS]tráfego nas[!UICONTROL DCS]exportações de arquivos de log?**

Traits onboarded via [!UICONTROL Inbound] are populated by [!UICONTROL Inbound] the same way they get populated by [!UICONTROL DCS]. There are a few different ways to tell that traffic came from [!UICONTROL Inbound]:

* IP remoto será definido como 68.67.173.18
* Domainid será definido como 5325
* A região será definida como 0

<br> 

**É possível fornecer uma lista de endereços IP que posso adicionar para dpm. demdex. net?**

Infelizmente, não podemos. These IPs are assigned dynamically, by geographic region, through [!DNL Amazon Web Services]. As a result, [!DNL Audience Manager] does not control the range of IPs that can be assigned to this address.

<br> 

**É possível fornecer um endereço IP com um endereço de permissão para o servidor FTP de entrada e saída?**

Sim, veja abaixo.

| Item | Endereço |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**Quais são os requisitos de inserção de código e carregamento de página para a[!UICONTROL DIL]integração de dados/[!DNL Analytics]dados?**

To bring [!DNL Analytics] data into [!DNL Audience Manager], load [!UICONTROL DIL] after the `s_code` module but *before* the `s.t()` function. Por exemplo, coloque seu código ou verifique se ele carrega, nesta ordem:

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager][!UICONTROL DIL] módulo

3. [!DNL Analytics]`s.t()` função

As a best practice, set up your [!DNL Audience Manager]- [!DNL Analytics] integration with either of these 2 methods:

* Put [!UICONTROL DIL] directly in the `s_code`.

* Serve [!UICONTROL DIL] and the `s_code` through [!DNL Adobe Launch] or [!DNL Adobe DTM].

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**Por que minhas[!DNL Analytics]variáveis estão ausentes em uma chamada[!DNL Audience Manager]de evento?**

Isso normalmente ocorre quando:

* You serve [!UICONTROL DIL] through a tag management system that loads it asynchronously with other code elements on the page.
* The `s.t()` function loads before [!UICONTROL DIL].

<br> 

**Com quais versões[!DNL Analytics]do trabalho[!UICONTROL DIL]?**

You must use [!DNL Analytics] version 20.2 (or higher) and the [!DNL Adobe AppMeasurement AS] library version 3.5.2 (or higher) to work with [!UICONTROL DIL]. If you don&#39;t know your [!DNL Analytics] or [!DNL AppMeasurement] version, check the [!DNL Analytics] call that gets made from the page. Informações da versão mostradas abaixo:

This customer uses [!DNL Analytics] version 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

This customer uses [!DNL AppMeasurement] version 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**É possível coletar dados de página se eu não sou[!DNL Analytics]cliente?**

Sim. [!UICONTROL DIL] O módulo ajuda a coletar dados da página mesmo que você não esteja usando [!DNL Analytics]. When set up properly, [!UICONTROL DIL] can capture data from and about:

* Tags meta
* Urls e cabeçalhos de URL
* Tipos de mecanismo de pesquisa
* Palavras-chave

Additionally, clients can deploy a simple onsite object and populate it with key-value pairs that you want [!UICONTROL DIL] to collect data on. This lets you add and remove specific audience data points on your site without any [!DNL Audience Management] updates. Work with your Partner Solutions representative to properly set this up and ensure the [!DNL DIL] module references the page object correctly.

<br> 

**É possível[!UICONTROL DIL]coletar dados?[!DNL Google Analytics]**

Sim. [!UICONTROL DIL] pode coletar alguns [!DNL Google Analytics] elementos (GA) e enviar esses dados [!DNL Audience Manager]para. Consulte:

* [GA. submituniversalanalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA. init](../dil/dil-modules.md#ga-init)

<br> 

**É possível obter dados brutos e[!DNL Audience Manager]como é granular?**

Yes, [!DNL Audience Manager] can provide you with data collected for users we&#39;ve seen on your inventory. Isso inclui:

* The unique user ID (UUID) assigned by [!DNL Audience Manager]
* IDs de características e segmentos
* Sinais não usados
* Carimbos de data e hora
* Urls de página

<br> 

**Quero coletar dados em um site e direcionar usuários por DFP em um site diferente. Do I need to deploy code on the other property if I don&#39;t want to collect data from that location?**

Não. Se a coleta de dados no segundo site não for um requisito, você não precisa implantar o DIL lá. Desde que você tenha acesso ao inventário no segundo site via DFP, poderá usar a coleção de dados do site inicial e de destino por DFP.

<br> 

**Qual é o melhor provedor de dados de terceiros?**

Cada provedor traz algo exclusivo para a tabela, portanto a resposta depende do que está procurando. Podemos ativar o relatório de sobreposição (sem custo) para ajudar você a entender qual provedor pode trabalhar melhor para você.

<br> 

**Como[!DNL Audience Manager]definir cookies e enviar variáveis para DFP?**

[!DNL Audience Manager] define 2 cookies: Um envia variáveis de segmento para a tag de anúncio DFP e a outra define nossa exclusiva ID de usuário (UUID), que também é lida pelo DFP. Adicionar o UUID à marca de anúncio significa que podemos fazer relatórios de nível de usuário e descoberta de público-alvo.

<br> 

**É possível enviar informações DSP sobre pontos no funil de conversão alcançado por um usuário?**

Sim. É possível enviar dados de funil, mas a DSP precisa ter o recurso técnico para usá-lo. Uma DSP deve confirmar que eles podem lidar com vários segmentos. Se não for possível, talvez seja necessário criar segmentos específicos para extrair um usuário de outros segmentos com base em seu progresso de conversão (por exemplo, a etapa 1 e 2, mas não a etapa 3). Você pode enviar essas informações para um DSP para que elas possam redirecionar usuários, direcioná-las para uma página de aterrissagem específica ou exibir anúncios específicos.

<br> 

**Como faço para confirmar se os dados enviados via FTP foram selecionados[!DNL Audience Manager]?**

A file has been picked up when the extension changes from `.sync` to `.processed`. Quando isso ocorre, o arquivo está na fila de ingestão. Além disso, o gerente da conta pode confirmar quando um arquivo foi carregado.

<br> 

**Quero testar a funcionalidade da API[DCS](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md). Estou enviando chamadas de evento como a mostrada abaixo. The calls contain[Declared IDs](../features/declared-ids.md)and signals, which should realize some traits and segments I have already set up. Can I use the[!UICONTROL General Reports]and[!UICONTROL Trend Reports]to verify if the trait and segment populations are increasing?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

No, do not rely on the [!UICONTROL General Reports] and [!UICONTROL Trend Reports] in this case.

Os relatórios computam populações com base nos registros de perfil não autenticados (uuids), visto no backend no momento em que os relatórios são gerados.

On a first call to the [!UICONTROL DCS], the declared IDs are *not* linked to any UUID (i.e. no [demdex cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) is present on the client side). The [!UICONTROL DCS] will randomly generate a UUID and set a [!DNL demdex] cookie and pass it on in the response call, but it will not transmit the UUID to the backend.

>[!NOTE]
>
>O UUID gerado só será materializado em nosso armazenamento de dados de backend depois que o dispositivo em que o cookie estiver definido acionar mais atividades.

Por isso, os relatórios não refletirão os eventos acionados pelas IDs declaradas na sua chamada. We recommend you use UUID, ECID (formerly MID) or mobile device IDs in event test calls to the [!UICONTROL DCS]. Then, you can verify the trait and segment realizations in the [!UICONTROL General Reports] and in the [!UICONTROL Trend Reports].

See also, the [Index of Audience Manager IDs](../reference/ids-in-aam.md).

<br> 

**Quanto tempo leva para que os perfis do usuário sejam sincronizados entre[regiões](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

Normalmente, leva até 24 horas para que um perfil de usuário seja sincronizado nas regiões. No entanto, em casos raros, o processo pode levar até 48 horas.
