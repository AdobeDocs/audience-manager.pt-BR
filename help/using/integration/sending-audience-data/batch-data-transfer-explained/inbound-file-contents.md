---
description: Campos, sintaxe e regras necessários que devem ser seguidos ao formatar um arquivo de dados de característica de entrada.
seo-description: Campos, sintaxe e regras necessários que devem ser seguidos ao formatar um arquivo de dados de característica de entrada.
seo-title: Sintaxe de conteúdo de arquivo de dados de entrada, caracteres inválidos, variáveis e exemplos
solution: Audience Manager
title: Sintaxe de conteúdo de arquivo de dados de entrada, caracteres inválidos, variáveis e exemplos
uuid: 88699 b 29-1502-4183-a 9 a 4-be 70692 a 02 bb
translation-type: tm+mt
source-git-commit: 5a822460f93bb7295edafff03104ae7626b69a51

---


# Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples{#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

Campos, sintaxe e regras necessários que devem ser seguidos ao formatar um arquivo de dados de característica de entrada.

## File Content Syntax {#file-content-syntax}

Os campos no arquivo de dados de entrada devem aparecer na ordem mostrada abaixo. In this example, the `<` `>` symbols have been added to help separate each element visually. Não é necessário incluí-los em seu arquivo de dados.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

For other accepted file content formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>Temos um limite de 200 linhas que podemos processar para cada ID de usuário enviada no arquivo de dados de entrada. Por exemplo, se você enviar 300 linhas para uma ID de usuário, as primeiras 200 linhas serão mantidas e as 100 linhas adicionais serão descartadas. No exemplo abaixo, você é bom, pois está enviando 3 linhas cada uma para a ID de usuário 1 e a ID de usuário 2. Não impuímos um limite no número de características ou pares de valores chave que você incluir em uma linha.
>
>```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## File Variables Defined {#file-variables-defined}

A tabela lista e define as variáveis usadas em um arquivo de dados de entrada devidamente formatado. *Itálico* indica um marcador de posição variável.

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variável </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>ID de usuário </i> </code> </p> </td> 
   <td colname="col2"> <p>Uma ID de usuário pode ser: </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B">A unique user ID assigned by <span class="keyword"> Audience Manager </span> ( <a href="../../../reference/ids-in-aam.md"> Audience Manager UUID </a>). </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">A unique user ID assigned in your CRM system ( <a href="../../../reference/ids-in-aam.md"> DPUUID, in Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">Uma ID do dispositivo Android ou iOS móvel em seu formulário original e não modificado, como exposto pelo sistema operacional móvel. </li> 
     </ul> </p> <p>Para IDs móveis: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">formato IDFA: As IDs devem ser letras maiúsculas e minúsculas e não hash. For example, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Formato Android: As IDs devem ser letras minúsculas e não hash. For example, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Separe a ID de usuário e as IDs características com um único delimitador de tabulação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>ID de característica </i></code> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> Audience Manager </span> trait ID. We ask that you include <i>only onboarded traits</i> in inbound data files. Não processamos nenhum outro tipo de característica na transferência de dados de entrada. </p> <p> <p>Observação: A ID de característica pode ser encontrada usando o método GET que retorna detalhes sobre todas as suas características. For more information, see <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formatting Trait IDs {#formatting-trait-ids}

A tabela a seguir descreve os prefixos que identificam nomes ou IDs de característica em um arquivo de dados de entrada. See the [sample files](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) for examples.

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prefixo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ sid = </code> </p> </td> 
   <td colname="col2"> <p>The <code> d_sid </code> prefix tells our system that the ID is an <span class="keyword"> Audience Manager </span> trait ID. Essa é a mesma ID exibida na interface do usuário. You can also return trait IDs with the API <code> GET </code> method. See <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_ unsid = </code> </p> </td> 
   <td colname="col2"> <p>Data prefixed with <code> d_unsid </code> removes users from that trait. The <code> d_unsid </code> prefix is ignored in an <code> overwrite </code> file. </p> <p>The <code> d_unsid= </code> prefix tells our system that the ID is an <span class="keyword"> Audience Manager </span> trait ID. Essa é a mesma ID exibida na interface do usuário. You can also return trait IDs with the API <code> GET </code> method. See <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic = </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> As regras de características </a> permitem definir critérios para a qualificação de características. If you format a trait rule as <code> ic == trait ID </code>, you can send in traits in a simple comma formatted list. </p> <p>Por exemplo, digamos que você crie essas duas regras de características: </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic = = "123" </code> </li>
      <li> <code> ic = = "456" </code> </li>
      <li> <code> ic = = "789" </code> </li>
     </ul> </p> <p>These traits are associated with the <code> ic </code> key. Isso permite criar uma lista de características mais simples no arquivo de dados. And, you do not need to include the <code> ic </code> prefix. Como resultado, o conteúdo de seu arquivo de dados pode ser parecido com: </p> <p>
     <code><i>ID de usuário</i>&lt; TAB &gt; 123,456,789 </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pares de valores chave </p> </td> 
   <td colname="col2"> <p>Os dados características podem ser formatados como pares de valores chave usando strings alfanuméricas. Há várias maneiras de formatação de pares de valores chave, como mostrado abaixo: </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> " key " = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> " key " =" value " </code> </li> 
     </ul><code> " idade " =" 32 " </code> , <code> " gênero " = m </code> , <code> model =" caminhão de verificação " </code> , <code> product = tablet </code> são todos exemplos de pares de valores chave corretamente formatados. </p> </td> 
  </tr>
 </tbody>
</table>

## Invalid Characters in Trait IDs, User IDs and Key-Value Pairs {#invalid-chars}

### IDs de características

As IDs características são constituídas por caracteres numéricos. We ask that you include *only onboarded traits* in inbound data files. Não processamos nenhum outro tipo de característica na transferência de dados de entrada.

### IDs de usuário

<table id="table_8C5C7271B813441EA2D45CA2FE2A6C59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de ID </th> 
   <th colname="col2" class="entry"> Requisito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p><i>Não</i> use um sinal de dois pontos ( <code> % 3 A </code>) ou dois pontos não codificados (: ) em dpuuids. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID do dispositivo móvel (IDFA) ou Android </p> </td> 
   <td colname="col2"> <p>As IDs de dispositivo móvel devem ser formatadas corretamente conforme mostrado aqui: </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">formato IDFA: As IDs devem ser letras maiúsculas e minúsculas e não hash. For example, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Formato Android: As IDs devem ser letras minúsculas e não hash. For example, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Pares de valores chave

Nomes de valores formatados incorretamente em um par de valor chave também causam problemas. Siga estas regras ao criar ou nomear o valor em um par de valor chave:

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caractere </th> 
   <th colname="col2" class="entry"> Requisito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caractere de aspas (") </p> </td> 
   <td colname="col2"> <p>Você pode usar o caractere de aspas na chave e, na parte do valor do par de valor chave, como: </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_ city = "New York", d_ city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> " d_ city " =" New York "," d_ city " =" San Francisco " </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caractere traço (-) </p> </td> 
   <td colname="col2"> <p>Ignoramos os sinais de traço no início das teclas. For example, <code> -product = camera </code> is interpreted as <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>Não</i> use <code> TAB </code> em vez de valores vazios em pares de valor chave. Only use <code> TAB </code> to separate variables in the inbound data file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \ n,\ t </code> </p> </td> 
   <td colname="col2"> <p>Do not use the new line or tab characters ( <code> \n, \t </code>) in keys or in values. </p> </td> 
  </tr>
 </tbody>
</table>

## Data File Examples {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formato do arquivo de dados </th> 
   <th colname="col2" class="entry"> Descrição e exemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>With <code> d_sid </code> or <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>Esse arquivo de dados mostra um usuário qualificado para características 24, 26, 27 e foi removido das características 28 e 29. </p> <p> 
     <code>59767559181262060060278870901087098252 &amp; amp; nbsp; &amp; amp; nbsp; d_ sid = 24, d_ sid = 26, d_ sid = 27, d_ unsid = 28, d_ unsid = 29 </code>
  </p> <p>Observação:  <p>Em vez de usar d_ unsid, você também pode remover características dos perfis do usuário usando a seguinte sintaxe: </p> <p> 
      <code>59767559181262060060278870901087098252 &amp; amp; nbsp; 28:0 e amp; nbsp; 29:0 </code>
  </p> <p> 
      <code>59767559181262060060278870901087098252 &amp; amp; nbsp; 28:-1, &amp; amp; nbsp; 29:-1 </code>
  </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>With <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>These traits have been added to a trait rule with the <code> ic </code> prefix. Dessa forma, é possível adicioná-los ao arquivo de dados separado por vírgulas como mostrado. Uma guia separa o UUID e as IDs características. The <code> ic </code> prefix is not required in the file. </p> <p><b>IDs numéricas</b> </p> <p> 
     <code>Dbwsmu3 dhfmncfbh 2 M 4 F 9 zkjexmnnrdh 2 pxvni 1 &amp; amp; nbsp; &amp; amp; nbsp; 30608,50354,50338,50352,30626 </code>
  </p> <p><b>IDs de string</b> </p> <p> 
     <code>Dbwsmu3 dhfmncfbh 2 M 4 F 9 zkjexmnnrdh 2 pxvni 1 &amp; amp; nbsp; &amp; amp; nbsp; ic = 52, ic = 55 </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Com pares de valor chave </p> </td> 
   <td colname="col2"> This file data uses key-value pairs to pass in data to <span class="keyword"> Audience Manager </span>. <p> 
     <code>59767559181262060060278870901087098252 &amp; amp; nbsp; «gender» =» women», «luxury_ shopper» =» yes» </code>
  </p> </td> 
  </tr> 
 </tbody> 
</table>

[Baixe](assets/ftp_dpm_1234_1445374061.overwrite) o arquivo de dados de amostra caso precise de mais exemplos. The download file has a `.overwrite` file extension. Você pode abri-lo com um editor de texto simples.

## Examples Matrix {#examples-matrix}

The chart below shows examples of the correct way to format your Inbound files, depending on the [type of IDs](../../../reference/ids-in-aam.md) and the method by which you want to add traits to profiles.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de ID/Operação </th> 
   <th colname="col2" class="entry"> Usar d_ sid para adicionar características a um perfil de usuário </th> 
   <th colname="col3" class="entry"> Usar d_ unsid para remover características de um perfil de usuário </th> 
   <th colname="col4" class="entry"> Enviar pares de valor chave para adicionar características a um perfil de usuário </th> 
   <th colname="col5" class="entry"> Use o prefixo ic para adicionar características a um perfil de usuário </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>UUID do Audience Manager </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> Exemplo 1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> Exemplo 2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> Exemplo 3 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> Exemplo 4 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de publicidade do Google para dispositivos Android </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> Exemplo 5 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> Exemplo 6 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> Exemplo 7 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> Exemplo 8 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apple IDFA para dispositivos iOS </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> Exemplo 9 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> Exemplo 10 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> Exemplo 11 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> Exemplo 12 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sua própria ID de CRM (DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> Exemplo 13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> Exemplo 14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> Exemplo 15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> Exemplo 16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemplo 1 {#example-1}

Use IDs características para enviar informações de qualificação de característica para uuids do Audience Manager.

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Exemplo 2 {#example-2}

Use IDs características para enviar informações de desqualificação de característica para uuids do Audience Manager.

```
59767559181262060060278870901087098252 <TAB> d_unsid=24, d_unsid=26, d_unsid=27
```

ou

```
59767559181262060060278870901087098252 <TAB> 24:0, 26:0, 27:0
```

ou

```
59767559181262060060278870901087098252 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 3 {#example-3}

Envie pares de valor chave para adicionar informações de qualificação de característica para uuids do Audience Manager.

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

ou

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 4 {#example-4}

Use o prefixo ic para enviar informações de qualificação de característica para uuids do Audience Manager.

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

ou

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Example 5 {#example-5}

Use IDs características para enviar informações de qualificação de característica para dispositivos Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 6 {#example-6}

Use IDs características para enviar informações de desqualificação de característica para dispositivos Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

ou

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:0, 26:0, 27:0
```

ou

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 7 {#example-7}

Envie pares de valor chave para adicionar informações de qualificação de característica para dispositivos Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

ou

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 8 {#example-8}

Use o prefixo ic para enviar informações de qualificação de característica para dispositivos Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

ou

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Example 9 {#example-9}

Use IDs características para enviar informações de qualificação de características para dispositivos iOS.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 10 {#example-10}

Use IDs características para enviar informações de desqualificação de característica para dispositivos iOS.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

ou

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:0, 26:0, 27:0
```

ou

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:-1, 26:-1, 27:-1
```

### Example 11 {#example-11}

Envie pares de valor chave para adicionar informações de qualificação de características para dispositivos iOS.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

ou

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Example 12 {#example-12}

Use o prefixo ic para enviar informações de qualificação de características para dispositivos iOS.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

ou

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Example 13 {#example-13}

Use IDs características para enviar informações de qualificação de característica para dpuuids.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 14 {#example-14}

Use IDs características para enviar informações de desqualificação de característica para dpuuids.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

ou

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:0, 26:0, 27:0
```

ou

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 15 {#example-15}

Envie pares de valor chave para adicionar informações de qualificação de característica para dpuuids.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

ou

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 16 {#example-16}

Use o prefixo ic para enviar informações de qualificação de característica para dpuuids.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

ou

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORE_ LIKE_ THIS]
>
>* [Construtor de perfil](../../../features/traits/about-trait-builder.md)

