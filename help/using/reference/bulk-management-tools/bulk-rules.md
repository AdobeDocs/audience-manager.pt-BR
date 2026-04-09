---
description: As planilhas criar e atualizar aceitam um cabeçalho de regra de característica que permite aplicar várias regras em uma única operação. Siga estas instruções para fazer solicitações de regra em massa.
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: Criar ou atualizar regras de características e regras de segmento
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
TQID: https://experienceleague.adobe.com/7vkYd55lKv1PCjRqX-OxK1A-VIjgH3O9Tx0AnbZvRWA
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 343
ht-degree: 1%

---

# Criar ou atualizar regras de características e regras de segmento{#create-or-update-trait-rules-and-segment-rules}

As planilhas criar e atualizar aceitam um cabeçalho de regra de característica que permite aplicar várias regras em uma única operação. Siga estas instruções para fazer solicitações de regra em massa.

>[!IMPORTANT]
>
>As Ferramentas de gerenciamento em massa não são uma oferta oficialmente compatível com o Adobe. A solução de problemas e o suporte por meio do Atendimento ao cliente serão tratados caso a caso.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>As [permissões do grupo RBAC](../../features/administration/administration-overview.md) atribuídas na interface do usuário [!DNL Audience Manager] são honradas no [!UICONTROL Bulk Management Tools].

## Trabalhar com regras de características {#trait-rules}

Em sua planilha, a coluna regra de característica retorna e aceita regras que consistem em expressões booleanas, operadores de comparação e expressões regulares. Você pode criar regras com o construtor de características ou segmentos em [!DNL Audience Manager] e copiá-las para sua planilha. Ou, se você estiver familiarizado com a sintaxe de regra, poderá escrever expressões diretamente nas planilhas.

## Exemplo do construtor de regras {#rule-builder-example}

Vamos ver um exemplo que demonstra como usar o [!UICONTROL Segment Builder] para criar uma regra que você pode incluir na planilha em massa. No entanto, isso não é um conjunto de instruções passo a passo para essas ferramentas. Em vez disso, começaremos com uma regra simples que já foi criada. Para obter instruções sobre como usar os construtores de regras, consulte [Construtor de segmentos](../../features/segments/segment-builder.md) e [Construtor de características](../../features/traits/about-trait-builder.md).

Com o construtor de regras visuais, criamos uma regra de segmento com 3 características e um operador booleano [!UICONTROL AND].

![](assets/visualrule.png)

Clique em **[!UICONTROL Code View]** para obter a versão de texto desta regra.

>[!TIP]
>
>Clique em **[!UICONTROL Validate Expression]** para verificar a lógica da regra. Isso ajudará a impedir que você carregue uma regra inválida.

![](assets/coderule.png)

Cole a regra na planilha [!UICONTROL Bulk Management Tools] e confirme suas alterações para atualizar regras de segmento em massa.

![](assets/segmentrule.png)

## Criar suas próprias regras {#create-rules}

Você pode escrever suas próprias regras fora do [!UICONTROL Rule Builder]. Antes de começar, leia a documentação que aborda coisas como operadores, expressão e variáveis necessárias. Recomendamos que você analise o seguinte:

* [Trabalhando Com Operadores De Comparação No Construtor De Características](../../features/traits/trait-comparison-operators.md)
* [Ordem de operação](../../features/traits/trait-operator-precedence.md)
* [Requisitos de prefixo para variáveis-chave](../../features/traits/trait-variable-prefixes.md)
* [Expressões de amostra com operadores booleanos e de comparação](../../features/traits/trait-expression-samples.md)
