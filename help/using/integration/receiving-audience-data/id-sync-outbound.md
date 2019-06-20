---
description: Descreve a sintaxe e os parâmetros usados na chamada HTTP inicial para sincronizar as IDs de usuário entre o Audience Manager e um provedor de dados de terceiros. Entre em contato com o consultor do Adobe Audience Manager antes de tentar a primeira sincronização de ID.
seo-description: Descreve a sintaxe e os parâmetros usados na chamada HTTP inicial para sincronizar as IDs de usuário entre o Audience Manager e um provedor de dados de terceiros. Entre em contato com o consultor do Adobe Audience Manager antes de tentar a primeira sincronização de ID.
seo-title: Sincronização de ID para transferências de dados de saída
solution: Audience Manager
title: Sincronização de ID para transferências de dados de saída
uuid: f 3849 be 8-1094-47 db -9296-7482 f 020 af 18
translation-type: tm+mt
source-git-commit: e206d3a3cba259dc215f2f4190c9b4e03264f080

---


# ID Synchronization for Outbound Data Transfers{#id-synchronization-for-outbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between Audience Manager and a third-party data provider. Entre em contato com o consultor do Adobe Audience Manager antes de tentar a primeira sincronização de ID.

<!-- c_id_sync_out.xml -->

## Finalidade da sincronização de ID

A sincronização de ID é a primeira etapa do processo de transferência de dados assíncrono e assíncrono. In this step, [!DNL Audience Manager] and the vendor compare and match IDs for their respective site visitors. For example, an [!DNL Audience Manager] customer may know a user by ID 123. No entanto, seu parceiro de dados pode identificar esse usuário com a ID 456. The synchronization process allows [!DNL Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL Audience Manager] and the third-party data provider should have corresponding IDs for each unique user seen on our networks.

## Sintaxe do URL

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## Parâmetros de URL

The [!DNL URL] for your inbound ID synchronization call should contain variables described in the table below.

>[!NOTE]
>
>Substitua o conteúdo itálico por valores de parâmetro reais.

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; PROVIDER_ ID &gt;</i></code> </td> 
   <td colname="col2">Unique ID for the data provider (assigned by <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; PROVIDER_ UUID &gt;</i></code> </td> 
   <td colname="col2"> ID de usuário exclusiva. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; REDIRECT_ URL &gt;</i></code> </td> 
   <td colname="col2">An encoded URL redirect with the macro <code> ${DD_UUID}</code> embedded within it. <p><b>Observação:</b> Adicionado apenas quando o provedor de dados inicia a chamada. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code><i>rog= &lt; 0|1 &gt;</i></code> </td> 
   <td colname="col2"> <p><code>pode</code> ser 0 (RGPD não se aplica) ou 1 (o RGPD se aplica).</p><p><b>Observação:</b> <ul><li>The <code>gdpr</code> and <code>gdpr_consent</code> parameters are being gradually rolled out in ID sync URLs with activation partners. See Activation partners that support IAB TCF in <a href="../../overview/aam-gdpr/aam-iab-plugin.md#aam-activation-partners">Audience Manager Plug-in for IAB TCF.</a></li><li>This parameter can only be used together with <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>ggb_ approval = &lt; STRING STRING &gt;</i></code> </td> 
   <td colname="col2"><p><code>ropr_ approval</code> é a sequência de consentimento de RGPD com base em URL segura para URL (consulte <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> especificação IAB</a>).</p><p><b>Observação:</b> Esse parâmetro só pode ser usado junto <code>com o rgpd.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Métodos e código da API do servidor de coleta de dados (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Componentes da coleção de dados](../../reference/system-components/components-data-collection.md)

