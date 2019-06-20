---
description: As planilhas criar e atualizar aceitam um cabeçalho traitrule que permite aplicar várias regras em uma única operação. Siga estas instruções para realizar solicitações de regras em massa.
seo-description: As planilhas criar e atualizar aceitam um cabeçalho traitrule que permite aplicar várias regras em uma única operação. Siga estas instruções para realizar solicitações de regras em massa.
seo-title: Criar ou atualizar regras de características e regras de segmento
solution: Audience Manager
title: Criar ou atualizar regras de características e regras de segmento
uuid: bdd 5 f 8 f 1-bb 83-4844-b 681-654 e 45 ace 3 e 1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create or Update Trait Rules and Segment Rules{#create-or-update-trait-rules-and-segment-rules}

As planilhas criar e atualizar aceitam um cabeçalho traitrule que permite aplicar várias regras em uma única operação. Siga estas instruções para realizar solicitações de regras em massa.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Essa ferramenta é fornecida para conveniência e apenas como cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [As permissões de grupo RBAC](../../features/administration/administration-overview.md) atribuídas na [!DNL Audience Manager] interface do usuário são respeitadas [!UICONTROL Bulk Management Tools].

## Working with trait rules {#trait-rules}

Na planilha, a coluna da regra de característica retorna e aceita regras que consistem em expressões booleanas, operadores de comparação e expressões regulares. You can create rules with trait or segment builder in [!DNL Audience Manager] and copy them to your worksheet. Ou, se você estiver familiarizado com a sintaxe da regra, poderá escrever expressões diretamente nas planilhas.

## Rule builder example {#rule-builder-example}

Let&#39;s take a look at an example that demonstrates how to use [!UICONTROL Segment Builder] to create a rule you can to the bulk worksheet. No entanto, esse não é um conjunto de instruções passo a passo para essas ferramentas. Em vez disso, começaremos com uma regra simples que já foi criada. For instructions about how to use the rule builders see [Segment Builder](../../features/segments/segment-builder.md) and [Trait Builder](../../features/traits/about-trait-builder.md).

With the visual rule builder, we&#39;ve created a segment rule with 3 traits and a Boolean [!UICONTROL AND] operator.

![](assets/visualrule.png)

Click **[!UICONTROL Code View]** to get the text version of this rule.

>[!TIP]
>
>Click **[!UICONTROL Validate Expression]** to check your rule logic. Isso ajudará a impedir que você carregue uma regra inválida.

![](assets/coderule.png)

Paste the rule into the [!UICONTROL Bulk Management Tools] worksheet and commit your changes to update segment rules in bulk.

![](assets/segmentrule.png)

## Creating your own rules {#create-rules}

You can write your own rules outside of [!UICONTROL Rule Builder]. Antes de começar, leia a documentação que abrange coisas como operadores, expressões e variáveis necessárias. Recomendamos que você analise o seguinte:

* [Trabalhar com operadores de comparação no Construtor de características](../../features/traits/trait-comparison-operators.md)
* [Ordem das operações](../../features/traits/trait-operator-precedence.md)
* [Requisitos de prefixo para variáveis principais](../../features/traits/trait-variable-prefixes.md)
* [Expressões de amostra com operadores booleanos e de comparação](../../features/traits/trait-expression-samples.md)

