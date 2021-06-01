---
description: Descreve a relação entre precisão e alcance em características algorítmicas.
seo-description: Descreve a relação entre precisão e alcance em características algorítmicas.
seo-title: Precisão e alcance
solution: Audience Manager
title: Precisão e alcance
uuid: d121e099-6642-4003-ad4f-507d21e478d8
feature: 'Características '
exl-id: 647b283a-fcfa-4e3f-8667-50c6aacbc78a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 3%

---

# Precisão e alcance {#accuracy-and-reach}

Descreve a relação entre precisão e alcance em características algorítmicas.

<!-- c_accuracy_reach.xml -->

## Precisão vs Alcance: Sobre

É importante entender a relação entre precisão e alcance ao trabalhar com características algorítmicas. A precisão é representada por um valor pontuado que reflete o nível de usuários semelhantes à sua linha de base. A escala de precisão varia de 0 (menos precisa) a 1 (mais precisa). Alcance é simplesmente um valor que representa o número de usuários únicos que você gostaria de incluir em uma característica. O alcance e a precisão estão inversamente relacionados. As características exatas atingem menos usuários e as características com maior alcance são menos precisas. A imagem a seguir ilustra esse conceito.

![](assets/Reach_v_Accuracy.png)

## Precisão e alcance afetam o tamanho do público-alvo

As metas de sua empresa devem ajudá-lo a tomar as decisões corretas sobre precisão e alcance ao trabalhar com características algorítmicas. Se a precisão for sua meta, observe que a população de uma característica pode aumentar ou diminuir em execuções de modelo. As alterações de população são os resultados do algoritmo que toma decisões durante cada período de avaliação. Às vezes, o algoritmo encontra usuários mais qualificados durante um ciclo de processamento e, durante outros, pode encontrar menos. Os resultados são determinados pelos dados de linha de base usados para criar o modelo e os novos visitantes e qualificações de característica que vieram desde a execução do modelo anterior. Por outro lado, ao trabalhar com o alcance, a contagem de população do usuário permanece constante. Por exemplo, se você quiser alcançar 10.000 usuários, o algoritmo sempre acessará esse número para cada execução de modelo.

## Casos de uso gerais para precisão e alcance

O foco na precisão ou no alcance depende do que você deseja alcançar com um segmento específico. A tabela a seguir pode ajudar a avaliar a precisão e o alcance ao criar uma característica.

| Favoritos da decisão da característica | Ajuda a localizar |
|---|---|
| **Precisão** | Usuários semelhantes aos clientes da linha de base em seu modelo. Útil para campanhas direcionadas quando você deseja alcançar um público-alvo específico. |
| **Alcance** | Um número específico de usuários para cada execução de dados. Útil para campanhas de marca quando você está interessado em alcançar um público-alvo de um tamanho específico. |
