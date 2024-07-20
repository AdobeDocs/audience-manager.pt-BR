---
description: O processo de transferência de dados de saída em tempo real retorna os dados do usuário como uma série de objetos JSON transmitidos com um método POST.
seo-description: The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.
seo-title: Real-Time Outbound Data Transfers
solution: Audience Manager
title: Transferências de dados de saída em tempo real
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
feature: Outbound Data Transfers
exl-id: 12aee831-1a44-4cd6-aeba-7738a584dfe7
source-git-commit: 0245dd11de31c3139c5df5dc78100f0d3935aa2e
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 2%

---

# Transferências de dados de saída em tempo real {#real-time-outbound-data-transfers}

O processo de transferência de dados em tempo real de saída fornece dados do usuário como uma série de [!DNL JSON] mensagens formatadas para uma plataforma de destino.

<!-- c_outbound_json.xml -->

## Recomendações  

Para usar esse método, a plataforma de destino deve atender aos seguintes requisitos:

* Ele deve fornecer um ponto de extremidade [!DNL URL] que possa ser dimensionado para receber um grande volume de mensagens do Audience Manager;
* Deve aceitar dados no formato [!DNL JSON] (`Content-type: application/json`);
* Ele deve aceitar transferências de dados `HTTPS` seguras. [!DNL Audience Manager] não enviará mensagens por meio do protocolo `HTTP` não seguro.

## Frequência

Esse método de transferência de dados pode enviar dados em tempo quase real, à medida que os usuários se qualificam para segmentos. As mensagens em tempo real só são entregues enquanto o usuário está online e ativamente visível para a rede Audience Manager Edge. Como opção, esse método também pode enviar lotes de dados offline ou integrados com a mesma frequência a cada 24 horas.

## Transferências em lote

As transferências em tempo real e em lote são enviadas para o mesmo endpoint e usam o mesmo formato de mensagem. Quando as transferências em lote estiverem ativadas, a plataforma de destino verá um pico no volume de mensagens enquanto as mensagens em lote forem entregues. Muitas das qualificações de segmento enviadas por mensagens em tempo real serão repetidas nas mensagens em lote. As transferências em lote incluirão apenas as qualificações de segmento (ou não qualificações) que foram alteradas desde que o último lote foi entregue.

## Limites de taxa

Não há limites de taxa definidos na taxa de transferência das mensagens entregues. A definição de limites de taxa pode levar à perda de dados.

## Respostas necessárias

Por padrão, o servidor de destinatários deve retornar o código `200 OK` para indicar um recebimento bem-sucedido. Outros códigos serão interpretados como falhas. Essa resposta é esperada em 3000 milissegundos. Em resposta a uma falha, [!DNL Audience Manager] fará apenas uma nova tentativa.

## Parâmetros

A tabela a seguir define os elementos do arquivo de dados [!DNL JSON] que você envia para o destino.

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
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">IDs do Android (GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">IDs do iOS (IDFA): <code> 20915</code> </li>
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
   <td colname="col3"> <p>A ID do objeto "destination" do Audience Manager. Essa ID é originária do Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Número inteiro </p> </td> 
   <td colname="col3"> <p>Número total de usuários na solicitação <code> POST</code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>Matriz </p> </td> 
   <td colname="col3"> <p>Uma matriz de objetos do usuário. Por padrão, cada mensagem conterá entre 1 e 10 usuários, para manter o tamanho ideal da mensagem. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>A UUID Audience Manager</span> <span class="keyword">. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>UUID da plataforma de destino ou ID do dispositivo global. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> Matriz </td> 
   <td colname="col3"> A ID da região do Audience Manager <span class="keyword"> </span> em que vimos este dispositivo. Por exemplo, se o dispositivo tivesse alguma atividade em Paris (Europa), a ID da região seria <code> 6</code>. Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md"> IDs da região do DCS, locais e nomes de host</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>Matriz </p> </td> 
   <td colname="col3"> <p>Uma matriz de objetos de segmento. Para mensagens em tempo real, a matriz contém todos os segmentos aos quais o usuário pertence. Para mensagens em lote, a matriz contém somente alterações de segmento desde o último lote.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Número inteiro </p> </td> 
   <td colname="col3"> <p>O identificador do segmento. Na maioria dos casos, essa é a ID de segmento gerada pelo Audience Manager (um número inteiro). Em alguns casos, se a plataforma de destino permitir, os clientes poderão definir o identificador de segmento na interface do usuário do Audience Manager (campo de texto aberto), que será refletido nessa propriedade. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>Número inteiro </p> </td> 
   <td colname="col3"> <p>Define o status de um usuário no segmento. Aceita os seguintes valores: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Ativo (padrão) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: inativo, recusa ou não segmentado. </li> 
    </ul> <p>Os usuários não são segmentados quando: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Removido de um segmento com base na regra de segmento. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Removido de um segmento com base no <a href="../../../features/traits/segment-ttl-explained.md"> intervalo de vida útil</a> do segmento. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Movido para um estado inativo se não tiver sido visto nos últimos 120 dias. </li>
     <li>Removido devido a uma solicitação de alteração de privacidade (ou seja, <span class="keyword"> GDPR</span>)</li>
    </ul> <p>Todas as IDs de parceiros sincronizadas com uma ID de Audience Manager</span> do <span class="keyword"> receberão o sinalizador <code> "Status":"0"</code> quando um usuário não estiver segmentado. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>A hora em que a qualificação do segmento de usuário foi verificada mais recentemente.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Segurança

Você pode proteger seu processo de transferência de dados de saída em tempo real [assinando solicitações HTTP](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) com chaves privadas ou fazendo com que o [!DNL Audience Manager] seja autenticado por meio do protocolo [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md).

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
