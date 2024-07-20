---
description: Rótulos de cabeçalho de coluna definidos.
seo-description: Column header labels defined.
seo-title: Bulk Management Tools Glossary
solution: Audience Manager
title: Glossário de ferramentas de gerenciamento em massa
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: BAAAM
exl-id: 036d16c7-1546-4539-a318-455b98e10026
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 0%

---

# Glossário de ferramentas de gerenciamento em massa{#bulk-management-tools-glossary}

Rótulos de cabeçalho de coluna definidos.

>[!IMPORTANT]
>
>As Ferramentas de gerenciamento em massa não são uma oferta de Adobe oficialmente compatível. A solução de problemas e o suporte por meio do Atendimento ao cliente serão tratados caso a caso.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>As [permissões do grupo RBAC](../../features/administration/administration-overview.md) atribuídas na interface do usuário [!DNL Audience Manager] são honradas no [!UICONTROL Bulk Management Tools].

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
   <td colname="col2"> <p>A ID de uma fonte de dados <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"></a> que você deseja retornar ou atribuir em massa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivouSignalId</span> </p> </td> 
   <td colname="col2"> <p>Um ID </a> de sinal derivado <a href="../../features/derived-signals.md">. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> descrição</span> </p> </td> 
   <td colname="col2"> <p>Uma descrição breve e informativa que você pode dar a um objeto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId</span> </p> </td> 
   <td colname="col2"> <p>A ID do <a href="../../features/destinations/destinations.md"> destino</a> que você deseja mapear ou excluir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>Uma ID especial atribuída a um segmento quando mapeado para um destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>A ID do segmento ou pasta de características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> nome</span> </p> </td> 
   <td colname="col2"> <p>O nome do objeto com o qual você está trabalhando. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> parentFolderId</span> </p> </td> 
   <td colname="col2"> <p>A ID de um segmento ou pasta de características que contém outras pastas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>ID do segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceKey</span> </p> </td> 
   <td colname="col2"> <p>Os sinais são bits de dados passados para <span class="keyword"> Audience Manager</span> com base na atividade do usuário. Eles são transmitidos como <a href="../../reference/key-value-pairs-explained.md"> pares de valor-chave</a>. A chave de origem é uma constante que não é alterada. Isso ajuda a categorizar o valor de origem que pode ser alterado. Consulte <a href="../../features/derived-signals.md"> Sinais derivados</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>O valor de origem é uma variável passada como parte de um <a href="../../reference/key-value-pairs-explained.md"> par de valor-chave</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term">startDate</span> </p> </td> 
   <td colname="col2"> <p>Indica quando um segmento pode começar a ser enviado para um destino. Usa o formato <i>aaaa-mm-dd</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term">targetKey</span> </p> </td> 
   <td colname="col2">A chave usada no sinal derivado. Consulte <a href="../../features/derived-signals.md"> Sinais derivados</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term">targetValue</span> </p> </td> 
   <td colname="col2"> <p>O valor passado com uma chave de sinal derivada. Consulte <a href="../../features/derived-signals.md"> Sinais derivados</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>Uma ID passada para um destino não baseado em cookie. Para um destino baseado em cookie, esta é a chave em um <a href="../../reference/key-value-pairs-explained.md"> par de valor-chave</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule / segmentRule</span> </p> </td> 
   <td colname="col2"> <p>A característica real ou regra de segmento usada para coletar dados. Uma solicitação em massa retorna as regras criadas em <span class="keyword"> Audience Manager</span> com o <a href="../../features/traits/about-trait-builder.md"> construtor de regras de características</a> ou o <a href="../../features/segments/segment-builder.md"> construtor de regras de segmentos</a>. Também é possível usar essas ferramentas para criar regras e aplicá-las em massa ao atualizar um segmento ou característica. </p> <p>Consulte também <a href="../../reference/bulk-management-tools/bulk-rules.md"> Criar ou atualizar regras de características e regras de segmento</a>. </p> </td> 
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
   <td colname="col2"> <p>Pixel acionado por DIL quando um usuário se qualifica para um segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p>A chave em um <a href="../../reference/key-value-pairs-explained.md"> par de valor-chave</a> passada para um destino de cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>
