---
description: Ao fazer uma chamada, o DCS aceita dados de valor chave em formato padrão ou serializado. Consulte esta seção para obter informações sobre como formatar dados de valores chave padrão e serializados.
seo-description: Ao fazer uma chamada, o DCS aceita dados de valor chave em formato padrão ou serializado. Consulte esta seção para obter informações sobre como formatar dados de valores chave padrão e serializados.
seo-title: Formatação de pares de valores-chave em chamadas DCS
solution: Audience Manager
title: Formatação de pares de valores-chave em chamadas DCS
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 12%

---


# Formatação de pares de valores-chave em chamadas DCS {#formatting-key-value-pairs-in-dcs-calls}

Ao fazer uma chamada, [!DNL DCS] aceita dados de valor chave em formato padrão ou serializado. Consulte esta seção para obter informações sobre como formatar dados de valores chave padrão e serializados.

## Pares padrão e serializados de valores chave {#standard-serialized}

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
   <td colname="col2"> <p>Um par de valores chave padrão consiste em uma única chave e valor. Essa estrutura organiza os dados em pares de valores chave separados. Cada chave é declarada explicitamente, mesmo quando é usada novamente para definir um valor diferente. Essa é a maneira mais comum de enviar dados para o DCS. </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Serializado</b> </td> 
   <td colname="col2"> <p>Um par serializado de valores chave consiste em uma única chave e vários valores. Essa pode ser uma maneira eficiente de organizar dados, mas pares serializados de valores chave exigem símbolos específicos para separar cada chave e cada conjunto de valores chave. </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## Delimitadores e separadores para pares de valores chave serializados {#delimiters-separators}

Com pares serializados de valores chave, você deve especificar os marcadores que separam valores dentro e entre essas variáveis. Audience Manager requer os seguintes delimitadores e separadores:

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Requisitos para </th> 
   <th colname="col2" class="entry"> Símbolo </th> 
   <th colname="col3" class="entry"> Separa individual </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Delimitadores</b> </td> 
   <td colname="col2"> E comercial &amp; </td> 
   <td colname="col3"> <p>Pares de valor chave: </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
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
>* [Prefixos e variáveis de valor-chave suportados pelo DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [Explicação dos pares de valor-chave](../../../reference/key-value-pairs-explained.md)

