---
description: Um sinal derivado qualifica os visitantes do site para características adicionais com base em uma característica já vista. Em outras palavras, a qualificação de característica adicional pode ser derivada de uma característica exibida atualmente mesmo que um usuário nunca tenha visto a nova característica antes.
seo-description: Um sinal derivado qualifica os visitantes do site para características adicionais com base em uma característica já vista. Em outras palavras, a qualificação de característica adicional pode ser derivada de uma característica exibida atualmente mesmo que um usuário nunca tenha visto a nova característica antes.
seo-title: Sinais derivados
solution: Audience Manager
title: Sinais derivados
uuid: e 52600 e 3-26 d 1-4607-9 b 96-afd 6086 a 252 d
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Derived Signals {#derived-signals}

A [!UICONTROL derived signal] qualifies site visitors for additional traits based on a trait they&#39;ve already seen. Em outras palavras, a qualificação de característica adicional pode ser derivada de uma característica exibida atualmente mesmo que um usuário nunca tenha visto a nova característica antes.

<!-- c_tb_derived_signal.xml -->

## Finalidade dos sinais derivados

In [!DNL Audience Manager], you can create a relationship between signals (or trait rules) passed in during an event call to other, specified signals or traits. For example, assume an event call passes in a signal composed of the key-value [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] conectaria esse sinal a qualquer outra pessoa criada com [!UICONTROL derived signals] a ferramenta. Although the associated signals can be any key-values you specify, they are most useful when linked to existing signals already set up as [!UICONTROL Trait Builder] rules. For example, in the illustration below, when a user action fires the signal [!DNL "product = new car"] that user can also qualify for traits defined by the target key and value signals.

![](assets/derived_signal_example.png)

## Localização de sinais derivados

Create and manage [!UICONTROL derived signals] in **[!UICONTROL Tools > Derived Signals]** from the sidebar navigation.

## Create a Derived Signal {#create}

<!-- t_tb_create_derived.xml -->

To create a [!UICONTROL derived signal]:

1. Select **[!UICONTROL Derived Signals]** from the [!UICONTROL Tools] menu.
1. Forneça a:
   * *(Opcional)*[!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Clique em **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>The character limit for the [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key], and [!UICONTROL Target Value] fields is 228 characters.

## Edit a Derived Signal {#edit}

<!-- t_tb_edit_derived.xml -->

To edit a [!UICONTROL derived signal]:

1. Hover over the signal, then click **[!UICONTROL Edit]**.
2. Make the required code, key, or value changes, then click **[!UICONTROL Save]**.

## Delete a Derived Signal {#delete}

<!-- t_tb_delete_derived.xml -->

To delete a [!UICONTROL derived signal], hover over the signal, then click **[!UICONTROL Delete]**.
