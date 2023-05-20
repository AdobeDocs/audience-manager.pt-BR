---
description: As planilhas criar e atualizar aceitam um cabeçalho de regra de característica que permite aplicar várias regras em uma única operação. Siga estas instruções para fazer solicitações de regra em massa.
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: Criar ou atualizar regras de características e regras de segmento
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 8%

---

# Criar ou atualizar regras de características e regras de segmento{#create-or-update-trait-rules-and-segment-rules}

As planilhas criar e atualizar aceitam um cabeçalho de regra de característica que permite aplicar várias regras em uma única operação. Siga estas instruções para fazer solicitações de regra em massa.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[Permissões de grupo RBAC](../../features/administration/administration-overview.md) atribuído no [!DNL Audience Manager] A interface do usuário do é respeitada na [!UICONTROL Bulk Management Tools].

## Trabalhar com regras de características {#trait-rules}

Em sua planilha, a coluna regra de característica retorna e aceita regras que consistem em expressões booleanas, operadores de comparação e expressões regulares. Você pode criar regras com o construtor de características ou segmentos em [!DNL Audience Manager] e copie-os na sua planilha. Ou, se você estiver familiarizado com a sintaxe de regra, poderá escrever expressões diretamente nas planilhas.

## Exemplo do construtor de regras {#rule-builder-example}

Vamos ver um exemplo que demonstra como usar [!UICONTROL Segment Builder] para criar uma regra, é possível adicionar à planilha em massa. No entanto, isso não é um conjunto de instruções passo a passo para essas ferramentas. Em vez disso, começaremos com uma regra simples que já foi criada. Para obter instruções sobre como usar os construtores de regras, consulte [Construtor de segmentos](../../features/segments/segment-builder.md) e [Construtor de características](../../features/traits/about-trait-builder.md).

Com o construtor de regras visuais, criamos uma regra de segmento com 3 características e um booleano [!UICONTROL AND] operador.

![](assets/visualrule.png)

Clique em **[!UICONTROL Code View]** para obter a versão de texto desta regra.

>[!TIP]
>
>Clique em **[!UICONTROL Validate Expression]** para verificar a lógica da regra. Isso ajudará a impedir que você carregue uma regra inválida.

![](assets/coderule.png)

Cole a regra na [!UICONTROL Bulk Management Tools] e confirme as alterações para atualizar as regras de segmento em massa.

![](assets/segmentrule.png)

## Criar suas próprias regras {#create-rules}

Você pode escrever suas próprias regras fora do [!UICONTROL Rule Builder]. Antes de começar, leia a documentação que aborda coisas como operadores, expressão e variáveis necessárias. Recomendamos que você analise o seguinte:

* [Trabalhar Com Operadores De Comparação No Construtor De Características](../../features/traits/trait-comparison-operators.md)
* [Ordem de operação](../../features/traits/trait-operator-precedence.md)
* [Requisitos de prefixo para variáveis-chave](../../features/traits/trait-variable-prefixes.md)
* [Expressões de amostra com operadores booleanos e de comparação](../../features/traits/trait-expression-samples.md)
