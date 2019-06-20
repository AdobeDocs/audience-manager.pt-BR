---
description: A Adobe cumpre com todos os padrões do setor em relação ao gerenciamento de não participação. Leia para obter informações completas sobre os tipos de opção de não participação compatíveis com o Audience Manager.
seo-description: A Adobe cumpre com todos os padrões do setor em relação ao gerenciamento de não participação. Leia para obter informações completas sobre os tipos de opção de não participação compatíveis com o Audience Manager.
seo-title: Gerenciamento de não participação
solution: Audience Manager
title: Gerenciamento de não participação
uuid: 61 b 43 e 0 e-bfe 3-497 e-ade 2-6 a 942 a 98407 e
translation-type: tm+mt
source-git-commit: 50a6627568bd472dae1cfbdf5c6c824622766df1

---


# Opt-out Management{#opt-out-management}

A Adobe cumpre com todos os padrões do setor em relação ao gerenciamento de não participação. Leia para obter informações completas sobre os tipos de opção de não participação compatíveis com o Audience Manager.

## Global Opt-Out {#global-opt-out}

A opção de recusa global representa uma opção de não participação no Audience Manager e outras soluções da Adobe Experience Cloud para todas as marcas. A tabela abaixo lista os métodos usados para recusar global:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recusar para </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>The <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices page </a> provides 1-click features that let your end users control and opt-out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> business customer section </a> of the Privacy Choices page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chamadas de API diretas para o Audience Manager </p> </td> 
   <td colname="col2"> <p>You can opt-out from data collection by all Audience Manager brands by making a call to the DCS API below and include the <a href="../../reference/ids-in-aam.md"> Audience Manager User ID </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" —cookie "demdex = 12345678901234567890123456789012345678; dextp = 12; DST = 12 " </code> </p> <p>As a result, we will set <code>demdex=NOTARGET</code> and <code>dextp=NOTARGET</code> cookies for the submitted Audience Manager User ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dispositivos móveis </p> </td> 
   <td colname="col2"> <p>Consulte as configurações de exclusão e privacidade para: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Dispositivos Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> Dispositivos iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Os usuários finais também podem recusar a coleta de dados global visitando os sites de nossos parceiros de padrões do setor.

* [A Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Iniciativa de publicidade de rede (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Seguindo as solicitações de não participação descritas acima:

* O Audience Manager interromperá toda a coleta de dados, a segmentação ou a ativação para frente.
* Os dados históricos são removidos do perfil do usuário após 120 dias.

## Partner Level Opt-Out {#partner-opt-out}

A opção de recusa no nível do parceiro permite recusar a coleta de dados por parceiros específicos do Audience Manager. The partner-level opt-out works with [Declared ID](../../features/declared-ids.md) calls and Device ID calls, as described in the sections below.

### Opção de recusa de nível de parceiro com chamadas de ID declarada

Seguindo uma opção de não participação no nível de parceiro com uma chamada de ID declarada:

* The last device ID ([Audience Manager Unique User ID](../../reference/ids-in-aam.md)) linked to the [CRM ID](../../reference/ids-in-aam.md) is opted out of data collection.
* O Audience Manager interromperá toda a coleta de dados, a segmentação ou a ativação para a última ID do dispositivo vinculada à ID do CRM.
* Nenhum dado histórico é excluído.

<br/>

**Chamadas de não participação**

When Audience Manager receives a partner-level opt-out request, the JSON returned by the DCS contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), with the message [!UICONTROL "Encountered opt out tag"], instead of the Audience Manager user ID.

<!-- 

<p> 
 <ul id="ul_65EF2E1ED8F24457A35299E38AFE1DBE"> 
  <li id="li_832D0B507BC64782A5D3662FD5173A37">Audience Manager can pass in a declared ID opt-out alongside an Audience Manager UUID in the URL. </li> 
  <li id="li_D6C41CB385C5401D98156E5A3D79AAEE">The declared ID opt-out is stored in the Profile Cache Server (PCS) on a per-partner basis. There is no platform-level opt-out using declared IDs. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross DCS regions). </li> 
 </ul> </p>

 -->

<!-- 

<p>See <a href="../../overview/data-security-and-privacy/data-privacy.md"> Data Privacy </a> for more information about opting-out of data collection. </p>

 -->



**Exemplos**

You can make a declared ID opt-out request with the `d_cid` and `d_cid_ic` key-value pairs. The legacy parameters like `d_dpid` and `d_dpuuid` still work, but are considered deprecated. Consulte [CID substitui DPID e DPUUID](../../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

**Opções com CID e CID_ IC**

For a description and syntax, see [URL Variables and Syntax for Declared IDs](../../features/declared-ids.md#variables-and-syntax).

| Opção de não participação | Amostra de código |
|--- |--- |
| Uma ID do provedor de dados e uma ID de usuário. | `https://domain name/demoptout.jpg?d_cid=123%01987...` |
| Um código de integração e uma ID de usuário. | `https://domain name/demoptout?d_cid_ic=456%01321...` |
| Vários pares d_ cid e d_ cid_ ic-value pares. | `https://domain name/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

### Opção de recusa de nível de parceiro com chamadas de ID do dispositivo

You can opt-out from data collection on a given device ID for a brand by making the following calls to the [DCS API](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Opção de não participação | Amostra de código |
|--- |--- |
| An Audience Manager Unique User ID (`uuid`). | `http://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| An Experience Cloud ID (`mid`) | `http://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Read more about `uuid`, `mid` and `imsOrgId` in the [Index of IDs in Audience Manager](/help/using/reference/ids-in-aam.md).

Seguindo uma opção de não participação no nível de parceiro com uma chamada de ID de dispositivo:

* A ID do dispositivo não é a coleta de dados.
* O Audience Manager interromperá toda a coleta de dados, a segmentação ou a ativação para o parceiro, avançando para a ID do dispositivo.
* Nenhum dado histórico é excluído.
