---
description: A modelagem semelhante ajuda você a descobrir públicos novos e exclusivos por meio da análise automatizada de dados. Este artigo fornece respostas às perguntas mais frequentes.
seo-description: A modelagem semelhante ajuda você a descobrir públicos novos e exclusivos por meio da análise automatizada de dados. Este artigo fornece respostas às perguntas mais frequentes.
seo-title: Perguntas frequentes sobre a modelagem semelhante
solution: Audience Manager
title: Perguntas frequentes sobre a modelagem semelhante
feature: Modelos algorítmicos
source-git-commit: cf9368d4690b61066646054543cc60d390eea021
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# Perguntas frequentes sobre a modelagem semelhante

## Visão geral {#overview}

Este artigo fornece respostas às perguntas mais frequentes sobre [!UICONTROL Look-Alike Modeling].

## Dúvidas {#questions}

**Por que estou recebendo um  [!UICONTROL Accuracy & Reach] gráfico plano?**

Um gráfico simples [!UICONTROL Accuracy & Reach] significa que quase todos os usuários receberam a mesma pontuação pelo modelo. Isso pode acontecer ao incluir a característica do visitante do site nas fontes de dados nas quais você executou o modelo. Para evitar isso, remova a característica genérica da entrada do modelo durante a etapa de criação do modelo, usando o campo [!UICONTROL Exclusions].

 

**Por que algumas das minhas características influentes principais têm públicos muito pequenos?**

O algoritmo seleciona características que estão altamente correlacionadas com a característica da linha de base. Por exemplo, se uma determinada característica tiver 100% de sobreposição com a característica da linha de base, ela terá um peso muito alto, mesmo se o número de usuários nessa característica for pequeno.

 

**Por que meu modelo não foi executado/executado novamente?**

Os modelos que produziram resultados continuarão a ser executados somente se você tiver criado pelo menos uma característica algorítmica ativa e mapeado-a para um segmento ativo e um destino.

 

**Por que meu modelo não produziu resultados?**

Normalmente, isso é causado por não ter sobreposições significativas de características entre a população da linha de base e a população nas fontes de dados selecionadas.

 

**Existe alguma recomendação sobre a característica da linha de base ou o tamanho do segmento?**

Alguns milhares de usuários devem ser suficientes para executar o modelo, visto que há uma sobreposição significativa de características entre a população da linha de base e a população nas fontes de dados selecionadas. [!UICONTROL Look-Alike Modeling] produz resultados mais precisos, quanto maior a linha de base.

 

**Quais fontes de dados de terceiros devo escolher para o meu modelo?**

Use fontes de dados que tenham pelo menos alguma sobreposição com sua característica/segmento da linha de base, mas ao mesmo tempo traga usuários adicionais. Você também deve considerar o custo associado a cada feed de dados. Os modelos de custo e preço variam entre os provedores de dados em [!UICONTROL Audience Marketplace].

 

**Custa usar dados de terceiros para modelagem?**

Depende do modelo de preço do feed de dados selecionado. Alguns feeds permitem modelagem sem custo, enquanto outros cobram uma taxa. Consulte [Faturamento para compradores de feed de dados](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md) para obter detalhes.

 

**Quantos modelos/características tenho permissão para criar?**

Atualmente, você pode criar até 20 modelos algorítmicos e 50 características algorítmicas.

 

**Qual é a frequência de atualização do treinamento modelo e da população de características algorítmicas?**

O modelo retrai uma vez a cada 8 dias, juntamente com a atualização da população de características algorítmicas.