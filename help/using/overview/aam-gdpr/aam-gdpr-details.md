---
description: Este documento aborda os aspectos técnicos relacionados ao Regulamento geral de proteção de dados (RGPD) do Audience Manager e mostra como enviar solicitações do RGPD ao Audience Manager.
seo-description: Este documento aborda os aspectos técnicos relacionados ao Regulamento geral de proteção de dados (RGPD) do Audience Manager e mostra como enviar solicitações do RGPD ao Audience Manager.
seo-title: RGPD no Audience Manager
solution: Audience Manager
title: RGPD no Audience Manager
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 98914987331ce31bc8d3e67647d5b8273b287d4c

---


# RGPD no Audience Manager{#gdpr-in-audience-manager}

Este documento aborda os aspectos técnicos relacionados ao Regulamento geral de proteção de dados (RGPD) do Audience Manager e mostra como enviar solicitações do RGPD ao Audience Manager.

## Documentação do RGPD na Experience Cloud {#gdpr-documentation}

Antes de ler as especificações do Audience Manager, recomendamos que você passe pelo material da Experience Cloud para o Regulamento geral europeu de proteção de dados (RGPD), relacionado abaixo:

* [RGPD e sua empresa](https://www.adobe.com/privacy/general-data-protection-regulation.html)
* [Publicação técnica do RGPD](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-whitepaper.md)
* [Terminologia do GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-terminology.md)

As seções abaixo explicam o que o RGPD significa para o Audience Manager e como você pode enviar solicitações do RGPD para o Audience Manager.

## Tipos de solicitações de RGPD e Como fazer uma solicitação de RGPD {#types-of-gdpr-requests}

Como cliente do Audience Manager, você pode enviar solicitações individuais do RGPD para acessar e excluir dados do cliente, por meio da interface do usuário **[do](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** RGPD Client Services ou ligando para a API **[do](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** RGPD. You can submit any Audience Manager identifiers (IDs), as described in the section **[Audience Manager Identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)**, in the requests along with their respective namespace IDs (data source IDs). Em caso de dúvidas, entre em contato com o Atendimento ao cliente em gdprsupport@adobe.com.

## Acessar dados {#access-data}

Compreendemos o seu compromisso de atender às suas solicitações de clientes RGPD dentro de 30 dias após a sua recepção. Por esse motivo, tentamos processar sua solicitação de acesso aos dados o mais rápido possível.

**Solicitação**

Você pode registrar solicitações de acesso a dados por meio da interface do usuário **[do](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** GDPR Client Services ou chamando a API **[do](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** RGPD (consulte a `access` ação). Em ambos os casos, você deve carregar um JSON com os identificadores do Audience Manager para os quais está enviando a solicitação de acesso aos dados. Consulte a aparência de um JSON bem formado na documentação **[GDPR da](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** Experience Cloud (especificamente, procure na página o "formato de solicitação POST"). Ou você pode **[baixar uma amostra de JSON](assets/access_request.json)**.

**Resposta**

As respostas às solicitações de dados de acesso contêm um resumo do número total de características e segmentos, tipo de característica, descrições de características e segmentos juntamente com os respectivos nomes de fonte de dados. A resposta do Access também incluirá dados de terceiros e de terceiros acessíveis ao Controlador de dados junto com os dados de terceiros. Quando, [!UICONTROL declared IDs] como IDs CRM de dispositivos cruzados ou IDs de cookies do cliente, forem enviadas em solicitações GDPR, o Audience Manager incluirá a resposta do Access de todos os dispositivos vinculados (até 100 dispositivos por ID declarada).

**Status da resposta**

Se houver erros do Audience Manager na resposta, eles serão exibidos como códigos de erro na resposta. Temos uma [lista de códigos](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)de erro, onde você pode encontrar mais informações sobre os erros retornados.

**Exemplo de resposta**

Uma resposta de acesso de amostra pode ser semelhante à abaixo. Neste exemplo, a ID da pessoa de dados é uma ID de cookie. Eles se qualificaram para várias características e pertencem a alguns segmentos. A ID do cookie está vinculada a uma ID móvel. O exemplo também contém metadados para o telefone que eles usam.

```
{
  "id": "45338264191156397602180946733455975613",
  "namespace": {
    "id": 0,
    "integration code": "",
    "data provider name": "Demdex, Inc",
    "type": "COOKIE"
  },
  "warnings": [{
    "title": "Device Data",
    "description": "Contains data from all users of this device"
  }],
  "data": {
    "traits": [{
      "name": "Website Visitors",
      "type": "1st party",
      "description": "All Active Visitors",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Interested in Italian Holidays",
      "type": "1st party",
      "description": "Query string contains holidays/bella_italia",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Lifestyle>Recreational>Garden Party",
      "type": "3rd party",
      "description": "Survey respondents that have expressed an interest in hosting garden parties",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:36"
    }],
    "segments": [{
      "name": "test",
      "description": "Interested in Photography",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "false"
    }, {
      "name": "Traveler and Frequent Flier",
      "description": "",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }, {
      "name": "Interested in Sports",
      "description": "",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }]
  },
  "links": [{
    "id": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2",
    "namespace": {
      "id": 20914,
      "integration code": "DSID_20914",
      "data provider name": "Google",
      "type": "MOBILE"
    },
    "linking datetime": "2018-04-10 17:00:37"
  }],
  "deviceMetadata": {
    "hardware": "Mobile Phone",
    "manufacturer": "Samsung",
    "marketing name": "Galaxy S8 Plus",
    "model": "",
    "os name": "Android",
    "os version": "7.0",
    "vendor": "Samsung"
  }
}
```

A tabela abaixo contém descrições para todos os campos retornados na resposta de acesso aos dados, na ordem em que aparecem acima.

<table id="table_DF08231257F64588B98BD71A088C50DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo </p> </th> 
   <th colname="col2" class="entry"> <p>Descrição </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>A ID do usuário para os dados a seguir. Esta é uma ID fornecida na solicitação de acesso a dados do RGPD ou uma ID vinculada a uma das IDs declaradas fornecidas. Os tipos de ID são descritos na seção Identificadores <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"></a> do Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace</code> </p> </td> 
   <td colname="col2"> <p>Também conhecido como fonte de dados. Consulte a seção Identificadores <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"></a> do Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>A ID do namespace/fonte de dados. Consulte <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers (IDs)</a> para obter todos os valores aceitos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> código de integração </code> </p> </td> 
   <td colname="col2"> <p>Os códigos de integração são nomes amigáveis para suas fontes de dados e ajudam a rastrear suas fontes de dados com mais facilidade do que usar IDs de fontes de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> nome do provedor de dados</code> </p> </td> 
   <td colname="col2"> <p>O nome do proprietário da fonte de dados. 
     <ul id="ul_5CEAF23C28154662AFC443D3494107D3"> 
      <li id="li_EC2DA09F618D4225B655ADF455C0D654">Para dados primários, este é o nome da própria empresa do cliente. </li> 
      <li id="li_C4A5E1BD2A994109BBCD839DDC4B2E64">Para dados de terceiros, este é o nome da empresa parceira. </li> 
      <li id="li_1AA1246B7E40443CB18108512FBB8B19">Para dados de terceiros, esse é o nome do parceiro de dados. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type </code> </p> </td> 
   <td colname="col2"> <p>O tipo de ID para a qual você solicitou o acesso de dados do GDPR. Os tipos aceitos são listados na seção Identificadores <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"></a> do Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> avisos</code> </p> </td> 
   <td colname="col2"> <p>Os avisos retornam informações adicionais relacionadas à solicitação de acesso aos dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> título </code> </p> </td> 
   <td colname="col2"> <p>Breve informação sobre o aviso. </p> <p>Os dois avisos que você pode receber são: </p> <p> 
     <ul id="ul_34019A1529594DC7B2566913937EAF0C"> 
      <li id="li_F0104BE3D5FE4DB7BA54195504E260E9">Dados do dispositivo </li> 
      <li id="li_8A22D9F9A1454AFDBC4CAF942E80498F">Solicitação incompleta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> descrição </code> </p> </td> 
   <td colname="col2"> <p>Uma descrição mais detalhada do aviso recebido: </p> <p> 
     <ul id="ul_78E03ABA52674E07A48835FDD3431FF8"> 
      <li id="li_6BB6D58660594CA0B1A89804F2FC6274">Dados do dispositivo - contém dados de todos os usuários deste dispositivo </li> 
      <li id="li_E328D5BF066C4E7E8CCCDCAA5E91CCDC">Solicitação incompleta - A recuperação de dados do Audience Manager não foi concluída. Algumas informações podem estar faltando. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data </code> </p> </td> 
   <td colname="col2"> <p>As características e os segmentos associados a essa ID do usuário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> traits </code> </p> </td> 
   <td colname="col2"> <p>Características associadas à ID do usuário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>O nome do traço. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type</code> </p> </td> 
   <td colname="col2"> <p>O tipo de característica. Os valores possíveis são: </p> <p> 
     <ul id="ul_DBAC618D9FE94B17B2494B83832A969F"> 
      <li id="li_740F2DCA8F2A4A22A7D9988ECD2FC976"> <i>O primeiro partido</i> pelas suas próprias características. </li> 
      <li id="li_D9354F40FD114802819191450F2375C8"> <i>O segundo partido</i> para características que pertencem aos seus parceiros. Leia o artigo Dados <a href="../../overview/data-types-collected.md#second-party-data"></a> de terceiros para obter mais informações. </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <i>Terceiros</i> para características obtidas de parceiros de dados, por meio do <a href="../../features/audience-marketplace/audience-marketplace.md"> Audience Marketplace</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> descrição</code> </p> </td> 
   <td colname="col2"> <p>Algumas palavras para ajudar a descrever o propósito ou a função do traço. Este é um campo opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> controles de exportação de dados</code> </p> </td> 
   <td colname="col2"> <p>Os controles <a href="../../features/data-export-controls.md"> de exportação de</a> dados aplicados à fonte de dados dessa característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> nome do provedor de dados</code> </p> </td> 
   <td colname="col2"> <p>O nome do proprietário da fonte de dados à qual essa característica pertence. 
     <ul id="ul_D2D424E903A143779342D35D6F625656"> 
      <li id="li_55B3A40A6CD24A25B5AAFD07AD28F662">Para dados primários, este é o nome da própria empresa do cliente. </li> 
      <li id="li_BC6A9F52543D4532BC7D90948D1EB35F">Para dados de terceiros, este é o nome da empresa parceira. </li> 
      <li id="li_DFD35A3E3E844E4993B59A62DB3C38D9">Para dados de terceiros, esse é o nome do parceiro de dados. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> última realização</code> </p> </td> 
   <td colname="col2"> <p>A hora exata em que o assunto de dados se qualificou pela última vez para esse traço. O formato de data é AAAA-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segmentos </code> </p> </td> 
   <td colname="col2"> <p>Segmentos aos quais este usuário pertence. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>O nome do segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> descrição</code> </p> </td> 
   <td colname="col2"> <p>Algumas palavras para ajudar a descrever este segmento. Este é um campo opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> controles de exportação de dados</code> </p> </td> 
   <td colname="col2"> <p>Os controles <a href="../../features/data-export-controls.md"> de exportação de</a> dados aplicados à fonte de dados desse segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> nome do provedor de dados</code> </p> </td> 
   <td colname="col2"> <p>O nome do proprietário da fonte de dados à qual este segmento pertence. 
     <ul id="ul_D437D149BDBE470489D1DD03CF47841C"> 
      <li id="li_90133644911A49AEB0DB209BCAC8E789">Para dados primários, este é o nome da própria empresa do cliente. </li> 
      <li id="li_788AAFCDA9914235830F0440DF9982E5">Para dados de terceiros, este é o nome da empresa parceira. </li> 
      <li id="li_F59FD714746E46BEB27FDF6B7245A7D1">Para dados de terceiros, esse é o nome do parceiro de dados. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> última realização</code> </p> </td> 
   <td colname="col2"> <p>A hora exata em que o assunto de dados se qualificou pela última vez para este segmento. O formato de data é AAAA-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ative</code> </p> </td> 
   <td colname="col2"> <p>Indica se a Pessoa de Dados está qualificada para esse segmento no momento. Returns <code><i>true</i></code> or <code><i>false</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> links </code> </p> </td> 
   <td colname="col2"> <p>ID adicional à qual essa ID foi vinculada. As informações são retornadas em: </p> <p> 
     <ul id="ul_679F372A83164CC8B6BFE5A833347B9E"> 
      <li id="li_BCBF4F4C6C4049519BDE9186EE84868A">ID </li> 
      <li id="li_46AC081C993041E6BCE70119FE04BE7F">namespace (fonte de dados) </li> 
      <li id="li_E9B906C8947E484B94FBCAEB03BDF4E2">ID do namespace </li> 
      <li id="li_FB2A2F28290B4BA7844A558C01F8D9D4">código de integração </li> 
      <li id="li_2569982810B64F8AABD78F5AC3717971"> nome do provedor de dados </li> 
      <li id="li_2A3C282279064373BF7E4619A63454CF">Tipo de ID </li> 
     </ul> </p> <p>Todos esses campos estão descritos nas primeiras linhas desta tabela. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datetime de vinculação</code> </p> </td> 
   <td colname="col2"> <p>A hora exata em que um evento de sincronização de ID fez o link entre IDs. O formato de data é AAAA-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> metadados do dispositivo </code> </p> </td> 
   <td colname="col2"> <p>Informações sobre o dispositivo. Essas informações incluem os campos abaixo. Observe que nem todos os campos são retornados para todos os tipos de dispositivos. </p> <p> 
     <ul id="ul_F0031D50DF074634A428DBC73F958159"> 
      <li id="li_4E26042A6B8D4397829F30B7BC7A2D6E"> <p>Informações de hardware </p> </li> 
      <li id="li_99A049D585A9440EA79F57A3B03181AB"> <p>Fabricante do dispositivo </p> </li> 
      <li id="li_290F92FC3F6449EFBC4E7870B62AFE8B"> <p>O nome de marketing do dispositivo </p> </li> 
      <li id="li_FC37954CE133471398352240A8B0478F"> <p>O modelo do dispositivo </p> </li> 
      <li id="li_D54AEB0527C34E32A8AEEAEDEA5AD1B2"> <p>O nome do sistema operacional (SO) do dispositivo </p> </li> 
      <li id="li_0B343C4599344E1791B35A56EBBDC567"> <p>A versão do SO </p> </li> 
      <li id="li_634B391D95104C42A43D6EFA95F3C0D3"> <p>O fornecedor do dispositivo </p> </li> 
     </ul> </p> <p> <p>Observação: Apenas retornamos metadados do dispositivo quando você envia um dos seguintes: 
      <ul id="ul_2692AF4D28DB44FEAF5F657397F58D32"> 
       <li id="li_FBA2446BB5914772AF24D12B32D9DF1B">IDs móveis </li> 
       <li id="li_FBC45D16DEFE49CF91A7A541402A3BF3">IDs do Audience Manager </li> 
       <li id="li_2051AA94B53049DEA26654E79ED8FF2A">Experience Cloud IDs </li> 
      </ul> </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Excluir dados {#delete-data}

Compreendemos o seu compromisso de atender às suas solicitações de clientes RGPD dentro de 30 dias após a sua recepção. Por esse motivo, tentamos processar sua solicitação de exclusão de dados o mais rápido possível.

**Solicitação**

Você pode registrar solicitações de exclusão de dados por meio da interface do usuário **[do](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** GDPR Client Services ou chamando a API **[do](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** RGPD (consulte a `delete` ação). Em ambos os casos, você deve carregar um JSON com os identificadores do Audience Manager para os quais está enviando a solicitação de acesso aos dados. Consulte a aparência de um JSON bem formado na documentação [GDPR da](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) Experience Cloud (especificamente, procure na página o "formato de solicitação POST"). Ou você pode **[baixar uma amostra de JSON](assets/delete_request.json)**.

**Resposta**

Em resposta às solicitações de exclusão de dados, excluímos características e segmentos associados ao respectivo identificador do Audience Manager. Além disso, os respectivos identificadores do Audience Manager para a pessoa de dados serão removidos permanentemente da coleta de dados adicional pelo Audience Manager e os respectivos mapeamentos de ID serão removidos. Quando IDs declaradas, como IDs CRM de dispositivo cruzado ou IDs de cookie do cliente, forem enviadas em solicitações GDPR, o Audience Manager executará as ações necessárias de exclusão em todos os dispositivos vinculados (até 100 dispositivos por ID declarada).

## Solicitação de recusa {#opt-out-request}

Para solicitações de não participação, consulte nossa documentação sobre o Gerenciamento [de](../../overview/data-security-and-privacy/opt-out-management.md)não participação.

## Identificadores (IDs) do Audience Manager {#aam-ids}

Ao enviar solicitações de RGPD ao Adobe Audience Manager, você deve incluir um dos identificadores (IDs) listados abaixo. Você pode encontrar mais informações sobre os formatos de ID em nosso [Índice de IDs](../../reference/ids-in-aam.md)do Audience Manager.

### ID de usuário exclusiva do Adobe Audience Manager

**ID** do usuário: aam_uuid

**Definição**:ID de usuário exclusiva do Adobe Audience Manager

**ID** do namespace: 0

>[!NOTE]
>
>Você também pode usar o namespace CORE. Consulte o segundo exemplo de JSON.

**Exemplo em JSON**:

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

### Adobe Experience Cloud ID

**ID** do usuário: mid

**Definição**: Adobe Experience Cloud ID, anteriormente conhecida como ID de visitante ou Marketing Cloud ID

**ID** do namespace: 4

>[!NOTE]
>
>Você também pode usar o namespace ECID. Consulte o segundo exemplo de JSON.

**Exemplo em JSON**:

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

### Customer ID

**ID** do usuário: cid

**Definição**: ID do cliente, como um cookie definido para visitantes anônimos do site ou uma ID CRM de um sistema offline ou nome de usuário com hash

**ID** do namespace: Específico do cliente. Localize-o na sua instância do Audience Manager.

**Exemplo em JSON**:

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

### ID de anúncio móvel

**ID** do usuário: d_cid

**Definição**: IDs de anúncios móveis.
>[!IMPORTANT]
>
> Se você estiver usando o SDK móvel, você também deverá enviar a Experience Cloud ID (MID) juntamente com as IDs de publicidade móvel para obter acesso GDPR completo e respostas de exclusão.

**ID de namespace**:

* IDFA: 2015
* GAID: 2014

**Exemplo em JSON**:

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

### Código de integração

**ID** do usuário: d_cid_ic

**Definição**: Um código de integração para a fonte de dados. Isso pode ser usado em vez da ID da fonte de dados / ID do namespace na solicitação da API para o serviço principal de privacidade da Adobe Experience Cloud.

**ID** do namespace: Não aplicável

Exemplo em JSON:

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
