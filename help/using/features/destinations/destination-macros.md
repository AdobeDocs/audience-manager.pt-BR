---
description: Descreve as macros que você pode adicionar a um URL de destino.
seo-description: Describes the macros you can add to a destination URL.
seo-title: Destination Macros Defined
solution: Audience Manager
title: Macros de destino definidas
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
exl-id: 7be4b417-046c-4fe3-a53c-e4e0ed36acb9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 1%

---

# Macros de destino definidas {#destination-macros-defined}

Descreve as macros que você pode adicionar a um destino [!DNL URL].

<!-- destination-macros.xml -->

Ao criar um destino [!DNL URL], você pode inserir as seguintes macros na cadeia de caracteres [!DNL URL]. Verifique com seu parceiro de dados/destino sobre o posicionamento de macro adequado no destino [!DNL URL].

>[!NOTE]
>
>As macros são opcionais, a menos que indicado de outra forma. *Itálico* indica um marcador de posição variável.

<table id="table_2C532EFB9DAE41B08714753EBD7DFB05"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Explicação </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> %alias%</code> </p> </td> 
   <td colname="col2"> <p>Obrigatório. </p> <p>Define o local do valor de segmento mapeado em um URL de destino. Normalmente, esta é a <i>ID do segmento</i>, mas também pode ser o código de integração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Insere a ID do Audience Manager</span> do <span class="keyword"> usuário na URL de destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>A <i>id da fonte de dados</i> corresponde ao identificador de uma fonte de dados passado para a macro. </p> <p>Vejamos como isso funciona em um exemplo simples. Nesse caso, temos um parceiro <span class="keyword"> Audience Manager</span> com as seguintes IDs e condições: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">ID da fonte de dados: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">Uma ID de cliente interna: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">ID Declarada: o parceiro deseja passar esses valores como a ID declarada <code> 1:CustomerABC</code>. </li> 
    </ul> <p>Para fazer isso com o <code>%dpid_<i>data source id</i>%</code>, o parceiro <span class="keyword"> Audience Manager</span> formataria a macro da seguinte maneira: </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>A macro substituirá <code> 1</code> por <code> CustomerABC</code>. </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>Indica se as regulamentações do GDPR se aplicam ao visitante ou não. Use essa macro para incluir consentimento nos segmentos enviados para destinos de URL integrados ao IAB. Consulte <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Plug-in de Audience Manager para TCF do IAB</a> para obter detalhes.</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>A cadeia de consentimento (incluindo a ID do fornecedor do IAB) coletada quando os visitantes fornecem ou negam consentimento em seu site. Use essa macro para incluir a string de consentimento nos segmentos enviados para destinos de URL integrados ao IAB. Substitua <code>XXXX</code> pela ID do parceiro de destino. Consulte <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Plug-in de Audience Manager para TCF do IAB</a> para obter detalhes. </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>Detecta o protocolo usado na página da Web pai e o insere no URL de destino. Por exemplo:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">se a página da web for <b>https</b>://aam_client.com, essa macro será substituída por <b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">se a página da web for <b>http</b>://aam_client.com, essa macro será substituída por <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>Insere a ID do Experience Cloud</span> <span class="keyword"> na URL de destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>Insere a região <span class="wintitle"> do Data Collection Server (DCS)</span> na URL de destino. Para minimizar a latência, quando o visitante faz uma chamada HTTP para <span class="keyword"> Audience Manager</span>, ele é redirecionado para o datacenter <span class="wintitle"> DCS</span> mais próximo. Isso é feito por meio do DNS, que é capaz de detectar a localização do visitante e direcioná-lo para o data center apropriado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>Executa uma função de eliminação de cache inserindo um número aleatório no URL de destino. Isso impede que os navegadores forneçam conteúdo em cache. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>Insere um carimbo de data e hora UNIX no URL de destino para impedir que os navegadores forneçam conteúdo em cache. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Busting de Cache com Macros de Destino {#destination-cache-busting}

As macros `%rnd%` e `%timestamp%` inserem valores únicos em uma cadeia de caracteres [!DNL URL] para impedir o armazenamento em cache do navegador.

## Busting de Cache com `%rnd%` e `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

Os navegadores armazenam em cache (salvam) o conteúdo solicitado com frequência na memória. Quando uma página é carregada, o conteúdo salvo serve do cache em vez de um servidor remoto. Esse processo ajuda a manter tempos de download eficientes, pois os dados são enviados localmente, e não de outro local. No entanto, como o armazenamento em cache não requer uma chamada de servidor, pode distorcer os relatórios reduzindo artificialmente o número de solicitações exclusivas.

O impedimento de cache impede que os navegadores salvem e reutilizem conteúdo. Essa técnica usa código que insere um número aleatório ou carimbo de data e hora em uma cadeia de caracteres de URL, o que a torna exclusiva ao navegador. Como resultado, cada chamada `HTTP` é contada como uma solicitação separada para o servidor. Forçar uma nova chamada de servidor para cada solicitação ajuda a manter a precisão dos relatórios e a reduzir as discrepâncias. [!DNL Audience Manager] fornece duas macros para eliminação de cache:

* `%rnd%`: insere um número aleatório em uma URL.
* `%timestamp%`: Insere data/hora Unix em uma URL.

## Comparando `%rnd%` e `%timestamp%` {#compare-rnd-timestamp}

Ambas as macros impedem o armazenamento em cache, mas `%rnd%` pode ser mais eficiente. Por exemplo, com `%timestamp%`, se vários usuários visualizarem uma página simultaneamente, obterão o mesmo valor de data/hora. Como resultado, [!DNL URL] não é único e várias chamadas são contadas apenas uma vez. No entanto, `%rnd%` gera um valor numérico exclusivo para cada chamada (mesmo quando os usuários veem a mesma página simultaneamente). Significa que a cadeia de caracteres [!DNL URL] contém valores diferentes e é contada como exclusiva.

>[!MORELIKETHIS]
>
>* [Macros de destino definidas](../../features/destinations/destination-macros.md#destination-macros-defined)
