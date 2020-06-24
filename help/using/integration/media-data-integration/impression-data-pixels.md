---
description: Uma abordagem para enviar dados de mídia ao Audience Manager usa macros de servidor de publicidade para enviar atributos de campanha ao Audience Manager.
seo-description: Uma abordagem para enviar dados de mídia ao Audience Manager usa macros de servidor de publicidade para enviar atributos de campanha ao Audience Manager.
seo-title: Captura de dados de impressão da campanha via Pixel Calls
solution: Audience Manager
title: Captura de dados de impressão da campanha via Pixel Calls
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
translation-type: tm+mt
source-git-commit: 3523cdb0d6d412c1a93694e4cbeab188154120f0
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 20%

---


# Captura de dados de impressão da campanha via Pixel Calls{#capturing-campaign-impression-data-via-pixel-calls}

Uma abordagem para enviar dados de mídia ao Audience Manager usa macros de servidor de publicidade para enviar atributos de campanha ao Audience Manager.

Esta metodologia é frequentemente chamada de &quot;pixeling the creative&quot;. Esses pontos de dados são inseridos dinamicamente no código de [!DNL Audience Manager] pixel pelas macros de servidores de publicidade de terceiros, que são usadas para mapear e relatar todas as impressões e cliques com base nos atributos chave do relatórios da campanha. Os dados agregados fornecem uma visualização unificada de desempenho de campanha, ajudam a identificar caminhos de conversão personalizados e ajudam os clientes a melhorar a sequência de eventos de servidor de anúncios que levam a conversões.

## Sintaxe de chamada de Evento

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *itálico*, colchetes `[ ]` `( )` etc.) indicar elementos e opções de código. Consulte [Convenções de estilo para código e elementos de texto](../../reference/code-style-elements.md) para obter mais informações.

A chamada de evento coleta dados de impressão e conversão e os envia para os [!DNL Audience Manager] [servidores de coleta de dados](/help/using/reference/system-components/components-data-collection.md) ([!DNL DCS]). Esse processo depende de servidores de publicidade de terceiros que colocam a chamada no criativo para controlar o conteúdo inserido no código. Os servidores de publicidade de terceiros (por exemplo, [!DNL DFA]) podem colocar esse código em cada impressão de anúncios. Além disso, uma chamada de anúncio não utiliza [!DNL JavaScript] nem emprega técnicas de frame-busting para acessar os dados do editor fora da tag de anúncio.

As chamadas de Evento consistem em pares de valores chave que usam a seguinte sintaxe:

```
http://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

No par de chave-valor, a variável value é uma ID ou macro inserida pelo servidor de publicidade. Quando a tag do anúncio é carregada, ela `%macro%` é substituída pelos valores necessários correspondentes. Esta chamada não retorna uma resposta.

## Pares de valor-chave suportados {#supported-key-value-pairs}

Chamadas de evento de impressão aceitam dados formados em pares de valores chave. A tabela a seguir lista e descreve as teclas usadas para manter essas variáveis. Muitos deles são necessários se você deseja capturar e analisar dados nos Relatórios [de otimização de](../../reporting/audience-optimization-reports/audience-optimization-reports.md)Audiência.

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Chave </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_adgroup </code> </td> 
   <td colname="col2"> <p>ID de grupo de publicidade numérica do servidor de publicidade. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>ID da fonte de dados ou código de integração para seu anunciante. </p> <p>Necessário para relatórios de Otimização de <span class="wintitle"> Audiência </span> . </p> <p>Opcional.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>ID da fonte de dados ou código de integração da unidade de negócios. </p> <p>Necessário para relatórios de Otimização de <span class="wintitle"> Audiência </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>Valor de economia de cache. <span class="keyword"> O Audience Manager envia </span> automaticamente cabeçalhos de controle de cache que são respeitados pela maioria dos navegadores e proxies. Se você quiser executar o cache busting adicional, inclua este parâmetro em uma chamada de evento, seguido por uma sequência aleatória. </p> <p> Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>ID de campanha numérica do servidor de publicidade. </p> <p>Necessário para relatórios de Otimização de <span class="wintitle"> Audiência </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>Neste contexto, <code> d_cid </code> instancia um par de valor chave que permite associar um tipo de dispositivo móvel a uma ID de usuário exclusiva (DPUUID). Uma ID fixa determina o tipo de dispositivo móvel. O valor, que é a ID do usuário, pode variar. Separe o par de valor chave por <code> %01 </code>, que é um caractere de controle não imprimível. Esse parâmetro aceita as seguintes chaves: </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">2014: Identifica um dispositivo Android (GAID). Por exemplo, <code> d_cid = 20914 %01 1234 </code> diz que o usuário 1234 está associado a um dispositivo Android. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">2015: Identifica um dispositivo iOS (IDFA). Por exemplo, <code> d_cid = 20915 %01 5678 </code> diz que o usuário 5678 está associado a um dispositivo iOS. </li> 
    </ul> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>ID criativa numérica do servidor de publicidade. </p> <p>Necessário para relatórios de Otimização de <span class="wintitle"> Audiência </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>Identifica uma chamada de evento como um evento de impressão. </p> <p>Obrigatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>ID de disposição numérica do servidor de publicidade. </p> <p> Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>ID numérica do site do servidor de publicidade. </p> <p>Necessário para relatórios de Otimização de <span class="wintitle"> Audiência </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>ID da fonte de dados ou código de integração da plataforma que fornece os metadados (por exemplo, DFA, Atlas, GBM, Media Math etc.). </p> <p>Necessário para relatórios de Otimização de <span class="wintitle"> Audiência </span> . </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code>gdpr</code>  </td> 
   <td colname="col2"> <p>Relacionado ao <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">plug-in do Audience Manager para IAB TCF.</a></p> <p><code>gdpr</code> pode ser 0 (RGPD não se aplica) ou 1 (RGPD se aplica).</p> <p>O valor padrão é 0.</p><p>Opcional.</p><p>Se <code>gdpr=1</code>, o <code>gdpr_consent</code> parâmetro deve conter o parâmetro de consentimento TC IAB para processar os dados com êxito. Caso contrário, todos os dados serão descartados.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_consent</code> </td> 
   <td colname="col2"> <p>Relacionado ao <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">plug-in do Audience Manager para IAB TCF.</a></p><p> Se <code>gdpr=1</code>, então <code>${gdpr_consent_XXXX}</code> é substituído pela <code>gdpr_consent</code> string e pela ID do fornecedor (consulte a especificação <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"></a>IAB).</p> <p>O valor padrão é 0.</p><p>Opcional.</p></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Entre em contato com sua consultoria de Adobe Audience Manager ou líder de conta para obter o URL exato específico do domínio do cliente.

## Funcionalidade adicional - [!DNL Audience Optimization Reports] {#additional-functionality-aor}

Você pode usar chamadas de pixel para alimentar os Relatórios [de otimização de](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md)Audiência. Consulte [Visão geral e mapeamentos para arquivos](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) de metadados se desejar usar pixels para alimentar os relatórios.

>[!MORELIKETHIS]
>
>* [Arquivos de dados e metadados para relatórios de otimização de Audiência](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

