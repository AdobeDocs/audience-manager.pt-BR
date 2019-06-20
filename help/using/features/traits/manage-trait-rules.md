---
description: No Construtor de traços, o Construtor de expressões permite criar e testar regras que estabelecem requisitos de qualificação de público-alvo. As regras consistem em pares de valor chave, como "color = = blue" ou "price > 100". Os operadores de comparação estabelecem a relação entre chaves e valores. Expressões booleanas determinam a relação entre grupos de regras.
seo-description: No Construtor de traços, o Construtor de expressões permite criar e testar regras que estabelecem requisitos de qualificação de público-alvo. As regras consistem em pares de valor chave, como "color = = blue" ou "price > 100". Os operadores de comparação estabelecem a relação entre chaves e valores. Expressões booleanas determinam a relação entre grupos de regras.
seo-title: Gerenciando regras de características
solution: Audience Manager
title: Gerenciando regras de características
uuid: 827 d 4567-2 b 6 f -411 e-bd 5 c -9735 c 916291 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Managing Trait Rules {#managing-trait-rules}

In [!UICONTROL Trait Builder], the [!UICONTROL Expression Builder] lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as `color == blue` or `price > 100`. Os operadores de comparação estabelecem a relação entre chaves e valores. [!DNL Boolean] expressões determinam a relação entre grupos de regras.

<!-- c_tb_rules.xml -->

## Recursos de regras de sinal principal descritos

![](assets/manage-trait-rules.png)

1. The **[!UICONTROL Expression Builder]** or **[!UICONTROL Code View]** tabs provide an overview of the rules in your trait. The **[!UICONTROL Expression Builder]** tab lets you create rules with fields and drop-down menus. The **[!UICONTROL Code View]** lets you create rules by manually writing those expressions as code. The illustration above shows a simple trait composed of a signal that evaluates data for a qualifying condition where a product key equals a specific value, in this case `color == "blue"`.

1. Os campos e controles nesta seção permitem criar sinais de pares de valores chave e definir a relação entre eles com um operador de comparação. É necessária uma chave, um operador e um valor.
1. The [!UICONTROL Data Explorer Options] allow you to backfill trait realizations for your signals.
   >[!NOTE]
   >
   >This option is only available for [!UICONTROL Data Explorer] customers. Entre em contato com o consultor da Adobe para obter detalhes.
1. This section shows you an estimation of trait realizations for the past 7 days, for the signals defined in the [!UICONTROL Expression Builder], for backfilled and non-backfilled traits.
   >[!NOTE]
   >
   >This option is only available for [!UICONTROL Data Explorer] customers. Entre em contato com o consultor da Adobe para obter detalhes.
1. The test fields let you validate combinations of signal rules or the [!DNL URL]s that you want to use when sending data to Audience Manager.

## Create a Trait Rule {#create-trait-rule}

As regras (ou expressões) consistem em pares individuais ou grupos de pares de valor chave. Os operadores de comparação definem a relação entre pares de valor chave. To create a rule,provide a key, a value, select an operator, and click **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Complete the required fields in the **[!UICONTROL Basic Information]** section *before* creating trait rules.

1. Expand the **[!UICONTROL Trait Expression]** section and enter a key and value name. This creates a *`signal`*.
   >[!NOTE]
   >
   >Include the `c_` prefix (or any other naming convention) for key variable if your event calls send data to [!DNL Audience Manager] using that syntax.
1. Select a [comparison operator](../../features/traits/trait-comparison-operators.md) from the **[!UICONTROL Operator]** dropdown. O operador de comparação avalia a relação entre os elementos em um sinal.
   >[!NOTE]
   >
   >The [!DNL Boolean] [!UICONTROL OR] operator establishes the relationship between multiple signals *within* a group and cannot be changed.
1. Clique em **[!UICONTROL Add Rule]**. A regra salva aparece na área de trabalho de características acima dos campos de entrada de dados.

### Exemplo {#example-trait-rule}

No exemplo abaixo, um usuário criou uma nova regra de característica com base na ID do produto. To build this rule, the user provided the key `productkey` linked with an equals operator ( `==`) to the value `2093`.
![](assets/tb_sample_rule1.png)

Clicking **[!UICONTROL Add Rule]** saves and moves the trait into the [!UICONTROL Expression Builder] workspace.

![](assets/tb_sample_rule2.png)

>[!MORE_ LIKE_ THIS]
>
>* [Criar um novo grupo de regras](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Mover regras entre grupos](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Excluir uma regra de característica](../../features/traits/manage-trait-rules.md#delete-trait)


## Create a New Rule Group {#create-rule-group}

Este procedimento descreve como criar um novo grupo de regras.

<!-- t_tb_new_rule_group.xml -->

Sua característica deve conter pelo menos duas regras antes de você poder criar um novo grupo de regras.

1. Mova o cursor sobre a regra que você deseja mover para destacá-lo.
1. Passe o mouse sobre a borda da regra realçada.
Isso separa automaticamente a regra de seu grupo atual e o move para um novo grupo.
   >[!NOTE]
   >
   >Arraste uma regra de volta para seu grupo original se você o mover de forma involuntária.
1. Select a [!DNL Boolean] operator ( [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) from the drop-down menu to set the relationship between the rule groups.

>[!MORE_ LIKE_ THIS]
>
>* [Criar uma regra de traços](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Mover regras entre grupos](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Excluir uma regra de característica](../../features/traits/manage-trait-rules.md#delete-trait)


## Move Rules Between Groups {#move-rules-between-groups}

Para mover uma regra, clique e arraste-a para outro grupo.

>[!MORE_ LIKE_ THIS]
>
>* [Criar uma regra de traços](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Criar um novo grupo de regras](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Excluir uma regra de característica](../../features/traits/manage-trait-rules.md#delete-trait)


## Edit a Trait {#edit-trait}

Este procedimento descreve como editar uma característica.

<!-- t_tb_edit.xml -->

1. In the [!UICONTROL Traits] dashboard, hover over the **[!UICONTROL Actions]** column for the trait you want to edit. Isso exibe os ícones de gerenciamento de características.
1. Clique no lápis para editar a característica.

   ![](assets/tb_edit_trait.png)

## Delete a Trait Rule {#delete-trait}

Este procedimento descreve como excluir uma regra de característica.

<!-- t_tb_delete_rule.xml -->

1. In the [!UICONTROL Traits] dashboard, hover over the [!UICONTROL Actions] columns for the trait you want to edit and click the pencil icon. Isso exibe os ícones de gerenciamento de características.
1. Expand the [!UICONTROL Trait Expression] section.
1. Passe o mouse sobre a regra que deseja excluir e clique no ícone X. A regra é excluída imediatamente.