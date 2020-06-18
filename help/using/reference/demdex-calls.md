---
description: O Audience Manager e o serviço de identificação do Adobe Experience Platform fazem chamadas e recebem dados do domínio demdex.net. Isso pode parecer que a Adobe está trabalhando com um domínio de terceiros incomum, mas não é o caso. Esta seção descreve os elementos em uma chamada demdex.net.
seo-description: O Audience Manager e o serviço de identificação do Adobe Experience Platform fazem chamadas e recebem dados do domínio demdex.net. Isso pode parecer que a Adobe está trabalhando com um domínio de terceiros incomum, mas não é o caso. Esta seção descreve os elementos em uma chamada demdex.net.
seo-title: Compreender as chamadas ao domínio Demdex
solution: Audience Manager
title: Compreender as chamadas ao domínio Demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: d219f6fa1e2a8396b049f86391142c00e263b629
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 5%

---


# Compreender as chamadas ao domínio Demdex{#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] e o Serviço de identificação do Adobe Experience Platform faz chamadas e recebe dados do domínio demdex.net. Isso pode parecer que a Adobe está trabalhando com um domínio de terceiros incomum, mas não é o caso. Esta seção descreve os elementos em uma `demdex.net` chamada.

<table id="table_B846CBEDDA4C4AD19416F7C27FC325C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de chamada </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> demdex.net</code> </p> </td> 
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. Ele reflete o nome original de pré-aquisição do <span class="keyword"> Audience Manager</span>(<span class="keyword"> Demdex</span>). <span class="keyword"> A Adobe</span> adquiriu a <span class="keyword"> Demdex</span> em 2011 e reatribuiu a marca da empresa como <span class="keyword"> Audience Manager</span>. É difícil alterar esse domínio porque ele está inserido profundamente com o <span class="keyword"> Audience Manager</span>, o serviço <span class="wintitle"> de</span>ID e a base de usuários instalada. Consulte <a href="../overview/aam-overview.md#history-and-background"> Histórico e plano de fundo</a>. </p> <p>Você pode ver outros prefixos anexados a <code> demdex.net</code> chamadas herdadas (por exemplo, <code> dcs.demdex.net</code>, <code> fast.demdex.net</code>etc.). Independentemente do prefixo, uma chamada para <code><i>something</i>.demdex.net</code> é sempre uma chamada para a <span class="keyword"> Adobe</span> e não para algum domínio de terceiros desconhecido ou suspeito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> O DPM</span> é uma abreviação para Correspondência <span class="wintitle"> do Provedor de</span>dados. Ele informa aos sistemas internos da Adobe <span class="keyword"> que uma chamada do</span> Audience Manager <span class="keyword"> ou do serviço</span> de <span class="wintitle"></span> ID está transmitindo os dados do cliente para sincronização ou solicitando uma ID. Esta é a <code> demdex.net</code> chamada mais comum que você verá da <span class="keyword"> Audience Manager</span> ou do serviço <span class="wintitle"> de</span>ID. </p> <p><span class="wintitle"> Noções básicas sobre chamadas do DPM</span> : </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b> <span class="keyword"> Audience Manager</span> </b>: Uma chamada <span class="wintitle"> DPM</span> do <span class="keyword"> Audience Manager</span> envia dados para os servidores <span class="wintitle"> de coleta de dados e servidores</span> de cache de <span class="wintitle"></span>Perfil. Consulte <a href="../reference/system-components/components-data-collection.md"> Componentes</a>da coleta de dados. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> <span class="wintitle"> Serviço</span> de ID </b>: Uma chamada <span class="wintitle"> DPM</span> do serviço <span class="wintitle"> de</span> ID é uma solicitação para uma ID de visitante. Consulte <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies e o serviço</a> de identidade do Adobe Experience Platform e <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html" format="https" scope="external"> Como o serviço de identidade do Adobe Experience Platform solicita e define IDs</a>. </li> 
     </ul> </p> <p> <p>Observação:  <span class="wintitle"> Os clientes do serviço</span> de ID podem alterar o prefixo <span class="wintitle"> DPM</span> no nome do domínio. Consulte <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html" format="https" scope="external"> audienceManager Server e audienceManagerServerSecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Serviço de identificação de Adobe Experience Platform](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Cookies do Audience Manager](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html)

