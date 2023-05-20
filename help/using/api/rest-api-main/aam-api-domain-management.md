---
description: Métodos de gerenciamento de domínio que permitem criar e gerenciar os domínios para os quais deseja enviar dados (somente para destinos de cookies).
seo-description: Domain management methods that let you create and manage the domains to which you want to send data (for cookie destinations only).
seo-title: Domain Management API Methods
solution: Audience Manager
title: Métodos da API de gerenciamento de domínio
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
exl-id: f9907f6e-d553-4771-945b-2fddb3c9ce2f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 5%

---

# Métodos da API de gerenciamento de domínio {#domain-management-api-methods}

Métodos de gerenciamento de domínio que permitem criar e gerenciar os domínios para os quais deseja enviar dados (somente para destinos de cookies).

<!-- c_partner_site.xml -->

## Criar um novo domínio {#create-new-domain}

A `POST` que permite criar um novo domínio para (somente destinos de cookies).

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

Uma resposta bem-sucedida retorna `201 created` e o site do parceiro, incluindo sua ID exclusiva.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Excluir um domínio {#delete-domain}

A `DELETE` que permite remover um domínio (somente para destinos de cookies).

<!-- r_delete_partner_site.xml -->

### Solicitação

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Resposta

Uma resposta bem-sucedida retorna `204 no content`. Devoluções `404 not found` se o site do parceiro não puder ser encontrado.

## Retornar propriedades de um domínio {#return-props-domain}

A `GET` que retorna detalhes sobre o domínio especificado (somente para destinos de cookies).

<!-- r_get_partner_site.xml -->

### Solicitação

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Resposta

Uma resposta bem-sucedida retorna `200 OK` e dados como mostrado na amostra abaixo. Devoluções `404 Not found` se a ID do site ou o parceiro não for encontrado.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Propriedades de retorno para todos os domínios {#return-props-all-domains}

A `GET` que retorna informações sobre todos os domínios (somente para destinos de cookies).

<!-- r_get_partner_sites.xml -->

### Solicitação

`GET https://api.demdex.com/v1/partner-sites/`

### Parâmetros de consulta opcionais

Você pode usar esses parâmetros opcionais com [!DNL API] métodos que retornam *all* propriedades de um objeto. Defina essas opções na string de solicitação ao transmitir essa consulta para o [!DNL API]. Consulte [Parâmetros opcionais](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col2"> Retorna resultados por número de página. A numeração começa em 0. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> Define o número de resultados de resposta retornados pela solicitação (10 é o padrão). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> Classifica e retorna resultados de acordo com a propriedade JSON especificada. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Classifica e retorna resultados em ordem decrescente. Crescente é o padrão. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Retorna resultados com base na cadeia de caracteres especificada que você deseja usar como parâmetro de pesquisa. Por exemplo, digamos que você queira encontrar resultados para todos os modelos que têm a palavra "Teste" em qualquer um dos campos de valor para esse item. Seu exemplo de solicitação pode ser semelhante a: <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>. </p> <p>Você pode pesquisar qualquer valor retornado por um método "get all". </p> </td>
  </tr> 
 </tbody> 
</table>

### Resposta

Uma resposta bem-sucedida retorna `200 OK` e dados em uma matriz, conforme mostrado na amostra abaixo. Devoluções `404 Not found` se a ID do site ou o parceiro não for encontrado.

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
