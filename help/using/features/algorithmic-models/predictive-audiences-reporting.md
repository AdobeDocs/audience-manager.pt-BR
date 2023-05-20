---
description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Reporting
solution: Audience Manager
title: Relatórios dos públicos preditivos
feature: Algorithmic Models
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 3%

---

# Relatórios dos públicos preditivos

Depois de salvar um [!UICONTROL Predictive Audiences] modelo, o Audience Manager começa a treiná-lo. Em algumas horas, o modelo calculado começará a analisar os públicos-alvo no [Servidores de coleta de dados](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs). Os relatórios estarão disponíveis no dia seguinte.

Para ver os resultados do seu [!UICONTROL Predictive Audiences] classificação, vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** e clique no modelo na lista.

Use as opções de filtro no lado esquerdo para pesquisar o nome do modelo ou filtrar os resultados com base no tipo de modelo.

![predictive-audiences-filter](assets/predictive-audiences-filter-models.png)

A tabela de modelos mostra as seguintes informações:

* **[!UICONTROL ID]**: a ID do modelo identifica exclusivamente cada modelo na conta Audience Manager;
* **[!UICONTROL Name]**: o nome fornecido na etapa de criação do modelo;
* **[!UICONTROL Description]**: a descrição fornecida na etapa de criação do modelo;
* **[!UICONTROL Model Type]**: o tipo de cada modelo ([!UICONTROL Look-Alike Modeling] ou [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**: o status de cada modelo:
   * **[!UICONTROL Pending]**: o modelo está sendo inicializado e começará a produzir resultados em breve;
   * **[!UICONTROL Active]**: o modelo está sendo executado com êxito e produzindo resultados;
   * **[!UICONTROL Warning]**: o modelo não conseguiu produzir resultados, devido a dados insuficientes (ou seja, baixa população de linhas de base, os perfis do usuário não são ricos);
   * **[!UICONTROL Error]**: falha na execução do modelo. Você deve entrar em contato com o representante da Adobe.

## Relatório de visão geral do modelo{#model-report}

Depois de escolher um modelo, a página de relatórios será carregada. Na parte superior da página, você pode ver os 5 maiores segmentos preditivos, com base na percepção em tempo real de 1 dia, que o modelo classificou seu público-alvo. A variável **[!UICONTROL Other]** A categoria inclui o restante dos perfis, que não foram incluídos nos 5 maiores segmentos preditivos.

O Audience Manager exibe um gráfico de rosca codificado por cores e um gráfico de linha do tempo para o seu [!UICONTROL Predictive Audiences].

Clicar nas guias de personas na parte superior da página adiciona ou remove essas personas do gráfico e do.

O gráfico de rosca mostra um detalhamento do seu público-alvo com base em persona, enquanto o gráfico mostra a tendência da população em tempo real de 1 dia dos seus segmentos preditivos nos últimos 6 dias.

Se o status do modelo for [!UICONTROL Pending], [!UICONTROL Warning]ou [!UICONTROL Error], o status do modelo é exibido em vez dos gráficos.

![smart-persona-report](assets/predictive-audiences-report.png)

A tabela de relatórios mostra as seguintes informações para cada [!UICONTROL Predictive Audiences] segmento.

1. **[!UICONTROL SEGMENT ID]**: a ID do segmento criado automaticamente associado a cada persona;
1. **[!UICONTROL NAME]**: o nome pessoal;
1. **[!UICONTROL STATUS]**: o status da [!UICONTROL Predictive Audiences] segmento:
   * **[!UICONTROL Succeeded]**: os usuários estão sendo classificados nesse segmento;
   * **[!UICONTROL Pending]**: o segmento ainda está sendo inicializado;
   * **[!UICONTROL Insufficient Training Data]**: os usuários não estão sendo classificados nesse segmento devido a dados insuficientes. A população total da linha de base é muito baixa e não fornece dados suficientes para aprender.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: o número de realizações de segmento para cada persona, nas últimas 24 horas.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: a porcentagem de realizações do segmento para cada persona, nas últimas 24 horas, da população total do modelo.

## Características influentes{#influential-traits}

[!UICONTROL Influential Traits] são características que o [!UICONTROL Predictive Audiences] descobriu-se que o algoritmo é o mais forte preditor para determinar a classificação pessoal de um visitante.

Seu sinal indica se a presença da característica aumenta(+) ou diminui(-) a probabilidade do usuário pertencer à persona selecionada.

Para exibir as características influentes de todas as personas, clique em [!UICONTROL View All Influential Traits].

A variável [!UICONTROL Influential Traits] mostra as seguintes informações para cada persona do modelo selecionado:

![características influentes](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: a ID de característica de cada característica influente para a persona selecionada;
1. **[!UICONTROL NAME]**: o nome de cada característica influente para a persona selecionada;
1. **[!UICONTROL DESCRIPTION]**: a descrição de cada característica influente para a persona selecionada;
1. **[!UICONTROL WEIGHT]**: o peso de cada característica influente para a persona selecionada. [!UICONTROL Influential Traits] por padrão, são classificados por peso, em ordem decrescente.  O valor dos pesos indica seu poder preditivo. O sinal indica se a presença da característica aumenta(+) ou diminui(-) a probabilidade de pertencer a uma persona.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: o número de realizações de características exclusivas para cada característica influente da persona selecionada, nos últimos 30 dias.
