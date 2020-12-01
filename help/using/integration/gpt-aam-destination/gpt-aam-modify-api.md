---
description: Adicione uma declaração if para verificar cookies de Audience Manager antes de chamar o método Google Publisher Tag .setTargeting.
seo-description: Adicione uma declaração if para verificar cookies de Audience Manager antes de chamar o método Google Publisher Tag .setTargeting.
seo-title: Modificar a chamada da API setTargeting GPT
solution: Audience Manager
title: Modificar a chamada da API setTargeting GPT
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 9%

---


# Modifique a chamada de API GPT `setTargeting` {#modify-the-gpt-settargeting-api-call}

Adicione uma instrução if para verificar os cookies de Audience Manager antes de chamar o método [!DNL Google Publisher Tag] `.setTargeting`.

## Verifique se há cookies de Audience Manager com uma instrução `IF`

O método `.setTargeting` obtém dados do cookie de destino do Audience Manager e do cookie de ID de usuário exclusivo ( `aam_uuid`). No entanto, se `.setTargeting` for chamado antes de [!UICONTROL DIL] gravar esses cookies, ou os cookies estiverem vazios, você poderá ver erros quando a página for carregada. Para ajudar a evitar isso, vincule o método `.setTargeting` em uma instrução `if` que verifique esses cookies. Se não estiverem definidas, esta instrução impedirá que `.setTargeting` chame a função `AamGpt`.

### `IF` Amostra de código do demonstrativo

Neste exemplo, o nome do cookie de destino do Audience Manager é `Sample`. Você define esse nome ao criar o cookie de destino na interface do usuário do Audience Manager. [!UICONTROL DIL] define o  `aam_uuid` cookie e o nome não pode ser alterado.

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
>Dependendo de como deseja integrar com [!DNL Google Ad Manager], você só precisa de algumas das linhas na amostra de código acima:
>
>* Integração do cliente: use somente as linhas 1-3.
>* Integração do servidor: nenhuma das linhas é necessária.
>* Ingest [!DNL Google Ad Manager] arquivos de registro para relatórios em [!DNL Audience Manager]: use somente as linhas 4-6. Esse código insere o valor do cookie `aam_uuid` nos registros para que eles possam ser ingeridos para o relatórios.


### `AamGpt` Funções e tipos de dados

Define as variáveis principais usadas na instrução `if`.

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
   <td colname="col1"> <p> <code> AamGpt.getKey </code> </p> </td> 
   <td colname="col2"> <p>String   </p> </td> 
   <td colname="col3"> <p>Retorna a chave no par de segmentos de valor chave. Por exemplo, se seu par de chave-valor consistir em <code> color=blue </code>, retornará <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Matriz de strings </p> </td> 
   <td colname="col3"> <p>Retorna valores em uma matriz, por exemplo, <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Retorna a ID de usuário do Audience Manager, por exemplo, <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Criar um destino com GPT](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Código do Audience Manager para Tags do Google Publisher](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

