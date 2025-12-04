---
description: Códigos de erro e mensagens geradas pelos Data Collection Servers (DCS) listados em ordem numérica pela ID de código.
title: Códigos de erros, mensagens e exemplos de DCS
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: 2012c244f6fa5ca01c7e2719ce621214cb22f93e
workflow-type: tm+mt
source-wordcount: '1517'
ht-degree: 3%

---

# Códigos de erros, mensagens e exemplos de DCS {#dcs-error-codes-messages-and-examples}

Códigos de erro e mensagens geradas pelo [!UICONTROL Data Collection Servers] ([!DNL DCS]) listados em ordem numérica por ID de código.

Nas tabelas abaixo, *itálico* representa um espaço reservado para variável.

## Códigos de erro do sistema {#system-error-codes}

| Código de erro | Mensagem de erro | Descrição |
|---|---|---|
| 0 | Erro não especificado | Este é um erro &quot;catch-all&quot; (global) que lida com eventos não cobertos por outros manipuladores de erro. É difícil solucionar esse erro. Ela pode ser causada por várias ações ou eventos desconhecidos. Se você receber esse erro, tente sua solicitação [!DNL DCS] novamente. Entre em contato com o representante do [!DNL Adobe] se o problema persistir. |
| 1 | Não foi possível encontrar a configuração para o nome de host: `hostname` | O nome do host enviado na solicitação não foi configurado pela equipe de provisionamento do parceiro. Entre em contato com o representante do [!DNL Adobe] se você vir esta mensagem de erro. |
| 2 | Valor `d_orgid` inválido (não foi possível encontrar uma configuração para esta id de organização): `ID` | A ID da organização está incorreta. Verifique sua ID e tente a solicitação novamente. Se você não souber ou tiver sua ID da Organização, consulte a seção &quot;Página de Administração&quot; [Organizações e vinculação de contas](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html) para obter informações sobre como encontrá-la. |
| 10 | Não foi possível avaliar as características | As características na solicitação foram parcialmente avaliadas ou não foram avaliadas. Entre em contato com o representante do [!DNL Adobe] se o problema persistir. |

## Códigos de erro de integração {#integration-error-codes}

| Código de erro | Mensagem de erro | Descrição |
|---|---|---|
| 100 | Não foi possível recuperar o nome do host para a solicitação | Uma chamada [!DNL API] não enviou o cabeçalho [!DNL HTTP] do host na solicitação. Adicione o cabeçalho do host à chamada e tente novamente. A maioria dos navegadores e [!DNL API] clientes fazem isso automaticamente. |
| 101 | ID inválida de [!DNL Experience Cloud] passada em `ID` | A chamada [!DNL DCS] contém uma ID de [!DNL Experience Cloud] inválida. Verifique o par de valor-chave `d_mid=` na cadeia de caracteres do cabeçalho. Verifique se você está transmitindo a ID [!DNL Experience Cloud] correta e tente a solicitação novamente. |
| 102 | [!DNL AAM ID] inválido transmitido na solicitação `ID` | A chamada [!DNL DCS] contém uma ID de [!DNL Audience Manager] inválida. Verifique o par de valor-chave `d_uuid=` na cadeia de caracteres do cabeçalho. Verifique se você está transmitindo a ID [!DNL Audience Manager] correta e tente a solicitação novamente. |
| 104 | Todas as IDs de cliente são inválidas | Todas as IDs do cliente em sua chamada são inválidas. Verifique suas IDs e tente novamente. |
| 109 | O referenciador `HTTP referer` não é permitido para o parceiro `Partner ID` | O cabeçalho `HTTP referer` na chamada não é permitido para a ID do parceiro na chamada. Verifique se o cabeçalho `HTTP referer` está correto. |
| 111 | Token `IMS` inválido recebido | Retornado para [!DNL Audience Manager] - [!DNL Adobe Target] integrações. O erro é lançado quando é feita uma chamada para [!DNL DCS], contendo um token [!DNL IMS] inválido. O token pode estar malformado, expirado ou o usuário pode não estar autorizado a acessar o recurso necessário. |

## Códigos de erro de recusa {#opt-out-error-codes}

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
   <td colname="col2"> <p>Tag de recusa encontrada para a ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Um cliente optou por não receber publicidade baseada em interesses. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Cookies bloqueados </p> </td> 
   <td colname="col3"> <p>Retornado quando o navegador do usuário bloqueia cookies de terceiros.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Relação de confiança encontrada via <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>O usuário iniciou um processo de recusa por meio da NAI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>As solicitações deste país são bloqueadas pelo parceiro </p> </td> 
   <td colname="col3"> <p>Com base no endereço IP, o <span class="wintitle"> DCS</span> bloqueia solicitações de países onde o parceiro tenha limitado deliberadamente o tráfego. </p> </td> 
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

## Códigos de erro de recuperação de perfil {#profile-retrieval-error-codes}

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
   <td colname="col2"> <p> Não é possível ler características do cache de perfil para a ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando um perfil de usuário não pode ser lido de nosso armazenamento interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Não é possível ler IDs de dispositivo do cache de perfil para ID de cliente: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando a ID de dispositivo <a href="../../../reference/ids-in-aam.md"> </a> não pode ser recuperada para uma regra de mesclagem de Links de Perfil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Não é possível ler o cliente relacionado para a ID do dispositivo: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando a <a href="../../../reference/ids-in-aam.md"> ID do cliente (UUID)</a> associada a uma ID de dispositivo não pode ser recuperada para uma regra de mesclagem da Última Autenticação do nosso armazenamento interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Não é possível ler o cluster de dispositivos para a ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>As IDs de dispositivo vinculadas do mesmo cluster de gráficos de dispositivo não podem ser retornadas para esta ID de dispositivo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Não foi possível executar a migração porque a leitura do perfil falhou para o dispositivo principal </p> </td> 
   <td colname="col3"> <p>Se você receber esse erro, talvez estejamos tendo problemas de escalabilidade com nosso repositório de dados (<span class="wintitle"> PCS</span>). Entre em contato com o representante da Adobe se o problema persistir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Não foi possível executar a migração de <code><i>ID</i></code> para <code><i>ID</i></code>, pois a leitura do perfil falhou para <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Se você receber esse erro, talvez estejamos tendo problemas de escalabilidade com nosso repositório de dados (<span class="wintitle"> PCS</span>). Entre em contato com o representante da Adobe se o problema persistir. </p> </td> 
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
   <td colname="col3"> <p>A ID do cliente é inválida (valores ausentes para fonte de dados, códigos de integração ausentes, formato inválido para fontes de dados, ID do cliente bloqueada, ID do cliente em branco, tentativa de acesso não autorizado a uma fonte de dados que não pertence ao parceiro). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>Número máximo de IDs do cliente excedido. O máximo permitido é <code><i>maximum allowed</i></code>. Encontrado é <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>O número de IDs do cliente associadas a uma fonte de dados entre dispositivos excede o número permitido de IDs entre dispositivos por solicitação. Essas IDs incluem IDs entre dispositivos, dispositivos móveis ou cookies. No momento, o limite está definido como 10. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>ID de cliente não autorizada <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando a fonte de dados da ID do cliente não pertence à ID da organização atual. Se você não souber ou tiver sua ID da organização, consulte a seção "Localizar a ID da organização" em <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organizações e Vinculação de Contas</a> para obter informações sobre como encontrá-la. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>ID do cliente bloqueada <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando a ID do cliente é identificada como mal-intencionada e é adicionada a um arquivo de inclui na lista de bloqueios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>ID da fonte de dados bloqueada <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando a ID da fonte de dados foi identificada como mal-intencionada e adicionada a um arquivo de inclui na lista de bloqueios </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>ID de dispositivo declarada bloqueada <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>A ID do dispositivo foi identificada como mal-intencionada e foi adicionada a uma inclui na lista de bloqueios. Isso pode acontecer quando recebemos uma quantidade extrema de <span class="wintitle"> solicitações DCS</span> contendo essa ID de dispositivo em um curto período. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Operação de perfil bloqueada para <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Uma ação de leitura/gravação foi bloqueada porque uma ID foi identificada como mal-intencionada e adicionada a um incluo na lista de bloqueios. Consulte o código de erro 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>A ID do cliente <code><i>ID</i></code> foi descartada porque excedeu o limite de IDs do cliente declaradas por solicitação </p> </td> 
   <td colname="col3"> <p>Relacionado ao erro 301. Este erro especifica qual ID de cliente foi descartada porque o limite foi excedido. </p> <p>Por exemplo, se houver 12 IDs de cliente declaradas na chamada <span class="wintitle"> DCS</span>, duas delas serão descartadas. Para retransmitir quais foram descartados, esse erro aparecerá duas vezes na resposta (uma vez para cada ID do cliente descartada ). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>A ID do cliente foi descartada porque excedeu o limite de um determinado namespace. A ID do namespace é <code><i>ID</i></code>, a ID do cliente é <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Este código de erro será retornado se houver mais de 3 IDs de cliente declaradas para o mesmo namespace (<code> DPID</code>) em uma chamada DCS<span class="wintitle"> do </span>. </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one </code> </p> <p>Nesta amostra de solicitação <span class="wintitle"> DCS</span>, há 4 IDs declaradas para o mesmo namespace (com o código de integração um). Uma das IDs é descartada e o erro 310 é retornado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>A solicitação contém parâmetros inválidos </p> </td> 
   <td colname="col3"> <p>O <span class="wintitle"> DCS</span> retorna este código de erro quando pelo menos um parâmetro de URL não está corretamente codificado. Nesse caso, o <span class="wintitle"> DCS</span> ignora toda a solicitação. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>Na solicitação de exemplo acima, a sequência <code> %</code> está codificada incorretamente. Consequentemente, o <span class="wintitle"> DCS</span> irá desconsiderá-lo. </p> <p>A amostra corretamente codificada deve ter esta aparência: </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>A solicitação contém uma ID de dispositivo global inválida </p> </td> 
   <td colname="col3"> <p>O <span class="wintitle">DCS</span> retorna este código de erro quando a solicitação contém uma ID de Dispositivo Global inválida. O DCS ignora a ID inválida e lança um erro 312 juntamente com os erros específicos da ID inválida. Consulte <a href="../../../features/global-data-sources.md" format="dita" scope="local">Fontes de Dados Globais</a> e <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Índice de IDs no Audience Manager</a> para obter informações detalhadas sobre os formatos corretos de ID de publicidade do dispositivo e as fontes de dados globais correspondentes.</p>
   <p>Exemplo de chamada incorreta: <code>"http://partner.demdex.net/event?d_rtbd=json&d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Explicação: Um <span class="keyword">IDFA (DPID 20915)</span> deve ser uma ID em maiúsculas. A ID fornecida na solicitação está em minúsculas.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>A ID de CMP não está presente no GCL</p> </td> 
   <td colname="col3"> <p>Quando <code>gdpr=1</code> e a cadeia de caracteres IAB TC são gerados por uma ID CMP que não está presente na versão em cache da Lista CMP Global do Audience Manager no momento da avaliação, o Plug-in do Audience Manager para IAB TCF descarta a cadeia de caracteres IAB TC e processa a solicitação como de costume. A macro IAB TCF v2.2 ${GDPR} está definida como 0 e a macro ${GDPR_CONSENT_XXX} está vazia.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>A ID CMP está marcada como excluída no GCL</p> </td> 
   <td colname="col3"> <p>Quando <code>gdpr=1</code> e a cadeia de caracteres IAB TC são gerados por um CMP marcado como excluído em nossa versão em cache da Lista CMP Global, o Plug-in do Audience Manager para IAB TCF descarta a cadeia de caracteres TC e processa a solicitação como de costume, se o tempo de avaliação ultrapassar o tempo de exclusão da Lista CMP Global. A macro IAB TCF v2.2 ${GDPR} está definida como 0 e a macro ${GDPR_CONSENT_XXX} está vazia.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>A sequência de consentimento indica não haver consentimento</p> </td> 
   <td colname="col3"> <p>Quando nenhum consentimento é fornecido, o Plug-in do Audience Manager para TCF do IAB recusa a coleta de dados adicional do usuário ou desativa a chamada completamente se não for detectado nenhum contexto de parceiro.</p>
   </td>
  </tr>
 </tbody>
</table>

## Exemplo de mensagens de código de erro {#sample-error-codes}

O [!DNL DCS] retorna códigos de erro e mensagens em um objeto [!DNL JSON] ou em um cabeçalho X na cadeia de caracteres de resposta HTTP.

### Código e mensagem de erro DCS de exemplo

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

Os códigos de erro capturados pelo cabeçalho X- aparecem na cadeia de caracteres da URL desta forma, `X-Error: 101,102`.

[Condições de raça e tratamento de erros](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
