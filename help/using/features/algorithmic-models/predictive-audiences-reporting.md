---
description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-title: Relatórios dos públicos preditivos
solution: Audience Manager
title: Relatórios dos públicos preditivos
feature: Algorithmic Models
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
translation-type: tm+mt
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 6%

---

# Relatórios dos públicos preditivos

Depois de salvar um modelo [!UICONTROL Predictive Audiences], o Audience Manager inicia o treinamento. Dentro de algumas horas, o modelo calculado começará a analisar públicos-alvo nos [Servidores de coleta de dados](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs). Os relatórios estarão disponíveis no dia seguinte.

Para ver os resultados da sua classificação [!UICONTROL Predictive Audiences], vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** e clique no modelo na lista.

Use as opções de filtragem no lado esquerdo para procurar pelo nome do modelo ou filtrar os resultados com base no tipo de modelo.

![filtro de públicos-alvo preditivos](assets/predictive-audiences-filter-models.png)

A tabela de modelos mostra as seguintes informações:

* **[!UICONTROL ID]**: a ID do modelo identifica exclusivamente cada modelo em sua conta do Audience Manager;
* **[!UICONTROL Name]**: o nome fornecido na etapa de criação do modelo;
* **[!UICONTROL Description]**: a descrição fornecida na etapa de criação do modelo;
* **[!UICONTROL Model Type]**: O tipo de cada modelo ([!UICONTROL Look-Alike Modeling] ou  [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**: o status de cada modelo:
   * **[!UICONTROL Pending]**: o modelo está a inicializar e começará a produzir resultados em breve;
   * **[!UICONTROL Active]**: O modelo está a ser executado com êxito e a produzir resultados;
   * **[!UICONTROL Warning]**: o modelo não conseguiu produzir resultados, devido a dados insuficientes (ou seja, baixa população de linhas de base, os perfis de usuário não são ricos);
   * **[!UICONTROL Error]**: falha ao executar o modelo. Você deve entrar em contato com o representante do Adobe.

## Relatório de Visão Geral do Modelo{#model-report}

Depois de escolher um modelo, a página de relatórios será carregada. Na parte superior da página, você pode ver os 5 maiores segmentos preditivos, com base em 1 dia de realização em tempo real, pelos quais o modelo classificou seu público alvo. A categoria **[!UICONTROL Other]** inclui o restante das personas, que não foram incluídas nos 5 maiores segmentos preditivos.

O Audience Manager exibe um gráfico de rosca codificado por cores e um gráfico de linha do tempo para seu [!UICONTROL Predictive Audiences].

Clicar nas guias de personas na parte superior da página as adiciona ou remove do gráfico e do gráfico.

O gráfico de rosca mostra um detalhamento com base em persona do público-alvo, enquanto o gráfico mostra a tendência da população em tempo real de 1 dia dos segmentos preditivos nos últimos 6 dias.

Se o status do modelo for [!UICONTROL Pending], [!UICONTROL Warning] ou [!UICONTROL Error], o status do modelo será exibido em vez dos gráficos.

![relatório de persona inteligente](assets/predictive-audiences-report.png)

A tabela de relatório mostra as seguintes informações para cada segmento [!UICONTROL Predictive Audiences].

1. **[!UICONTROL SEGMENT ID]**: a ID do segmento criado automaticamente associada a cada persona;
1. **[!UICONTROL NAME]**: o nome da pessoa;
1. **[!UICONTROL STATUS]**: o status do  [!UICONTROL Predictive Audiences] segmento:
   * **[!UICONTROL Succeeded]**: os usuários estão sendo classificados nesse segmento;
   * **[!UICONTROL Pending]**: o segmento ainda está sendo inicializado;
   * **[!UICONTROL Insufficient Training Data]**: Os usuários do não estão sendo classificados nesse segmento devido a dados insuficientes. A população total da linha de base é muito baixa e não fornece dados suficientes para aprender.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: O número de realizações do segmento para cada persona, nas últimas 24 horas.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: A porcentagem das realizações do segmento para cada persona, nas últimas 24 horas, da população total do modelo.

## Características influentes{#influential-traits}

[!UICONTROL Influential Traits] são características que o  [!UICONTROL Predictive Audiences] algoritmo descobriu serem os maiores indicadores para determinar a classificação de persona de um visitante.

Seu sinal indica se a presença da característica aumenta (+) ou diminui (-) a probabilidade do usuário pertencer à persona selecionada.

Para exibir as características influentes de todas as suas personas, clique em [!UICONTROL View All Influential Traits].

A janela [!UICONTROL Influential Traits] mostra as seguintes informações, para cada persona do modelo selecionado:

![traços influentes](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: a ID de característica de cada característica influente para a persona selecionada;
1. **[!UICONTROL NAME]**: o nome de cada característica influente da persona selecionada;
1. **[!UICONTROL DESCRIPTION]**: a descrição de cada característica influente para a persona selecionada;
1. **[!UICONTROL WEIGHT]**: o peso de cada característica influente para a persona selecionada. [!UICONTROL Influential Traits] são classificadas por padrão por peso, em ordem decrescente.  O valor dos pesos indica seu poder preditivo. O sinal indica se a presença da característica aumenta (+) ou diminui (-) a probabilidade de pertencer a uma persona.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: o número de realizações de características exclusivas para cada característica influente do persona selecionado, nos últimos 30 dias.
