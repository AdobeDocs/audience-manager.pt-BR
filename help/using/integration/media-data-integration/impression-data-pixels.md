---
description: Uma abordagem para enviar dados de mídia ao Audience Manager usa macros do servidor de publicidade para enviar atributos de campanha para o Audience Manager.
seo-description: Uma abordagem para enviar dados de mídia ao Audience Manager usa macros do servidor de publicidade para enviar atributos de campanha para o Audience Manager.
seo-title: Captura de dados de impressão da campanha via Pixel Calls
solution: Audience Manager
title: Captura de dados de impressão da campanha via Pixel Calls
uuid: 6 ac 44100-4 c 55-4992-8835-0 d 578 bb 4 e 5 c 2
translation-type: tm+mt
source-git-commit: c79c2311c3ea76ce2450dc1b84a7a22b60a6edb7

---


# Captura de dados de impressão da campanha via Pixel Calls{#capturing-campaign-impression-data-via-pixel-calls}

Uma abordagem para enviar dados de mídia ao Audience Manager usa macros do servidor de publicidade para enviar atributos de campanha para o Audience Manager.

Essa metodologia é geralmente chamada de "pixelando a criação". Those data points are dynamically inserted into the [!DNL Audience Manager] pixel code by the third-party ad server macros, which are used to map and report all impressions and clicks based on the key reporting attributes of the campaign. Os dados agregados fornecem uma visão unificada do desempenho da campanha, ajuda a identificar caminhos de conversão personalizados e ajuda os clientes a melhorar a sequência de eventos do servidor de anúncios que levam a conversões.

## Sintaxe de chamada de evento

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *itálico*, colchetes `[ ]` `( )` etc.) indicar elementos e opções de código. Consulte [Convenções de estilo para código e elementos de texto](../../reference/code-style-elements.md) para obter mais informações.

A chamada de evento coleta dados de impressão e conversão e os envia para os [!DNL Audience Manager] [servidores de coleta de dados](/help/using/reference/system-components/components-data-collection.md) ([!UICONTROL DCS]). Esse processo depende de servidores de publicidade de terceiros que colocam a chamada no criativo para controlar o conteúdo inserido no código. Os servidores de publicidade de terceiros (por exemplo, [!DNL DFA]) podem colocar esse código em cada impressão de anúncios. Além disso, uma chamada de anúncio não utiliza [!DNL JavaScript] nem emprega técnicas de frame-busting para acessar os dados do editor fora da tag de anúncio.

As chamadas de evento consistem em pares de valores chave que usam a seguinte sintaxe:

<pre>
http://clientname.demdex.net/event?d_event=imp&amp;d_src=datasource_id&amp;d_site=siteID&amp;
d_creative=<i>creative_id</i>&amp;d_adgroup=<i>adgroup_id</i>&amp;d_placement=<i>placement_id</i>
&amp;d_campaign=<i>campaign_id</i>[&amp;d_cid=(GAID|IDFA)%01 DPUUID]&amp;d_bust=cache buster value
</pre>

No par de valor chave, a variável de valor é uma ID ou macro inserido pelo servidor de publicidade. When the ad tag loads, that `%macro%` gets replaced with the required, corresponding values. Essa chamada não retornará uma resposta.

## Supported Key-Value Pairs {#supported-key-value-pairs}

As chamadas de evento de impressão aceitam dados formados em pares de valor chave. A tabela a seguir lista e descreve as teclas usadas para manter essas variáveis. Many of these are required if you want to capture and analyze data in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Chave </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_ adgroup </code> </td> 
   <td colname="col2"> <p>ID do grupo de publicidade numérico do servidor de publicidade. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ adsrc </code> </td> 
   <td colname="col2"> <p>ID de fonte de dados ou código de integração do seu anunciante. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ bu </code> </td> 
   <td colname="col2"> <p>ID de fonte de dados ou código de integração da unidade de negócios. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bust </code> </p> </td> 
   <td colname="col2"> <p>Valor de cache. <span class="keyword"> O Audience Manager </span> envia automaticamente cabeçalhos de controle de cache que são respeitados pela maioria dos navegadores e proxies. Se você quiser realizar uma ocorrência de cache adicional, inclua esse parâmetro em uma chamada de evento, seguido por uma sequência aleatória. </p> <p> Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ campaign </code> </td> 
   <td colname="col2"> <p>ID de campanha numérica do servidor de publicidade. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>In this context, <code> d_cid </code> instantiates a key-value pair that lets you associate a mobile device type to a unique user ID (DPUUID). Uma ID fixa determina o tipo de dispositivo móvel. O valor, que é a ID do usuário, pode variar. Separate the key-value pair with <code> %01 </code>, which is a non-printing control character. Esse parâmetro aceita as seguintes chaves: </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914: Identifica um dispositivo Android (GAID). For example, <code> d_cid = 20914 %01 1234 </code> says that user 1234 is associated with an Android device. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915: Identifica um dispositivo iOS (IDFA). For example, <code> d_cid = 20915 %01 5678 </code> says that user 5678 is associated with an iOS device. </li> 
    </ul> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ creative </code> </td> 
   <td colname="col2"> <p>ID de criação numérica do servidor de publicidade. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ event = imp </code> </td> 
   <td colname="col2"> <p>Identifica uma chamada de evento como um evento de impressão. </p> <p>Obrigatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ placement </code> </td> 
   <td colname="col2"> <p>ID de posicionamento numérico do servidor de publicidade. </p> <p> Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ site </code> </td> 
   <td colname="col2"> <p>ID do site numérico do servidor de publicidade. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ src </code> </td> 
   <td colname="col2"> <p>ID de fonte de dados ou código de integração da plataforma que fornece os metadados (por exemplo, DFA, Atlas, GBM, Math Math etc.). </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code><i>rggrgrgrgrg</i></code>  </td> 
   <td colname="col2"> <p>Relacionado ao <a href="../../overview/aam-gdpr/aam-iab-plugin.md">plug-in do Audience Manager para IAB TCF.</a></p> <p><code>pode</code> ser 0 (RGPD não se aplica) ou 1 (o RGPD se aplica).</p> <p>O valor padrão é 0.</p><p>Opcional.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>rggônia_ consentimento</code> </td> 
   <td colname="col2"> <p>Relacionado ao <a href="../../overview/aam-gdpr/aam-iab-plugin.md">plug-in do Audience Manager para IAB TCF.</a></p><p> Se <code>gdpr=1</code>, então <code>%gdpr_consent%</code> é substituído pela cadeia de caracteres <code>gdpr_consent</code> (consulte a <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">especificação do IAB</a>).</p> <p>O valor padrão é 0.</p><p>Opcional.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Entre em contato com a consultoria ou a conta do Adobe Audience Manager para obter o URL exato específico ao domínio do cliente.

>[!MORE_ LIKE_ THIS]
>
>* [Dados e arquivos de metadados para relatórios de otimização de público-alvo](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

