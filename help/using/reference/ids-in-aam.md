---
description: Consulte este documento para obter a lista completa das IDs do Adobe Audience Manager.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Consulte este documento para obter a lista completa das IDs do Adobe Audience Manager.
seo-title: Índice de IDs no Audience Manager
solution: Audience Manager
title: Índice de IDs no Audience Manager
uuid: 292185 ec -7 c 6 a -414 b-ab 17-800 c 21 cb 1 f 01
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
   <td colname="col1"> <p>AAM UUID </p> </td> 
   <td colname="col2"> <p> <b><span class="keyword"> ID de usuário exclusiva do</span> Audience Manager </b> </p> <p> Uma ID de dispositivo numérica e de 38 dígitos que <span class="keyword"> o Audience Manager</span> associa a cada dispositivo com o qual ele interage. Pense nesta ID sempre que você vir uma menção de usuários exclusivos na interface do usuário do Audience Manager.<p><span class="keyword"> O Audience Manager</span> tenta salvar essa ID como um cookie no domínio de terceiros "demdex. net".</p> </p> <p>O UUID do Audience Manager é enviado em chamadas de evento como o sinal d_ uuid. </p> </td> 
   <td colname="col3"> <p><code> demdex = 07955261652886032950143702505894272138</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imsorgid </p> </td> 
   <td colname="col2"> <p> <b>ID da organização</b> </p> <p>Essa é a ID com a qual uma empresa é fornecida ao se inscrever para a Experience Cloud. Para saber como encontrar a ID de empresa da sua empresa, leia <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> Organizações e vinculação de contas</a> e role para baixo para encontrar a ID da organização.</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>ID do parceiro</b> </p> <p> A PID é uma ID da empresa no <span class="keyword"> Audience Manager</span>. <span class="keyword"> O Audience Manager</span> associa um imsorgid a uma PID. </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ECID, MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>A Experience Cloud ID (ECID, abreviações herdadas MID ou MCID) é derivada matematicamente da ID da organização e da <span class="keyword"> ID de usuário exclusiva do</span> Audience Manager. Contanto que essas IDs permaneçam constantes, gerar o ECID correto para um usuário específico é apenas um problema matemático. Com a mesma ID de empresa e UUID do Audience Manager, você obtém o mesmo valor ECID todas as vezes. Você pode ler mais sobre o ECID nos <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> cookies e no documento da</a> Experience Cloud ID. </p> </td> 
   <td colname="col3"> <p><code> mid=08382830887934830189014177072406221371 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>ID de característica</b> </p> <p>A ID de característica identifica exclusivamente as características no ambiente <span class="keyword"> do Audience Manager</span> . Uma ID de característica é atribuída a cada característica na interface do usuário (IU). </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>ID do segmento </b> </p> <p>A ID do segmento identifica de forma exclusiva os segmentos no ambiente <span class="keyword"> do Audience Manager</span> . Uma ID de segmento é atribuída a cada segmento na interface do usuário. </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Csegid </p> </td> 
   <td colname="col2"> <p> <b>ID do segmento herdado </b> </p> <p>Essa ID identifica exclusivamente os segmentos no ambiente <span class="keyword"> do Audience Manager</span> . Uma ID de segmento herdada é atribuída a cada segmento na interface do usuário. </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Destid </p> </td> 
   <td colname="col2"> <p> <b>ID de destino </b> </p> <p>A ID de destino identifica exclusivamente os destinos no ambiente <span class="keyword"> do Audience Manager</span> . Uma ID é atribuída a cada destino na interface do usuário. </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPID </p> </td> 
   <td colname="col2"> <p> <b>ID da fonte de dados (também conhecido como ID do provedor de dados)</b> </p> <p>A ID da fonte de dados é um namespace para IDs ou características. Uma ID é atribuída a cada fonte de dados (provedor de dados) na interface do usuário. </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p> <b>ID de usuário exclusiva do provedor de dados </b><b>(também conhecido como ID de CRM)</b> </p> <p>Uma ID de terceiros. Essa é a ID pela qual você identifica os usuários finais em seu próprio sistema CRM. É possível sincronizar dpuuids com <span class="keyword"> uuids do Audience Manager</span> e sincronizar dpuuids com as diferentes <span class="wintitle"> Fontes de Dados</span> (dpids) no processo de sincronização <a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md"> de ID</a>. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423 vn -343 fds -3432 r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID do CRM </p> </td> 
   <td colname="col2"> <p>Consulte DPUUID acima. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423 vn -343 fds -3432 r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CID, CID_ IC </p> </td>
   <td colname="col2"> <p> <b>ID do cliente, código de integração da ID do cliente</b> </p> <p> <b>Os pares de valores chave CID e CID_ IC <a href="../reference/cid.md"> substituem DPID e DPUUID</a>.</b> Eles fornecem as mesmas funções que DPID e DPUUID, mas são mais eficientes, pois incluem a ID do provedor de dados e a ID do usuário (ou código de integração) em um único par de valores chave. </p> </td> 
   <td colname="col3"> <p><code> 81841% 013 ad 2948 b 1570 a 7 e 408 a 7 cfb 7 ff 4879 e 4 </code> </p> </td> 
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
   <td colname="col2"> <p> <b>ID de publicidade do dispositivo</b> </p> <p>Uma ID única para cada dispositivo de hardware, a ser utilizada para fins de publicidade. Normalmente fornecido pelo fabricante do dispositivo ou do sistema operacional do dispositivo. </p> </td> 
   <td colname="col3"> <p>IDFA, GAID, Roku ID, Playstation ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>ID de publicidade do dispositivo - IDFA - dispositivos iOS</b> </p> <p> <b>IDs do IDFA</b> são identificadores de dispositivos móveis, fornecidos pelo fabricante do dispositivo. Essas IDs representam dispositivos que executam o sistema operacional iOS. </p> </td> 
   <td colname="col3"> <p> O formato consiste estritamente em 32 <i>dígitos</i> hexadecimais maiúsculos, exibidos em cinco grupos e separados por hífens, no formulário 8-4-4-4-12, para um total de 36 caracteres. </p> <p><code> AEBE 52 E 7-03 EE -455 A-B 3 C 4-E 57283966239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>ID de publicidade do dispositivo - GAID - dispositivos Android</b> </p> <p><b>IDs de GAID</b> são identificadores de dispositivos móveis, fornecidos pelo fabricante do dispositivo. Essas IDs representam dispositivos que executam o sistema operacional Android. </p> </td> 
   <td colname="col3"> <p>O formato consiste estritamente em 32 <i>dígitos de minúsculas,</i> exibidos em cinco grupos e separados por hífens, no formulário 8-4-4-4-12, para um total de 36 caracteres. </p> <p> <code> e 4 fe 9 bde-caa 0-47 b 6-908 d-ffba 3 fa 184 f 2</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku - RIDA - Dispositivos de streaming roku</b> </p> <p><b>As IDs</b> RAID RAID são identificadores de dispositivo de streaming fornecidos pelo fabricante de dispositivos Roku.</p> </td>
   <td colname="col3"> <p>O formato consiste estritamente em 32 <i>dígitos de minúsculas,</i> exibidos em cinco grupos e separados por hífens, no formulário 8-4-4-4-12, para um total de 36 caracteres. </p> <p> <code> fcb 2 a 29 c -315 a -5 e 6 b-bcfd-d 889 ba 19 aada</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Microsoft Advertising ID - MAID - Dispositivos Windows 10</b> </p> <p><b>IDs de MAID</b> são identificadores de dispositivo gerados pelo Windows 10 em um dispositivo por dispositivo, por usuário.</p> </td>
   <td colname="col3"> <p>As maids são formatadas como strings alfanuméricas.</p></td>
  </tr>
   <tr> 
   <td colname="col2"> <p> <b>Samsung DUID - Dispositivos Samsung</b> </p> A Samsung duids são identificadores de dispositivo fornecidos pela Samsung tvs.</p> </td>
   <td colname="col3"> <p>A Samsung duids é formatada como sequência alfanumérica.</p></td>
  </tr>
 </tbody> 
</table>