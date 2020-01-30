---
description: 'null'
seo-description: 'null'
seo-title: Captura de dados de clique da campanha por meio de chamadas de pixels
solution: Audience Manager
title: Captura de dados de clique da campanha por meio de chamadas de pixels
uuid: 7c3797f7-9674-493d-972b-38be0584fede
translation-type: tm+mt
source-git-commit: 776aaad0c063a870ef804d166292228f83575f48

---


# Capturing Campaign Click Data via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

O rastreamento de cliques permite a medição do envolvimento do visitante em toda a sua campanha, pois registra uma atividade baseada em cliques para criações de terceiros. Semelhante à coleção de impressões, uma chamada de evento é enviada para os servidores de coleta de dados ([!UICONTROL DCS]) do Audience Manager para processamento. O visitante é então redirecionado para o endereço da Web desejado.

>[!IMPORTANT]
>
>Para que o Audience Manager interprete corretamente os campos recebidos em chamadas de evento e renderize os dados da sua campanha nos relatórios [de Otimização de](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md)público-alvo, você deve enviar arquivos de metadados que mapeiam esses campos para valores legíveis para humanos. Consulte [Visão geral e mapeamentos para arquivos](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) de metadados e entre em contato com seu consultor do Audience Manager ou com o Atendimento ao cliente para configurar um diretório Amazon S3 para arquivos de metadados.

>[!NOTE]
>
>Entre em contato com sua consultoria do Adobe Audience Manager ou cliente potencial da conta para obter o URL exato específico do domínio do cliente.

## Requisitos

As chamadas de rastreamento de cliques exigem os seguintes parâmetros:

* `d_event=click`: Um par de valor chave que identifica uma chamada de evento como um evento de clique.
* `d_rd=redirect URL`: Um par de valor chave que contém um redirecionamento codificado duas vezes [!DNL URL]. Se você estiver usando uma ferramenta de codificação on-line, execute a string pelo codificador e, em seguida, codifique o resultado novamente para que o redirecionamento funcione.

Além disso, a chamada pode conter pares de valores chave que podem ser usados para qualificação de características ou para fornecer dados e metadados para outros relatórios.

## Exemplo de solicitação

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Resposta

A resposta redireciona o navegador para o [!DNL URL] especificado no `d_rd` parâmetro. A string de resposta pode incluir valores gerados por qualquer uma das macros suportadas listadas abaixo.

Com base no exemplo acima, o navegador é redirecionado para o seguinte [!DNL URL]:

`https://adobe.com/callback?creative=123`

## Macros suportadas

Os eventos de clique suportam as macros listadas na tabela a seguir. Uma macro é uma pequena unidade de código autocontido que é ativada quando a tag de anúncio é carregada para campanha e rastreamento de usuário. As macros serão transmitidas juntamente com o destino [!DNL URL], desde que estejam marcadas com o seguinte formato: `%macro%`. Algumas teclas não têm macros e aceitam um valor de ID codificado. As teclas que aceitam valores codificados são necessárias se você quiser analisar dados nos Relatórios [de otimização de](../../reporting/audience-optimization-reports/audience-optimization-reports.md)público-alvo.

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
   <td colname="col02"> <p>Sem macro. </p> <p>Aceita um valor de ID codificado. </p> </td> 
   <td colname="col2"> <p>ID do anunciante.</p> <p>Um código de integração para a fonte de dados do anunciante. Observe que isso não está relacionado às fontes de dados do Audience Manager.</p> <p> Necessário para <span class="wintitle"> relatórios de Otimização</span> de público-alvo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>ID numérica da unidade de negócios. </p> <p> Necessário para <span class="wintitle"> relatórios de Otimização</span> de público-alvo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>ID de campanha numérica do servidor de publicidade. </p> <p> Necessário para <span class="wintitle"> relatórios de Otimização</span> de público-alvo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>ID criativa numérica do servidor de publicidade. </p> <p>Obrigatório. </p> </td> 
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
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud ID (ECID). </span> For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>ID de disposição numérica do servidor de publicidade. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>A ID de região numérica do cluster DCS que atende a uma solicitação. Para obter mais informações sobre o DCS, consulte <a href="../../reference/system-components/components-data-collection.md"> Componentes</a>da coleta de dados. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>Número aleatório usado para o cache busting. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>ID numérica do site do servidor de publicidade. </p> <p>Opcional. </p> </td> 
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
   <td colname="col02"> <p> <code>%gdpr_applies%</code> </p> </td> 
   <td colname="col2"> <p>Relacionado ao <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">plug-in do Audience Manager para IAB TCF.</a> </p><p><code>gdpr</code> pode ser 0 (RGPD não se aplica) ou 1 (RGPD se aplica).</p> <p>O valor padrão é 0.</p><p>Opcional.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_consent%</code> </p> </td> 
   <td colname="col2"> <p>Relacionado ao <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">plug-in do Audience Manager para IAB TCF.</a></p><p> Se <code>gdpr=1</code>, então <code>%gdpr_consent%</code> é substituído pela string <code>gdpr_consent</code> (consulte a <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">especificação do IAB</a>).</p> <p>O valor padrão é 0.</p><p>Opcional.</p></td> 
  </tr> 
 </tbody> 
</table>

## Exemplo de macros

Este exemplo demonstra como passar as macros criativas, adgroup e placement. Ele supõe que os valores para cada parâmetro sejam passados na parte não redirecionamento da chamada de rastreamento de cliques.

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

>[!MORELIKETHIS]
>
>* [Arquivos de dados e metadados para relatórios de otimização de público-alvo](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

