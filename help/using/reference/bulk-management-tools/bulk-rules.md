---
description: As planilhas de criação e atualização aceitam um cabeçalho traitRule que permite aplicar várias regras em uma única operação. Siga estas instruções para fazer solicitações de regras em massa.
seo-description: As planilhas de criação e atualização aceitam um cabeçalho traitRule que permite aplicar várias regras em uma única operação. Siga estas instruções para fazer solicitações de regras em massa.
seo-title: Criar ou atualizar regras de características e regras de segmento
solution: Audience Manager
title: Criar ou atualizar regras de características e regras de segmento
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 10%

---

# Criar ou atualizar regras de características e regras de segmento{#create-or-update-trait-rules-and-segment-rules}

As planilhas de criação e atualização aceitam um cabeçalho traitRule que permite aplicar várias regras em uma única operação. Siga estas instruções para fazer solicitações de regras em massa.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[As ](../../features/administration/administration-overview.md) permissões do grupo RBAC atribuídas na  [!DNL Audience Manager] interface do usuário são honradas no  [!UICONTROL Bulk Management Tools].

## Trabalhar com regras de características {#trait-rules}

Na planilha, a coluna de regra de característica retorna e aceita regras que consistem em expressões booleanas, operadores de comparação e expressões regulares. Você pode criar regras com características ou construtor de segmentos em [!DNL Audience Manager] e copiá-las para sua planilha. Ou, se você estiver familiarizado com a sintaxe da regra, poderá gravar expressões diretamente nas planilhas.

## Exemplo do construtor de regras {#rule-builder-example}

Vejamos um exemplo que demonstra como usar [!UICONTROL Segment Builder] para criar uma regra que possa ser usada na planilha em massa. No entanto, este não é um conjunto de instruções passo a passo para essas ferramentas. Em vez disso, vamos começar com uma regra simples que já foi criada. Para obter instruções sobre como usar os construtores de regras, consulte [Construtor de segmentos](../../features/segments/segment-builder.md) e [Construtor de características](../../features/traits/about-trait-builder.md).

Com o construtor de regras visuais, criamos uma regra de segmento com 3 características e um operador booleano [!UICONTROL AND].

![](assets/visualrule.png)

Clique em **[!UICONTROL Code View]** para obter a versão de texto dessa regra.

>[!TIP]
>
>Clique em **[!UICONTROL Validate Expression]** para verificar a lógica da regra. Isso ajudará a impedir o upload de uma regra inválida.

![](assets/coderule.png)

Cole a regra na planilha [!UICONTROL Bulk Management Tools] e confira as alterações para atualizar as regras de segmento em massa.

![](assets/segmentrule.png)

## Criar suas próprias regras {#create-rules}

Você pode gravar suas próprias regras fora de [!UICONTROL Rule Builder]. Antes de começar, leia a documentação que abrange coisas como operadores, expressão e variáveis obrigatórias. Recomendamos que você analise o seguinte:

* [Trabalhar Com Operadores De Comparação No Construtor De Características](../../features/traits/trait-comparison-operators.md)
* [Ordem de operação](../../features/traits/trait-operator-precedence.md)
* [Requisitos de prefixo para variáveis-chave](../../features/traits/trait-variable-prefixes.md)
* [Expressões de amostra com operadores booleanos e de comparação](../../features/traits/trait-expression-samples.md)
