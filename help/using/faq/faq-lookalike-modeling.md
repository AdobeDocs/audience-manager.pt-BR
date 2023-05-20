---
description: A modelagem semelhante ajuda você a descobrir públicos novos e exclusivos por meio da análise de dados automatizada. Este artigo fornece respostas para as perguntas mais frequentes.
seo-description: Look-Alike Modeling helps you discover new, unique audiences through automated data analysis. This article provides answers to the most frequently asked questions.
seo-title: Look-Alike Modeling FAQ
solution: Audience Manager
title: Perguntas frequentes sobre a modelagem semelhante
feature: Algorithmic Models
exl-id: c6e92db0-129f-489e-8cf0-600e0e09698b
source-git-commit: 37823ae54e106e32aa195a6b69e0f1ebfc322f09
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---

# Perguntas frequentes sobre a modelagem semelhante

## Visão geral {#overview}

Este artigo fornece respostas às perguntas mais frequentes sobre [!UICONTROL Look-Alike Modeling].

## Perguntas {#questions}

**Por que estou pegando um apartamento? [!UICONTROL Accuracy & Reach] gráfico?**

A bemol [!UICONTROL Accuracy & Reach] gráfico significa que quase todos os usuários receberam a mesma pontuação pelo modelo. Isso pode acontecer quando você inclui a característica de visitante do site nas fontes de dados em que você executou o modelo. Para evitar isso, remova a característica genérica da entrada do modelo durante a etapa de criação do modelo usando o [!UICONTROL Exclusions] campo.

 

**Por que algumas de minhas características influentes principais têm públicos muito pequenos?**

O algoritmo seleciona características altamente correlacionadas com a característica da linha de base. Por exemplo, se uma determinada característica tiver uma sobreposição de 100% com a característica da linha de base, ela terá um peso muito alto, mesmo que o número de usuários nessa característica seja pequeno.

 

**Por que meu modelo não foi executado/executado novamente?**

Os modelos que produziram resultados continuarão a ser executados somente se você tiver criado pelo menos uma característica algorítmica ativa e a mapeou para um segmento ativo e um destino.

 

**Por que meu modelo não produziu resultados?**

Normalmente, isso é causado por não haver sobreposições significativas de características entre a população da linha de base e a população nas fontes de dados selecionadas.

 

**Há alguma recomendação sobre a característica da linha de base ou o tamanho do segmento?**

Alguns milhares de usuários devem ser suficientes para executar o modelo, visto que há uma sobreposição significativa de características entre a população da linha de base e a população nas fontes de dados selecionadas. [!UICONTROL Look-Alike Modeling] produz resultados mais precisos, quanto maior a linha de base.

 

**Quais fontes de dados de terceiros devo escolher para meu modelo?**

Use fontes de dados que tenham pelo menos alguma sobreposição com sua característica/segmento de linha de base, mas que, ao mesmo tempo, tragam usuários adicionais. Você também deve considerar o custo associado a cada feed de dados. Os modelos de custo e preço variam entre os provedores de dados na [!UICONTROL Audience Marketplace].

 

**Custa usar dados de terceiros para modelagem?**

Depende do modelo de preços do feed de dados selecionado. Alguns feeds permitem modelagem sem custo, enquanto outros cobram uma taxa. Consulte [Faturamento para compradores de feed de dados](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md) para obter detalhes.

 

**Quantos modelos/características tenho permissão para criar?**

Atualmente, você pode criar até 20 modelos algorítmicos e 50 características algorítmicas.

 

**Qual é a frequência de atualização do treinamento de modelo e o público de características algorítmicas?**

O modelo é reciclado uma vez a cada 8 dias, juntamente com a atualização da população de características algorítmicas.
