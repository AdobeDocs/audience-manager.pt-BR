---
description: O processo de transferência de dados em tempo real de saída retorna os dados do usuário como uma série de objetos JSON passados com um método POST.
seo-description: O processo de transferência de dados em tempo real de saída retorna os dados do usuário como uma série de objetos JSON passados com um método POST.
seo-title: Transferências de dados de saída em tempo real
solution: Audience Manager
title: Transferências de dados de saída em tempo real
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: b76e905ec890dbe8270177d142dddb351438b039

---


# Real-Time Outbound Data Transfers {#real-time-outbound-data-transfers}

O processo de transferência de dados em tempo real de saída fornece dados do usuário como uma série de mensagens [!DNL JSON] formatadas para uma plataforma de destino.

<!-- c_outbound_json.xml -->

## Recomendações  

To use this method, the destination platform must meet the following requirements:

* It must provide an endpoint  that can scale to receive a high volume of messages from Audience Manager;[!DNL URL]
* It must accept data in  format ();[!DNL JSON]`Content-type: application/json`
* It must accept secure  data transfers. `HTTPS` [!DNL Audience Manager] will not send messages through the unsecure  protocol.`HTTP`

## Frequência

Esse método de transferência de dados pode enviar dados em tempo quase real, à medida que os usuários se qualificam para segmentos. Real-time messages are only delivered while the user is online and actively visible to the Audience Manager Edge network. Como opção, esse método também pode enviar lotes de dados offline ou integrados com a mesma frequência a cada 24 horas.

## Transferências em lote

As transferências em tempo real e em lote são enviadas para o mesmo terminal e usam o mesmo formato de mensagem. When batch transfers are enabled, the destination platform will see a spike in message volume while the batch messages are delivered. Muitas das qualificações de segmento enviadas por mensagens em tempo real serão repetidas nas mensagens em lote. As transferências em lote incluirão apenas as qualificações de segmento (ou inqualificações) que foram alteradas desde que o último lote foi entregue.

## Limites de taxa

Não há limites de taxa definidos na saída de mensagens entregues. A definição de limites de taxa pode levar à perda de dados.

## Respostas Obrigatórias

Por padrão, o servidor destinatário deve retornar o `200 OK` código para indicar o recebimento bem-sucedido. Outros códigos serão interpretados como falhas. Esta resposta é esperada dentro de 3000 milissegundos. Em resposta a uma falha, [!DNL Audience Manager] fará apenas uma tentativa.

## Parâmetros

A tabela a seguir define os elementos no arquivo de [!DNL JSON] dados retornado.

<table id="table_68475F9D01ED4A44B5909234114AEDE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Tipo de dados </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>ProcessTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Hora em que a solicitação foi executada. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>Número inteiro </p> </td> 
   <td colname="col3"> <p>Uma ID que indica o tipo de IDs de dispositivo contidas na mensagem, na propriedade User.DataPartner_UUID. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">IDs do Android (GAID): <code> 2014</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">IDs do iOS (IDFA): <code> 2015</code> </li>
     <li>IDs da Web/Cookie: varia de acordo com a plataforma de destino</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Representa a conta de destino na plataforma de destino. Essa ID é originária da plataforma de destino.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>Número inteiro </p> </td> 
   <td colname="col3"> <p>The ID of the Audience Manager “destination” object. This ID originates from Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Número inteiro </p> </td> 
   <td colname="col3"> <p>Total number of users in the  POST request.<code></code> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Usuários</i></code> </td> 
   <td colname="col2"> <p>Matriz </p> </td> 
   <td colname="col3"> <p>An array of user objects. Por padrão, cada mensagem conterá entre 1 e 10 usuários, para manter o tamanho da mensagem ótimo. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>O <span class="keyword"> Audience Manager</span> UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>UUID da plataforma de destino ou a ID do dispositivo global. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> Matriz </td> 
   <td colname="col3"> A ID da região do <span class="keyword"> Audience Manager</span> onde vimos este dispositivo. For instance, if the device had some activity in Paris (Europe), the region ID would be  6. <code></code> Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">IDs da região do DCS, locais e nomes de host</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmentos</i></code> </td> 
   <td colname="col2"> <p>Matriz </p> </td> 
   <td colname="col3"> <p>An array of segment objects. For real-time messages, the array contains all of the segments the user belongs to. For batch messages, the array contains only segment changes since the last batch.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Número inteiro </p> </td> 
   <td colname="col3"> <p>The identifier for the segment. In most cases, this is the segment ID generated by Audience Manager (an integer). In some cases, if the destination platform allows, customers can define the segment identifier in the Audience Manager UI (open text field), which would then reflect in this property. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>Número inteiro </p> </td> 
   <td colname="col3"> <p>Define o status de um usuário no segmento. Aceita os seguintes valores: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Ativo (padrão) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inativo, excluído ou não segmentado. </li> 
    </ul> <p>Os usuários não são segmentados quando: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Removido de um segmento com base na regra de segmento. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Removido de um segmento com base no intervalo <a href="../../../features/traits/segment-ttl-explained.md"></a>de tempo para vida do segmento. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Movido para um estado inativo se não tiver sido visto nos últimos 120 dias. </li>
     <li>Removido devido a uma solicitação de alteração de privacidade (isto é, [!DNL GDPR])</li>
    </ul> <p>Todas as IDs de parceiro sincronizadas com uma ID do <span class="keyword"> Audience Manager</span> receberão o sinalizador <code> "Status":"0"</code> quando um usuário não estiver segmentado. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>A hora em que a qualificação do segmento de usuário foi verificada recentemente.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Segurança

Você pode proteger seu processo de transferência de dados de saída em tempo real [assinando solicitações](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) HTTP usando chaves privadas ou [!DNL Audience Manager] autenticando pelo protocolo [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) .

## Solicitação

Uma solicitação em tempo real pode ser semelhante ao seguinte:

```js
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{  
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         },
         {
            "Segment_ID": "12176",
            "Status": "0",  
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   },
   {
   "AAM_UUID": "0578240750487542456854736923319946899715232",
   "DataPartner_UUID": "848457757347734",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "10329",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
         },
         {
            "Segment_ID": "23954",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
        }]
    }]
}
```
