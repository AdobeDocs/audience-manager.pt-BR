---
description: O rastreamento de cliques permite medir o engajamento do visitante em toda a campanha, pois registra atividades baseadas em cliques para criações de terceiros.
seo-description: Click tracking enables measurement of visitor engagement throughout your campaign, as it records click-based activity for third-party creatives.
seo-title: Capturing Campaign Click Data via Pixel Calls
solution: Audience Manager
title: Captura de dados de cliques da campanha via Pixel Calls
uuid: 7c3797f7-9674-493d-972b-38be0584fede
feature: Adobe Campaign Integration
exl-id: 41b169bf-3727-4ed7-b74f-fea75244d2cb
TQID: https://experienceleague.adobe.com/LzQsKoBZYRyfg8F87yWhT2CB2ojlydELPKRfy4xjXHo
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 639
ht-degree: 6%

---

# Captura de dados de cliques da campanha via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

O rastreamento de cliques permite medir o engajamento do visitante em toda a campanha, pois registra atividades baseadas em cliques para criações de terceiros. Semelhante à [coleção de impressões](/help/using/integration/media-data-integration/impression-data-pixels.md), uma chamada de evento é enviada aos [!DNL Audience Manager] servidores de coleção de dados ([!DNL DCS]) para processamento. O visitante é então redirecionado para o endereço Web desejado.

>[!NOTE]
>
>Entre em contato com sua consultoria do [!DNL Audience Manager] ou com o líder da conta para obter o [!DNL URL] exato específico do domínio do cliente.

## Requisitos

As chamadas de rastreamento de cliques exigem os seguintes parâmetros:

* `d_event=click`: um par de valores chave que identifica uma chamada de evento como um evento de clique.
* `d_rd=redirect URL`: Um par de valores chave que contém um redirecionamento codificado duplo [!DNL URL]. Se estiver usando uma ferramenta de codificação online, execute a cadeia de caracteres por meio do codificador e codifique o resultado novamente para que o redirecionamento funcione.

Além disso, a chamada pode conter pares de valores chave que podem ser usados para a qualificação de características ou para fornecer dados e metadados para outros relatórios.

## Amostra de solicitação

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Resposta

A resposta redireciona o navegador para o [!DNL URL] especificado no parâmetro `d_rd`. A cadeia de caracteres de resposta pode incluir valores gerados por qualquer uma das macros compatíveis listadas abaixo.

Com base no exemplo acima, o navegador é redirecionado para o seguinte [!DNL URL]:

`https://adobe.com/callback?creative=123`

## Macros suportadas

Os eventos de clique suportam as macros listadas na tabela a seguir. Uma macro é uma pequena unidade de código independente que é ativada quando a tag de anúncio é carregada para rastreamento de campanha e usuário. As macros serão transmitidas com o destino [!DNL URL], desde que estejam marcadas com o seguinte formato: `%macro%`. Algumas chaves não têm macros e aceitam um valor de ID embutido em código. As chaves que aceitam valores codificados são necessárias se você quiser analisar dados nos [Relatórios do Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_6EB65C3B7D0E49C59AA6C932549E33FC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Chave </th> 
   <th colname="col02" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_adgroup%</code> </p> </td> 
   <td colname="col2"> <p>ID numérica do grupo de publicidade do servidor de publicidade. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>Sem macro. </p> <p>Aceita um valor de ID codificado. </p> </td> 
   <td colname="col2"> <p>ID do anunciante.</p> <p>Um código de integração para a fonte de dados do anunciante. Observe que isso não está relacionado às fontes de dados do Audience Manager.</p> <p> Necessário para <span class="wintitle"> relatórios do Audience Optimization</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>ID numérica da unidade de negócios. </p> <p> Necessário para <span class="wintitle"> relatórios do Audience Optimization</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>ID numérica da campanha do servidor de publicidade. </p> <p> Necessário para <span class="wintitle"> relatórios do Audience Optimization</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>ID de criação numérica do servidor de publicidade. </p> <p>Obrigatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>ID do provedor de dados. </p> <p>Usado frequentemente com <code> d_dpuuid</code> para vincular uma ID de provedor de dados a uma ID de usuário. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>ID de usuário exclusiva fornecida pelo provedor de dados. </p> <p>Usado com <code> d_dpid</code> com frequência para vincular uma ID de usuário a uma ID de provedor de dados. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud </span> ID (ECID). Para obter mais informações sobre a ECID, consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=pt-BR" format="https" scope="external"> Cookies e a Experience Cloud ID</a>. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>ID de posicionamento numérico do servidor de publicidade. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>A ID da região numérica do cluster DCS que atende a uma solicitação. Para obter mais informações sobre o DCS, consulte <a href="../../reference/system-components/components-data-collection.md"> Componentes da Coleção de Dados</a>. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>Número aleatório usado para eliminação de cache. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>ID numérica do site no servidor de publicidade. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>DPID da origem da qual o Audience Manager extrai os metadados. </p> <p>Obrigatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>Especifique a ID do visitante diretamente no URL em vez de depender do cookie Demdex. </p> <p>Opcional. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p>Relacionado ao <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">plug-in do Audience Manager para IAB TCF.</a> </p><p><code>gdpr</code> pode ser 0 (o GDPR não se aplica) ou 1 (o GDPR se aplica).</p> <p>O valor padrão é 0.</p><p>Opcional.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p>Relacionado ao <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">plug-in do Audience Manager para IAB TCF.</a></p><p> Se <code>gdpr=1</code>, então <code>${gdpr_consent_XXXX}</code> é substituído pela cadeia de caracteres <code>gdpr_consent</code> e pela ID do fornecedor (consulte a especificação do IAB <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> </a>).</p> <p>O valor padrão é 0.</p><p>Opcional.</p></td> 
  </tr> 
 </tbody> 
</table>

## Exemplo de macros

Este exemplo demonstra como transmitir as macros creative, adgroup e placement. Ele presume que os valores de cada parâmetro sejam transmitidos na parte de não redirecionamento da chamada de rastreamento de cliques.

<ul class="simplelist"> 
 <li> <code> creative=1235 </code> </li> 
 <li> <code> campaign=4709 </code> </li> 
 <li> <code> adgroup=3408 </code> </li> 
 <li> <code> placement=1001 </code> </li> 
 <li> <code> src=203 </code> </li> 
</ul>

## Solicitação

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd%3Dhttp%253A%252F%252Fadobe.com%252Fcallback%253Fcreative%253D%2525d_creative%2525%2526campaign%253D%2525d_campaign%2525%2526adgroup%253D%2525%0Ad_adgroup%2525%2526d_placement%253D%2525placement%2525%2526src%253D%2525d_src%2525
```

## Resposta

Com base no exemplo acima, o navegador é redirecionado para o seguinte [!DNL URL]:

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## Funcionalidade adicional - [!UICONTROL Audience Optimization Reports]

Você pode usar chamadas de pixel para acionar os [Relatórios do Audience Optimization](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md). Consulte [Visão geral e mapeamentos para arquivos de metadados](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) se desejar usar pixels para potencializar os relatórios.


>[!MORELIKETHIS]
>
>* [Arquivos de dados e metadados para relatórios do Audience Optimization](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)
