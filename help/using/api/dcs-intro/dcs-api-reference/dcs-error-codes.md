---
description: Códigos de erro e mensagens geradas pelos Servidores de coleta de dados (DCS) listados em ordem numérica por ID de código.
title: Códigos de erros, mensagens e exemplos de DCS
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: dbb557928a296d3dd5f0646644e2ca0cdc11dfdc
workflow-type: tm+mt
source-wordcount: '1520'
ht-degree: 4%

---

# Códigos de erros, mensagens e exemplos de DCS {#dcs-error-codes-messages-and-examples}

Códigos de erro e mensagens geradas pela variável [!UICONTROL Data Collection Servers] ([!DNL DCS]) listado em ordem numérica por ID de código.

Nas tabelas abaixo, *itálico* representa um espaço reservado de variável.

## Códigos de erro do sistema {#system-error-codes}

| Código de erro | Mensagem de erro | Descrição |
|---|---|---|
| 0 | Erro não especificado | Este é um erro genérico que trata eventos não cobertos pelos outros manipuladores de erro. A solução de problemas desse erro é difícil. Isso pode ser causado por uma variedade de ações ou eventos desconhecidos. Se receber esse erro, tente [!DNL DCS] solicite novamente. Entre em contato com seu [!DNL Adobe] se o problema persistir. |
| 1 | Não foi possível localizar a configuração para o nome de host: `hostname` | O nome do host enviado na solicitação não foi configurado pela equipe de provisionamento do parceiro. Entre em contato com seu [!DNL Adobe] caso veja esta mensagem de erro. |
| 2 | Inválido `d_orgid` valor (não foi possível localizar uma configuração para esta id de organização): `ID` | A ID da organização está incorreta. Verifique sua ID e tente a solicitação novamente. Se você não souber ou não possuir a ID da organização, consulte a seção &quot;Página do administrador&quot; [Organizações e vinculação de contas](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html) para obter informações sobre como encontrá-lo. |
| 10 | Não é possível avaliar características | As características da solicitação foram parcialmente avaliadas ou não foram avaliadas. Entre em contato com seu [!DNL Adobe] se o problema persistir. |

## Códigos de erro de integração {#integration-error-codes}

| Código de erro | Mensagem de erro | Descrição |
|---|---|---|
| 100 | Não foi possível recuperar o nome do host para a solicitação | Um [!DNL API] chamada não enviou o host [!DNL HTTP] na solicitação. Adicione o cabeçalho do host à chamada e tente novamente. A maioria dos navegadores e [!DNL API] Os clientes fazem isso automaticamente. |
| 101 | Inválido [!DNL Experience Cloud] id passada `ID` | O [!DNL DCS] chamada contém um valor inválido [!DNL Experience Cloud] ID. Verifique a `d_mid=` par chave-valor na string de cabeçalho. Certifique-se de que está passando o sinal correto [!DNL Experience Cloud] ID e tente a solicitação novamente. |
| 102 | Inválido [!DNL AAM ID] solicitação passada `ID` | O [!DNL DCS] chamada contém um valor inválido [!DNL Audience Manager] ID. Verifique a `d_uuid=` par chave-valor na string de cabeçalho. Certifique-se de que está passando o sinal correto [!DNL Audience Manager] ID e tente a solicitação novamente. |
| 104 | Todas as IDs de cliente são inválidas | Todas as IDs do cliente em sua chamada são inválidas. Verifique suas IDs e tente novamente. |
| 109 | Referenciador `HTTP referer` não é permitido para parceiro `Partner ID` | O `HTTP referer` não é permitido o cabeçalho na chamada para a ID do parceiro na chamada. Verifique se a variável `HTTP referer` O cabeçalho está correto. |
| 111 | Inválido `IMS` token recebido | Retornado para [!DNL Audience Manager] - [!DNL Adobe Target] integrações. O erro é lançado quando uma chamada é feita para a variável [!DNL DCS], contendo um valor inválido [!DNL IMS] token. O token pode estar malformado, expirado ou o usuário pode não estar autorizado a acessar o recurso desejado. |

## Códigos de erro de não participação {#opt-out-error-codes}

<table id="table_A50C284AB84F48A79B01223D991884A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID de código </th> 
   <th colname="col2" class="entry"> Mensagem </th> 
   <th colname="col3" class="entry"> Descrição </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>171 </p> </td> 
   <td colname="col2"> <p>Tag de rejeição encontrada para id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Um cliente optou por não receber anúncios com base em interesses. </p> </td> 
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
   <td colname="col2"> <p>Solicitações deste país são bloqueadas pelo parceiro </p> </td> 
   <td colname="col3"> <p>Com base no endereço IP, a variável <span class="wintitle"> DCS</span> bloqueia pedidos de países onde o parceiro tenha deliberadamente limitado o tráfego. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>Não são permitidas solicitações deste país </p> </td> 
   <td colname="col3"> <p>Com base no endereço IP, a variável <span class="wintitle"> DCS</span> bloqueia pedidos dos seguintes países: </p> <p> 
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

## Códigos de erro da recuperação de perfis {#profile-retrieval-error-codes}

<table id="table_CFF2252A3CC54960802905454A867D7A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID de código </th> 
   <th colname="col2" class="entry"> Mensagem </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>200 </p> </td> 
   <td colname="col2"> <p> Não é possível ler características do cache de perfil para o id: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando um perfil de usuário não pode ser lido de nosso armazenamento interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Não é possível ler ids de dispositivo do cache de perfil para a ID do cliente: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando a variável <a href="../../../reference/ids-in-aam.md"> ID do dispositivo</a> não pode ser recuperado para uma regra de mesclagem Link de perfil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Não é possível ler o cliente relacionado para a ID do dispositivo: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando a variável <a href="../../../reference/ids-in-aam.md"> customer ID (UUID)</a> associada a uma ID de dispositivo não pode ser recuperada para uma regra de mesclagem Última autenticação de nosso armazenamento interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Não é possível ler o cluster de dispositivos para a id: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>As IDs de dispositivo vinculadas do mesmo cluster de gráficos de dispositivo não podem ser retornadas para essa ID de dispositivo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Não foi possível executar a migração porque a leitura do perfil falhou para o dispositivo principal </p> </td> 
   <td colname="col3"> <p>Se você receber esse erro, talvez estejamos tendo problemas de escalabilidade com nosso armazenamento de dados (<span class="wintitle"> PCS</span>). Entre em contato com o representante do Adobe se o problema persistir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Não foi possível executar a migração de <code><i>ID</i></code> para <code><i>ID</i></code>, porque a leitura do perfil falhou para <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Se você receber esse erro, talvez estejamos tendo problemas de escalabilidade com nosso armazenamento de dados (<span class="wintitle"> PCS</span>). Entre em contato com o representante do Adobe se o problema persistir. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Códigos de aviso de integração {#integration-warning-codes}

<table id="table_31F1593C46804DDBA2E9BEDE83F2417F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID de código </th> 
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
   <td colname="col1"> <p>301º </p> </td> 
   <td colname="col2"> <p>Número máximo de IDs de cliente excedido. O máximo permitido é <code><i>maximum allowed</i></code>. Encontrado <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>O número de IDs de cliente associadas a uma fonte de dados entre dispositivos excede o número permitido de IDs entre dispositivos por solicitação. Essas IDs incluem IDs entre dispositivos, dispositivos móveis ou cookies. No momento, o limite é definido como 10. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>ID de cliente não autorizado <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando a fonte de dados da ID do cliente não é de propriedade da ID da organização atual. Se você não souber ou não possuir a ID da organização, consulte a seção "Encontrar a ID da organização" em <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organizações e vinculação de contas</a> para obter informações sobre como encontrá-lo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>ID do cliente bloqueado <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando a ID do cliente foi identificada como mal-intencionada e foi adicionada a uma lista de bloqueios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>ID da fonte de dados bloqueada <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retornado quando a ID da fonte de dados foi identificada como maliciosa e foi adicionada a uma lista de bloqueios </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>ID de dispositivo declarada bloqueada <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>A ID de dispositivo foi identificada como mal-intencionada e foi adicionada a uma  de lista de bloqueios. Isso pode ocorrer quando recebermos uma quantidade extrema de <span class="wintitle"> DCS</span> solicitações que contêm essa ID de dispositivo em um curto período de tempo. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Operação de perfil bloqueada para <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Uma ação de leitura/gravação foi bloqueada porque uma ID foi identificada como maliciosa e foi adicionada a uma lista de bloqueios Ver código de erro 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>ID do cliente <code><i>ID</i></code> foi descartada porque excedeu o limite de IDs de cliente declaradas por solicitação </p> </td> 
   <td colname="col3"> <p>Relacionado ao erro 301. Esse erro especifica qual ID do cliente foi descartada porque o limite foi excedido. </p> <p>Por exemplo, se houver 12 IDs do cliente declaradas na variável <span class="wintitle"> DCS</span> dois deles serão descartados. Para retransmitir quais foram descartadas, esse erro aparecerá duas vezes na resposta (uma para cada uma das IDs do cliente descartadas ). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>A ID do cliente foi descartada porque excedeu o limite de um determinado namespace. ID de namespace é <code><i>ID</i></code>, a id do cliente é <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Esse código de erro será retornado se houver mais de 3 IDs do cliente declaradas para o mesmo namespace (<code> DPID</code>) em um <span class="wintitle"> DCS</span> chame. </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>Nesta amostra <span class="wintitle"> DCS</span> , há 4 ids declaradas para o mesmo namespace (com o código de integração um). Uma das IDs é descartada e o erro 310 é retornado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311º </p> </td> 
   <td colname="col2"> <p>A solicitação contém parâmetros inválidos </p> </td> 
   <td colname="col3"> <p>O <span class="wintitle"> DCS</span> retorna esse código de erro quando pelo menos um parâmetro de URL não é codificado corretamente. Nesse caso, a variável <span class="wintitle"> DCS</span> ignora toda a solicitação. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>Na solicitação de amostra acima, a variável <code> %</code> sequência é codificada incorretamente. Consequentemente, a <span class="wintitle"> DCS</span> não o levará em consideração. </p> <p>A amostra codificada corretamente deve ter esta aparência: </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>A solicitação contém uma ID de Dispositivo Global inválida </p> </td> 
   <td colname="col3"> <p>O <span class="wintitle">DCS</span> retorna esse código de erro quando a solicitação contém uma ID de dispositivo global inválida. O DCS ignora a ID inválida e gera um erro 312 junto com os erros específicos da ID inválida. Consulte <a href="../../../features/global-data-sources.md" format="dita" scope="local">Fontes de dados globais</a> e <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Índice de IDs no Audience Manager</a> para obter informações detalhadas sobre os formatos corretos de ID de publicidade do dispositivo e as fontes de dados globais correspondentes.</p>
   <p>Exemplo de uma chamada incorreta: <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Explicação: Um <span class="keyword">IDFA (DPID 20915)</span> deve ser uma ID em maiúsculas. A ID fornecida na solicitação está em minúsculas.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>A ID da CMP não está presente no GCL</p> </td> 
   <td colname="col3"> <p>When <code>gdpr=1</code> e o IAB TC é gerado por uma ID CMP que não está presente na versão em cache do CMP global no momento da avaliação, o Plug-in do Audience Manager para TCF do IAB descarta a cadeia de caracteres TC do IAB e processa a solicitação como de costume. A macro TCF do IAB v2.0 ${GDPR} está definida como 0 e a macro ${GDPR_CONSENT_XXX} está vazia.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>A ID da CMP é marcada como excluída na GCL</p> </td> 
   <td colname="col3"> <p>When <code>gdpr=1</code> e a cadeia de caracteres IAB TC é gerada por um CMP marcado como excluído em nossa versão em cache da Lista Global de CMP, o Plug-in do Audience Manager para TCF do IAB descarta a cadeia de caracteres TC e processa a solicitação como de costume, se o tempo de avaliação ultrapassar o tempo de exclusão da Lista Global de CMP. A macro TCF do IAB v2.0 ${GDPR} está definida como 0 e a macro ${GDPR_CONSENT_XXX} está vazia.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>A cadeia de consentimento indica nenhum consentimento</p> </td> 
   <td colname="col3"> <p>Quando nenhum consentimento é fornecido, o Plug-in do Audience Manager para TCF do IAB recusa o usuário a sair de outra coleta de dados ou elimina a chamada completamente se não houver contexto de parceiro detectado.</p>
   </td>
  </tr>

</tbody>
</table>

## Exemplo de mensagens de código de erro {#sample-error-codes}

O [!DNL DCS] retorna códigos de erro e mensagens em um [!DNL JSON] ou em um cabeçalho X na string de resposta HTTP.

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

Os códigos de erro capturados pelo cabeçalho X são exibidos na string de URL como esta, `X-Error: 101,102`.

[Condições de raça e tratamento de erros](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
