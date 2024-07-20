---
description: Descreve a relação entre precisão e alcance em características algorítmicas.
seo-description: Describes the relationship between accuracy and reach in algorithmic traits.
seo-title: Accuracy and Reach
solution: Audience Manager
title: Precisão e alcance
uuid: d121e099-6642-4003-ad4f-507d21e478d8
feature: Traits
exl-id: 647b283a-fcfa-4e3f-8667-50c6aacbc78a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 0%

---

# Precisão e alcance {#accuracy-and-reach}

Descreve a relação entre precisão e alcance em características algorítmicas.

<!-- c_accuracy_reach.xml -->

## Precisão vs Alcance: Sobre

É importante entender a relação entre precisão e alcance ao trabalhar com características algorítmicas. A precisão é representada por um valor pontuado que reflete a semelhança dos usuários com a sua linha de base. A escala de precisão varia de 0 (menos precisa) a 1 (mais precisa). Alcance é simplesmente um valor que representa o número de usuários únicos que você gostaria de incluir em uma característica. O alcance e a precisão estão inversamente relacionados. Características precisas alcançam menos usuários e características com maior alcance são menos precisas. A imagem a seguir ilustra esse conceito.

![](assets/Reach_v_Accuracy.png)

## Precisão e alcance afetam o tamanho do público

Suas metas comerciais devem ajudá-lo a tomar as decisões certas sobre precisão e alcance ao trabalhar com características algorítmicas. Se a precisão for o seu objetivo, observe que a população de uma característica pode aumentar ou diminuir nas execuções de modelo. As alterações na população são o resultado do algoritmo que toma as decisões durante cada período de avaliação. Às vezes, o algoritmo encontra mais usuários qualificados durante um ciclo de processamento e, durante outros, pode encontrar menos. Os resultados são determinados pelos dados da linha de base usados para criar o modelo e os novos visitantes e qualificações de característica que vieram desde a execução do modelo anterior. Por outro lado, ao trabalhar com alcance, a contagem de população do usuário permanece constante. Por exemplo, se você quiser atingir 10.000 usuários, o algoritmo sempre atingirá esse número para cada execução de modelo.

## Casos de uso gerais para precisão vs. alcance

O foco na precisão ou no alcance depende do que você deseja alcançar com um segmento específico. A tabela a seguir pode ajudar você a avaliar a precisão em relação ao alcance ao criar uma característica.

| Favorecimentos de decisão de características | Ajuda a Localizar |
|---|---|
| **Precisão** | Usuários semelhantes aos clientes da linha de base em seu modelo. Útil para campanhas direcionadas quando você deseja alcançar um público específico. |
| **Alcance** | Um número específico de usuários para cada execução de dados. Útil para campanhas de marca quando você está interessado em alcançar um público de um tamanho específico. |
