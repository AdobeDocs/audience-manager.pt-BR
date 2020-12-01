---
description: Métodos de gerenciamento de domínio que permitem criar e gerenciar os domínios para os quais deseja enviar dados (somente para destinos de cookie).
seo-description: Métodos de gerenciamento de domínio que permitem criar e gerenciar os domínios para os quais deseja enviar dados (somente para destinos de cookie).
seo-title: Métodos da API de gerenciamento de domínio
solution: Audience Manager
title: Métodos da API de gerenciamento de domínio
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 6%

---


# Métodos da API de gerenciamento de domínio {#domain-management-api-methods}

Métodos de gerenciamento de domínio que permitem criar e gerenciar os domínios para os quais deseja enviar dados (somente para destinos de cookie).

<!-- c_partner_site.xml -->

## Criar um novo domínio {#create-new-domain}

Um método `POST` que permite criar um novo domínio para (somente destinos de cookie).

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

Uma resposta bem-sucedida retorna `201 created` e o site parceiro, incluindo sua ID exclusiva.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Excluir um Domínio {#delete-domain}

Um método `DELETE` que permite remover um domínio (somente para destinos de cookies).

<!-- r_delete_partner_site.xml -->

### Solicitação

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Resposta

Uma resposta bem-sucedida retorna `204 no content`. Retorna `404 not found` se o site parceiro não puder ser encontrado.

## Propriedades de retorno para um domínio {#return-props-domain}

Um método `GET` que retorna detalhes sobre o domínio especificado (somente para destinos de cookie).

<!-- r_get_partner_site.xml -->

### Solicitação

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Resposta

Uma resposta bem-sucedida retorna `200 OK` e os dados, conforme mostrado na amostra abaixo. Retorna `404 Not found` se a ID do site ou o parceiro não for encontrado.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Propriedades de retorno para todos os domínios {#return-props-all-domains}

Um método `GET` que retorna informações sobre todos os domínios (somente para destinos de cookies).

<!-- r_get_partner_sites.xml -->

### Solicitação

`GET https://api.demdex.com/v1/partner-sites/`

### Parâmetros de Query opcionais

Você pode usar esses parâmetros opcionais com métodos [!DNL API] que retornam *todas* propriedades para um objeto. Defina essas opções na string de solicitação ao passar esse query para [!DNL API]. Consulte [Parâmetros Opcionais](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col2"> Retorna os resultados por número de página. Numerando start em 0. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> Define o número de resultados de resposta retornados pela solicitação (10 é padrão). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> Classifica e retorna os resultados de acordo com a propriedade JSON especificada. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Classifica e retorna os resultados em ordem decrescente. Crescente é padrão. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Retorna os resultados com base na string especificada que você deseja usar como parâmetro de pesquisa. Por exemplo, digamos que você queira encontrar resultados para todos os modelos que têm a palavra "Teste" em qualquer um dos campos de valor desse item. Sua solicitação de amostra pode ser semelhante a: <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>. </p> <p>Você pode pesquisar qualquer valor retornado por um método "obter tudo". </p> </td>
  </tr> 
 </tbody> 
</table>

### Resposta

Uma resposta bem-sucedida retorna `200 OK` e os dados em um storage, como mostrado na amostra abaixo. Retorna `404 Not found` se a ID do site ou o parceiro não for encontrado.

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
