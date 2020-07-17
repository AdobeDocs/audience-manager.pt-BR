---
description: No Construtor de características, o Construtor de Expressões permite criar e testar regras que estabelecem requisitos de qualificação de audiências. As regras consistem em pares de valores chave, como "color == blue" ou "price > 100". Operadores de comparação estabelecem a relação entre chaves e valores. expressões booleanas determinam a relação entre grupos de regras.
seo-description: No Construtor de características, o Construtor de Expressões permite criar e testar regras que estabelecem requisitos de qualificação de audiências. As regras consistem em pares de valores chave, como "color == blue" ou "price > 100". Operadores de comparação estabelecem a relação entre chaves e valores. expressões booleanas determinam a relação entre grupos de regras.
seo-title: Gerenciamento de regras de características
solution: Audience Manager
title: Gerenciamento de regras de características
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 1%

---


# Gerenciamento de regras de características {#managing-trait-rules}

Em [!UICONTROL Trait Builder], o [!UICONTROL Expression Builder] permite criar e testar regras que estabelecem requisitos de qualificação de audiência. As regras consistem em pares de valores chave, como `color == blue` ou `price > 100`. Operadores de comparação estabelecem a relação entre chaves e valores. [!DNL Boolean] As expressões determinam a relação entre grupos de regras.

<!-- c_tb_rules.xml -->

## Principais recursos das regras de sinal descritos

![](assets/manage-trait-rules.png)

1. As guias **[!UICONTROL Expression Builder]** ou **[!UICONTROL Code View]** fornecem uma visão geral das regras em seu traço. A **[!UICONTROL Expression Builder]** guia permite criar regras com campos e menus suspensos. O **[!UICONTROL Code View]** permite criar regras escrevendo manualmente essas expressões como código. A ilustração acima mostra uma característica simples composta de um sinal que avalia os dados para uma condição de qualificação, onde uma chave de produto é igual a um valor específico, neste caso `color == "blue"`.

1. Os campos e controles desta seção permitem criar sinais a partir de pares de valores chave e definir a relação entre eles e um operador de comparação. Uma chave, um operador e um valor são necessários.
1. O [!UICONTROL Data Explorer Options] permite preencher retroativamente as realizações de características para seus sinais.
   >[!NOTE]
   >
   >Esta opção só está disponível para [!UICONTROL Data Explorer] clientes. Entre em contato com seu consultor da Adobe para obter detalhes.
1. Esta seção mostra uma estimativa das realizações de características dos últimos 7 dias, para os sinais definidos no [!UICONTROL Expression Builder], para traços preenchidos retroativamente e não preenchidos retroativamente.
   >[!NOTE]
   >
   >Esta opção só está disponível para [!UICONTROL Data Explorer] clientes. Entre em contato com seu consultor da Adobe para obter detalhes.
1. Os campos de teste permitem que você valide combinações de regras de sinal ou [!DNL URL]os valores que deseja usar ao enviar dados para o Audience Manager.

## Criar uma regra de característica {#create-trait-rule}

As regras (ou expressões) consistem em indivíduos ou grupos de pares de valores chave. Os operadores de comparação definem a relação entre pares de valores chave. Para criar uma regra, forneça uma chave, um valor, selecione um operador e clique em **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Preencha os campos obrigatórios na **[!UICONTROL Basic Information]** seção *antes* de criar regras de características.

1. Expanda a **[!UICONTROL Trait Expression]** seção e digite um nome de chave e valor. Isto cria um *`signal`*.
   >[!NOTE]
   >
   >Inclua o `c_` prefixo (ou qualquer outra convenção de nomenclatura) da variável principal se as chamadas de evento enviarem dados para [!DNL Audience Manager] usar essa sintaxe.
1. Selecione um operador [de](../../features/traits/trait-comparison-operators.md) comparação no **[!UICONTROL Operator]** menu suspenso. O operador de comparação avalia a relação entre os elementos em um sinal.
   >[!NOTE]
   >
   >O [!DNL Boolean] operador estabelece a relação entre vários sinais [!UICONTROL OR] dentro ** de um grupo e não pode ser alterada.
1. Clique em **[!UICONTROL Add Rule]**. A regra salva aparece na área de trabalho de características acima dos campos de entrada de dados.

### Exemplo {#example-trait-rule}

No exemplo abaixo, um usuário criou uma nova regra de característica com base na ID do produto. Para criar essa regra, o usuário forneceu a chave `productkey` vinculada a um operador igual ( `==`) ao valor `2093`.
![](assets/tb_sample_rule1.png)

Clicar **[!UICONTROL Add Rule]** salva e move a característica para dentro da [!UICONTROL Expression Builder] área de trabalho.

![](assets/tb_sample_rule2.png)

## Create a New Rule Group {#create-rule-group}

Este procedimento descreve como criar um novo grupo de regras.

<!-- t_tb_new_rule_group.xml -->

Sua característica deve conter pelo menos duas regras antes de você poder criar um novo grupo de regras.

1. Mova o cursor sobre a regra que deseja mover para realçá-la.
1. Passe o mouse sobre a borda da regra realçada.
Isso automaticamente separa a regra do grupo atual e a move para um novo grupo.
   >[!NOTE]
   >
   >Arraste uma regra de volta ao grupo original se movê-la não intencionalmente.
1. Selecione um [!DNL Boolean] operador ( [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) no menu suspenso para definir a relação entre os grupos de regras.

## Mover regras entre grupos {#move-rules-between-groups}

Para mover uma regra, clique e arraste-a para outro grupo.

## Editar uma característica {#edit-trait}

Este procedimento descreve como editar uma característica.

<!-- t_tb_edit.xml -->

1. No [!UICONTROL Traits] painel, passe o mouse sobre a **[!UICONTROL Actions]** coluna referente à característica que deseja editar. Isso traz à tona os ícones de gerenciamento de características.
1. Clique no lápis para editar a característica.

   ![](assets/tb_edit_trait.png)

## Excluir uma regra de característica {#delete-trait}

Este procedimento descreve como excluir uma regra de característica.

<!-- t_tb_delete_rule.xml -->

1. No [!UICONTROL Traits] painel, passe o mouse sobre as [!UICONTROL Actions] colunas da característica que deseja editar e clique no ícone de lápis. Isso traz à tona os ícones de gerenciamento de características.
1. Expand the [!UICONTROL Trait Expression] section.
1. Passe o mouse sobre a regra que deseja excluir e clique no ícone X. A regra é excluída imediatamente.

>[!MORELIKETHIS]
>
>* [Criar um novo grupo de regras](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Mover regras entre grupos](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Criar uma regra de característica](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Excluir uma regra de característica](../../features/traits/manage-trait-rules.md#delete-trait)
>* [Mover regras entre grupos](../../features/traits/manage-trait-rules.md#move-rules-between-groups)

