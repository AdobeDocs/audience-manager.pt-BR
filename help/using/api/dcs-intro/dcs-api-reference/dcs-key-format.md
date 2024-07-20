---
description: Ao fazer uma chamada, o DCS aceita dados de valores-chave em formato padrão ou serializado. Consulte esta seção para obter informações sobre como formatar dados de valor-chave padrão e serializados.
seo-description: When making a call, the DCS accepts key-value data in standard or serialized format. Review this section for information about how to format standard and serialized key-value data.
seo-title: Formatting Key-Value Pairs in DCS Calls
solution: Audience Manager
title: Formatação de pares de valores-chave em chamadas DCS
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
feature: DCS
exl-id: ff2d9ff6-7d5b-4a0d-b831-5d9bc79b32a1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Formatação de pares de valores-chave em chamadas DCS {#formatting-key-value-pairs-in-dcs-calls}

Ao fazer uma chamada, o [!DNL DCS] aceita dados de valores-chave em formato padrão ou serializado. Consulte esta seção para obter informações sobre como formatar dados de valor-chave padrão e serializados.

## Pares de valor-chave padrão e serializados {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de valor-chave </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Exemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Padrão</b> </td> 
   <td colname="col2"> <p>Um par padrão de valor-chave consiste em uma única chave e valor. Essa estrutura organiza os dados em pares de valores chave separados. Cada chave é declarada explicitamente, mesmo quando usada novamente para definir um valor diferente. Essa é a maneira mais comum de enviar dados para o DCS. </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Serializado</b> </td> 
   <td colname="col2"> <p>Um par de valor-chave serializado consiste em uma única chave e vários valores. Essa pode ser uma maneira eficiente de organizar dados, mas pares de valores-chave serializados exigem símbolos específicos para separar cada chave e cada conjunto de valores-chave. </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## Delimitadores e Separadores para Pares de Valor-Chave Serializados {#delimiters-separators}

Com pares de valores chave serializados, você deve especificar os marcadores que separam valores dentro e entre essas variáveis. O Audience Manager exige os seguintes delimitadores e separadores:

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Requisitos para </th> 
   <th colname="col2" class="entry"> Símbolo </th> 
   <th colname="col3" class="entry"> Separa Indivíduo </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Delimitadores</b> </td> 
   <td colname="col2"> E comercial e </td> 
   <td colname="col3"> <p>Pares de valor-chave: </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Separadores</b> </td> 
   <td colname="col2"> Vírgula , </td> 
   <td colname="col3"> <p>Valores em pares de valores chave: </p> <p><code> key1=val1,val2,val3&amp;key2=valA,valB,valC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Enviar dados para o DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [Prefixos e Variáveis de Valor-Chave com Suporte do DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [Explicação dos pares de valor-chave](../../../reference/key-value-pairs-explained.md)
