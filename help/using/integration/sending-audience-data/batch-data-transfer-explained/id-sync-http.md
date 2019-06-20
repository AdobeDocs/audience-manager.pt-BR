---
description: Descreve a sintaxe e os parâmetros usados na chamada HTTP inicial para sincronizar as IDs do usuário entre um fornecedor e o Audience Manager. A sincronização de ID pode começar depois de enviar a taxonomia de dados para o Audience Manager.
seo-description: Descreve a sintaxe e os parâmetros usados na chamada HTTP inicial para sincronizar as IDs do usuário entre um fornecedor e o Audience Manager. A sincronização de ID pode começar depois de enviar a taxonomia de dados para o Audience Manager.
seo-title: Sincronização de ID para transferências de dados de entrada
solution: Audience Manager
title: Sincronização de ID para transferências de dados de entrada
uuid: 037 e 74 a 6-acfd -4 cef-b 693-16 b 7 aaa 8 e 976
translation-type: tm+mt
source-git-commit: 0fac081c93be36d2aa40023c7323ef1886b3860a

---


# ID Synchronization for Inbound Data Transfers{#id-synchronization-for-inbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between a vendor and Audience Manager. A sincronização de ID pode começar depois de enviar a taxonomia de dados para o Audience Manager.

<!-- c_id_sync_in.xml -->

A sincronização de ID é a primeira etapa no processo de transferência de dados assíncronos e assíncronos. Nesta etapa, o Audience Manager e o fornecedor comparam e combinam IDs para seus respectivos visitantes do site. For example, an [!DNL Audience Manager] customer may know a user by ID 123. No entanto, seu parceiro de dados pode identificar esse usuário com a ID 456. The synchronization process allows [!DNL Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL Audience Manager] and your third-party partner should have corresponding IDs for each unique user seen on our networks.

You can use the following methods to get your data into [!DNL Audience Manager]:

* [Solicitação HTTP de sincronização de ID](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Evento de ID declarada](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [Sincronização de ID de uma imagem incorporada por email](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID Synchronization `HTTP` Request {#id-sync-http}

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

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
  <tr> 
   <td colname="col1"> <code><i>&lt; PROVIDER_ ID &gt;</i></code> </td> 
   <td colname="col2"> <p>Unique ID for the content provider (assigned by <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; PROVIDER_ UUID &gt;</i></code> </td> 
   <td colname="col2"> <p>Representação codificada de URL (Porcentagem) de sua ID de usuário exclusiva. Além de codificar caracteres ASCII reservados, qualquer caractere não ASCII deve ser codificado por porcentagem com base na tabela de codificação de caracteres UTF -8. </p> <p>For more information, see the <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online</a> website. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; REDIRECT_ URL &gt;</i></code> </td> 
   <td colname="col2"> <p>An encoded URL redirect with the macro <code> ${DD_UUID}</code> embedded within it. </p> <p>Observação: Adicionado apenas quando o provedor de conteúdo inicia a chamada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>rog= &lt; 0|1 &gt;</i></code> </td> 
   <td colname="col2"> <p>Opcional. Add this parameter if you are using the <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code> pode</code> ser 0 (RGPD não se aplica) ou 1 (o RGPD se aplica). </p> <p> <b>Observação:</b> Esse parâmetro só pode ser usado juntamente <code>com o rgpd_ consentimento</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>ggb_ approval = &lt; STRING STRING &gt;</i></code> </td> 
   <td colname="col2"> <p>Opcional. Add this parameter if you are using the <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code>ropr_ approval</code> é a sequência de consentimento de RGPD com base em URL segura para URL (consulte <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> especificação IAB</a>). </p> <p> <b>Observação:</b> Esse parâmetro só pode ser usado junto <code>com o rgpd.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

## Declared ID Event {#declared-id-event}

For more information, see [Declared IDs](../../../features/declared-ids.md).

## ID Synchronization From an Email Embedded Image {#id-sync-email-image}

O formato para correspondência de IDs por uma imagem de email é o mesmo mostrado acima. No entanto, observe que as imagens em um email devem estar ativadas para que isso funcione. Isso pode afetar a sincronização de ID por email, pois a maioria dos sistemas de email desativa as imagens por padrão.

>[!MORE_ LIKE_ THIS]
>
>* [Componentes da coleção de dados](../../../reference/system-components/components-data-collection.md)

