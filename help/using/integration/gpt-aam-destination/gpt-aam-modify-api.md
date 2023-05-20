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
source-wordcount: '274'
ht-degree: 7%

---

# Modificar o GPT `setTargeting` Chamada de API {#modify-the-gpt-settargeting-api-call}

Adicione uma instrução if para verificar se há cookies Audience Manager antes de chamar o [!DNL Google Publisher Tag] `.setTargeting` método.

## Verifique se há cookies Audience Manager com um `IF` Declaração

A variável `.setTargeting` O método do obtém dados do cookie de destino do Audience Manager e do cookie de ID de usuário exclusiva ( `aam_uuid`). No entanto, se `.setTargeting` é chamado antes de [!UICONTROL DIL] O grava esses cookies ou eles estão vazios, talvez você veja erros quando a página for carregada. Para ajudar a evitar isso, envolva o `.setTargeting` em um `if` que verifica a existência desses cookies. Se não estiverem definidos, essa instrução impede `.setTargeting` de chamar o `AamGpt` função.

### `IF` Amostra de código do demonstrativo

Neste exemplo, o nome do cookie de destino do Audience Manager é `Sample`. Você define esse nome ao criar o cookie de destino na interface de usuário do Audience Manager. [!UICONTROL DIL] define o `aam_uuid` cookie e o nome não podem ser alterados.

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
>Dependendo de como você deseja integrar o com o [!DNL Google Ad Manager], você só precisa de algumas das linhas na amostra de código acima:
>
>* Integração do lado do cliente: use somente as linhas 1-3.
>* Integração do lado do servidor: nenhuma das linhas é necessária.
>* Assimilar [!DNL Google Ad Manager] arquivos de log para relatórios no [!DNL Audience Manager]: use somente as linhas 4 a 6. Esse código insere o valor de `aam_uuid` cookies nos logs para que eles possam ser assimilados para relatórios.


### `AamGpt` Funções e tipos de dados

Define as variáveis principais usadas na variável `if` declaração.

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
   <td colname="col3"> <p>Retorna a chave no par de segmentos de valor-chave. Por exemplo, se seu par de valor-chave consistia de <code> color=blue </code>, isso retorna <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Matriz de cadeias de caracteres </p> </td> 
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

