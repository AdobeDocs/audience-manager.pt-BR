---
description: Descreve a relação entre precisão e alcance em características algorítmicas.
seo-description: Descreve a relação entre precisão e alcance em características algorítmicas.
seo-title: Precisão e alcance
solution: Audience Manager
title: Precisão e alcance
uuid: d 121 e 099-6642-4003-ad 4 f -507 d 21 e 478 d 8
translation-type: tm+mt
source-git-commit: 44bb4d511215a7bbc8889cc9518b3b5ffcb79a2a

---


# Accuracy and Reach {#accuracy-and-reach}

Descreve a relação entre precisão e alcance em características algorítmicas.

<!-- c_accuracy_reach.xml -->

## Precisão x Alcance: Sobre

É importante entender a relação entre precisão e alcance ao trabalhar com características algorítmicas. A precisão é representada por um valor pontuado que reflete como os usuários semelhantes estão à sua linha de base. A precisão varia de 0 (menos preciso) para 1 (mais precisa). Alcance é apenas um valor que representa o número de usuários únicos que você gostaria de incluir em uma característica. Alcance e precisão são inversamente relacionados. O alcance preciso do alcance menos usuários e características com maior alcance é menos preciso. A imagem a seguir ilustra este conceito.

![](assets/Reach_v_Accuracy.png)

## Precisão e alcance afetam o tamanho do público-alvo

Suas metas empresariais devem ajudá-lo a tomar as decisões certas sobre a precisão e o alcance ao trabalhar com algoritmos algorítmicos. Se a precisão for a sua meta, observe que a população de uma característica pode aumentar ou diminuir em execuções de modelo. As alterações de população são os resultados do algoritmo que tomar decisões durante cada período de avaliação. Às vezes, o algoritmo encontra usuários mais qualificados durante um ciclo de processamento e, durante outras, pode encontrar menos. Os resultados são determinados pelos dados da linha de base usados para criar o modelo e os novos visitantes e as qualificações de característica que vêm desde o modelo anterior. Por outro lado, ao trabalhar com alcance, a contagem de população do usuário permanece constante. Por exemplo, se você quiser atingir 10,000 usuários, o algoritmo garantirá que sempre atinja o número para cada modelo executado.

## Casos de uso geral para precisão versus Alcance

O foco na precisão ou no alcance depende do que você deseja alcançar com um segmento específico. A tabela a seguir pode ajudar a avaliar a precisão em comparação ao alcance ao criar uma característica.

| Favors da Decisão de Característica | Ajuda a encontrar |
|---|---|
| **Precisão** | Usuários semelhantes aos clientes de linha de base no modelo. Útil para campanhas direcionadas quando você deseja alcançar um público específico. |
| **Alcance** | Um número específico de usuários para cada execução de dados. Útil para campanhas de marca quando você estiver interessado em alcançar um público de um tamanho específico. |