---
description: Um sinal derivado qualifica os visitantes do site para características adicionais com base em uma característica que eles já viram. Em outras palavras, a qualificação de característica adicional pode ser derivada de uma característica atualmente exibida, mesmo se um usuário nunca tiver visto a nova característica antes.
seo-description: Um sinal derivado qualifica os visitantes do site para características adicionais com base em uma característica que eles já viram. Em outras palavras, a qualificação de característica adicional pode ser derivada de uma característica atualmente exibida, mesmo se um usuário nunca tiver visto a nova característica antes.
seo-title: Sinais derivados
solution: Audience Manager
title: Sinais derivados
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 2%

---


# Sinais derivados {#derived-signals}

Um [!UICONTROL derived signal] qualifica os visitantes do site para características adicionais com base em uma característica que eles já viram. Em outras palavras, a qualificação de característica adicional pode ser derivada de uma característica atualmente exibida, mesmo se um usuário nunca tiver visto a nova característica antes.

<!-- c_tb_derived_signal.xml -->

## Finalidade dos sinais derivados

Em [!DNL Audience Manager], você pode criar uma relação entre sinais (ou regras de características) transmitidos durante uma chamada de evento para outros sinais ou características especificados. Por exemplo, suponha que uma chamada de evento passe em um sinal composto pelo valor-chave [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] conectaria esse sinal a quaisquer outros criados com a [!UICONTROL derived signals] ferramenta. Embora os sinais associados possam ser quaisquer valores-chave especificados por você, eles são mais úteis quando vinculados a sinais existentes já configurados como [!UICONTROL Trait Builder] regras. Por exemplo, na figura abaixo, quando uma ação do usuário dispara o sinal [!DNL "product = new car"] que o usuário também pode se qualificar para características definidas pela chave do público alvo e sinais de valor.

![](assets/derived_signal_example.png)

## Localização dos Sinais Derivados

Crie e gerencie [!UICONTROL derived signals] a partir **[!UICONTROL Tools > Derived Signals]** da barra lateral.

## Criar um sinal derivado {#create}

<!-- t_tb_create_derived.xml -->

To create a [!UICONTROL derived signal]:

1. Selecione **[!UICONTROL Derived Signals]** no [!UICONTROL Tools] menu.
1. Forneça um:
   * *(Opcional)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Clique em **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>O limite de caracteres para os campos [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key]e [!UICONTROL Target Value] é de 228 caracteres.

## Editar um sinal derivado {#edit}

<!-- t_tb_edit_derived.xml -->

To edit a [!UICONTROL derived signal]:

1. Passe o mouse sobre o sinal e clique em **[!UICONTROL Edit]**.
2. Faça as alterações necessárias de código, chave ou valor e clique em **[!UICONTROL Save]**.

## Excluir um sinal derivado {#delete}

<!-- t_tb_delete_derived.xml -->

Para apagar um sinal [!UICONTROL derived signal], passe o mouse sobre o sinal e clique em **[!UICONTROL Delete]**.
