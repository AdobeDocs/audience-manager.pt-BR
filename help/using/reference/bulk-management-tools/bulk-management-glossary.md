---
description: Rótulos de cabeçalho de coluna definidos.
seo-description: Rótulos de cabeçalho de coluna definidos.
seo-title: Glossário de ferramentas de gerenciamento em massa
solution: Audience Manager
title: Glossário de ferramentas de gerenciamento em massa
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 5%

---


# Glossário de ferramentas de gerenciamento em massa{#bulk-management-tools-glossary}

Rótulos de cabeçalho de coluna definidos.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[As permissões](../../features/administration/administration-overview.md) de grupo RBAC atribuídas na [!DNL Audience Manager] interface do usuário são respeitadas na [!UICONTROL Bulk Management Tools].

<table id="table_2C2BC2FB3EFC443C9A5AE18EFC6FABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cabeçalho da coluna </th> 
   <th colname="col2" class="entry"> Definição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> dataSourceId</span> </p> </td> 
   <td colname="col2"> <p>A ID de uma fonte <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> de</a> dados que você deseja retornar ou atribuir em massa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivadoSignalId</span> </p> </td> 
   <td colname="col2"> <p>Uma ID de sinal <a href="../../features/derived-signals.md"></a> derivada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> descrição</span> </p> </td> 
   <td colname="col2"> <p>Uma descrição breve e informativa que você pode fornecer a um objeto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetId</span> </p> </td> 
   <td colname="col2"> <p>A ID do <a href="../../features/destinations/destinations.md"> destino</a> que você deseja mapear ou excluir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetMappingId</span> </p> </td> 
   <td colname="col2"> <p>Uma ID especial atribuída a um segmento quando ele é mapeado para um destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>A ID do segmento ou da pasta de características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> name</span> </p> </td> 
   <td colname="col2"> <p>O nome do objeto com o qual você está trabalhando. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> parentFolderId</span> </p> </td> 
   <td colname="col2"> <p>A ID de um segmento ou pasta de característica que contém outras pastas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>ID do segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceKey</span> </p> </td> 
   <td colname="col2"> <p>Os sinais são bits de dados passados para o <span class="keyword"> Audience Manager</span> com base na atividade do usuário. Estes são transmitidos como pares <a href="../../reference/key-value-pairs-explained.md"></a>de valores chave. A chave de origem é uma constante que não é alterada. Ajuda a categorizar o valor de origem que pode ser alterado. Consulte <a href="../../features/derived-signals.md"> Sinais</a>derivados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>O valor de origem é uma variável transmitida como parte de um par <a href="../../reference/key-value-pairs-explained.md"></a>de valores chave. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>Indica quando um start de segmento pode ser enviado para um destino. Usa o formato <tt>aaaa-mm-dd</tt> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">A tecla usada no sinal derivado. Consulte <a href="../../features/derived-signals.md"> Sinais</a>derivados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>O valor passado com uma chave de sinal derivada. Consulte <a href="../../features/derived-signals.md"> Sinais</a>derivados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>Uma ID transmitida para um destino não baseado em cookie. Para um destino baseado em cookies, esta é a chave em um par <a href="../../reference/key-value-pairs-explained.md"> de valor-</a>chave. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule / segmentRule</span> </p> </td> 
   <td colname="col2"> <p>A característica real ou regra de segmento usada para coletar dados. Uma solicitação em massa retorna as regras criadas no <span class="keyword"> Audience Manager</span> com o construtor <a href="../../features/traits/about-trait-builder.md"> de regras de</a> características ou o construtor <a href="../../features/segments/segment-builder.md"> de regras de</a>segmento. Você também pode usar essas ferramentas para criar regras e aplicá-las em massa ao atualizar um segmento ou característica. </p> <p>See also, <a href="../../reference/bulk-management-tools/bulk-rules.md"> Create or Update Trait Rules and Segment Rules</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitType</span> </p> </td> 
   <td colname="col2"> <p>Uma string que identifica o tipo de característica. As opções incluem: </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_BASED_TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_BOARDED_TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>Pixel acionado pelo DIL quando um usuário se qualifica para um segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p>A chave em um par <a href="../../reference/key-value-pairs-explained.md"> de valor-</a> chave passado para um destino de cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>

