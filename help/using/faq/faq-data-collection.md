---
description: Perguntas e problemas comuns de coleta e integração de dados.
seo-description: Common data collection and integration questions and issues.
seo-title: Data Collection and Product Integration FAQ
solution: Audience Manager
title: Perguntas frequentes sobre coleta de dados e integração de produtos
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP, endereço SFTP, endereço IP STFP, endereço FTP
feature: Administration
exl-id: 2951ab0c-6f1c-4126-b83e-ce4a33c0d4ab
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '1211'
ht-degree: 78%

---

# Perguntas frequentes sobre coleta de dados e integração de produtos{#data-collection-and-product-integration-faq}

Perguntas e problemas comuns de coleta e integração de dados.

<br> 

**Como posso diferenciar o tráfego de entrada do tráfego do [!DNL DCS] nas exportações de arquivo de log do [!DNL DCS]?**

As características integradas via [!UICONTROL Inbound] são preenchidas pelo [!UICONTROL Inbound] da mesma forma que são preenchidas pelo [!DNL DCS]. Há algumas maneiras diferentes de dizer que o tráfego veio do [!UICONTROL Inbound]:

* O IP remoto será definido como 68.67.173.18
* DomainID será definido como 5325
* Região será definida como 0

<br> 

**Você pode me fornecer uma lista de endereços IP que eu posso adicionar a uma lista de permissões para dpm.demdex.net?**

Infelizmente, não podemos. Esses IPs são atribuídos dinamicamente, por região geográfica, pelo [!DNL Amazon Web Services]. Por isso, o [!DNL Audience Manager] não controla o intervalo de IPs que podem ser atribuídos a este endereço.

 

**Você pode me fornecer um endereço IP que eu possa adicionar a uma lista de permissões para seu servidor SFTP de entrada e saída?**

Sim, veja abaixo.

| Servidor | Endereço IP |
| ---------|----------|
| ftp-in-gtw.demdex.com | 52.3.74.119; 3.233.68.222 |
| ftp-out-gtw.demdex.com | 23.22.232.252; 18.211.109.184 |

 

Os servidores SFTP abaixo estão obsoletos. Nenhuma conta nova será provisionada usando esses servidores.

| Servidor | Endereço IP |
|---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

 

**Como configurar minha instância do Audience Manager para usar os novos servidores SFTP?**

Entre em contato com o consultor do [!DNL Audience Manager] ou com o Atendimento ao cliente, que configurará suas novas contas SFTP.

 

**Quais são os métodos de autenticação com suporte para os novos servidores SFTP?**

Os novos servidores SFTP (`ftp-in-gtw` e `ftp-out-gtw`) oferecem suporte a [!DNL OpenSSH Key-Based Authentication]. Podemos gerar as chaves [!DNL SSH] para você ou você pode nos fornecer sua própria chave pública.

 

**Quais são os requisitos de posicionamento de código e carregamento de página para uma Integração de dados do [!UICONTROL DIL]/[!DNL Analytics]?**

Para trazer dados do [!DNL Analytics] para o [!DNL Audience Manager], carregue o [!UICONTROL DIL] após o módulo `s_code`, mas *antes* da função `s.t()`. Por exemplo, posicione o código ou verifique se ele é carregado, nesta ordem:

1. [!DNL Analytics] `s_code`

2. Módulo [!DNL Audience Manager] [!UICONTROL DIL]

3. Função [!DNL Analytics] `s.t()`

Como prática recomendada, configure a integração [!DNL Audience Manager] - [!DNL Analytics] com um destes dois métodos:

* Coloque a [!UICONTROL DIL] diretamente no `s_code`.

* Atenda a [!UICONTROL DIL] e a `s_code` até [!DNL Adobe Experience Platform Tags].

Consulte [API da Biblioteca de integração de dados (DIL)](../dil/dil-overview.md).

 

**Por que minhas variáveis do [!DNL Analytics] estão ausentes em uma chamada de evento do [!DNL Audience Manager]?**

Isso normalmente acontece quando:

* Você atende à [!UICONTROL DIL] por meio de um sistema de gerenciamento de tags que a carrega de forma assíncrona com outros elementos de código na página.
* A função `s.t()` é carregada antes da [!UICONTROL DIL].

 

**Quais versões do [!DNL Analytics] funcionam com a [!UICONTROL DIL]?**

Você deve usar o [!DNL Analytics] versão 20.2 (ou superior) e a biblioteca [!DNL Adobe AppMeasurement AS] versão 3.5.2 (ou superior) para trabalhar com a [!UICONTROL DIL]. Se você não souber a versão do [!DNL Analytics] ou da [!DNL AppMeasurement], verifique a chamada do [!DNL Analytics] que é feita na página. Informações de versão mostradas abaixo:

Este cliente usa o [!DNL Analytics] versão 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

Este cliente usa o [!DNL AppMeasurement] versão 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**Posso coletar dados de página se eu não for um cliente do [!DNL Analytics]?**

Sim. O módulo [!UICONTROL DIL] ajuda a coletar dados de página mesmo se você não estiver usando o [!DNL Analytics]. Quando configurada corretamente, a [!UICONTROL DIL] é captura dados de e sobre:

* Meta tags
* URLs e cabeçalhos de URLs
* Tipos de mecanismo de pesquisa
* Palavras-chave

Além disso, os clientes podem implantar um objeto simples no site e preenchê-lo com pares de valores-chave nos quais deseja que a [!UICONTROL DIL] colete dados. Você poderá adicionar ou remover pontos de dados de público-alvo específicos do site sem atualizar o [!DNL Audience Management]. Entre em contato com o representante de soluções de parceiros para configurar corretamente e garantir que o módulo [!DNL DIL] faça referência ao objeto da página corretamente.

<br> 

**A [!UICONTROL DIL] pode coletar dados do [!DNL Google Analytics]?**

Sim. A [!UICONTROL DIL] pode coletar alguns elementos do [!DNL Google Analytics] (GA) e enviar esses dados para o [!DNL Audience Manager]. Consulte:

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**Posso obter dados brutos do [!DNL Audience Manager] e sua granularidade?**

Sim, o [!DNL Audience Manager] pode fornecer dados coletados para usuários que já vimos em seu inventário. Isso inclui:

* A ID de usuário exclusiva (UUID) atribuída pelo [!DNL Audience Manager]
* IDs de características e segmentos
* Sinais não utilizados
* Carimbos de data e hora
* URLs de página

<br> 

**Desejo coletar dados em um site e direcionar usuários via [!DNL Google Ad Manager] em um site diferente. Preciso implantar o código na outra propriedade se não quiser coletar dados desse local?**

Não. Se a coleta de dados no segundo site não for um requisito, não será necessário implantar a DIL lá. Se você tiver acesso ao inventário no segundo site via [!DNL Google Ad Manager], poderá usar a coleta de dados do site inicial e direcionar via [!DNL Google Ad Manager].

<br> 

**Qual é o melhor provedor de dados de terceiros?**

Cada provedor traz algo único para a tabela, então a resposta depende do que você está procurando. Podemos ativar o relatórios de sobreposição (sem custo) para ajudar você a entender qual provedor pode funcionar melhor para você.

<br> 

**Como o [!DNL Audience Manager] define cookies e transmite variáveis para [!DNL Google Ad Manager]?**

[!DNL Audience Manager] define 2 cookies: um envia variáveis de segmento para a marca de anúncio [!DNL Google Ad Manager] e o outro define a ID de usuário exclusiva (UUID), que também é lida por [!DNL Google Ad Manager]. Adicionar a UUID à tag de publicidade significa que podemos fazer relatórios no nível do usuário e descobrir públicos-alvo.

<br> 

**É possível enviar informações do DSP sobre pontos no funil de conversão alcançados por um usuário?**

Sim. Podemos enviar dados de funil, mas o DSP deve ter a capacidade técnica para usá-los. Um DSP deve confirmar que pode lidar com vários segmentos. Caso contrário, talvez seja necessário criar segmentos específicos para retirar um usuário de outros segmentos com base em seu progresso de conversão (por exemplo, etapa 1 e 2 concluídas, mas não etapa 3). Você pode enviar essas informações para um DSP para que ele possa redirecionar os usuários, direcioná-los para uma landing page específica ou exibir criações específicas.

<br> 

**Como posso confirmar se os dados enviados via FTP foram coletados pelo [!DNL Audience Manager]?**

Um arquivo foi selecionado quando a extensão muda de `.sync` para `.processed`. Quando isso acontece, o arquivo está na fila de assimilação. Além disso, o gerente de conta pode confirmar quando um arquivo foi carregado.

<br> 

**Quero testar a funcionalidade da [DCS API](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md). Estou enviando chamadas de evento como as mostradas abaixo. As chamadas contêm [IDs](../features/declared-ids.md) declaradas e sinais, que devem perceber algumas características e segmentos que já configurei. Posso usar [!UICONTROL General Reports] e [!UICONTROL Trend Reports] para verificar se as populações de características e segmentos estão aumentando?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

Não, não confie nos [!UICONTROL General Reports] e nos [!UICONTROL Trend Reports] neste caso.

Os relatórios calculam as populações com base nos registros de perfis não autenticados (UUIDs) que vemos no backend no momento em que os relatórios são gerados.

Em uma primeira chamada para o [!DNL DCS], as IDs declaradas *não* estão vinculadas a qualquer UUID (ou seja, nenhum [cookie demdex](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html) está presente no lado do cliente). O [!DNL DCS] gerará aleatoriamente uma UUID e definirá um cookie [!DNL demdex] e o transmitirá na chamada de resposta, mas ele não transmitirá a UUID para o backend.

>[!NOTE]
>
>A UUID gerada só será materializada em nosso armazenamento de dados de backend quando o dispositivo no qual o cookie está definido acionar mais atividade.

Por esse motivo, os relatórios não refletirão os eventos acionados pelas IDs declaradas em sua chamada. Recomendamos que você use UUID, ECID (anteriormente MID) ou IDs de dispositivo móvel em chamadas de teste de evento para o [!DNL DCS]. Em seguida, você pode verificar a característica e as realizações do segmento nos [!UICONTROL General Reports] e nos [!UICONTROL Trend Reports].

Consulte também [Índice de IDs do Audience Manager](../reference/ids-in-aam.md).

<br> 

**Quanto tempo leva para perfis de usuários sincronizarem entre [regiões](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

Geralmente, leva até 24 horas para um perfil do usuário sincronizar entre regiões. Mas, em casos raros, o processo pode levar até 48 horas.

 

**O que acontece com chaves de acesso de usuário inativas do Amazon S3?**

O Adobe fornece aos clientes do Audience Manager chaves de acesso do usuário para os buckets do Audience Manager [!DNL Amazon S3]. Por motivos de segurança, as chaves são automaticamente desativadas após 100 dias de inatividade.

Para reativar suas chaves de acesso ou solicitar novas, entre em contato com o Suporte ao cliente.
