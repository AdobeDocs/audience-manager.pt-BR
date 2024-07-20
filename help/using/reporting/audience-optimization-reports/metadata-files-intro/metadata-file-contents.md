---
description: Formate o conteúdo do arquivo de metadados Audience Optimization de acordo com essas especificações.
seo-description: Format the contents of your Audience Optimization metadata file according to these specifications.
seo-title: Content Format for Metadata Files
solution: Audience Manager
title: Formato de conteúdo para arquivos de metadados
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: Log Files
exl-id: 1aed39f4-f893-4f25-b041-e198895e338a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 1%

---

# Formato de conteúdo para arquivos de metadados{#content-format-for-metadata-files}

Formate o conteúdo do arquivo de metadados Audience Optimization de acordo com essas especificações.

## Sintaxe {#syntax}

A sintaxe a seguir define a estrutura do conteúdo bem formado em um arquivo de metadados. Observe que *itálico* indica um espaço reservado para variável.

**Sintaxe:** *ID de conteúdo* | *nome* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

A terceira coluna **-1** é tecnicamente a ID Pai, que é um campo herdado. O valor deve ser sempre definido como **-1**.

>[!NOTE]
>
>Observe que é necessário um arquivo de metadados por dimensão, portanto, vários arquivos de metadados são esperados no bucket. As dimensões estão listadas no artigo [Convenções de nomenclatura para arquivo de metadados](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Separar Entradas de Arquivo com ^a (control-A ou ASCII 001)**

Use `^a` (control-A ou ASCII 001) para separar o conteúdo em seus arquivos de metadados. Como esses são caracteres não imprimíveis, o exemplo de sintaxe acima mostra uma barra vertical &quot;|&quot; somente para fins de exibição.

Se necessário, você pode baixar o arquivo de exemplo - [20181105_0_1](assets/20181105_0_1.zip). Descompacte-o e edite-o no editor de sua escolha e ajuste de acordo com o conteúdo real dos metadados, pois ele já contém o delimitador necessário.

>[!IMPORTANT]
>
>Não adicione linhas de cabeçalho a arquivos de metadados.

## Exemplos {#examples}

Vamos ver como você estruturaria o conteúdo em um arquivo de metadados. Parte dessa estrutura depende da dimensão. As dimensões estão listadas no artigo [Convenções de nomenclatura para arquivo de metadados](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

Neste exemplo, o título do arquivo é 20180921_0_1 e as três colunas no arquivo são: ID da campanha, Nome e ID do pai.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Criativo**

Neste exemplo, o título do arquivo é 20180827_0_2 e as três colunas no arquivo são: ID de criação, Nome e ID principal.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Site**

Neste exemplo, o título do arquivo é 20180921_0_5 e as três colunas no arquivo são: ID do site, Nome e ID principal.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
