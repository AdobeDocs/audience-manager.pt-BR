---
description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences FAQ
solution: Audience Manager
title: Perguntas frequentes sobre Públicos preditivos
feature: Algorithmic Models
exl-id: 21073970-8457-470b-89fc-724a118a18d2
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 59%

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

 

**Quando posso ver os primeiros resultados produzidos pelo meu modelo?**

Os resultados do modelo de [!UICONTROL Predictive Audiences] estão disponíveis em 24 horas após a criação bem-sucedida do modelo.

Caso o modelo não produza resultados em 24 horas, entre em contato com o representante da Adobe.

 

**Por que meu modelo não está produzindo resultados ou mostrando o status de Aviso?**

Os modelos de [!UICONTROL Predictive Audiences] podem deixar de produzir resultados devido a várias razões:

1. Nenhum dos perfis de usuário selecionados [!UICONTROL traits] / [!UICONTROL segments] tem perfis de usuário suficientes. Recomendamos escolher [!UICONTROL traits] ou [!UICONTROL segments] para que cada persona tenha pelo menos algumas centenas de perfis de usuário.
1. Nenhum dos perfis selecionados [!UICONTROL traits] / [!UICONTROL segments] possui dados suficientes em seus perfis de usuário (características insuficientes para analisar).
1. A característica/segmento do público-alvo não tem nenhum usuário ativo ou integrado.
1. Os usuários do público-alvo que estavam ativos ou integrados nos últimos 30 dias não têm dados suficientes nos perfis do usuário (não há características suficientes para analisar).
1. O segmento de público-alvo usa um [!UICONTROL Profile Merge Rule] diferente daquele que você escolheu para o modelo.
1. A fonte de dados das suas características de público-alvo de destino pode não ser incluída no [!UICONTROL Profile Merge Rule] que você escolheu para o modelo.

Para obter os melhores resultados, siga as diretrizes sugeridas em [Critérios de seleção para personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) e [Critérios de seleção para público-alvo](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**Por que meu modelo está mostrando o status [!UICONTROL Error]?**

Pode ser uma falha ao executar o modelo. Nesses casos, entre em contato com o representante do [!DNL Adobe].

 

**Como posso alterar o [!UICONTROL Profile Merge Rule] de um [!UICONTROL Predictive Audiences] [!UICONTROL segment]?**

Crie um novo modelo selecionando as mesmas personas e público alvo do modelo anterior. Durante a criação do modelo, atribua um [!UICONTROL Profile Merge Rule] diferente.

>[!WARNING]
> Como alternativa, você pode usar o [Construtor de segmentos](../features/segments/segment-builder.md) para criar manualmente um [!UICONTROL segment] com um [!UICONTROL trait] preditivo existente e atribuí-lo a um [!UICONTROL Profile Merge Rule] de sua escolha.
> 
> No entanto, não recomendamos essa prática, pois o [!UICONTROL traits] preditivo herda automaticamente o [!UICONTROL Profile Merge Rule] do modelo ao qual pertence e é construído a partir de [!UICONTROL traits] influentes que estão em conformidade com o [!UICONTROL Profile Merge Rule] do modelo.

 

**Que [!UICONTROL Profile Merge Rule] devo escolher?**

Ao escolher o [!UICONTROL Profile Merge Rule] para seu modelo, analise seu caso de uso detalhadamente.

Digamos que o público-alvo [!UICONTROL segment] use um [!UICONTROL Profile Merge Rule] com base em perfis autenticados + [!DNL Device Graph] perfis e você selecione o mesmo [!UICONTROL Profile Merge Rule] para o [!UICONTROL segments] preditivo. Nesse caso, o nível de dispositivo e o nível entre dispositivos [!UICONTROL traits] serão usados no treinamento do modelo e no posicionamento do usuário em um [!UICONTROL segment] preditivo.

No entanto, se você selecionar um [!UICONTROL Profile Merge Rule] com base apenas em perfis de dispositivo, nenhum de seus [!UICONTROL traits] entre dispositivos se tornará influente e não contribuirá para o posicionamento de usuários em um [!UICONTROL segment] preditivo. Isso pode afetar negativamente a precisão e o alcance do modelo.

Analise cuidadosamente seu caso de uso e decida com quais [!UICONTROL trait] tipos você deseja que o modelo aprenda e que tipo de dados você deseja que o modelo use para classificação.

**Um usuário do público-alvo que não faz parte de nenhuma característica/segmento de persona pode não ser classificado?**

Sim, caso o usuário não tenha nenhuma característica em seu perfil. Nesse caso, o usuário obterá uma pontuação de correspondência de 0 para todas as características/segmentos de persona e, portanto, não será classificado em nenhum dos segmentos preditivos.

 

**Um usuário que foi classificado em um dos segmentos preditivos pode ser reclassificado em um segmento diferente do [!UICONTROL Predictive Audiences]?**

Sim. Como o algoritmo é treinado diariamente, ele aplica as alterações para cada persona em termos de pontuação de características. Se um usuário que faz parte de um segmento do [!UICONTROL Predictive Audiences] estiver ativo, as alterações em sua pontuação de característica podem alterar a classificação com base na atividade dos últimos 30 dias.

 

**Posso ver as características pelas quais a classificação de público-alvo é feita?**

Sim, você pode ver todas as características influentes de todas as linhas de base na página de relatórios do modelo. Consulte [Características influentes](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**É possível alterar o TTL (tempo de vida útil) para características preditivas?**

O TTL da característica preditiva está definido como 0 (duração) e não pode ser alterado. O [!UICONTROL Predictive Audiences] só pode dessegmentar usuários de segmentos preditivos quando eles se qualificam para o segmento base ou são reclassificados em um segmento preditivo diferente.

Se necessário, você pode contornar essa funcionalidade criando um novo segmento que contenha uma característica preditiva e uma característica de atividade com um TTL especificado.

 


**O que acontece com o modelo se eu editar uma de suas características ou segmentos de linha de base?**

O modelo avalia as características ou os segmentos uma vez por dia. Você deverá ver a classificação atualizada no dia seguinte após a atualização.

 

**É possível selecionar as fontes de dados a partir das quais o modelo aprenderá?**

Não, não é possível selecionar a fontes de dados. O algoritmo [!UICONTROL Predictive Audiences] aprende com todas as suas características originais.
