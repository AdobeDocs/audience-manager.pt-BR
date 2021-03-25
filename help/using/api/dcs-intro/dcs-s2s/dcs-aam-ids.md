---
description: Esta seção descreve como analisar uma resposta do DCS para recuperar as IDs de visitante e de região necessárias para fazer chamadas em tempo real para o DCS.
seo-description: Esta seção descreve como analisar uma resposta do DCS para recuperar as IDs de visitante e de região necessárias para fazer chamadas em tempo real para o DCS.
seo-title: Obter IDs de usuário e regiões de uma resposta do DCS
solution: Audience Manager
title: Obter IDs de usuário e regiões de uma resposta do DCS
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
translation-type: tm+mt
source-git-commit: e40233ace5cb74743db7d0f9f90707fa596a7e79
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 17%

---


# Obter IDs de usuário e regiões de uma resposta do DCS {#get-user-ids-and-regions-from-a-dcs-response}

Esta seção descreve como analisar uma resposta [!DNL DCS] para recuperar as IDs de visitante e de região necessárias para fazer chamadas em tempo real para o [!DNL DCS].

## IDs de usuário e região {#user-region-ids}

Uma resposta [!DNL DCS] contém dados sobre os visitantes do site. Você precisa do visitante e da ID da região antes de poder fazer chamadas de servidor para servidor para o [!DNL DCS].

* A ID de usuário é necessária para identificar e associar dados a um visitante específico.
* A ID da região é necessária porque está vinculada a um nome de servidor regional, que você precisa enviar dados para o [!DNL DCS]. O [!DNL DCS] armazena informações em data centers que são geograficamente os mais próximos aos visitantes do site. Consulte [IDs da região do DCS, locais e nomes de host](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Esses parâmetros são descritos abaixo. O código em *itálico* representa um espaço reservado de variável.

<table id="table_822C02D5978348DCB7153001882D397C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Tipo de dados </th> 
   <th colname="col3" class="entry"> Exemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code>"uuid": <i>user ID</i></code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p> <code> "uuid":"123456789"</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>"dcs_region":<i>region ID</i></code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Resposta de exemplo {#sample-response}

Esta resposta simples mostra o `UUID` e a região `ID`. Observação: trata-se apenas de dados de amostra. Seus arquivos de log podem ser mais longos e complexos.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Próximas etapas {#next-steps}

Depois de ter o ID do usuário e o nome do servidor regional, você pode começar a enviar e receber dados [!DNL DCS]. Consulte [Efetuar chamadas de API DCS](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
