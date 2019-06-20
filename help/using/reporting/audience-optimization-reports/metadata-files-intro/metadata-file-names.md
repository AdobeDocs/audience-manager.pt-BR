---
description: Dê um nome ao seu arquivo de metadados de Otimização de público-alvo de acordo com essas especificações.
seo-description: Dê um nome ao seu arquivo de metadados de Otimização de público-alvo de acordo com essas especificações.
seo-title: Convenções de nomenclatura para arquivos de metadados
solution: Audience Manager
title: Convenções de nomenclatura para arquivos de metadados
uuid: cab 55 b 2 a -2 e 54-45 f 6-aeea -3735 b 911 f 821
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Naming Conventions for Metadata Files{#naming-conventions-for-metadata-files}

Dê um nome ao seu arquivo de metadados de Otimização de público-alvo de acordo com essas especificações.

## Syntax and ID Categories {#syntax}

A sintaxe a seguir define a estrutura de um nome de arquivo de metadados bem formado. Note, *italics* indicates a variable placeholder. Os outros elementos são constantes e não são alterados.

**Sintaxe:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*Não* use extensões de arquivo em seus arquivos de metadados (.txt ou outro).

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* The middle component **0** is technically the Parent ID, which is a legacy field. The value should always be set as **0**.
* A ID secundária pode ter um valor entre 1 e 10, dependendo da dimensão. Consulte abaixo:

## Child ID dimensions {#child-dimension}

No nome do arquivo de metadados, o ID filho é um identificador que classifica o tipo de dados em um arquivo e o coloca em uma hierarquia. Você pode marcar a ID secundária no nome do arquivo com as seguintes IDs de categoria:

1. Campanha
1. Creative
1. Disposição
1. Exchange
1. Site
1. Advertiser (if using integration codes in a [data source](../../../features/manage-datasources.md#details))
1. Ordem de inserção (IO)
1. Vertical (ou seja, um setor específico ou uma categoria de negócios como &quot;computadores,&quot; automóveis &quot;automóveis&quot;, etc.)
1. Táticas
1. Unidade de negócios ou marca

## Exemplo {#example}

Para um arquivo de metadados Creative, o nome do arquivo pode ser 20190115_ 0_ 2.

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
