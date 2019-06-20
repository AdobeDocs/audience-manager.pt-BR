---
description: Rótulos de cabeçalho de coluna definidos.
seo-description: Rótulos de cabeçalho de coluna definidos.
seo-title: Glossário das Ferramentas de Gerenciamento em Massa
solution: Audience Manager
title: Glossário das Ferramentas de Gerenciamento em Massa
uuid: 4658 a 6 bc -9515-4 d 31-9715-0084760 b 0 cea
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Management Tools Glossary{#bulk-management-tools-glossary}

Rótulos de cabeçalho de coluna definidos.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Essa ferramenta é fornecida para conveniência e apenas como cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [As permissões de grupo RBAC](../../features/administration/administration-overview.md) atribuídas na [!DNL Audience Manager] interface do usuário são respeitadas [!UICONTROL Bulk Management Tools].

<table id="table_2C2BC2FB3EFC443C9A5AE18EFC6FABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cabeçalho da coluna </th> 
   <th colname="col2" class="entry"> Definição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Datasourceid</span> </p> </td> 
   <td colname="col2"> <p>The ID of a <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> data source</a> you want to return or assign in bulk. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Derivedsignali</span> </p> </td> 
   <td colname="col2"> <p>A <a href="../../features/derived-signals.md"> derived signal</a> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> descrição</span> </p> </td> 
   <td colname="col2"> <p>Uma descrição resumida e informativa que pode ser fornecida para um objeto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Signationid</span> </p> </td> 
   <td colname="col2"> <p>The ID of the <a href="../../features/destinations/destinations.md"> destination</a> you want to map or delete. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Destinationmappingid</span> </p> </td> 
   <td colname="col2"> <p>Uma ID especial atribuída a um segmento quando ela é mapeada para um destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Folderid</span> </p> </td> 
   <td colname="col2"> <p>A ID de sua pasta de segmento ou de característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> name</span> </p> </td> 
   <td colname="col2"> <p>O nome do objeto com o qual você está trabalhando. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Parentfolderid</span> </p> </td> 
   <td colname="col2"> <p>A ID de um segmento ou pasta de característica que contém outras pastas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>ID do segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Sourcekey</span> </p> </td> 
   <td colname="col2"> <p>Signals are bits of data passed in to <span class="keyword"> Audience Manager</span> based on user activity. These are transmitted as <a href="../../reference/key-value-pairs-explained.md"> key-value pairs</a>. A chave de origem é uma constante que não muda. Isso ajuda a categorizar o valor de origem que pode ser alterado. See <a href="../../features/derived-signals.md"> Derived Signals</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Sourcevalue</span> </p> </td> 
   <td colname="col2"> <p>The source value is a variable passed in as part a <a href="../../reference/key-value-pairs-explained.md"> key-value pair</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>Indica quando um segmento pode começar a ser enviado para um destino. Uses <tt>yyyy-mm-dd</tt> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Targetkey</span> </p> </td> 
   <td colname="col2">A chave usada no sinal derivado. See <a href="../../features/derived-signals.md"> Derived Signals</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Targetvalue</span> </p> </td> 
   <td colname="col2"> <p>O valor passado com uma chave de sinal derivada. See <a href="../../features/derived-signals.md"> Derived Signals</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Traitalias</span> </p> </td> 
   <td colname="col2"> <p>Uma ID transmitida para um destino com base em não cookie. For a cookie-based destination, this is the key in a <a href="../../reference/key-value-pairs-explained.md"> key-value pair</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Traitrule/segmentrule</span> </p> </td> 
   <td colname="col2"> <p>A regra de característica ou segmento real usada para coletar dados. A bulk request returns the rules created in <span class="keyword"> Audience Manager</span> with the <a href="../../features/traits/about-trait-builder.md"> trait rule builder</a> or the <a href="../../features/segments/segment-builder.md"> segment rule builder</a>. Você também pode usar essas ferramentas para criar regras e aplicá-las em massa ao atualizar um segmento ou característica. </p> <p>See also, <a href="../../reference/bulk-management-tools/bulk-rules.md"> Create or Update Trait Rules and Segment Rules</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Traittype</span> </p> </td> 
   <td colname="col2"> <p>Uma string que identifica o tipo de característica. As opções incluem: </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_ BASED_ TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_ BOARDED_ TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENTO</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>O pixel acionado pela DIL quando um usuário é qualificado para um segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Valuealias</span> </p> </td> 
   <td colname="col2"> <p>The key in a <a href="../../reference/key-value-pairs-explained.md"> key-value pair</a> passed to a cookie destination. </p> </td> 
  </tr> 
 </tbody> 
</table>

