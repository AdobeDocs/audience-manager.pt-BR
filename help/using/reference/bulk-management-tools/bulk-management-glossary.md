---
description: Rótulos do cabeçalho da coluna definidos.
seo-description: Rótulos do cabeçalho da coluna definidos.
seo-title: Glossário de ferramentas de gerenciamento em massa
solution: Audience Manager
title: Glossário de ferramentas de gerenciamento em massa
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: BAAAM
exl-id: 036d16c7-1546-4539-a318-455b98e10026
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 5%

---

# Glossário de ferramentas de gerenciamento em massa{#bulk-management-tools-glossary}

Rótulos do cabeçalho da coluna definidos.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[As ](../../features/administration/administration-overview.md) permissões do grupo RBAC atribuídas na  [!DNL Audience Manager] interface do usuário são honradas no  [!UICONTROL Bulk Management Tools].

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
   <td colname="col1"> <p> <span class="term"> derivadoSignalId</span> </p> </td> 
   <td colname="col2"> <p>Uma ID <a href="../../features/derived-signals.md"> de sinal derivado</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> descrição</span> </p> </td> 
   <td colname="col2"> <p>Uma breve descrição informativa que pode ser fornecida a um objeto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId</span> </p> </td> 
   <td colname="col2"> <p>A ID do destino <a href="../../features/destinations/destinations.md"></a> que você deseja mapear ou excluir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>Uma ID especial atribuída a um segmento quando ele é mapeado a um destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>A ID do seu segmento ou pasta de características. </p> </td> 
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
   <td colname="col2"> <p>Os sinais são bits de dados passados para <span class="keyword"> Audience Manager</span> com base na atividade do usuário. Elas são transmitidas como pares de valores chave <a href="../../reference/key-value-pairs-explained.md"></a>. A chave de origem é uma constante que não é alterada. Ajuda a categorizar o valor de origem que pode ser alterado. Consulte <a href="../../features/derived-signals.md"> Sinais derivados</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>O valor de origem é uma variável passada como parte de um par de valores chave <a href="../../reference/key-value-pairs-explained.md"> </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>Indica quando um segmento pode começar a ser enviado para um destino. Usa o formato <i>aaaa-mm-dd</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">A chave usada no sinal derivado. Consulte <a href="../../features/derived-signals.md"> Sinais derivados</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>O valor passado com uma chave de sinal derivada. Consulte <a href="../../features/derived-signals.md"> Sinais derivados</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>Uma ID passada para um destino não baseado em cookies. Para um destino com base em cookies, essa é a chave em um par de valores chave <a href="../../reference/key-value-pairs-explained.md"></a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule / segmentRule</span> </p> </td> 
   <td colname="col2"> <p>A regra de característica ou segmento real usada para coletar dados. Uma solicitação em massa retorna as regras criadas em <span class="keyword"> Audience Manager</span> com o <a href="../../features/traits/about-trait-builder.md"> construtor de regras de características</a> ou o <a href="../../features/segments/segment-builder.md"> construtor de regras de segmento</a>. Também é possível usar essas ferramentas para criar regras e aplicá-las em massa ao atualizar um segmento ou característica. </p> <p>Consulte também <a href="../../reference/bulk-management-tools/bulk-rules.md"> Criar ou atualizar regras de características e regras de segmento</a>. </p> </td> 
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
   <td colname="col2"> <p>A chave em um par de valores chave <a href="../../reference/key-value-pairs-explained.md"> </a> passado para um destino de cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>
