---
description: Atualize seu código para usar d_cid ou d_cid_ic em vez de d_dpid e d_dpuuid. As variáveis DPID e DPUUID continuarão a funcionar, mas você deve considerá-las obsoletas. Isso inclui as variantes DPID e DPUUID sem o prefixo d_.
seo-description: Update your code to use d_cid or d_cid_ic instead of d_dpid and d_dpuuid. The DPID and DPUUID variables will continue to work, but you should consider them deprecated. This includes DPID and DPUUID variants without the d_ prefix.
seo-title: CID Replaces DPID and DPUUID
solution: Audience Manager
title: CID substitui DPID e DPUUID
uuid: 3641eac5-b19e-45d5-bc1c-35a23b4bab8c
feature: Reference
exl-id: 18e6b1db-fe51-4560-9458-8d65474d2506
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 1%

---

# CID substitui DPID e DPUUID{#cid-replaces-dpid-and-dpuuid}

Atualize seu código para usar `d_cid` ou `d_cid_ic` em vez de `d_dpid` e `d_dpuuid`. As variáveis DPID e DPUUID continuarão a funcionar, mas você deve considerá-las obsoletas. Isso inclui as variantes DPID e DPUUID sem o `d_ prefix`.

## DPID e DPUUID: uma revisão {#dpid-dpuuid-review}

A DPID e a DPUUID são pares de valores chave que contêm uma ID de provedor de dados e uma ID de usuário. Esses pares de valor-chave vinculam IDs do provedor às IDs do usuário. Eles enviam dados durante chamadas de evento, para eventos de sincronização de entrada e para chamadas de ID. Sem eles, o [!DNL Audience Manager] e outros serviços ou recursos não teria uma maneira de corresponder e sincronizar IDs. Às vezes, essas variáveis são expressas com ou sem o prefixo `d_`, como mostrado abaixo. Observe que, no código, *itálico* indica um espaço reservado para variável.

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variável </th> 
   <th colname="col2" class="entry"> Sintaxe </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID do provedor de dados (DPID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_dpid=<i>data provider ID</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid=<i>data provider ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de usuário exclusiva (DPUUID) do provedor de dados </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_dpuuid=<i>data provider unique user ID</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid=<i>data provider unique user ID</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Esses pares de valor-chave ainda funcionam, mas foram descontinuados. Em vez disso, você deve atualizar seu código para usar CID ou CID_IC.

## CID e CID_IC: sobre {#cid-cidic-about}

Os pares de valores-chave CID e CID_IC substituem DPID e DPUUID. Elas fornecem as mesmas funções que a DPID e a DPUUID, mas são mais eficientes porque incluem a ID do provedor de dados (ou código de integração) e a ID do usuário em um único par de valores chave. Em cada par de valor-chave:

* O símbolo = separa a chave de seus valores relacionados.
* O caractere ASCII não imprimível %01 separa os valores.

`d_cid` e `d_cid_ic` usam a sintaxe mostrada abaixo. Observe que, no código, *itálico* indica um espaço reservado para variável.

<table id="table_0C8A4F8FDBC84416B4EB476F67BCFA8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variável </th> 
   <th colname="col2" class="entry"> Sintaxe </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID do cliente (CID) </p> </td> 
   <td colname="col2"> <p> <code>d_cid=<i>data provider ID</i>%01<i>user ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código de integração de ID do cliente (CID_IC) </p> </td> 
   <td colname="col2"> <p> <code>d_cid_ic=<i>integration code</i>%01<i>user ID</i></code> </p> <p> Um código de integração <span class="term"> </span> é uma ID alternativa que você pode usar em vez da ID de Source de Dados, atribuída por <span class="keyword"> Audience Manager</span>. Consulte <a href="../features/manage-datasources.md#create-data-source"> Criar um Source de dados</a> se precisar configurar um código de integração. </p> </td> 
  </tr> 
 </tbody> 
</table>

Consulte também [Sintaxe e variáveis de URL para IDs declaradas](../features/declared-ids.md#variables-and-syntax).

>[!NOTE]
>
>Você pode usar códigos de integração para suas próprias fontes de dados e para [fontes de dados compartilhadas](../features/datasources-list-and-settings.md#settings-menu-options) globais, às quais você tem acesso. Por exemplo, você pode usar códigos de integração ao trabalhar com fontes de dados de identificadores móveis. Use os seguintes códigos de integração, exatamente como especificado abaixo:

* **DSID_20914** para GAID, representando dispositivos que executam o sistema operacional Android.
* **DSID_20915** para IDFA, representando dispositivos que executam o sistema operacional iOS.

**Exemplos**

A tabela a seguir fornece exemplos por tipo de evento.

<table id="table_097A58CCD6E64C4DB0652271A4F31AE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de evento </th> 
   <th colname="col2" class="entry"> Exemplo </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Evento </p> </td> 
   <td colname="col2"> 
    <ul id="ul_6EAB4188C6954512A28D1A8328794BCB"> 
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">Novo: <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">Obsoleto: <code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sincronização de entrada (IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">Novo: <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">Obsoleto: <code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gerar UUID do Audience Manager (ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">Novo: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">Obsoleto: <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Cada chamada também pode incluir vários pares de valores principais `d_cid` e `d_cid_ic`, desta forma:

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## Considerações importantes para equipes de desenvolvimento {#dev-considerations}

<table id="table_5DD068FAE68A42CDB49B6C064706802A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Item </p> </th> 
   <th colname="col2" class="entry"> <p>Descrição </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Codificação de URL </p> </td> 
   <td colname="col2"> <p>As equipes de desenvolvimento <i>devem</i> aplicar codificação de URL às seguintes variáveis no par de valores chave CID: </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> user ID</code> <code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> integration code</code> </li> 
     </ul> </p> <p> <p>Observação: você deve codificar a ID de usuário e o código de integração <i>antes</i> da concatenação em uma cadeia de caracteres. Isso ocorre porque o caractere ASCII %01 que separa as duas variáveis não deve ser capturado na codificação do URL. </p> </p> <p>A codificação de URL garante que suas IDs de usuário e códigos de integração que contêm caracteres reservados ou não seguros, como, mas não limitados a, + ou =, sejam transmitidos corretamente para nossos servidores. </p> <p>Use a <a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> tabela de codificação ASCII </a> para referência. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uso de códigos de integração para fontes de dados globais compartilhadas </p> </td> 
   <td colname="col2"> <p>Você pode usar códigos de integração para suas próprias fontes de dados e para <a href="../features/datasources-list-and-settings.md#settings-menu-options"> fontes de dados compartilhadas</a> globais, às quais você tem acesso. Por exemplo, você pode usar códigos de integração ao trabalhar com fontes de dados de identificadores móveis. Use os seguintes códigos de integração, exatamente como especificado abaixo: </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>DSID_20914</b> para GAID, representando dispositivos que executam o sistema operacional Android. </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>DSID_20915</b> para IDFA, representando dispositivos que executam o sistema operacional iOS. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>
