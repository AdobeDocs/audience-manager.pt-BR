---
description: Descreve a sintaxe e os parâmetros usados na chamada HTTP inicial para sincronizar IDs de usuário entre o Audience Manager e um provedor de dados de terceiros. Entre em contato com o consultor da Adobe Audience Manager antes de tentar a primeira sincronização de ID.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between Audience Manager and a third-party data provider. Contact your Adobe Audience Manager consultant before attempting your first ID synchronization.
seo-title: ID Synchronization for Outbound Data Transfers
solution: Audience Manager
title: Sincronização de ID para transferências de dados de saída
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
exl-id: 02cca19a-eebf-43b2-b034-24f072fe2efb
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 2%

---

# Sincronização de ID para transferências de dados de saída{#id-synchronization-for-outbound-data-transfers}

Descreve a sintaxe e os parâmetros usados na chamada inicial `HTTP` para sincronizar IDs de usuário entre o Audience Manager e um provedor de dados de terceiros. Entre em contato com o consultor da Adobe Audience Manager antes de tentar a primeira sincronização de ID.

<!-- c_id_sync_out.xml -->

## Finalidade da sincronização de ID

A sincronização de ID é a primeira etapa do processo de transferência de dados assíncrono de saída. Nesta etapa, [!DNL Audience Manager] e o fornecedor comparam e correspondem IDs para os respectivos visitantes do site. Por exemplo, um cliente [!DNL Audience Manager] pode conhecer um usuário pela ID 123. No entanto, o parceiro de dados pode identificar esse usuário com a ID 456. O processo de sincronização permite que o [!DNL Audience Manager] e um fornecedor de dados reconcilie essas diferentes IDs e identifique usuários em seus respectivos sistemas. Uma vez concluído, o [!DNL Audience Manager] e o provedor de dados de terceiros devem ter IDs correspondentes para cada usuário único visto em nossas redes.

## Sintaxe do URL

Em uma troca de ID, uma cadeia de caracteres [!DNL URL] formatada corretamente deve ter esta aparência:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## Parâmetros de URL

O [!DNL URL] da chamada de sincronização de ID de entrada deve conter variáveis descritas na tabela abaixo.

>[!NOTE]
>
>Substitua o conteúdo em itálico pelos valores reais do parâmetro.

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">Identificador exclusivo do provedor de dados (atribuído por <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> ID exclusiva do usuário. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">Um redirecionamento de URL codificado com a macro <code> ${DD_UUID}</code> incorporada. <p><b>Observação:</b> adicionada somente quando o provedor de dados inicia a chamada. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> pode ser 0 (o GDPR não se aplica) ou 1 (o GDPR se aplica).</p><p><b>Observação:</b> <ul><li>Os parâmetros <code>gdpr</code> e <code>gdpr_consent</code> estão sendo gradualmente implantados em URLs de sincronização de ID com parceiros de ativação. Consulte Parceiros de ativação que oferecem suporte à TCF do IAB no <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">Plug-in de Audience Manager para a TCF do IAB.</a></li><li>Este parâmetro só pode ser usado junto com <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> é a cadeia de consentimento do GDPR com codificação base64 segura para URL (consulte <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> especificação do IAB</a>).</p><p><b>Observação:</b> este parâmetro só pode ser usado com <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Métodos API e código DCS (Data Collection Server)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Componentes da coleção de dados](../../reference/system-components/components-data-collection.md)
