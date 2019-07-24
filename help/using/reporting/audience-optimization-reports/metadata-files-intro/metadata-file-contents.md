---
description: Formate o conteúdo do seu arquivo de metadados de Otimização do público-alvo de acordo com essas especificações.
seo-description: Formate o conteúdo do seu arquivo de metadados de Otimização do público-alvo de acordo com essas especificações.
seo-title: Formato de conteúdo para arquivos de metadados
solution: Audience Manager
title: Formato de conteúdo para arquivos de metadados
uuid: 9 ba 44738-3 e 17-40 c 7-9 e 8 c -5 abd 8361 e 16 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Content Format for Metadata Files{#content-format-for-metadata-files}

Formate o conteúdo do seu arquivo de metadados de Otimização do público-alvo de acordo com essas especificações.

## Sintaxe {#syntax}

A sintaxe a seguir define a estrutura de conteúdo bem formado em um arquivo de metadados. Note, *italics* indicates a variable placeholder.

**Sintaxe:***ID do conteúdo* | *name* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

The third column **-1** is technically the Parent ID, which is a legacy field. The value should always be set as **-1**.

>[!NOTE]
>
>Observe que é necessário um arquivo de metadados por dimensão, para que vários arquivos de metadados sejam esperados no compartimento. The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Entradas de arquivo separadas com ^ a (control-A ou ASCII 001)**

Use `^a` (control-A or ASCII 001) to separate content in your metadata files. Como esses caracteres não são imprimíveis, o exemplo de sintaxe acima mostra uma barra vertical|" apenas para fins de exibição.

If needed, you may download the example file - [20181105_0_1](assets/20181105_0_1.zip). Descompacte-o e edite-o no seu editor de escolha e ajuste de acordo com seu conteúdo de metadados reais, já que ele já contém o delimitador necessário.

>[!IMPORTANT]
>
>Não adicione linhas de cabeçalho a arquivos de metadados.

## Exemplos {#examples}

Vejamos como estruturar o conteúdo em um arquivo de metadados. Parte dessa estrutura depende da dimensão. The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

Neste exemplo, o título do arquivo é 20180921_ 0_ 1, e as três colunas no arquivo são: ID da campanha, nome e ID pai.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Creative**

Neste exemplo, o título do arquivo é 20180827_ 0_ 2, e as três colunas no arquivo são: ID de criação, nome e ID pai.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Site**

Neste exemplo, o título do arquivo é 20180921_ 0_ 5, e as três colunas no arquivo são: ID do site, nome e ID pai.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
