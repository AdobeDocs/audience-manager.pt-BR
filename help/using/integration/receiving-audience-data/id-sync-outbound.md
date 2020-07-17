---
description: Descreve a sintaxe e os parâmetros usados na chamada HTTP inicial para sincronizar IDs de usuário entre o Audience Manager e um provedor de dados de terceiros. Entre em contato com seu consultor de Adobe Audience Manager antes de tentar a primeira sincronização de ID.
seo-description: Descreve a sintaxe e os parâmetros usados na chamada HTTP inicial para sincronizar IDs de usuário entre o Audience Manager e um provedor de dados de terceiros. Entre em contato com seu consultor de Adobe Audience Manager antes de tentar a primeira sincronização de ID.
seo-title: Sincronização de ID para transferências de dados de saída
solution: Audience Manager
title: Sincronização de ID para transferências de dados de saída
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 14%

---


# Sincronização de ID para transferências de dados de saída{#id-synchronization-for-outbound-data-transfers}

Descreve a sintaxe e os parâmetros usados na `HTTP` chamada inicial para sincronizar IDs de usuário entre o Audience Manager e um provedor de dados de terceiros. Entre em contato com seu consultor de Adobe Audience Manager antes de tentar a primeira sincronização de ID.

<!-- c_id_sync_out.xml -->

## Finalidade da sincronização de ID

A sincronização de ID é a primeira etapa do processo de transferência de dados assíncrono de saída. Nesta etapa, [!DNL Audience Manager] e o fornecedor compara e corresponde IDs para os respectivos visitantes do site. Por exemplo, um [!DNL Audience Manager] cliente pode conhecer um usuário pela ID 123. No entanto, seu parceiro de dados pode identificar esse usuário com a ID 456. O processo de sincronização permite que um fornecedor [!DNL Audience Manager] de dados reconcilie essas diferentes IDs e identifique usuários em seus respectivos sistemas. Após a conclusão, [!DNL Audience Manager] e o provedor de dados de terceiros deve ter IDs correspondentes para cada usuário único visto em nossas redes.

## Sintaxe de URL

Em uma troca de ID, uma [!DNL URL] string formatada corretamente deve ser semelhante a:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## Parâmetros de URL

A chamada [!DNL URL] de sincronização de ID de entrada deve conter variáveis descritas na tabela abaixo.

>[!NOTE]
>
>Substitua o conteúdo em itálico por valores de parâmetro reais.

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
   <td colname="col2">ID exclusiva do provedor de dados (atribuída por <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> ID exclusiva do usuário. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">Um redirecionamento de URL codificado com a macro <code> ${DD_UUID}</code> incorporada. <p><b>Observação:</b> Adicionado somente quando o provedor de dados inicia a chamada. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> pode ser 0 (o GDPR não se aplica) ou 1 (o GDPR se aplica).</p><p><b>Observação:</b> <ul><li>Os parâmetros <code>gdpr</code> e <code>gdpr_consent</code> estão sendo implantados gradualmente em URLs de sincronização de ID com parceiros de ativação. Consulte Parceiros de Ativação que suportam IAB TCF no Plug-in <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">Audience Manager para IAB TCF.</a></li><li>Esse parâmetro só pode ser usado junto com <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> is the URL-safe base64-encoded GDPR consent string (see <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB specification</a>).</p><p><b>Observação:</b> Esse parâmetro só pode ser usado junto com <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Métodos e código API do Data Collection Server (DCS) ](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Componentes da coleção de dados](../../reference/system-components/components-data-collection.md)

