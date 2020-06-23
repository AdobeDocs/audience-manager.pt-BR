---
description: Campos obrigatórios, sintaxe e regras que você deve seguir ao formatar um arquivo de dados de característica de entrada.
seo-description: Campos obrigatórios, sintaxe e regras que você deve seguir ao formatar um arquivo de dados de característica de entrada.
seo-title: Sintaxe de conteúdo do arquivo de dados de entrada, caracteres inválidos, variáveis e exemplos
solution: Audience Manager
title: Sintaxe de conteúdo do arquivo de dados de entrada, caracteres inválidos, variáveis e exemplos
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
translation-type: tm+mt
source-git-commit: 620730ab1596d4777a768de4453b73538671279d
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 4%

---


# Conteúdo do arquivo de dados de entrada: Sintaxe, caracteres inválidos, variáveis e exemplos {#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

Campos obrigatórios, sintaxe e regras que você deve seguir ao formatar um arquivo de dados de característica de entrada.

## Sintaxe de conteúdo de arquivo {#file-content-syntax}

Os campos no arquivo de dados de entrada devem aparecer na ordem mostrada abaixo. Neste exemplo, os `<` `>` símbolos foram adicionados para ajudar a separar cada elemento visualmente. Não é necessário incluí-los no arquivo de dados.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

Para obter outros formatos de conteúdo de arquivo aceitos, consulte Integrações [](/help/using/integration/sending-audience-data/custom-partner-integrations.md)personalizadas de parceiros.

>[!NOTE]
>
>Temos um limite de 200 linhas que podem ser processadas para cada ID de usuário enviada no arquivo de dados de entrada. Por exemplo, se você enviar 300 linhas para uma ID de usuário, as primeiras 200 linhas serão mantidas e as 100 linhas adicionais serão descartadas. No exemplo abaixo, você está bem porque está enviando 3 linhas cada para a ID de usuário 1 e a ID de usuário 2. Não impomos um limite no número de características ou pares de valores chave que você inclui em uma linha.
>
>
```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## Variáveis de arquivo definidas {#file-variables-defined}

A tabela lista e define as variáveis usadas em um arquivo de dados de entrada corretamente formatado. *Itálico* indica um marcador de posição variável.

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variável </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>User ID </i> </code> </p> </td> 
   <td colname="col2"> <p>Uma ID de usuário pode ser: </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B">Uma ID de usuário exclusiva atribuída por <span class="keyword"> Audience Manager </span> ( <a href="../../../reference/ids-in-aam.md"> Audience Manager UUID </a>). </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">Uma ID de usuário exclusiva atribuída no sistema CRM ( <a href="../../../reference/ids-in-aam.md"> DPUUID, no Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">Uma ID de dispositivo Android ou iOS móvel em sua forma original e não modificada, como exposta pelo sistema operacional móvel. </li> 
     </ul> </p> <p>Para IDs móveis: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">Formato IDFA: As IDs devem estar em maiúsculas e não em hash. Por exemplo, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Formato Android: As IDs devem estar em minúsculas e não devem ter hash. Por exemplo, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Separe a ID de usuário e as IDs de característica com um único delimitador de guia. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p>A ID <span class="keyword"> Audience Manager </span> . Solicitamos que você inclua <i>apenas traços</i> integrados em arquivos de dados de entrada. Não processamos nenhum outro tipo de característica na transferência de dados de entrada. </p> <p> <p>Observação:  A ID de característica pode ser encontrada usando o método GET que retorna detalhes sobre todas as suas características. Para obter mais informações, consulte Métodos <a href="../../../api/rest-api-main/api-traits.md"> de API de características </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formatação [!UICONTROL Trait IDs] {#formatting-trait-ids}

A tabela a seguir descreve os prefixos que identificam [!UICONTROL trait] nomes ou IDs em um arquivo de dados de entrada. Consulte os arquivos [de](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) amostra para obter exemplos.

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prefixo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_sid= </code> </p> </td> 
   <td colname="col2"> <p>O <code> d_sid </code> prefixo informa ao sistema que a ID é uma ID <span class="keyword"> Audience Manager </span> . Essa é a mesma ID mostrada na interface do usuário. Você também pode retornar IDs de características com o <code> GET </code> método da API. Consulte Métodos <a href="../../../api/rest-api-main/api-traits.md"> da API de características </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>O prefixo de dados com <code> d_unsid </code> remove os usuários dessa característica. O <code> d_unsid </code> prefixo é ignorado em um <code> overwrite </code> arquivo. </p> <p>O <code> d_unsid= </code> prefixo informa ao sistema que a ID é uma ID <span class="keyword"> Audience Manager </span> . Essa é a mesma ID mostrada na interface do usuário. Você também pode retornar IDs de características com o <code> GET </code> método da API. Consulte Métodos <a href="../../../api/rest-api-main/api-traits.md"> da API de características </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> As regras de características </a> permitem definir critérios para a qualificação de características. Se formatar uma regra de característica como <code> ic == trait ID </code>, você poderá enviar características em uma lista formatada por vírgula simples. </p> <p>Por exemplo, digamos que você crie estas três regras de características: </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>Essas características estão associadas à <code> ic </code> chave. Isso permite criar uma lista de característica mais simples no arquivo de dados. E não é necessário incluir o <code> ic </code> prefixo. Como resultado, o conteúdo do arquivo de dados pode ser semelhante a: </p> <p>
     <code> 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
      <i>user ID</i>&nbsp;&lt;TAB&gt;&nbsp;123,456,789 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pares de valor-chave </p> </td> 
   <td colname="col2"> <p>Os dados de características podem ser formatados como pares de valores chave usando strings alfanuméricas. Há várias maneiras de formatar pares de valores chave, como mostrado abaixo: </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul><code> "age"="32" </code> , <code> "gender"=m </code> , <code> model = "pickup truck" </code> , <code> product = tablet </code> são exemplos de pares de valores chave formatados corretamente. </p> </td> 
  </tr>
 </tbody>
</table>

## Caracteres inválidos em pares de [!UICONTROL Trait IDs]chave [!UICONTROL User IDs] e valores-chave {#invalid-chars}

### [!UICONTROL Trait IDs]

[!UICONTROL Trait IDs] consistem apenas em caracteres numéricos. Solicitamos que você inclua *somente[!UICONTROL onboarded traits]*os arquivos de dados de entrada. Não processamos nenhum outro[!UICONTROL trait]tipo na transferência de dados de entrada.

### [!UICONTROL User IDs]

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
   <td colname="col2"> <p><i>Não</i> utilize dois pontos codificados ( <code> %3A </code>) ou dois pontos não codificados ( : ) em DPUUIDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID do dispositivo móvel iOS (IDFA) ou Android </p> </td> 
   <td colname="col2"> <p>As IDs de dispositivo móvel devem ser formatadas rigorosamente conforme mostrado aqui: </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">Formato IDFA: As IDs devem estar em maiúsculas e não em hash. Por exemplo, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Formato Android: As IDs devem estar em minúsculas e não devem ter hash. Por exemplo, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Pares de valor-chave

Nomes de valores formatados incorretamente em um par de valores chave também causam problemas. Siga estas regras ao criar ou nomear o valor em um par de valores chave:

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caractere </th> 
   <th colname="col2" class="entry"> Requisito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caractere de citação (") </p> </td> 
   <td colname="col2"> <p>Você pode usar o caractere de aspas na chave e na parte de valor do par de valor chave, como segue: </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caractere traço (-) </p> </td> 
   <td colname="col2"> <p>Ignoramos sinais de travessão no start das chaves. Por exemplo, <code> -product = camera </code> é interpretado como <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>Não</i> use valores vazios <code> TAB </code> em pares de valores chave. Use apenas <code> TAB </code> para separar variáveis no arquivo de dados de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>Não use os novos caracteres de linha ou tabulação ( <code> \n, \t </code>) em teclas ou valores. </p> </td> 
  </tr>
 </tbody>
</table>

## Exemplos de arquivos de dados {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formato de arquivo de dados </th> 
   <th colname="col2" class="entry"> Descrição e exemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Com <code> d_sid </code> ou <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>Este arquivo de dados mostra um usuário qualificado para as características 24, 26, 27 e foi removido da característica 28 e 29. </p> <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;&amp;nbsp;d_sid=24,d_sid=26,d_sid=27,d_unsid=28,d_unsid=29 
     </code> </p> <p>Observação:  <p>Em vez de usar d_unsid, também é possível remover características de perfis do usuário usando a seguinte sintaxe: </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:0,&amp;nbsp;29:0 
      </code> </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:-1,&amp;nbsp;29:-1 
      </code> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Com <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>Essas características foram adicionadas a uma regra de característica com o <code> ic </code> prefixo. Dessa forma, é possível adicioná-los ao arquivo de dados separado por vírgulas, conforme mostrado. Uma guia separa o UUID e as IDs de características. O <code> ic </code> prefixo não é necessário no arquivo. </p> <p><b>IDs numéricas</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;30608,50354,50338,50352,30626 
     </code> </p> <p><b>IDs de string</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;ic=52,ic=55 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Com pares de valor chave </p> </td> 
   <td colname="col2"> Esses dados de arquivo usam pares de valor chave para passar os dados para o <span class="keyword"> Audience Manager </span>. <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[Baixe](assets/ftp_dpm_1234_1445374061.overwrite) o arquivo de dados de amostra se precisar de exemplos adicionais. O arquivo de download tem uma extensão `.overwrite` de arquivo. É possível abri-lo com um editor de texto simples.

## Matriz de exemplos {#examples-matrix}

O gráfico abaixo mostra exemplos da maneira correta de formatar seus arquivos de entrada, dependendo do [tipo de IDs](../../../reference/ids-in-aam.md) e do método pelo qual você deseja adicionar [!UICONTROL traits] aos perfis.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo/operação de ID </th> 
   <th colname="col2" class="entry"> Use d_sid para adicionar características a um perfil do usuário </th> 
   <th colname="col3" class="entry"> Usar d_unsid para remover características de um perfil de usuário </th> 
   <th colname="col4" class="entry"> Enviar pares de valores chave para adicionar características a um perfil de usuário </th> 
   <th colname="col5" class="entry"> Use o prefixo ic para adicionar características a um perfil do usuário </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Audience Manager UUID </p> </td> 
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
   <td colname="col1"> <p>Sua própria ID do CRM (DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> Exemplo 13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> Exemplo 14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> Exemplo 15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> Exemplo 16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemplo 1 {#example-1}

Use [!UICONTROL trait IDs] para enviar informações [!UICONTROL trait] de qualificação para [!DNL Audience Manager][!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Exemplo 2 {#example-2}

Use [!UICONTROL trait IDs] para enviar informações de [!UICONTROL trait] desqualificação para [!DNL Audience Manager][!DNL UUIDs].

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

Envie pares de valor chave para adicionar [!UICONTROL trait] informações de qualificação para [!DNL Audience Manager][!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

ou

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 4 {#example-4}

Use o `ic` prefixo para enviar informações de [!UICONTROL trait] qualificação para [!DNL Audience Manager][!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

ou

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Example 5 {#example-5}

Use [!UICONTROL trait IDs] para enviar informações [!UICONTROL trait] de qualificação para [!DNL Android] dispositivos.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 6 {#example-6}

Use [!UICONTROL trait IDs] para enviar informações de [!UICONTROL trait] desqualificação para [!DNL Android] dispositivos.

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

Envie pares de valor chave para adicionar [!UICONTROL trait] informações de qualificação para [!DNL Android] dispositivos.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

ou

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 8 {#example-8}

Use o `ic` prefixo para enviar informações de [!UICONTROL trait] qualificação para [!DNL Android] dispositivos.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

ou

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Example 9 {#example-9}

Use [!UICONTROL trait IDs] para enviar informações [!UICONTROL trait] de qualificação para [!DNL iOS] dispositivos.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 10 {#example-10}

Use [!UICONTROL trait IDs] para enviar informações de [!UICONTROL trait] desqualificação para [!DNL iOS] dispositivos.

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

Envie pares de valor chave para adicionar [!UICONTROL trait] informações de qualificação para [!DNL iOS] dispositivos.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

ou

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Example 12 {#example-12}

Use o `ic` prefixo para enviar informações de [!UICONTROL trait] qualificação para [!DNL iOS] dispositivos.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

ou

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Example 13 {#example-13}

Use [!UICONTROL trait IDs] para enviar informações de [!UICONTROL trait] qualificação para [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 14 {#example-14}

Use [!UICONTROL trait IDs] para enviar informações de [!UICONTROL trait] desqualificação para [!DNL DPUUIDs].

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

Envie pares de valor chave para adicionar [!UICONTROL trait] informações de qualificação para [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

ou

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 16 {#example-16}

Use o `ic` prefixo para enviar informações de [!UICONTROL trait] qualificação para [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

ou

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORELIKETHIS]
>
>* [Construtor de perfil](../../../features/traits/about-trait-builder.md)

