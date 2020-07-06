---
description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-title: Perguntas frequentes sobre Públicos preditivos
solution: Audience Manager
title: Públicos preditivos do Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 100%

---


# Perguntas frequentes sobre Públicos preditivos

Perguntas frequentes sobre [!UICONTROL Predictive Audiences].

 

**Quando devo usar [!UICONTROL Predictive Audiences] em vez de [!UICONTROL Look-alike modeling]?**

[!UICONTROL Predictive Audiences] e [!UICONTROL Look-alike modeling] atendem a casos de uso diferentes. Estas são as principais diferenças entre os dois algoritmos:

1. A [!UICONTROL Look-alike modeling] pega um pequeno público-alvo como entrada e o expande. O [!UICONTROL Predictive Audiences] pega um grande público-alvo como entrada e o divide em públicos-alvo distintos menores, definidos pelas suas personas.
1. O número de segmentos base é diferente para cada algoritmo. O [!UICONTROL Predictive Audiences] exige pelo menos duas linhas de base, enquanto a [!UICONTROL Look-alike modeling] usa uma linha de base no máximo.
1. O [!UICONTROL Predictive Audiences] avalia segmentos em tempo real, mas a [!UICONTROL Look-alike modeling] não.

Com base no seu caso de uso, você deve decidir qual modelo será mais relevante para você.

Você pode pensar em construir um modelo de [!UICONTROL Predictive Audiences] com um número de linhas de base como sendo o equivalente a construir o mesmo número de modelos de semelhança, apenas sem a avaliação em tempo real, e com uma alta probabilidade de ter visitantes pertencentes a várias personas diferentes, em vez de uma persona distinta.

 

**Quantas personas/modelos tenho permissão para criar?**

Você pode criar até 10 modelos de [!UICONTROL Predictive Audiences]. Para cada modelo, é possível definir até 50 características ou segmentos da linha de base.

 

**Como posso criar novos segmentos a partir de um segmento de [!UICONTROL Predictive Audiences]?**

Vá até **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** e clique na pasta **[!UICONTROL Predictive Audiences]**. Encontre o segmento desejado, duplique-o e faça edições de acordo com suas necessidades.

 

**Por que alguns dos meus visitantes integrados não são classificados?**

Atualmente, a classificação de público-alvo funciona apenas para qualificações em tempo real, exceto para usuários autenticados que foram definidos como parte das [!UICONTROL Profile Merge Rules].

O suporte total para dados integrados será adicionado em uma atualização futura.

 

**Quando posso ver os primeiros resultados produzidos pelo meu modelo?**

Os resultados do modelo de [!UICONTROL Predictive Audiences] estão disponíveis em 24 horas após a criação bem-sucedida do modelo.

Caso o modelo não produza resultados em 24 horas, entre em contato com o representante da Adobe.

 

**Por que meu modelo não está produzindo resultados ou mostrando o status de Aviso?**

Os modelos de [!UICONTROL Predictive Audiences] podem deixar de produzir resultados devido a várias razões:

1. Nenhuma das características/segmentos de persona selecionados tem perfis de usuário suficientes. Recomendamos escolher suas características ou segmentos para que cada persona tenha pelo menos algumas centenas de perfis de usuário.
1. Nenhuma das características/segmentos de persona selecionados tem dados suficientes em seus perfis do usuário (características insuficientes para analisar).
1. A característica/segmento do público-alvo não tinha nenhum usuário ativo ou integrado nos últimos 30 dias.
1. Os usuários do público-alvo que estavam ativos ou integrados nos últimos 30 dias não têm dados suficientes nos perfis do usuário (não há características suficientes para analisar).

Para produzir resultados relevantes, o algoritmo [!UICONTROL Predictive Audiences] avalia as realizações de características e segmentos com base na atividade do usuário em tempo real visualizada pelo DCS. Se você selecionar novas características e segmentos básicos que ainda não têm usuários suficientes, o algoritmo pode levar alguns dias para classificar o público-alvo.

Para obter os melhores resultados, siga as diretrizes sugeridas em [Critérios de seleção para personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) e [Critérios de seleção para público-alvo](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**Por que meu modelo está mostrando o status de erro?**

Pode ser uma falha ao executar o modelo. Nesses casos, entre em contato com o representante da Adobe.

 

**Como posso alterar a Regra de mesclagem de perfis para um segmento de Públicos preditivos?**

Duplique o segmento do [!UICONTROL Predictive Audiences] altere a [!UICONTROL Profile Merge Rule] para o segmento duplicado.

 

**Um usuário do público-alvo que não faz parte de nenhuma característica/segmento de persona pode não ser classificado?**

Sim, caso o usuário não tenha nenhuma característica em seu perfil. Nesse caso, o usuário obterá uma pontuação de correspondência de 0 para todas as características/segmentos de persona e, portanto, não será classificado em nenhum dos segmentos preditivos.

 

**Um usuário que foi classificado em um dos segmentos preditivos pode ser reclassificado em um segmento diferente do [!UICONTROL Predictive Audiences]?**

Sim. Como o algoritmo é treinado diariamente, ele aplica as alterações para cada persona em termos de pontuação de características. Se um usuário que faz parte de um segmento do [!UICONTROL Predictive Audiences] estiver ativo, as alterações em sua pontuação de característica podem alterar a classificação com base na atividade dos últimos 30 dias.

 

**Posso ver as características pelas quais a classificação de público-alvo é feita?**

Sim, você pode ver todas as características influentes de todas as linhas de base na página de relatórios do modelo. Consulte [Características influentes](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**O que acontece com o modelo se eu editar uma de suas características ou segmentos de linha de base?**

O modelo avalia as características ou os segmentos uma vez por dia. Você deverá ver a classificação atualizada no dia seguinte após a atualização.

 

**É possível selecionar as fontes de dados a partir das quais o modelo aprenderá?**

Não, não é possível selecionar a fontes de dados. O algoritmo [!UICONTROL Predictive Audiences] aprende com todas as suas características originais.