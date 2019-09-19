---
description: Consulte este documento para obter a lista completa das IDs do Adobe Audience Manager.
keywords: DPID; DPUUID; CID; UUID; uid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Consulte este documento para obter a lista completa das IDs do Adobe Audience Manager.
seo-title: Índice de IDs no Audience Manager
solution: Audience Manager
title: Índice de IDs no Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Índice de IDs no Audience Manager{#index-of-ids-in-audience-manager}

Consulte este documento para obter a lista completa das IDs do Adobe Audience Manager.

<table frame="all" id="table_6727BA8BBF2C40E48768126B4EC9984E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> Nome e descrição </th> 
   <th colname="col3" class="entry"> Exemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>UUID do AAM </p> </td> 
   <td colname="col2"> <p> <b><span class="keyword"> ID de usuário exclusiva do Audience Manager</span></b> </p> <p> Uma ID de dispositivo numérica de 38 dígitos que <span class="keyword"> o Audience Manager</span> associa a cada dispositivo com o qual ele interage. Pense nessa ID sempre que vir uma menção de usuários únicos na interface do usuário do Audience Manager.<p><span class="keyword"> O Audience Manager</span> tenta salvar essa ID como um cookie no domínio de terceiros "demdex.net".</p> </p> <p>A UUID do Audience Manager é enviada em chamadas de evento como sinal d_uuid. </p> </td> 
   <td colname="col3"> <p><code> demdex = 07955261652886032950143702505894272138</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ImsOrgId </p> </td> 
   <td colname="col2"> <p> <b>ID da organização</b> </p> <p>Essa é a ID que uma empresa fornece ao se inscrever na Experience Cloud. Para saber como encontrar a ID da empresa, leia <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> Organizações e vinculação</a> de contas e role para baixo até Encontrar a ID da empresa.</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>ID do parceiro</b> </p> <p> O PID é uma ID da empresa no <span class="keyword"> Audience Manager</span>. <span class="keyword"> O Audience Manager</span> associa uma imsOrgId a um PID. </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ECID, MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>A Experience Cloud ID (ECID, abreviações herdadas MID ou MCID) é derivada matematicamente da ID da empresa e da ID de usuário exclusiva do <span class="keyword"> Audience Manager</span> . Desde que essas IDs permaneçam constantes, gerar a ECID correta para um usuário específico é simplesmente um problema matemático. Com a mesma ID de empresa e o UUID do Audience Manager, você obtém o mesmo valor ECID sempre. Você pode ler mais sobre a ECID no documento <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies e Experience Cloud ID</a> . </p> </td> 
   <td colname="col3"> <p><code> mid=08382830887934830189014177072406221371 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>ID da característica</b> </p> <p>A ID de características identifica exclusivamente características no ambiente do <span class="keyword"> Audience Manager</span> . Uma ID de característica é atribuída a cada característica na interface do usuário (UI). </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>ID do segmento </b> </p> <p>A ID do segmento identifica exclusivamente segmentos no ambiente do <span class="keyword"> Audience Manager</span> . Uma ID de segmento é atribuída a cada segmento na interface do usuário. </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>csegID </p> </td> 
   <td colname="col2"> <p> <b>ID do segmento herdado </b> </p> <p>Essa ID identifica exclusivamente segmentos no ambiente do <span class="keyword"> Audience Manager</span> . Uma ID de segmento herdada é atribuída a cada segmento na interface do usuário. </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>destID </p> </td> 
   <td colname="col2"> <p> <b>ID de destino </b> </p> <p>A ID de destino identifica exclusivamente os destinos no ambiente do <span class="keyword"> Audience Manager</span> . Uma ID é atribuída a cada destino na interface do usuário. </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPID </p> </td> 
   <td colname="col2"> <p> <b>ID da fonte de dados (também chamada de ID do provedor de dados)</b> </p> <p>A ID da fonte de dados é um namespace para IDs ou características. Uma ID é atribuída a cada fonte de dados (provedor de dados) na interface. </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p> <b>ID de usuário único do provedor de dados </b> <b>(também chamada de ID de CRM)</b> </p> <p>Uma ID de terceiros. Esta é a ID pela qual você identifica usuários finais em seu próprio sistema CRM. Você pode sincronizar DPUUIDs com UUIDs do <span class="keyword"> Audience Manager</span> e pode sincronizar DPUUIDs de diferentes <span class="wintitle"> Fontes</span> de Dados (DPIDs) no processo <a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md"> de sincronização da</a>ID. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID do CRM </p> </td> 
   <td colname="col2"> <p>Consulte DPUUID acima. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CID, CID_IC </p> </td>
   <td colname="col2"> <p> <b>ID do cliente, Código de integração da ID do cliente</b> </p> <p> <b>Os pares de valores chave CID e CID_IC <a href="../reference/cid.md"> substituem DPID e DPUUID</a>.</b> Elas fornecem as mesmas funções que a DPID e a DPUUID, mas são mais eficientes porque incluem a ID do provedor de dados e a ID do usuário (ou código de integração) em um único par de valores chave. </p> </td> 
   <td colname="col3"> <p><code> 81841%013ad2948b1570a7e408a7cfb7ff4879e4 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="2"> <p>DAID </p> <p> 
     <ul id="ul_4EA61BDD0C9140C894162F50300BA9DB"> 
      <li id="li_16148BDD80194F509FF7935364B77F7A">IDFA </li> 
      <li id="li_DF7FEEF2D46A42C5B9FECD6377758B1A">GAID </li>
      <li>RIDA</li>
      <li>MAID</li>
      <li>DUID</li>
     </ul> </p> </td> 
   <td colname="col2"> <p> <b>ID de anúncio do dispositivo</b> </p> <p>Uma ID única para cada dispositivo de hardware, a ser utilizada para fins de publicidade. Normalmente fornecido pelo fabricante do dispositivo ou do sistema operacional do dispositivo. </p> </td> 
   <td colname="col3"> <p>IDFA, GAID, Roku ID, Playstation ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>ID de anúncio de dispositivo - IDFA - dispositivos iOS</b> </p> <p> <b>IDFA</b> IDs são identificadores de dispositivos móveis fornecidos pelo fabricante do dispositivo. Essas IDs representam dispositivos que executam o sistema operacional iOS. </p> </td> 
   <td colname="col3"> <p> O formato consiste estritamente em 32 dígitos hexadecimais <i>maiúsculos</i> , exibidos em cinco grupos e separados por hífens, no formato 8-4-4-4-12, para um total de 36 caracteres. </p> <p><code> AEBE52E7-03EE-455A-B3C4-E5728396239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>ID de anúncio de dispositivo - GAID - Dispositivos Android</b> </p> <p><b>IDs GAID</b> são identificadores de dispositivos móveis fornecidos pelo fabricante do dispositivo. Essas IDs representam dispositivos que executam o sistema operacional Android. </p> </td> 
   <td colname="col3"> <p>O formato consiste estritamente em 32 dígitos hexadecimais <i>minúsculos</i> , exibidos em cinco grupos e separados por hífens, na forma 8-4-4-4-12, para um total de 36 caracteres. </p> <p> <code> e4fe9bde-caa0-47b6-908d-ffba3fa184f2</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku - RIDA - Dispositivos de transmissão Roku</b> </p> <p><b>As IDs de RIDA GAID</b> são identificadores de dispositivos de fluxo contínuo fornecidos pelo fabricante de dispositivos Roku.</p> </td>
   <td colname="col3"> <p>O formato consiste estritamente em 32 dígitos hexadecimais <i>minúsculos</i> , exibidos em cinco grupos e separados por hífens, na forma 8-4-4-4-12, para um total de 36 caracteres. </p> <p> <code> fcb2a29c-315a-5e6b-bcfd-d889ba19aada</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>ID de anúncio da Microsoft - MAID - Dispositivos do Windows 10</b> </p> <p><b>IDs MAID</b> são identificadores de dispositivos gerados pelo Windows 10 por dispositivo e por usuário.</p> </td>
   <td colname="col3"> <p>Os MAIDs são formatados como strings alfanuméricas.</p></td>
  </tr>
   <tr> 
   <td colname="col2"> <p> <b>Samsung DUID - Dispositivos Samsung</b> </p> Os DUIDs da Samsung são identificadores de dispositivos fornecidos pelas TVs da Samsung.</p> </td>
   <td colname="col3"> <p>Os DUIDs da Samsung são formatados como strings alfanuméricas.</p></td>
  </tr>
 </tbody> 
</table>