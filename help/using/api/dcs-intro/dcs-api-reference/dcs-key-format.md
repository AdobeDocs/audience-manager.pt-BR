---
description: Ao fazer uma chamada, o DCS aceita dados de valor chave no formato padrão ou serializado. Analise esta seção para obter informações sobre como formatar dados padrão e serializados de valor-chave.
seo-description: Ao fazer uma chamada, o DCS aceita dados de valor chave no formato padrão ou serializado. Analise esta seção para obter informações sobre como formatar dados padrão e serializados de valor-chave.
seo-title: Formatação de pares de valores chave em chamadas DCS
solution: Audience Manager
title: Formatação de pares de valores chave em chamadas DCS
uuid: af 02 f 2 a 1-4388-4074-ab 4 e -66 ee 82023 f 1 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Formatting Key-Value Pairs in DCS Calls {#formatting-key-value-pairs-in-dcs-calls}

When making a call, the [!UICONTROL DCS] accepts key-value data in standard or serialized format. Analise esta seção para obter informações sobre como formatar dados padrão e serializados de valor-chave.

## Standard and Serialized Key-Value Pairs {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de valor principal </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Exemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Padrão</b> </td> 
   <td colname="col2"> <p>Um par de valor chave padrão consiste em uma única chave e valor. Essa estrutura organiza os dados em pares de valor chave separados. Cada chave é declarada explicitamente, mesmo quando é usada novamente para definir um valor diferente. Essa é a maneira mais comum de enviar dados para o DCS. </p> </td>
   <td colname="col3"> <code> key 1 = val 1 &amp; key 2 = val 2 &amp; key 3 = val 3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Serializado</b> </td> 
   <td colname="col2"> <p>Um par de valor chave serializado consiste em uma única chave e vários valores. Essa pode ser uma maneira eficiente de organizar dados, mas os pares de valor chave serializado exigem símbolos específicos para separar cada chave e cada conjunto de valores chave. </p> </td> 
   <td colname="col3"> <code> key 1 = val 1, val 2, val 3</code> </td> 
  </tr>
 </tbody>
</table>

## Delimiters and Separators for Serialized Key-Value Pairs {#delimiters-separators}

Com pares de valor chave serializado, você deve especificar os marcadores que separam valores dentro e entre essas variáveis. O Audience Manager exige os seguintes delimitadores e separadores:

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Requisitos para </th> 
   <th colname="col2" class="entry"> Símbolo </th> 
   <th colname="col3" class="entry"> Separar individuais </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Delimitadores</b> </td> 
   <td colname="col2"> E Comercial e </td> 
   <td colname="col3"> <p>Pares de valores chave: </p> <p><code> key 1 = val 1 &amp; key 2 = val 2, val 3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Separadores</b> </td> 
   <td colname="col2"> Vírgula , </td> 
   <td colname="col3"> <p>Valores nos pares de valor chave: </p> <p><code> key 1 = val 1, val 2, val 3 &amp; key 2 = vala, valb, valc</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Enviar dados para o DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [Prefixos de valores chave e variáveis suportadas pelo DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [Pares de valores chave explicados](../../../reference/key-value-pairs-explained.md)

