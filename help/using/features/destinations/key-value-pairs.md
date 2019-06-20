---
description: Um par de valor chave consiste em elementos relacionados A chave, que é uma constante que define o conjunto de dados (por exemplo, sexo, cor, preço) e um valor, que é uma variável que pertence ao conjunto (por exemplo, masculino/feminino, verde, 100). O Construtor de destinos envia dados formatados como pares de valores chave.
seo-description: Um par de valor chave consiste em elementos relacionados A chave, que é uma constante que define o conjunto de dados (por exemplo, sexo, cor, preço) e um valor, que é uma variável que pertence ao conjunto (por exemplo, masculino/feminino, verde, 100). O Construtor de destinos envia dados formatados como pares de valores chave.
seo-title: Pares de valores-chave padrão e padrão
solution: Audience Manager
title: Pares de valores-chave padrão e padrão
uuid: 43789419-5 b 3 f -4 e 62-b 2 e 0-2722340 bdd 41
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Standard and Serial Key-Value Pairs {#standard-and-serial-key-value-pairs}

Um par de valor chave consiste em elementos relacionados: Uma chave, que é uma constante que define o conjunto de dados (por exemplo, sexo, cor, preço) e um valor, que é uma variável que pertence ao conjunto (por exemplo, masculino/feminino, verde, 100). [!UICONTROL Destination Builder] envia dados formatados como pares de valores chave.

## Basic Key-Value Pairs {#basic-key-value-pairs}

Completamente formado, um conjunto básico de par de valor chave pode ser parecido com:

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serial Key-Value Pairs {#standard-serial-key-value-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format.

* **Pares de valores chave-chave:** Formata os dados de destino em pares de valor chave separados. Cada chave é declarada explicitamente, mesmo quando usada novamente para definir um valor diferente.
* **Pares de valores chave serializados:** Condula vários valores em um único par de valor chave. Em um par de valor chave serializado, um indicador especial separa os valores dentro do conjunto de valores chave.

Os valores de chave padrão e serializados podem conter valores únicos ou múltiplos. A tabela a seguir fornece exemplos de formatos padrão e de valor de chave de série.

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formatação </th>
   <th colname="col2" class="entry"> Pares de valores chave-chave </th>
   <th colname="col3" class="entry"> Vários pares de valores chave </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Padrão</b> </p> </td>
   <td colname="col2"> <p> <code> x = 1 &amp; x = 2 </code> </p> </td>
   <td colname="col3"> <p> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Serializado</b> </p> </td> 
   <td colname="col2"> <p> <code> x = 1; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1; 2 &amp; y = 3; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## Delimiters and Separators {#delimiters-separators}

The characters that separate values within and between keys and values are known as *`delimiters`* and *`separators`*. Elas se tornam particularmente importantes quando você envia segmentos para um destino em um formato de série. A serialização permite passar vários valores com uma única chave e combinar pares de valores chave. Os delimitadores e separadores são definidos da seguinte maneira:

* **Separador de valor chave:** Separa uma chave e um valor dentro de um par de valor chave.
* **Delimitador de valor chave:** Separa conjuntos de pares de valor chave.
* **Separador de série:** Separa vários valores dentro dos conjuntos de pares de valor chave serializado.

## Exemplos {#examples}

With [!UICONTROL Destination Builder] you can format key-value data in several different ways. Vejamos alguns exemplos de cada tipo.

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemplos de par de valores chave </th> 
   <th colname="col2" class="entry"> Exemplo </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Chave única padrão</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>Um conjunto simples de pares de valores chave. O exemplo contém estes elementos: </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">Chave: X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">Valores: 1, 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">Separador: = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">Delimitador de valor chave: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Vários pares de valor chave</b> (não serial) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>Um conjunto de vários pares de valores chave que passam valores com conjuntos de valores chave separados. O exemplo contém estes elementos: </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">Teclas: X, Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">Valores: 1, 2, 3, 4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">Separador: = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">Delimitador de valor chave: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Chave única em série</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1; 2; 3 </code> </p> </td> 
   <td colname="col3"> <p>Um conjunto de valores chave que passa em vários valores com uma única chave. Como essa chave tem vários valores, ela é conhecida como um par de valor chave serializado. O exemplo contém estes elementos: </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">Chave: X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">Valores: 1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">Separador: = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">Separador de série: ponto e vírgula </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Vários pares de valor chave</b> (serial) </p> </td> 
   <td colname="col2"> <p> <code> X = 1; 2 &amp; Y = 3; 4 </code> </p> </td> 
   <td colname="col3"> <p>Um conjunto de vários pares de valores chave que passam vários valores em chaves separadas. O exemplo contém estes elementos: </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">Teclas: X, Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">Valores: 1, 2, 3, 4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">Separador: = </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">Delimitador: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">Separador de série: ponto e vírgula </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Destination Serialization {#destination-serialized}

Um destino serializado combina várias características em uma única string e envia essas informações para um destino.

<!-- c_dest_serialized.xml -->

A transmissão de dados serializados ajuda a melhorar a eficiência, pois várias características são acionadas sequencialmente, em vez de simultaneamente. Isso fornece ao servidor de destino tempo suficiente para receber, processar e retornar dados antes de responder a solicitações adicionais.

### Destinos suportados

In [!DNL Audience Manager], you can serialize and send data to just about any destination you want to work with. However, before using this feature, you will need to know the destination [!DNL URL] and where to place some required or optional macros. Obtenha as informações sobre o posicionamento de macro do seu parceiro de destino. See [Destination Macros Defined](../../features/destinations/destination-macros.md#destination-macros-defined) for more information.