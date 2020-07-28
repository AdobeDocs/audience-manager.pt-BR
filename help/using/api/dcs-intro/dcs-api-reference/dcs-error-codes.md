---
description: Códigos de erro e mensagens geradas pelos servidores de coleta de dados (DCS) listados em ordem numérica por ID de código.
seo-description: Códigos de erro e mensagens geradas pelos servidores de coleta de dados (DCS) listados em ordem numérica por ID de código.
seo-title: Códigos de erros, mensagens e exemplos de DCS
solution: Audience Manager
title: Códigos de erros, mensagens e exemplos de DCS
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
translation-type: tm+mt
source-git-commit: 11b79d46e7358c736c797bcf0809af4937717fc5
workflow-type: tm+mt
source-wordcount: '1518'
ht-degree: 4%

---


# Códigos de erros, mensagens e exemplos de DCS {#dcs-error-codes-messages-and-examples}

Códigos de erro e mensagens geradas pela [!UICONTROL Data Collection Servers] ([!DNL DCS]) listada em ordem numérica pela ID de código.

In the tables below, *italics* represents a variable placeholder.

## Códigos de erro do sistema {#system-error-codes}

| Código de erro | Mensagem de erro | Descrição |
|---|---|---|
| 0 | Erro não especificado | Este é um erro catch-all que manipula eventos que não são cobertos pelos outros manipuladores de erro. A solução de problemas desse erro é difícil. Pode ser causado por uma variedade de ações ou eventos desconhecidos. Se você receber esse erro, tente sua [!DNL DCS] solicitação novamente. Entre em contato com seu [!DNL Adobe] representante se o problema persistir. |
| 1 | Não foi possível localizar a configuração para o nome do host: `hostname` | O nome do host enviado na solicitação não foi configurado pela nossa equipe de provisionamento do parceiro. Entre em contato com seu [!DNL Adobe] representante se vir esta mensagem de erro. |
| 2 | Valor inválido `d_orgid` (não foi possível localizar uma configuração para esta ID de organização): `ID` | A ID da organização está incorreta. Verifique sua ID e tente a solicitação novamente. Se você não souber ou não possuir a ID da organização, consulte a seção &quot;Página de administração&quot; [Organizações e vinculação](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html) de contas para obter informações sobre como encontrá-la. |

## Códigos de erro de integração {#integration-error-codes}

| Código de erro | Mensagem de erro | Descrição |
|---|---|---|
| 100 | Não foi possível recuperar o nome do host para a solicitação | Uma [!DNL API] chamada não enviou o cabeçalho do host [!DNL HTTP] na solicitação. Adicione o cabeçalho do host à chamada e tente novamente. A maioria dos navegadores e [!DNL API] clientes faz isso automaticamente. |
| 101 | Id [!DNL Experience Cloud] inválida transmitida `ID` | A [!DNL DCS] chamada contém uma ID inválida [!DNL Experience Cloud] . Verifique o par de `d_mid=` chave-valor na string de cabeçalho. Verifique se você está transmitindo a ID [!DNL Experience Cloud] correta e tente a solicitação novamente. |
| 102 | Solicitação [!DNL AAM ID] transmitida inválida `ID` | A [!DNL DCS] chamada contém uma ID inválida [!DNL Audience Manager] . Verifique o par de `d_uuid=` chave-valor na string de cabeçalho. Verifique se você está transmitindo a ID [!DNL Audience Manager] correta e tente a solicitação novamente. |
| 104 | Todas as IDs do cliente são inválidas | Todas as IDs do cliente na sua chamada são inválidas. Verifique suas IDs e tente novamente. |
| 109 | Referenciador não `HTTP referer` permitido para parceiro `Partner ID` | O cabeçalho da `HTTP referer` chamada não é permitido para a ID do parceiro na chamada. Verifique se o `HTTP referer` cabeçalho está correto. |
| 111 | Token inválido recebido `IMS` | Retornado para [!DNL Audience Manager] - [!DNL Adobe Target] integrações. O erro é emitido quando uma chamada é feita para o [!DNL DCS], contendo um [!DNL IMS] token inválido. O token pode estar malformado, expirado ou o usuário pode não estar autorizado a acessar o recurso desejado. |

## Códigos de erro de não participação {#opt-out-error-codes}

<table id="table_A50C284AB84F48A79B01223D991884A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID do código </th> 
   <th colname="col2" class="entry"> Mensagem </th> 
   <th colname="col3" class="entry"> Descrição </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>171 </p> </td> 
   <td colname="col2"> <p>Tag opt out encontrada para id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Um cliente optou por não receber publicidade com base em juros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Cookies bloqueados </p> </td> 
   <td colname="col3"> <p>Retornado quando o navegador do usuário bloqueia cookies de terceiros.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Relação de confiança encontrada via <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>O usuário iniciou um processo de não participação por meio do NAI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>Solicitações deste país são bloqueadas pelo parceiro </p> </td> 
   <td colname="col3"> <p>Com base no endereço IP, o <span class="wintitle"> DCS</span> bloqueia solicitações de países onde o parceiro limitou deliberadamente o tráfego. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>Solicitações deste país não são permitidas </p> </td> 
   <td colname="col3"> <p>Com base no endereço IP, o <span class="wintitle"> DCS</span> bloqueia solicitações dos seguintes países: </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">Cuba (CU) </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">Irã (IR) </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">Coreia do Norte (KP) </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">Sudão (SD) </li> 
      <li id="li_0875540C20204158ADBD92698CEB10EA">Síria (SY) </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Códigos de erro de recuperação de Perfis {#profile-retrieval-error-codes}

<table id="table_CFF2252A3CC54960802905454A867D7A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID do código </th> 
   <th colname="col2" class="entry"> Mensagem </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>200 </p> </td> 
   <td colname="col2"> <p> Não é possível ler as características do cache de perfis para a ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando um perfil de usuário não pode ser lido de nosso armazenamento interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Não é possível ler as IDs do dispositivo do cache de perfis para a ID do cliente: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando a ID <a href="../../../reference/ids-in-aam.md"> do</a> dispositivo não pode ser recuperada para uma regra de mesclagem de Link de Perfil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Não é possível ler o cliente relacionado para a ID do dispositivo: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando a ID do <a href="../../../reference/ids-in-aam.md"> cliente (UUID)</a> associada a uma ID de dispositivo não pode ser recuperada para uma regra de mesclagem da última autenticação do nosso armazenamento interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Não é possível ler o cluster de dispositivos para a ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>As IDs de dispositivo vinculadas do mesmo cluster de gráficos de dispositivo não podem ser retornadas para essa ID de dispositivo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Não foi possível executar a migração porque a leitura do perfil falhou para o dispositivo primário </p> </td> 
   <td colname="col3"> <p>Se você receber esse erro, podemos estar enfrentando problemas de escalabilidade com nosso armazenamento de dados (<span class="wintitle"> PCS</span>). Entre em contato com seu representante de Adobe se o problema persistir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Não foi possível executar a migração de <code><i>ID</i></code> para <code><i>ID</i></code>, porque a leitura do perfil falhou para <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Se você receber esse erro, podemos estar enfrentando problemas de escalabilidade com nosso armazenamento de dados (<span class="wintitle"> PCS</span>). Entre em contato com seu representante de Adobe se o problema persistir. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Códigos de aviso de integração {#integration-warning-codes}

<table id="table_31F1593C46804DDBA2E9BEDE83F2417F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID do código </th> 
   <th colname="col2" class="entry"> Mensagem </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>300 </p> </td> 
   <td colname="col2"> <p>ID de cliente inválida <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>A ID do cliente é inválida (valores ausentes para a fonte de dados, códigos de integração ausentes, formato inválido para fontes de dados, ID do cliente bloqueada, ID do cliente em branco, tentativa de acesso não autorizado a uma fonte de dados que não pertence ao parceiro). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>O número máximo de IDs do cliente foi excedido. O máximo permitido é <code><i>maximum allowed</i></code>. Encontrado é <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>O número de IDs do cliente associadas a uma fonte de dados entre dispositivos excede o número permitido de IDs entre dispositivos por solicitação. Essas IDs incluem IDs de dispositivo, dispositivo móvel ou cookie. O limite está atualmente definido como 10. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>Id do cliente não autorizada <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando a fonte de dados da ID do cliente não é pertencente à ID da organização atual. Se você não souber ou não possuir a ID da organização, consulte a seção "Localizar a ID da organização" em <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organizações e vinculação</a> de contas para obter informações sobre como encontrá-la. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>ID do cliente bloqueado <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando a ID do cliente foi identificada como mal-intencionada e adicionada a uma lista de bloqueios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>ID da fonte de dados bloqueada <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando a ID da fonte de dados foi identificada como mal-intencionada e adicionada a uma lista de bloqueios </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>ID de dispositivo declarada bloqueada <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>A ID do dispositivo foi identificada como mal-intencionada e adicionada a uma lista de bloqueios. Isso pode ocorrer quando recebemos uma quantidade extrema de solicitações <span class="wintitle"> DCS</span> contendo essa ID do dispositivo em um curto período de tempo. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Operação de perfil bloqueada para <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Uma ação de leitura/gravação foi bloqueada porque uma ID foi identificada como mal-intencionada e adicionada a uma lista de bloqueios Consulte o código de erro 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>A ID do cliente <code><i>ID</i></code> foi descartada porque excedeu o limite de IDs do cliente declaradas por solicitação </p> </td> 
   <td colname="col3"> <p>Relacionado ao erro 301. Esse erro especifica qual ID do cliente foi descartada porque o limite foi excedido. </p> <p>Por exemplo, se houver 12 IDs de cliente declaradas na chamada <span class="wintitle"> DCS</span> , duas delas serão descartadas. Para retransmitir quais foram descartados, esse erro aparecerá duas vezes na resposta (uma para cada uma das ID de cliente descartadas). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>A ID do cliente foi descartada porque excedeu o limite de uma determinada namespace. A ID da Namespace é <code><i>ID</i></code>, a ID do cliente é <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Esse código de erro será retornado se houver mais de 3 IDs do cliente declaradas para a mesma namespace (<code> DPID</code>) em uma chamada <span class="wintitle"> DCS</span> . </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>Nessa solicitação de exemplo do <span class="wintitle"> DCS</span> , há quatro IDs declaradas para a mesma namespace (com o código de integração um). Uma das IDs é descartada e o erro 310 é retornado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>A solicitação contém parâmetros inválidos </p> </td> 
   <td colname="col3"> <p>O <span class="wintitle"> DCS</span> retorna esse código de erro quando pelo menos um parâmetro de URL não está corretamente codificado. Nesse caso, o <span class="wintitle"> DCS</span> ignora a solicitação inteira. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>Na solicitação de amostra acima, a <code> %</code> sequência é codificada incorretamente. Consequentemente, o <span class="wintitle"> DCS</span> irá ignorá-lo. </p> <p>A amostra codificada corretamente deve ser semelhante a: </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>A solicitação contém uma ID de dispositivo global inválida </p> </td> 
   <td colname="col3"> <p>O <span class="wintitle">DCS</span> retorna esse código de erro quando a solicitação contém uma ID de dispositivo global inválida. O DCS ignora a ID inválida e lança um erro 312 junto com os erros específicos da ID inválida. Consulte Fontes <a href="../../../features/global-data-sources.md" format="dita" scope="local">de dados</a> globais e <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Índice de IDs no Audience Manager</a> para obter informações detalhadas sobre os formatos corretos de ID de publicidade do dispositivo e as fontes de dados globais correspondentes.</p>
   <p>Exemplo de uma chamada incorreta: <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Explicação: Um <span class="keyword">IDFA (DPID 20915)</span> deve ser uma ID em maiúsculas. A ID fornecida na solicitação está em minúsculas.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>A ID CMP não está presente no GCL</p> </td> 
   <td colname="col3"> <p>Quando <code>gdpr=1</code> e a sequência de caracteres TC IAB é gerada por uma ID CMP não presente na versão em cache do CMP Global no momento da avaliação, o Plug-in Audience Manager para TCF IAB descarta a sequência de caracteres TC IAB e processa a solicitação como de costume. A macro IAB TCF v2.0 ${GDPR} está definida como 0 e a macro ${GDPR_CONSENT_XXX} está vazia.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>A ID CMP é marcada como excluída no GCL</p> </td> 
   <td colname="col3"> <p>Quando <code>gdpr=1</code> e a string IAB TC é gerada por um CMP marcado como excluído em nossa versão em cache da Lista Global CMP, o Plug-in Audience Manager para IAB TCF descarta a string TC e processa a solicitação como de costume, se o tempo de avaliação ultrapassar o tempo de exclusão da Lista Global CMP. A macro IAB TCF v2.0 ${GDPR} está definida como 0 e a macro ${GDPR_CONSENT_XXX} está vazia.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>A sequência de caracteres de consentimento indica que não há consentimento</p> </td> 
   <td colname="col3"> <p>Quando nenhum consentimento é fornecido, o Plug-in de Audience Manager para TCF IAB rejeita o usuário para fora da coleta de dados adicional ou elimina a chamada completamente se não houver contexto de parceiro detectado.</p>
   </td>
  </tr>

</tbody>
</table>

## Exemplo de mensagens de código de erro {#sample-error-codes}

O [!DNL DCS] retorna códigos de erro e mensagens em um [!DNL JSON] objeto ou em um cabeçalho X na sequência de resposta HTTP.

### Exemplo de código de erro e mensagem do DCS

```
{ 
   "errors":[ 
      { 
         "code":101,
         "msg":"Invalid Experience Cloud id passed in"
      },
      { 
         "code":102,
         "msg":"Invalid aam id passed in request"
      }
   ]
}
```

### X-Error

Os códigos de erro capturados pelo cabeçalho X aparecem na sequência de caracteres do URL como esta, `X-Error: 101,102`.

[Condições de raça e tratamento de erros](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)