---
description: Audiências preditivas ajudam a classificar audiências desconhecidas em personas distintas em tempo real, usando a ciência de dados.
seo-description: Audiências preditivas ajudam a classificar audiências desconhecidas em personas distintas em tempo real, usando a ciência de dados.
seo-title: Perguntas frequentes sobre Audiências preditivas
solution: Audience Manager
title: Audiências Audience Manager preditivas
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 0%

---


# Perguntas frequentes sobre Audiências preditivas

Perguntas frequentes sobre [!UICONTROL Predictive Audiences].

 

**Quando devo usar[!UICONTROL Predictive Audiences]em vez de[!UICONTROL Look-alike modeling]?**

[!UICONTROL Predictive Audiences] e [!UICONTROL Look-alike modeling] sirvam casos de uso diferentes. As principais diferenças entre os dois algoritmos são as seguintes:

1. [!UICONTROL Look-alike modeling] pega uma pequena audiência como entrada e a expande. [!UICONTROL Predictive Audiences] toma uma grande audiência como entrada, e a divide em audiências distintas menores, definidas pelas suas personas.
1. O número de segmentos base é diferente para cada algoritmo. [!UICONTROL Predictive Audiences] requer pelo menos duas linhas de base, enquanto [!UICONTROL Look-alike modeling] usa uma linha de base no máximo.
1. [!UICONTROL Predictive Audiences] realiza a avaliação de segmentos em tempo real, mas [!UICONTROL Look-alike modeling] não.

Com base no seu caso de uso, você deve decidir qual modelo será mais relevante para você.

Você pode pensar em construir um [!UICONTROL Predictive Audiences] modelo com um número de linhas de base como sendo o equivalente a construir o mesmo número de modelos de sósia, apenas sem a avaliação em tempo real, e com uma alta probabilidade de ter visitantes pertencentes a múltiplas personas diferentes, em vez de uma persona distinta.

 

**Quantas pessoas/modelos tenho permissão para criar?**

Você pode criar até 10 [!UICONTROL Predictive Audiences] modelos. Para cada modelo, é possível definir até 50 características ou segmentos da linha de base.

 

**Como posso criar novos segmentos a partir de um[!UICONTROL Predictive Audiences]segmento?**

Vá até **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** e clique na **[!UICONTROL Predictive Audiences]** pasta. Encontre o segmento desejado, duplicado-o e edite-o de acordo com suas necessidades.

 

**Por que alguns dos meus visitantes integrados não são classificados?**

Atualmente, a classificação de audiência funciona apenas para qualificações em tempo real, exceto para usuários autenticados que foram definidos como parte do [!UICONTROL Profile Merge Rules].

O suporte total para dados integrados será adicionado em uma atualização futura.

 

**Quando posso ver os primeiros resultados produzidos pelo meu modelo?**

[!UICONTROL Predictive Audiences] os resultados do modelo estão disponíveis dentro de 24 horas após a criação do modelo, se o modelo for executado com êxito.

Caso o modelo não produza resultados em 24 horas, entre em contato com seu representante da Adobe.

 

**Por que meu modelo não está produzindo resultados ou mostrando o status de Aviso?**

[!UICONTROL Predictive Audiences] os modelos podem deixar de produzir resultados devido a várias razões:

1. Nenhum dos traços / segmentos personalizados selecionados têm perfis de usuário suficientes. Recomendamos escolher suas características ou segmentos para que cada pessoa tenha pelo menos algumas centenas de perfis de usuário.
1. Nenhum dos traços / segmentos personalizados selecionados têm dados suficientes em seus perfis do usuário (características insuficientes para analisar).
1. A característica/segmento da audiência do público alvo não tinha nenhum usuário ativo ou integrado nos últimos 30 dias.
1. Os usuários da audiência do público alvo que estavam ativos ou integrados nos últimos 30 dias não têm dados suficientes nos perfis do usuário (não há características suficientes para analisar).

Para produzir resultados relevantes, o [!UICONTROL Predictive Audiences] algoritmo avalia as realizações de características e segmentos com base na atividade do usuário em tempo real visualizada pelo DCS. Se você selecionar novos traços básicos e segmentos que ainda não possuem usuários suficientes, o algoritmo pode levar alguns dias para classificar sua audiência.

Para obter os melhores resultados, siga as diretrizes sugeridas em Critérios de [seleção para personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) e Critérios [de seleção para Audiência](../features/algorithmic-models/predictive-audiences.md#selection-audience)de Público alvo.

 

**Por que meu modelo está mostrando o status de erro?**

Falha ao executar o modelo. Nesses casos, entre em contato com seu representante da Adobe.

 

**Como posso alterar a Regra de mesclagem de Perfis para um segmento de Audiências previsíveis?**

Duplicado o [!UICONTROL Predictive Audiences] segmento e altere o [!UICONTROL Profile Merge Rule] para o segmento duplicado.

 

**Um usuário da audiência do público alvo que não faz parte de nenhum traço / segmento pessoal pode não ser classificado?**

Sim, caso o usuário não tenha nenhuma característica em seu perfil. Nesse caso, o usuário obterá uma pontuação de correspondência de 0 para todas as características/segmentos pessoais e, portanto, não será classificado em nenhum dos segmentos preditivos.

 

**Um usuário que foi classificado em um dos segmentos preditivos pode ser reclassificado em um[!UICONTROL Predictive Audiences]segmento diferente?**

Sim. Como o algoritmo é treinado diariamente, ele aplica as alterações para cada pessoa em termos de pontuação de características. Se um usuário que faz parte de um [!UICONTROL Predictive Audiences] segmento estiver ativo, as alterações em sua pontuação de característica podem alterar a classificação com base na atividade dos últimos 30 dias.

 

**Posso ver as características pelas quais a classificação de audiências é feita?**

Sim, você pode ver todas as características influentes de todas as linhas de base na página de relatórios do modelo. Consulte Características [influentes](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**O que acontece com o modelo se eu editar um de seus traços ou segmentos de linha de base?**

O modelo avalia as características ou os segmentos uma vez por dia. Você deverá ver a classificação atualizada no dia seguinte após a atualização.

 

**É possível selecionar as fontes de dados a partir das quais o modelo aprenderá?**

Não, a seleção de fontes de dados não é suportada. O [!UICONTROL Predictive Audiences] algoritmo aprende com todas as suas características originais.