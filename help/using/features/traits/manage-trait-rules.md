---
description: No Construtor de características, o Construtor de expressões permite criar e testar regras que estabelecem requisitos de qualificação de público-alvo. As regras consistem em pares de valores- chave como "color == blue" ou "price &gt; 100". Os operadores de comparação estabelecem a relação entre chaves e valores. Expressões booleanas determinam a relação entre grupos de regras.
seo-description: In Trait Builder, the Expression Builder lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as "color == blue" or "price &gt; 100". Comparison operators establish the relationship between keys and values. Boolean expressions determine the relationship between rule groups.
seo-title: Managing Trait Rules
solution: Audience Manager
title: Gerenciamento de regras de características
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
exl-id: 4561b19a-bbb5-41ec-ac79-ab3e2ab75548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 1%

---

# Gerenciamento de regras de características {#managing-trait-rules}

Entrada [!UICONTROL Trait Builder], o [!UICONTROL Expression Builder] O permite criar e testar regras que estabelecem requisitos de qualificação de público-alvo. As regras consistem em pares de valores chave, como `color == blue` ou `price > 100`. Os operadores de comparação estabelecem a relação entre chaves e valores. [!DNL Boolean] as expressões determinam a relação entre grupos de regras.

<!-- c_tb_rules.xml -->

## Descrição dos recursos principais das regras de sinal

![](assets/manage-trait-rules.png)

1. A variável **[!UICONTROL Expression Builder]** ou **[!UICONTROL Code View]** As guias fornecem uma visão geral das regras em sua característica. A variável **[!UICONTROL Expression Builder]** permite criar regras com campos e menus suspensos. A variável **[!UICONTROL Code View]** O permite criar regras ao escrever manualmente essas expressões como código. A ilustração acima mostra uma característica simples composta por um sinal que avalia dados para uma condição de qualificação em que uma chave do produto é igual a um valor específico, neste caso `color == "blue"`.

1. Os campos e controles nesta seção permitem criar sinais de pares de valores chave e definir a relação entre eles com um operador de comparação. Uma chave, operador e valor são necessários.
1. A variável [!UICONTROL Data Explorer Options] O permite preencher retroativamente realizações de características para seus sinais.

   >[!NOTE]
   >
   >Essa opção só está disponível para [!UICONTROL Data Explorer] clientes. Entre em contato com seu consultor do Adobe para obter detalhes.

1. Esta seção mostra uma estimativa das realizações de características dos últimos 7 dias, para os sinais definidos na variável [!UICONTROL Expression Builder], para características preenchidas e não preenchidas retroativamente.

   >[!NOTE]
   >
   >Essa opção só está disponível para [!UICONTROL Data Explorer] clientes. Entre em contato com seu consultor do Adobe para obter detalhes.

1. Os campos de teste permitem validar combinações de regras de sinal ou [!DNL URL]s que você deseja usar ao enviar dados para o Audience Manager.

## Criar uma regra de característica {#create-trait-rule}

As regras (ou expressões) consistem em pares de valores chave individuais ou em grupos. Os operadores de comparação definem a relação entre pares de valores chave. Para criar uma regra, forneça uma chave, um valor, selecione um operador e clique em **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Preencha os campos obrigatórios na **[!UICONTROL Basic Information]** seção *antes* criação de regras de características.

1. Expanda a **[!UICONTROL Trait Expression]** e insira um nome de chave e valor. Isso cria uma *`signal`*.

   >[!NOTE]
   >
   >Inclua o `c_` prefixo (ou qualquer outra convenção de nomenclatura) para a variável principal, se as chamadas de evento enviarem dados para [!DNL Audience Manager] usando essa sintaxe.

1. Selecione um [operador de comparação](../../features/traits/trait-comparison-operators.md) do **[!UICONTROL Operator]** lista suspensa. O operador de comparação avalia a relação entre os elementos em um sinal.

   >[!NOTE]
   >
   >A variável [!DNL Boolean] [!UICONTROL OR] estabelece a relação entre sinais múltiplos *no prazo de* um grupo e não podem ser alteradas.

1. Clique em **[!UICONTROL Add Rule]**. A regra salva aparece no espaço de trabalho de características acima dos campos de entrada de dados.

### Exemplo {#example-trait-rule}

No exemplo abaixo, um usuário criou uma nova regra de característica com base na ID do produto. Para criar essa regra, o usuário forneceu a chave `productkey` vinculado a um operador igual ( `==`) para o valor `2093`.

![](assets/tb_sample_rule1.png)

Clicando **[!UICONTROL Add Rule]** salva e move a característica para a [!UICONTROL Expression Builder] espaço de trabalho.

![](assets/tb_sample_rule2.png)

## Criar um novo grupo de regras {#create-rule-group}

Este procedimento descreve como criar um novo grupo de regras.

<!-- t_tb_new_rule_group.xml -->

Sua característica deve conter pelo menos duas regras para que você possa criar um novo grupo de regras.

1. Mova o cursor sobre a regra que deseja mover para realçá-la.
1. Passe o mouse sobre a borda da regra destacada.

   Isso separa automaticamente a regra de seu grupo atual e a move para um novo grupo.

   >[!NOTE]
   >
   >Arraste uma regra de volta ao seu grupo original se você movê-la involuntariamente.

1. Selecione um [!DNL Boolean] operador ([!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) no menu suspenso para definir a relação entre os grupos de regras.

## Mover regras entre grupos {#move-rules-between-groups}

Para mover uma regra, clique nela e arraste-a para outro grupo.

## Editar uma característica {#edit-trait}

Este procedimento descreve como editar uma característica.

<!-- t_tb_edit.xml -->

1. No [!UICONTROL Traits] painel, passe o mouse sobre o **[!UICONTROL Actions]** para a característica que deseja editar. Isso exibe os ícones de gerenciamento de características.
1. Clique no lápis para editar a característica.

   ![](assets/tb_edit_trait.png)

## Excluir uma regra de característica {#delete-trait}

Este procedimento descreve como excluir uma regra de característica.

<!-- t_tb_delete_rule.xml -->

1. No [!UICONTROL Traits] painel, passe o mouse sobre o [!UICONTROL Actions] para a característica que deseja editar e clique no ícone de lápis. Isso exibe os ícones de gerenciamento de características.
1. Expanda a [!UICONTROL Trait Expression] seção.
1. Passe o mouse sobre a regra que deseja excluir e clique no ícone X. A regra é excluída imediatamente.

>[!MORELIKETHIS]
>
>* [Criar um novo grupo de regras](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Mover regras entre grupos](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Criar uma regra de característica](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Excluir uma regra de característica](../../features/traits/manage-trait-rules.md#delete-trait)
>* [Mover regras entre grupos](../../features/traits/manage-trait-rules.md#move-rules-between-groups)

