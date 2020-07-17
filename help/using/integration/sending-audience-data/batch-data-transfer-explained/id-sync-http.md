---
description: Descreve a sintaxe e os parâmetros usados na chamada HTTP inicial para sincronizar IDs de usuário entre um fornecedor e um Audience Manager. A sincronização de ID pode começar depois de enviar a taxonomia de dados para a Audience Manager.
seo-description: Descreve a sintaxe e os parâmetros usados na chamada HTTP inicial para sincronizar IDs de usuário entre um fornecedor e um Audience Manager. A sincronização de ID pode começar depois de enviar a taxonomia de dados para a Audience Manager.
seo-title: Sincronização de ID para transferências de dados de entrada
solution: Audience Manager
title: Sincronização de ID para transferências de dados de entrada
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 9%

---


# Sincronização de ID para transferências de dados de entrada {#id-synchronization-for-inbound-data-transfers}

Descreve a sintaxe e os parâmetros usados na `HTTP` chamada inicial para sincronizar IDs de usuário entre um fornecedor e [!DNL Audience Manager]. A sincronização de ID pode começar depois de enviar a taxonomia de dados para [!DNL Audience Manager].

A sincronização de ID é a primeira etapa do processo de transferência de dados assíncrono de entrada. Nesta etapa, [!DNL Audience Manager] e o fornecedor compara e corresponde IDs para os respectivos visitantes do site. Por exemplo, um [!DNL Audience Manager] cliente pode conhecer um usuário pela ID 123. No entanto, seu parceiro de dados pode identificar esse usuário com a ID 456. O processo de sincronização permite que um fornecedor [!DNL Audience Manager] de dados reconcilie essas diferentes IDs e identifique usuários em seus respectivos sistemas. Após a conclusão, [!DNL Audience Manager] e seu parceiro de terceiros deve ter IDs correspondentes para cada usuário único visto em nossas redes.

Você pode usar os seguintes métodos para inserir seus dados [!DNL Audience Manager]:

* [Solicitação HTTP de Sincronização de ID](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Evento de ID declarado](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [Sincronização de ID a partir de uma imagem incorporada por email](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## Solicitação de sincronização de ID `HTTP` {#id-sync-http}

Em uma troca de ID, uma [!DNL URL] string formatada corretamente deve ser semelhante a:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

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
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>ID exclusiva do provedor de conteúdo (atribuída por <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>URL (Porcentagem) Representação codificada da ID de usuário exclusiva. Além da codificação de caracteres ASCII reservados, todos os caracteres não ASCII devem ser codificados por porcentagem com base na tabela de codificação de caracteres UTF-8. </p> <p>Para obter mais informações, consulte o site Codificar/Decodificar <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL online</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>Um redirecionamento de URL codificado com a macro <code> ${DD_UUID}</code> incorporada. </p> <p>Observação:  Adicionado somente quando o provedor de conteúdo inicia a chamada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>Opcional. Adicione esse parâmetro se estiver usando o Plug-in <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager para IAB TCF.</a></p> <p><code> gdpr</code> pode ser 0 (o GDPR não se aplica) ou 1 (o GDPR se aplica). </p> <p> <b>Observação:</b> Esse parâmetro só pode ser usado junto com <code>gdpr_consent</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>Opcional. Adicione esse parâmetro se estiver usando o Plug-in <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager para IAB TCF.</a></p> <p><code>gdpr_consent</code> is the URL-safe base64-encoded GDPR consent string (see <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB specification</a>). </p> <p> <b>Observação:</b> Esse parâmetro só pode ser usado junto com <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Evento {#declared-id-event}

Para obter mais informações, consulte IDs [declaradas](../../../features/declared-ids.md).

## Sincronização de ID a partir de uma imagem incorporada por email {#id-sync-email-image}

O formato para IDs correspondentes por meio de uma imagem de email é o mesmo mostrado acima. Observe, no entanto, que as imagens em um email devem ser ativadas para que isso funcione. Isso pode afetar a sincronização de ID por email, pois a maioria dos sistemas de email desativa as imagens por padrão.

>[!MORELIKETHIS]
>
>* [Componentes da coleção de dados](../../../reference/system-components/components-data-collection.md)

