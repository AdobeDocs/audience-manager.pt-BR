---
description: O processo de transferência de dados em tempo real externo retorna os dados do usuário como uma série de objetos JSON passados com um método POST.
seo-description: O processo de transferência de dados em tempo real externo retorna os dados do usuário como uma série de objetos JSON passados com um método POST.
seo-title: Transferências de dados de saída em tempo real
solution: Audience Manager
title: Transferências de dados de saída em tempo real
uuid: 1895 e 818-7 ab 8-4569-a 920-4 b 0 a 4 c 8 b 83 d 2
translation-type: tm+mt
source-git-commit: 425315a0a6aa739a90e34deb270ac21df9b88d31

---


# Transferências de dados de saída em tempo real {#real-time-outbound-data-transfers}

O processo de transferência de dados em tempo real externo retorna os dados do usuário como uma série [!DNL JSON] de objetos passados com um `POST` método.

<!-- c_outbound_json.xml -->

## Recomendações  

Para usar este método, recomendamos que seu parceiro de dados:

* Aceita dados no [!DNL JSON] formato.
* Fornece um URL que pode ser usado pela `POST` chamada para retornar dados.
* Aceita transferências de `HTTPS` dados seguras. [!DNL Audience Manager] não enviará este arquivo com `HTTP` o protocolo inseguro.

## Frequência

Esse método de transferência de dados pode enviar dados em tempo próximo à medida que os usuários se qualificam para segmentos. Além disso, esse método pode enviar lotes de dados offline ou integrados com frequência a cada 24 horas.

## Respostas obrigatórias

Por padrão, o servidor do destinatário deve retornar `200 OK` o código para indicar o recibo bem-sucedido. Outros códigos serão interpretados como falhas. Essa resposta é esperada dentro de 3000 milissegundos. Em resposta a uma falha, [!DNL Audience Manager] fará uma tentativa de tentativa 1.

## Parâmetros

A tabela a seguir define os elementos no arquivo [!DNL JSON] de dados retornado.

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
   <td colname="col1"> <code><i>Processtime</i></code> </td> 
   <td colname="col2"> <p>Datetime </p> </td> 
   <td colname="col3"> <p>Hora em que a solicitação foi executada. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_ DPID</i></code> </td> 
   <td colname="col2"> <p>Número inteiro </p> </td> 
   <td colname="col3"> <p>Uma ID que indica se o arquivo contém IDs do Android ou iOS. Usa os seguintes valores de ID: </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">IDs do Android (GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">IDs do iOS (IDFA): <code> 20915</code> </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ ID</i></code> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>ID do cliente usada pelo sistema para o qual você está enviando dados. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ Destination_ ID</i></code> </td> 
   <td colname="col2"> <p>Número inteiro </p> </td> 
   <td colname="col3"> <p>A ID atribuída a você pelo seu parceiro de destino. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_ count</i></code> </td> 
   <td colname="col2"> <p>Número inteiro </p> </td> 
   <td colname="col3"> <p>O número total de usuários na solicitação <code> POST</code> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Usuários</i></code> </td> 
   <td colname="col2"> <p>Matriz </p> </td> 
   <td colname="col3"> <p>Uma matriz de objetos do usuário. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ UUID</i></code> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>O UUID <span class="keyword"> do Audience Manager</span> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Datapartner_ UUID</i></code> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>UUID do parceiro de dados. Deixe em branco se seu parceiro de dados não tiver um UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ Regions</i></code> </td> 
   <td colname="col2"> Matriz </td> 
   <td colname="col3"> A ID da região <span class="keyword"> do Audience Manager</span> , onde já vimos este dispositivo. Por exemplo, se o dispositivo tinha alguma atividade em Paris (Europa), a ID da região seria <code> 6</code>. Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">IDs da região do DCS, locais e nomes de host</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmentos</i></code> </td> 
   <td colname="col2"> <p>Matriz </p> </td> 
   <td colname="col3"> <p>Uma matriz de objetos de segmento. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment_ ID</i></code> </td> 
   <td colname="col2"> <p>Número inteiro </p> </td> 
   <td colname="col3"> <p>O mapeamento de destino da ID do segmento. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Status</i></code> </td> 
   <td colname="col2"> <p>Número inteiro </p> </td> 
   <td colname="col3"> <p>Define o status de um usuário no segmento. Aceita o seguinte: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Ativo (padrão) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inativo, cancelado ou não segmentado. </li> 
    </ul> <p>Os usuários não são segmentados quando são: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Removido de um segmento com base na regra de segmento. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Removido de um segmento com base no intervalo <a href="../../../features/traits/segment-ttl-explained.md"> de tempo para live do segmento</a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Movido para um estado inativo se eles não tiverem sido vistos nos últimos 120 dias. </li> 
    </ul> <p>Todas as IDs de parceiro sincronizadas com uma <span class="keyword"> ID do Audience Manager</span> receberão o <code> "Status": Sinalizador "0"</code> quando um usuário não está segmentado. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Datetime</i></code> </td> 
   <td colname="col2"> <p>Datetime </p> </td> 
   <td colname="col3"> <p>A hora da qualificação de segmento mais recente.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Segurança

Você pode proteger o processo de transferência de dados de saída em tempo real [assinando solicitações](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) HTTP usando chaves privadas ou fazendo [!DNL Audience Manager] autenticação por meio do [protocolo oauth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) .

## Amostra de código

Uma resposta de dados em tempo real pode ser semelhante ao seguinte:

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
