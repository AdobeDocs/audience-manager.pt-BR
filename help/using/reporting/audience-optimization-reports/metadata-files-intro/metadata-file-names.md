---
description: Nomeie seu arquivo de metadados de Audience Optimization de acordo com essas especificações.
seo-description: Name your Audience Optimization metadata file according to these specifications.
seo-title: Naming Conventions for Metadata Files
solution: Audience Manager
title: Convenções de nomenclatura para arquivos de metadados
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
feature: Log Files
exl-id: 7a895c4f-1100-4ba1-947e-abb47307fb40
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 2%

---

# Convenções de nomenclatura para arquivos de metadados{#naming-conventions-for-metadata-files}

Nomeie seu arquivo de metadados de Audience Optimization de acordo com essas especificações.

## Sintaxe e categorias de ID {#syntax}

A sintaxe a seguir define a estrutura de um nome de arquivo de metadados bem formado. Observe que *itálico* indica um espaço reservado para variável. Os outros elementos são constantes e não são alterados.

**Sintaxe:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*Não* use extensões de arquivo em seus arquivos de metadados (.txt ou outro).

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* Tecnicamente, o componente intermediário **0** é a ID pai, que é um campo herdado. O valor deve ser sempre definido como **0**.
* A ID secundária pode ter um valor entre 1 e 10, dependendo da dimensão. Consulte abaixo:

## Dimensões da ID secundária {#child-dimension}

No nome do arquivo de metadados, a ID secundária é um identificador que classifica o tipo de dados em um arquivo e o coloca em uma hierarquia. Você pode marcar a ID secundária no nome do arquivo com as seguintes IDs de categoria:

1. Campanha
1. Creative
1. Posicionamento
1. Exchange
1. Site
1. Anunciante (se estiver usando códigos de integração em uma [fonte de dados](../../../features/manage-datasources.md#details))
1. Ordem de inserção (IO)
1. Vertical (ou seja, uma indústria específica ou categoria de negócios como &quot;computadores&quot;, &quot;automóveis&quot;, &quot;imóveis&quot; etc.)
1. Tático
1. Unidade de negócios ou marca

## Exemplo {#example}

Para um arquivo de metadados da Creative, o nome do arquivo pode ser 20190115_0_2.

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
