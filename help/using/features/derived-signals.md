---
description: Um sinal derivado qualifica os visitantes do site para características adicionais com base em uma característica que eles já viram. Em outras palavras, a qualificação de característica adicional pode ser derivada de uma característica exibida no momento, mesmo se um usuário nunca tiver visto a nova característica antes.
seo-description: Um sinal derivado qualifica os visitantes do site para características adicionais com base em uma característica que eles já viram. Em outras palavras, a qualificação de característica adicional pode ser derivada de uma característica exibida no momento, mesmo se um usuário nunca tiver visto a nova característica antes.
seo-title: Sinais derivados
solution: Audience Manager
title: Sinais derivados
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: 'Características '
exl-id: 64bc004a-a31a-49bb-aa58-323fbc92f76f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 2%

---

# Sinais derivados {#derived-signals}

Um [!UICONTROL derived signal] qualifica os visitantes do site para características adicionais com base em uma característica que eles já viram. Em outras palavras, a qualificação de característica adicional pode ser derivada de uma característica exibida no momento, mesmo se um usuário nunca tiver visto a nova característica antes.

<!-- c_tb_derived_signal.xml -->

## Finalidade dos sinais derivados

Em [!DNL Audience Manager], você pode criar uma relação entre sinais (ou regras de características) passados durante uma chamada de evento para outros sinais ou características especificados. Por exemplo, suponha que uma chamada de evento passe em um sinal composto pelo valor-chave [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] conectaria esse sinal a qualquer outro criado com a  [!UICONTROL derived signals] ferramenta. Embora os sinais associados possam ser quaisquer valores-chave especificados, eles são mais úteis quando vinculados a sinais existentes já configurados como regras [!UICONTROL Trait Builder]. Por exemplo, na ilustração abaixo, quando uma ação do usuário aciona o sinal [!DNL "product = new car"], esse usuário também pode se qualificar para características definidas pela chave de destino e sinais de valor.

![](assets/derived_signal_example.png)

## Localização dos sinais derivados

Crie e gerencie [!UICONTROL derived signals] em **[!UICONTROL Tools > Derived Signals]** na barra de navegação lateral.

## Criar um sinal derivado {#create}

<!-- t_tb_create_derived.xml -->

Para criar um [!UICONTROL derived signal]:

1. Selecione **[!UICONTROL Derived Signals]** no menu [!UICONTROL Tools].
1. Forneça um:
   * *(Opcional)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Clique em **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>O limite de caracteres para os campos [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key] e [!UICONTROL Target Value] é de 228 caracteres.

## Editar um sinal derivado {#edit}

<!-- t_tb_edit_derived.xml -->

Para editar um [!UICONTROL derived signal]:

1. Passe o cursor do mouse sobre o sinal e clique em **[!UICONTROL Edit]**.
2. Faça as alterações necessárias no código, chave ou valor e clique em **[!UICONTROL Save]**.

## Excluir um sinal derivado {#delete}

<!-- t_tb_delete_derived.xml -->

Para excluir um [!UICONTROL derived signal], passe o mouse sobre o sinal e clique em **[!UICONTROL Delete]**.
