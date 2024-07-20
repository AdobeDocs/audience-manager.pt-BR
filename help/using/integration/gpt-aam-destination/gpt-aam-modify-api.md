---
description: Adicione uma instrução if para verificar se há cookies Audience Manager antes de chamar o método .setTargeting da tag do Google Publisher.
seo-description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-title: Modify the GPT setTargeting API Call
solution: Audience Manager
title: Modificar a chamada da API setTargeting GPT
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---

# Modificar a chamada à API `setTargeting` do GPT {#modify-the-gpt-settargeting-api-call}

Adicione uma instrução if para verificar se há cookies Audience Manager antes de chamar o método [!DNL Google Publisher Tag] `.setTargeting`.

## Verificar Cookies Audience Manager com uma Instrução `IF`

O método `.setTargeting` obtém dados do cookie de destino do Audience Manager e do cookie de ID de usuário exclusiva ( `aam_uuid`). No entanto, se `.setTargeting` for chamado antes de [!UICONTROL DIL] gravar esses cookies, ou se os cookies estiverem vazios, você poderá ver erros quando a página for carregada. Para ajudar a evitar isso, envolva o método `.setTargeting` em uma instrução `if` que verifique esses cookies. Se não estiverem definidos, esta instrução impede `.setTargeting` de chamar a função `AamGpt`.

### Amostra de código da instrução `IF`

Neste exemplo, o nome do cookie de destino do Audience Manager é `Sample`. Você define esse nome ao criar o cookie de destino na interface de usuário do Audience Manager. [!UICONTROL DIL] define o cookie `aam_uuid` e o nome não pode ser alterado.

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
>Dependendo de como você deseja integrar com o [!DNL Google Ad Manager], você só precisará de algumas das linhas no exemplo de código acima:
>
>* Integração do lado do cliente: use somente as linhas 1-3.
>* Integração do lado do servidor: nenhuma das linhas é necessária.
>* Assimilar arquivos de log [!DNL Google Ad Manager] para relatórios em [!DNL Audience Manager]: use somente as linhas 4-6. Este código insere o valor do cookie `aam_uuid` nos logs para que eles possam ser assimilados para relatórios.

### `AamGpt` Funções e Tipos de Dados

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
   <td colname="col3"> <p>Retorna a chave no par de segmentos de valor-chave. Por exemplo, se o seu par de valor-chave consistia de <code> color=blue </code>, ele retornaria <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Matriz de cadeias de caracteres </p> </td> 
   <td colname="col3"> <p>Retorna valores em uma matriz, por exemplo, <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Retorna a ID de usuário Audience Manager, por exemplo, <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Criar um destino com GPT](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Código do Audience Manager para Tags do Google Publisher](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)
