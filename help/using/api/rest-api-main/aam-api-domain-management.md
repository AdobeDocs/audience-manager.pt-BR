---
description: Métodos de gerenciamento de domínio que permitem criar e gerenciar os domínios aos quais você deseja enviar dados (apenas para destinos de cookies).
seo-description: Métodos de gerenciamento de domínio que permitem criar e gerenciar os domínios aos quais você deseja enviar dados (apenas para destinos de cookies).
seo-title: Métodos de API de gerenciamento de domínio
solution: Audience Manager
title: Métodos de API de gerenciamento de domínio
uuid: f 2 f 08 bc 5-ea 42-4171-9 a 43-0 b 20976 f 0 cb 0
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Domain Management API Methods {#domain-management-api-methods}

Métodos de gerenciamento de domínio que permitem criar e gerenciar os domínios aos quais você deseja enviar dados (apenas para destinos de cookies).

<!-- c_partner_site.xml -->

## Create a New Domain {#create-new-domain}

A `POST` method that lets you create a new domain for (cookie destinations only).

<!-- r_post_new_partner_site.xml -->

### Solicitação

`POST` `https://api.demdex.com/v1/partner-sites/`

### Solicitação de exemplo

```
{
   "url":"example1.com"
}
```

### Resposta

A successful response returns `201 created` and the partner site, including its unique ID.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Delete a Domain {#delete-domain}

`DELETE` Um método que permite remover um domínio (apenas para destinos de cookies).

<!-- r_delete_partner_site.xml -->

### Solicitação

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Resposta

A successful response returns `204 no content`. Returns `404 not found` if the partner site cannot be found.

## Return Properties for a Domain {#return-props-domain}

A `GET` method that returns details about the specified domain (for cookie destinations only).

<!-- r_get_partner_site.xml -->

### Solicitação

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Resposta

A successful response returns `200 OK` and data as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Return Properties for all Domains {#return-props-all-domains}

`GET` Um método que retorna informações sobre todos os domínios (apenas para destinos de cookies).

<!-- r_get_partner_sites.xml -->

### Solicitação

`GET https://api.demdex.com/v1/partner-sites/`

### Parâmetros de consulta opcionais

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API]. See [Optional Parameters](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td> 
   <td colname="col2"> Retorna os resultados por número de página. A numeração é iniciada em 0. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> Pagesize</code> </td> 
   <td colname="col2"> Define o número de resultados da resposta retornados pela solicitação (10 é padrão). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> Sortby</code> </td> 
   <td colname="col2"> Classifica e retorna resultados de acordo com a propriedade JSON especificada. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> decrescente</code> </td>
   <td colname="col2"> Os resultados e retornos resultam em ordem decrescente. Crescente é padrão. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Retorna os resultados com base na sequência especificada que você deseja usar como um parâmetro de pesquisa. Por exemplo, digamos que você queira encontrar resultados para todos os modelos com a palavra "Teste" em qualquer um dos campos de valor desse item. A solicitação de amostra seria semelhante a: <p><code> ' GET '' https://api.demdex.com/v1/models/?search=Test '</code>. </p> <p>Você pode pesquisar qualquer valor retornado por um método "get all". </p> </td>
  </tr> 
 </tbody> 
</table>

### Resposta

A successful response returns `200 OK` and data in an array as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

```
[
    {
        "pid": 1111,
        "siteId": 111,
        "url": "example1.com"
    },
    {
        "pid": 2222,
        "siteId": 222,
        "url": "example2.com"
    },
    {
        "pid": 3333,
        "siteId": 333,
        "url": "example3.com"
    }
]
```
