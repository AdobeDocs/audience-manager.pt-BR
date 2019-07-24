---
description: Adicione uma declaração if para verificar os cookies do Audience Manager antes de chamar o método Tag Er Tag. settargeting.
seo-description: Adicione uma declaração if para verificar os cookies do Audience Manager antes de chamar o método Tag Er Tag. settargeting.
seo-title: Modificar a chamada da API de definição de metas do GPT
solution: Audience Manager
title: Modificar a chamada da API de definição de metas do GPT
uuid: 0 cd 38 f 30-5 d 29-4511-a 779-d 32587 f 1 dafb
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Modify the GPT `setTargeting` API Call {#modify-the-gpt-settargeting-api-call}

Add an if statement to check for Audience Manager cookies before calling the [!DNL Google Publisher Tag] `.setTargeting` method.

## Check for Audience Manager Cookies With an `IF` Statement

The `.setTargeting` method gets data from the Audience Manager destination cookie and the unique user ID cookie ( `aam_uuid`). However, if `.setTargeting` gets invoked before [!UICONTROL DIL] writes these cookies, or the cookies are empty, you may see errors when the page loads. To help avoid this, wrap the `.setTargeting` method in an `if` statement that checks for these cookies. If they're not set, this statement prevents `.setTargeting` from calling the `AamGpt` function.

### `IF` Amostra de código de declaração

In this example, the Audience Manager destination cookie name is `Sample`. Você define esse nome quando cria o cookie de destino na interface do usuário do Audience Manager. [!UICONTROL DIL] define o `aam_uuid` cookie e o nome não pode ser alterado.

```js
if(typeof AamGpt.getCookie("Sample") != "undefined"){ 
  googletag.pubads().setTargeting(AamGpt.getKey("Sample"),AamGpt.getValues("Sample")); 
}; 
if(typeof AamGpt.getCookie("aam_uuid") != "undefined" ){ 
   googletag.pubads().setTargeting("aamId", AamGpt.getCookie("aam_uuid")); 
};
```

>[!IMPORTANT]
>
>Depending on how you want to integrate with [!DNL DFP], you only need some of the lines in the code sample above:
>
>* Integração do cliente: usar apenas linhas 1-3.
>* Integração do servidor: nenhuma das linhas é necessária.
>* Ingest [!DNL DFP] log files for reporting in [!DNL Audience Manager]: use lines 4-6 only. This code inserts the value of the `aam_uuid` cookie into the logs so they can be ingested for reporting.


### `AamGpt` Funções e tipos de dados

Defines the key variables used in the `if` statement.

<table id="table_881391C9BDDF4FACAFC37A47B14B31A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Função </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Aamgpt. getkey </code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Retorna a chave no par do segmento de chave-valor. For example, if your key-value pair consisted of <code> color=blue </code>, this returns <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Aamgpt. getvalues </code> </p> </td> 
   <td colname="col2"> <p>Matriz de strings </p> </td> 
   <td colname="col3"> <p>Returns values in an array, e.g., <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Aamgpt. getcookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Returns the Audience Manager user ID, e.g., <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Criar um destino GPT](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Código do Audience Manager para tags do Editor do Google](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

