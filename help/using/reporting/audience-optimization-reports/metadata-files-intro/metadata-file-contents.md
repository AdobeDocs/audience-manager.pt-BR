---
description: Formate o conteúdo do arquivo de metadados do Audience Optimization de acordo com essas especificações.
seo-description: Formate o conteúdo do arquivo de metadados do Audience Optimization de acordo com essas especificações.
seo-title: Formato de conteúdo para arquivos de metadados
solution: Audience Manager
title: Formato de conteúdo para arquivos de metadados
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: log files
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 5%

---


# Formato de conteúdo para arquivos de metadados{#content-format-for-metadata-files}

Formate o conteúdo do arquivo de metadados do Audience Optimization de acordo com essas especificações.

## Sintaxe {#syntax}

A sintaxe a seguir define a estrutura do conteúdo bem formado em um arquivo de metadados. Observação: *italics* indica um espaço reservado variável.

**Sintaxe:ID**  *de* conteúdo|  *nome* |  *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

A terceira coluna **-1** é tecnicamente a ID pai, que é um campo herdado. O valor deve ser sempre definido como **-1**.

>[!NOTE]
>
>Observe que um arquivo de metadados por dimensão é necessário, portanto, vários arquivos de metadados são esperados no bucket. As dimensões estão listadas no artigo [Convenções de nomenclatura para o arquivo de metadados](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Entradas de arquivo separadas com ^a (controle-A ou ASCII 001)**

Use `^a` (controle-A ou ASCII 001) para separar o conteúdo dos arquivos de metadados. Como são caracteres não imprimíveis, o exemplo de sintaxe acima mostra um pipe &quot;|&quot; somente para fins de exibição.

Se necessário, você pode baixar o arquivo de exemplo - [20181105_0_1](assets/20181105_0_1.zip). Descompacte-o e edite-o no editor de sua escolha e ajuste-o de acordo com o conteúdo real dos metadados, pois já contém o delimitador necessário.

>[!IMPORTANT]
>
>Não adicione linhas de cabeçalho a arquivos de metadados.

## Exemplos {#examples}

Vejamos como você deve estruturar o conteúdo em um arquivo de metadados. Parte dessa estrutura depende da dimensão. As dimensões estão listadas no artigo [Convenções de nomenclatura para o arquivo de metadados](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

Neste exemplo, o título do arquivo é 20180921_0_1 e as três colunas do arquivo são: ID da campanha, Nome e ID pai.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Creative**

Neste exemplo, o título do arquivo é 20180827_0_2 e as três colunas do arquivo são: ID criativa, nome e ID pai.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Site**

Neste exemplo, o título do arquivo é 20180921_0_5 e as três colunas do arquivo são: ID do site, nome e ID pai.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
