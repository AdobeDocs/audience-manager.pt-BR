---
description: Perguntas e problemas comuns de coleta e integração de dados.
seo-description: Perguntas e problemas comuns de coleta e integração de dados.
seo-title: Perguntas frequentes sobre coleta de dados e integração de produtos
solution: Audience Manager
title: Perguntas frequentes sobre coleta de dados e integração de produtos
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; SFTP address; STFP IP address; FTP address
translation-type: tm+mt
source-git-commit: d221890d2a80cd557a6968d3382ee8842fea9aef

---


# Perguntas frequentes sobre coleta de dados e integração de produtos{#data-collection-and-product-integration-faq}

Perguntas e problemas comuns de coleta e integração de dados.

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**Como posso diferenciar o tráfego de entrada do[!UICONTROL DCS]tráfego nas exportações de arquivos de[!UICONTROL DCS]log?**

As características a bordo [!UICONTROL Inbound] são preenchidas [!UICONTROL Inbound] da mesma forma que são preenchidas por [!UICONTROL DCS]. Há algumas maneiras diferentes de dizer que o tráfego veio de [!UICONTROL Inbound]:

* O IP remoto será definido como 68.67.173.18
* DomainID será definido como 5325
* Região será definida como 0

<br> 

**Você pode me fornecer uma lista de endereços IP que eu posso adicionar à lista de permissões para dpm.demdex.net?**

Infelizmente, não podemos. Esses IPs são atribuídos dinamicamente, por região geográfica, por [!DNL Amazon Web Services]. Como resultado, [!DNL Audience Manager] não controla o intervalo de IPs que podem ser atribuídos a este endereço.

<br> 

**Você pode me fornecer um endereço IP para o qual posso adicionar uma lista de permissões ao seu servidor sFTP de entrada e de saída?**

Sim, veja abaixo.

| Item | Endereço |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**Quais são os requisitos de posicionamento de código e carregamento de página para uma Integração[!UICONTROL DIL]/[!DNL Analytics]de dados?**

Para trazer [!DNL Analytics] dados para [!DNL Audience Manager], carregue [!UICONTROL DIL] após o `s_code` módulo, mas *antes* da `s.t()` função. Por exemplo, posicione seu código ou verifique se ele é carregado, nesta ordem:

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL] módulo

3. [!DNL Analytics] `s.t()` função

Como prática recomendada, configure sua [!DNL Audience Manager]- [!DNL Analytics] integração com um destes dois métodos:

* Coloque [!UICONTROL DIL] diretamente no `s_code`.

* Serve [!UICONTROL DIL] e o `s_code` através [!DNL Adobe Experience Platform Launch] ou [!DNL Adobe DTM].

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**Por que minhas[!DNL Analytics]variáveis estão faltando em uma chamada de[!DNL Audience Manager]evento?**

Isso normalmente acontece quando:

* Você serve [!UICONTROL DIL] por meio de um sistema de gerenciamento de tags que o carrega de forma assíncrona com outros elementos de código na página.
* A `s.t()` função é carregada antes [!UICONTROL DIL].

<br> 

**Com que versões de[!DNL Analytics]trabalho[!UICONTROL DIL]?**

Você deve usar a [!DNL Analytics] versão 20.2 (ou superior) e a [!DNL Adobe AppMeasurement AS] versão 3.5.2 da biblioteca (ou superior) para trabalhar com [!UICONTROL DIL]. Se você não souber sua versão [!DNL Analytics] ou [!DNL AppMeasurement] versão, verifique a [!DNL Analytics] chamada que é feita na página. Informações de versão mostradas abaixo:

Este cliente usa a [!DNL Analytics] versão 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

Este cliente usa a [!DNL AppMeasurement] versão 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**Posso coletar dados de página se não for um[!DNL Analytics]cliente?**

Sim. O [!UICONTROL DIL] módulo ajuda a coletar dados de página mesmo se você não estiver usando [!DNL Analytics]. Quando configurado corretamente, [!UICONTROL DIL] é possível capturar dados de e sobre:

* Mettags
* URLs e cabeçalhos de URLs
* Tipos de mecanismo de pesquisa
* Palavras-chave

Além disso, os clientes podem implantar um objeto simples no site e preenchê-lo com pares de valores chave nos quais você deseja coletar dados [!UICONTROL DIL] . Isso permite que você adicione e remova pontos de dados de público-alvo específicos do site sem nenhuma [!DNL Audience Management] atualização. Entre em contato com seu representante de soluções de parceiros para configurar corretamente e garantir que o [!DNL DIL] módulo faça referência ao objeto da página corretamente.

<br> 

**É possível[!UICONTROL DIL]coletar dados de[!DNL Google Analytics]?**

Sim. [!UICONTROL DIL] pode coletar alguns elementos [!DNL Google Analytics] (GA) e enviar esses dados para [!DNL Audience Manager]. Consulte:

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**Posso obter dados brutos de[!DNL Audience Manager]e quão granular é?**

Sim, [!DNL Audience Manager] pode fornecer dados coletados para usuários que já vimos em seu inventário. Isso inclui:

* A ID de usuário exclusiva (UUID) atribuída por [!DNL Audience Manager]
* IDs de características e segmentos
* Sinais não utilizados
* Carimbos de data e hora
* URLs da página

<br> 

**Quero coletar dados em um site e direcionar usuários por DFP em um site diferente. Preciso implantar o código na outra propriedade se não quiser coletar dados desse local?**

Não. Se a coleta de dados no segundo site não for um requisito, não será necessário implantar o DIL lá. Desde que você tenha acesso ao inventário no segundo site por meio do DFP, é possível usar a coleta de dados do site inicial e da meta por meio do DFP.

<br> 

**Qual é o melhor provedor de dados de terceiros?**

Cada provedor traz algo único para a tabela, então a resposta depende do que você está procurando. Podemos ativar o relatório de sobreposição (sem custo) para ajudá-lo a entender qual provedor pode funcionar melhor para você.

<br> 

**Como[!DNL Audience Manager]definir cookies e transmitir variáveis para o DFP?**

[!DNL Audience Manager] define 2 cookies: Um envia variáveis de segmento para a tag de anúncio DFP e o outro define a ID de usuário exclusiva (UUID), que também é lida pelo DFP. Adicionar a UUID à tag de anúncio significa que podemos fazer relatórios no nível do usuário e descoberta de público-alvo.

<br> 

**É possível enviar informações do DSP sobre pontos no funil de conversão alcançados por um usuário?**

Sim. Podemos enviar dados de funil, mas o DSP deve ter a capacidade técnica para usá-los. Um DSP deve confirmar que pode lidar com vários segmentos. Caso contrário, talvez seja necessário criar segmentos específicos para retirar um usuário de outros segmentos com base em seu progresso de conversão (por exemplo, etapa 1 e 2 concluídas, mas não etapa 3). Você pode enviar essas informações para um DSP para que eles possam redirecionar os usuários, direcioná-los para uma página de aterrissagem específica ou exibir criações específicas.

<br> 

**Como posso confirmar se os dados enviados via FTP foram coletados por[!DNL Audience Manager]?**

Um arquivo foi selecionado quando a extensão muda de `.sync` para `.processed`. Quando isso acontece, o arquivo está na fila de ingestão. Além disso, seu gerente de conta pode confirmar quando um arquivo foi carregado.

<br> 

**Quero testar a funcionalidade da API[do](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)DCS. Estou enviando chamadas de evento como a mostrada abaixo. As chamadas contêm[IDs](../features/declared-ids.md)declaradas e sinais, que devem perceber algumas características e segmentos que já configurei. Posso usar o[!UICONTROL General Reports]e[!UICONTROL Trend Reports]para verificar se as populações de características e segmentos estão aumentando?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

Não, não confie no [!UICONTROL General Reports] e [!UICONTROL Trend Reports] neste caso.

Os relatórios calculam populações com base nos registros de perfil não autenticados (UUIDs) que vemos no backend no momento em que os relatórios são gerados.

Em uma primeira chamada para o [!UICONTROL DCS], as IDs declaradas *não* estão vinculadas a qualquer UUID (ou seja, nenhum cookie [](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) demdex está presente no lado do cliente). O [!UICONTROL DCS] gerará aleatoriamente um UUID e definirá um [!DNL demdex] cookie e o transmitirá na chamada de resposta, mas ele não transmitirá o UUID para o backend.

>[!NOTE]
>
>A UUID gerada só será materializada em nosso armazenamento de dados de backend quando o dispositivo no qual o cookie está definido acionar mais atividade.

Por esse motivo, os relatórios não refletirão os eventos acionados pelas IDs declaradas em sua chamada. Recomendamos que você use UUID, ECID (anteriormente MID) ou IDs de dispositivo móvel em chamadas de teste de evento para o [!UICONTROL DCS]. Em seguida, você pode verificar a característica e as realizações do segmento no [!UICONTROL General Reports] e no [!UICONTROL Trend Reports].

Consulte também o [Índice de IDs](../reference/ids-in-aam.md)do Audience Manager.

<br> 

**Quanto tempo leva para que os perfis de usuário sejam sincronizados entre[regiões](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

Geralmente, demora até 24 horas para que um perfil de usuário seja sincronizado entre regiões. Mas, em casos raros, o processo pode levar até 48 horas.
