---
description: Descreve as macros que podem ser adicionadas a um URL de destino.
seo-description: Descreve as macros que podem ser adicionadas a um URL de destino.
seo-title: Macros de destino definidas
solution: Audience Manager
title: Macros de destino definidas
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 4bf32099e964c421d943d9925c74dd0d4d6ee576
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 3%

---


# Macros de destino definidas {#destination-macros-defined}

Descreve as macros que podem ser adicionadas a um destino [!DNL URL].

<!-- destination-macros.xml -->

Ao criar um [!DNL URL] destino, você pode inserir as seguintes macros na [!DNL URL] string. Verifique com seu parceiro de dados/destino se a macro está posicionada corretamente no destino [!DNL URL].

>[!NOTE]
>
>As macros são opcionais, a menos que seja indicado o contrário. *Itálico* indica um marcador de posição variável.

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
   <td colname="col2"> <p>Obrigatório. </p> <p>Define o local do valor do segmento mapeado em um URL de destino. Geralmente, essa é a ID <i>do</i>segmento, mas também pode ser o código de integração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Insere a ID de <span class="keyword"> Audience Manager</span> do usuário no URL de destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>A ID <i>da fonte de</i> dados corresponde ao identificador de uma fonte de dados transmitida para a macro. </p> <p>Vejamos como isto funciona num exemplo simples. Nesse caso, temos um parceiro <span class="keyword"> Audience Manager</span> com as seguintes IDs e condições: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">ID da fonte de dados: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">Uma ID interna do cliente: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">ID declarada: O parceiro deseja transmitir esses valores como a ID declarada <code> 1:CustomerABC</code>. </li> 
    </ul> <p>Para fazer isso com o <code>%dpid_<i>data source id</i>%</code>, o parceiro de <span class="keyword"> Audience Manager</span> formataria a macro desta forma: </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>A macro será substituída <code> 1</code> por <code> CustomerABC</code>. </p> <p> 
     <!--
       Based on AAM-22193 https://jira.corp.adobe.com/browse/AAM-22193 
     --> </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>Indica se os regulamentos RGPD se aplicam ao visitante ou não. Use essa macro para incluir o consentimento em segmentos enviados para destinos de URL integrados com o IAB. Consulte Plug-in <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager para IAB TCF</a> para obter detalhes.</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>A sequência de caracteres de consentimento (incluindo a ID de fornecedor IAB) coletada quando os visitantes fornecem ou negam o consentimento em seu site. Use essa macro para incluir a sequência de caracteres de consentimento nos segmentos enviados para destinos de URL integrados com IAB. Substitua <code>XXXX</code> pela ID do parceiro de destino. Consulte Plug-in <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager para IAB TCF</a> para obter detalhes. </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>Detecta o protocolo usado na página da Web pai e o insere no URL de destino. Por exemplo:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">se a página da Web for <b>https</b>://aam_client.com, esta macro será substituída por <b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">se a página da Web for <b>http</b>://aam_client.com, esta macro será substituída por <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>Insere a ID do <span class="keyword"> Experience Cloud</span> no URL de destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>Insere a região <span class="wintitle"> Data Collection Server (DCS)</span> no URL de destino. Para minimizar a latência, quando o visitante faz uma chamada HTTP para o <span class="keyword"> Audience Manager</span>, eles estão sendo redirecionados para o datacenter <span class="wintitle"> DCS</span> mais próximo. Isso é feito por meio do DNS, que é capaz de detectar o local do visitante e direcioná-lo para o data center apropriado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>Executa uma função de cache busting inserindo um número aleatório no URL de destino. Isso impede que os navegadores disponibilizem conteúdo em cache. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>Insere um carimbo de data e hora UNIX no URL de destino para impedir que os navegadores disponibilizem conteúdo em cache. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Compuração de cache com macros de destino {#destination-cache-busting}

As macros `%rnd%` e `%timestamp%` os inserem valores exclusivos em uma [!DNL URL] sequência de caracteres para impedir o armazenamento em cache do navegador.

## Compartilhamento de cache com %rnd% e %timestamp% {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

O cache dos navegadores (salvar) solicitava com frequência o conteúdo na memória. Quando uma página é carregada, o conteúdo salvo serve do cache em vez de de um servidor remoto. Esse processo ajuda a manter tempos de download eficientes, pois os dados são fornecidos localmente, em vez de em outro local. No entanto, como o cache não requer uma chamada de servidor, ele pode distorcer o relatórios reduzindo artificialmente o número de solicitações exclusivas.

A eliminação de cache impede que os navegadores salvem e reutilizem conteúdo. Essa técnica usa um código que insere um número aleatório ou carimbo de data e hora em uma string de URL, o que faz com que pareça exclusivo para o navegador. Como resultado, cada `HTTP` chamada é contada como uma solicitação separada para o servidor. Forçar uma nova chamada de servidor para cada solicitação ajuda a manter a precisão do relatórios e a reduzir as discrepâncias. [!DNL Audience Manager] fornece duas macros para o cache busting:

* `%rnd%`: Insere um número aleatório em um URL.
* `%timestamp%`: Insere a data/hora do Unix em um URL.

## Comparando %rnd% e %timestamp% {#compare-rnd-timestamp}

Ambas as macros impedem o cache, mas `%rnd%` podem ser mais eficientes. Por exemplo, com `%timestamp%`, se vários usuários visualizações uma página simultaneamente, eles obterão o mesmo valor de data/hora. Como resultado, as chamadas não [!DNL URL] são exclusivas e várias são contadas apenas uma vez. No entanto, `%rnd%` gera um valor numérico exclusivo para cada chamada (mesmo quando os usuários veem a mesma página simultaneamente). Isso significa que a [!DNL URL] string contém valores diferentes e é contada como exclusiva.

>[!MORELIKETHIS]
>
>* [Macros de destino definidas](../../features/destinations/destination-macros.md#destination-macros-defined)