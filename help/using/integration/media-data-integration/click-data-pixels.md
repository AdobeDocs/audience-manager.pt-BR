---
description: O rastreamento de cliques permite a medição do engajamento do visitante em toda a campanha, pois registra a atividade baseada em cliques para anúncios de terceiros.
seo-description: O rastreamento de cliques permite a medição do engajamento do visitante em toda a campanha, pois registra a atividade baseada em cliques para anúncios de terceiros.
seo-title: Captura de dados de cliques da campanha via Pixel Calls
solution: Audience Manager
title: Captura de dados de cliques da campanha via Pixel Calls
uuid: 7c3797f7-9674-493d-972b-38be0584fede
feature: Integração do Adobe Campaign
exl-id: 41b169bf-3727-4ed7-b74f-fea75244d2cb
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 12%

---

# Captura de dados de cliques da campanha via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

O rastreamento de cliques permite a medição do engajamento do visitante em toda a campanha, pois registra a atividade baseada em cliques para anúncios de terceiros. Semelhante a [coleção de impressões](/help/using/integration/media-data-integration/impression-data-pixels.md), uma chamada de evento é enviada para os servidores de coleta de dados [!DNL Audience Manager] ([!DNL DCS]) para processamento. O visitante é então redirecionado para o endereço da Web desejado.

>[!NOTE]
>
>Entre em contato com seu [!DNL Audience Manager] consultor ou gerente de conta para obter o [!DNL URL] exato do domínio cliente.

## Requisitos

As chamadas de rastreamento de cliques exigem os seguintes parâmetros:

* `d_event=click`: Um par de valores chave que identifica uma chamada de evento como um evento de clique.
* `d_rd=redirect URL`: Um par de valores chave que contém um redirecionamento codificado duas vezes  [!DNL URL]. Se você estiver usando uma ferramenta de codificação online, execute a string pelo codificador e, em seguida, codifique o resultado novamente para que o redirecionamento funcione.

Além disso, a chamada pode conter pares de valores chave que podem ser usados para qualificação de característica ou para fornecer dados e metadados para outros relatórios.

## Exemplo de solicitação

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Resposta

A resposta redireciona o navegador para o [!DNL URL] especificado no parâmetro `d_rd`. A cadeia de caracteres de resposta pode incluir valores gerados por qualquer uma das macros suportadas listadas abaixo.

Com base no exemplo acima, o navegador é redirecionado para o seguinte [!DNL URL]:

`https://adobe.com/callback?creative=123`

## Macros suportadas

Os eventos de clique são compatíveis com as macros listadas na tabela a seguir. Uma macro é uma pequena unidade de código autocontido que é ativada quando a tag de anúncio é carregada para campanha e rastreamento de usuário. As macros serão transmitidas com o destino [!DNL URL], desde que estejam marcadas com o seguinte formato: `%macro%`. Algumas chaves não têm macros e aceitam um valor de ID codificado. Chaves que aceitam valores codificados são necessárias se você deseja analisar dados nos [Relatórios do Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

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
   <td colname="col2"> <p>ID de grupo de publicidade numérica do servidor de publicidade. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>Sem macro. </p> <p>Aceita um valor de ID codificado permanentemente. </p> </td> 
   <td colname="col2"> <p>ID do anunciante.</p> <p>Um código de integração para a fonte de dados do anunciante. Observe que isso não está relacionado a fontes de dados Audience Manager.</p> <p> Necessário para relatórios <span class="wintitle"> Audience Optimization</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>ID numérica da unidade comercial. </p> <p> Necessário para relatórios <span class="wintitle"> Audience Optimization</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>ID de campanha numérica do servidor de publicidade. </p> <p> Necessário para relatórios <span class="wintitle"> Audience Optimization</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>ID de criação numérica do servidor de publicidade. </p> <p>Obrigatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>ID do provedor de dados. </p> <p>Geralmente usado com <code> d_dpuuid</code> para vincular uma ID de provedor de dados a uma ID de usuário. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>ID exclusiva do usuário fornecida pelo provedor de dados. </p> <p>Geralmente usado com <code> d_dpid</code> para vincular uma ID de usuário a uma ID de provedor de dados. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"></span> Experience Cloud ID (ECID). Para obter mais informações sobre a ECID, consulte Cookies <a href="https://docs.adobe.com/content/help/pt-BR/id-service/using/intro/cookies.html" format="https" scope="external"> e Experience Cloud ID</a>. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>ID de posicionamento numérico do servidor de anúncios. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>A ID de região numérica do cluster DCS que atende a uma solicitação. Para obter mais informações sobre o DCS, consulte <a href="../../reference/system-components/components-data-collection.md"> Componentes da coleta de dados</a>. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>Número aleatório usado para eliminação de cache. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>ID de site numérica do servidor de publicidade. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>DPID da origem de onde o Audience Manager extrai os metadados. </p> <p>Obrigatório. </p> </td> 
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
   <td colname="col2"> <p>Relacionado ao <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">plug-in do Audience Manager para IAB TCF.</a></p><p> Se <code>gdpr=1</code>, então <code>${gdpr_consent_XXXX}</code> é substituído pela sequência <code>gdpr_consent</code> e pelo ID do fornecedor (consulte <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> especificação IAB</a>).</p> <p>O valor padrão é 0.</p><p>Opcional.</p></td> 
  </tr> 
 </tbody> 
</table>

## Exemplo de macros

Este exemplo demonstra como passar as macros creative, adgroup e placement. Ele presume que os valores de cada parâmetro sejam passados na parte não redirecionada da chamada de rastreamento de cliques.

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

Você pode usar chamadas de pixel para alimentar os [Relatórios do Audience Optimization](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md). Consulte [Visão geral e mapeamentos para arquivos de metadados](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) se desejar usar pixels para alimentar os relatórios.


>[!MORELIKETHIS]
>
>* [Arquivos de dados e metadados para relatórios do Audience Optimization](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

