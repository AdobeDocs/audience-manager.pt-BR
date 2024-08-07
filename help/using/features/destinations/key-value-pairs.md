---
description: A [!DNL key-value pair] consiste de [!DNL related elements]. Uma chave, que é uma constante que define o conjunto de dados (por exemplo, gênero, cor, preço) e um valor, que é uma variável que pertence ao conjunto (por exemplo, masculino/feminino, verde, 100). O Construtor de destinos envia dados formatados como pares de valores chave.
solution: Audience Manager
title: Padrão e Serial [!DNL Key-value pairs]
uuid: 43789419-5b3f-4e62-b2e0-2722340bdd41
feature: Destination Basics
exl-id: b37c829b-66be-4c31-8198-bc032371279e
source-git-commit: 0dfe96a4644c61fb5bc22e4791bfd09c574dcf34
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# Pares padrão e de valor-chave serial {#standard-and-serial-key-value-pairs}

Um par de valores chave consiste em elementos relacionados: uma chave, que é uma constante que define o conjunto de dados (por exemplo: gênero, cor, preço) e um valor, que é uma variável que pertence ao conjunto (por exemplo, masculino/feminino, verde, 100). [!UICONTROL Destination Builder] envia dados formatados como pares de valores chave.

## Pares básicos de valor-chave {#basic-key-value-pairs}

Totalmente formado, um conjunto básico de par de valor-chave pode se parecer com o seguinte:

* `gender = male`
* `color = green`
* `price > 100`

## Pares padrão e de valor-chave serial {#standard-serial-key-value-pairs}

Os destinos aceitam dados de valores-chave no formato *`standard`* ou *`serialized`*.

* **Pares de valor-chave padrão:** Formata os dados de destino em pares de valor-chave separados. Cada chave é declarada explicitamente, mesmo quando usada novamente para definir um valor diferente.
* **Pares de valor-chave serializados:** Condensa vários valores em um único par de valor-chave. Em um par de valor-chave serializado, um indicador especial separa os valores no conjunto de valor-chave.

Os valores-chave padrão e serializados podem conter um ou vários valores. A tabela a seguir fornece exemplos de formatos de valor-chave padrão e serial.

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formatação </th>
   <th colname="col2" class="entry"> Pares de valor-chave únicos </th>
   <th colname="col3" class="entry"> Vários pares de valor-chave </th>
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
   <td colname="col2"> <p> <code> x = 1 ; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1 ; 2 &amp; y = 3 ; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## Delimitadores e Separadores {#delimiters-separators}

Os caracteres que separam valores dentro e entre chaves e valores são conhecidos como *`delimiters`* e *`separators`*. Isso se torna particularmente importante quando você envia segmentos para um destino em um formato serial. A serialização permite transmitir vários valores com uma única chave e combinar pares de valores chave. Os delimitadores e separadores são definidos do seguinte modo:

* **Separador de valor-chave:** separa uma chave e um valor em um par de valor-chave.
* **Delimitador de valor-chave:** separa conjuntos de pares de valor-chave.
* **Separador serial:** separa vários valores em conjuntos de pares de valores-chave serializados.

## Exemplos {#examples}

Com [!UICONTROL Destination Builder] você pode formatar dados de valores-chave de várias maneiras diferentes. Vamos analisar alguns exemplos de cada tipo.

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemplos de par de valor-chave </th> 
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
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">Delimitador de valor-chave: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Vários pares de valor-chave</b> (não-serial) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>Um conjunto de vários pares de valores chave que transmitem valores com conjuntos separados de valores chave. O exemplo contém estes elementos: </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">Chaves: X, Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">Valores: 1, 2, 3, 4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">Separador: = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">Delimitador de valor-chave: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Chave única serial</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 ; 3 </code> </p> </td> 
   <td colname="col3"> <p>Um conjunto de valores chave que passa vários valores com uma única chave. Como essa chave tem vários valores, ela é conhecida como um par de valores-chave serializado. O exemplo contém estes elementos: </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">Chave: X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">Valores: 1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">Separador: = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">Separador serial: ponto e vírgula </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Vários pares de valor-chave</b> (serial) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 &amp; Y = 3 ; 4 </code> </p> </td> 
   <td colname="col3"> <p>Um conjunto de vários pares de valor-chave que transmitem vários valores em chaves separadas. O exemplo contém estes elementos: </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">Chaves: X, Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">Valores: 1, 2, 3, 4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">Separador: = </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">Delimitador: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">Separador serial: ponto e vírgula </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Serialização de destino {#destination-serialized}

Um destino serializado combina várias características em uma única cadeia de caracteres e envia essas informações para um destino.

<!-- c_dest_serialized.xml -->

A transmissão de dados serializada ajuda a melhorar a eficiência, pois várias características são acionadas sequencialmente, em vez de em paralelo. Isso proporciona ao servidor de destino tempo suficiente para receber, processar e retornar dados antes de responder a solicitações adicionais.

### Destinos suportados

No [!DNL Audience Manager], você pode serializar e enviar dados para praticamente qualquer destino com o qual deseje trabalhar. No entanto, antes de usar este recurso, você precisará saber o destino [!DNL URL] e onde colocar algumas macros obrigatórias ou opcionais. Obtenha as informações sobre posicionamento de macro do parceiro de destino. Consulte [Macros de destino definidas](../../features/destinations/destination-macros.md#destination-macros-defined) para obter mais informações.
