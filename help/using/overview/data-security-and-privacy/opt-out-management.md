---
description: A Adobe cumpre todos os padrões do setor em relação ao gerenciamento de opções. Leia para obter informações completas sobre os tipos de opção de não participação suportados pelo Audience Manager.
seo-description: A Adobe cumpre todos os padrões do setor em relação ao gerenciamento de opções. Leia para obter informações completas sobre os tipos de opção de não participação suportados pelo Audience Manager.
seo-title: Gerenciamento de não participação
solution: Audience Manager
title: Gerenciamento de não participação
uuid: 61b43e0e-bfe3-497e-ade2-6a942a98407e
translation-type: tm+mt
source-git-commit: 50a6627568bd472dae1cfbdf5c6c824622766df1

---


# Gerenciamento de não participação{#opt-out-management}

A Adobe cumpre todos os padrões do setor em relação ao gerenciamento de opções. Leia para obter informações completas sobre os tipos de opção de não participação suportados pelo Audience Manager.

## Recusa global {#global-opt-out}

A opção de não participação global representa uma opção de não participação no Audience Manager e em outras soluções da Adobe Experience Cloud para todas as marcas. A tabela abaixo lista os métodos usados para opção de não participação global:

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
   <td colname="col2"> <p>A página <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Suas escolhas de privacidade </a> fornece recursos de 1 clique que permitem que os usuários finais controlem e excluam a coleta de dados pelas soluções de publicidade da Adobe Experience Cloud (incluindo o Audience Manager). Especificamente, consulte a seção Cliente <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> comercial </a> da página Opções de privacidade. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chamadas de API diretas para o Audience Manager </p> </td> 
   <td colname="col2"> <p>Você pode optar por não participar da coleta de dados por todas as marcas do Audience Manager, fazendo uma chamada para a API DCS abaixo e incluindo a ID de usuário do <a href="../../reference/ids-in-aam.md"> Audience Manager </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" —cookie "demdex=12345678901234567890123456789012345678;dextp=12;Dextp ST=12" </code> </p> <p>Como resultado, definiremos os cookies <code>demdex=NOTARGET</code> e <code>dextp=NOTARGET</code> para a ID de usuário do Audience Manager enviada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dispositivos móveis </p> </td> 
   <td colname="col2"> <p>Consulte as configurações de não participação e privacidade para: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Dispositivos Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> Dispositivos iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Seus usuários finais também podem optar por não participar da coleta global de dados visitando os sites de nossos parceiros de padrões do setor.

* [A Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Seguindo as solicitações de opção de não participação descritas acima:

* O Audience Manager irá parar toda a coleta, segmentação ou ativação de dados em diante.
* Os dados históricos são removidos do perfil do usuário após 120 dias.

## Recusar nível de parceiro {#partner-opt-out}

A opção de não participação em nível de parceiro permite a não participação na coleta de dados por parceiros específicos do Audience Manager. A opção de não participação em nível de parceiro funciona com chamadas de ID [](../../features/declared-ids.md) declarada e chamadas de ID de dispositivo, conforme descrito nas seções abaixo.

### Recusar nível de parceiro com chamadas de ID declaradas

Seguindo uma opção de não participação em nível de parceiro com uma chamada de ID declarada:

* A última ID de dispositivo (ID[de usuário exclusiva do](../../reference/ids-in-aam.md)Audience Manager) vinculada à ID [do](../../reference/ids-in-aam.md) CRM é excluída da coleta de dados.
* O Audience Manager irá parar toda a coleta, segmentação ou ativação de dados para a última ID de dispositivo vinculada à ID do CRM.
* Nenhum dado histórico é excluído.

<br/>

**Chamadas de cancelamento**

Quando o Audience Manager recebe uma solicitação de recusa de nível de parceiro, o JSON retornado pelo DCS contém o código de [erro 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), com a mensagem [!UICONTROL "Encountered opt out tag"], em vez da ID de usuário do Audience Manager.

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

Você pode fazer uma solicitação de recusa de ID declarada com os pares de valor-chave `d_cid` e `d_cid_ic` e IDs declaradas. Os parâmetros herdados como `d_dpid` e `d_dpuuid` ainda funcionam, mas são considerados obsoletos. Consulte [CID substitui DPID e DPUUID](../../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

**Opções com CID e CID_IC**

Para obter uma descrição e sintaxe, consulte Variáveis e sintaxe [URL para IDs](../../features/declared-ids.md#variables-and-syntax)declaradas.

| Opção de não participação usando | Amostra de código |
|--- |--- |
| Uma ID de provedor de dados e ID de usuário. | `https://domain name/demoptout.jpg?d_cid=123%01987...` |
| Um código de integração e ID de usuário. | `https://domain name/demoptout?d_cid_ic=456%01321...` |
| Vários pares de valores chave d_cid e d_cid_ic. | `https://domain name/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

### Recusar nível de parceiro com chamadas de ID de dispositivo

Você pode optar por não participar da coleta de dados em uma determinada ID de dispositivo para uma marca, fazendo as seguintes chamadas para a API [do](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)DCS:

| Opção de não participação usando | Amostra de código |
|--- |--- |
| Uma ID de usuário exclusiva (`uuid`) do Audience Manager. | `http://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Uma Experience Cloud ID (`mid`) | `http://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Leia mais sobre `uuid`, `mid` e `imsOrgId` no [Índice de IDs no Audience Manager](/help/using/reference/ids-in-aam.md).

Seguindo uma opção de não participação em nível de parceiro com uma chamada de ID de dispositivo:

* A ID do dispositivo é excluída da coleta de dados.
* O Audience Manager encerrará toda a coleta, segmentação ou ativação de dados, para o parceiro, a partir da ID do dispositivo.
* Nenhum dado histórico é excluído.
