---
description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Reporting
solution: Audience Manager
title: Relatórios de públicos preditivos
feature: Algorithmic Models
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 2%

---

# Relatórios de públicos preditivos

Depois de salvar um modelo [!UICONTROL Predictive Audiences], a Audience Manager começa a treiná-lo. Em algumas horas, o modelo computado iniciará a análise de públicos-alvo nos [Servidores de Coleta de Dados](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html?lang=pt-BR#dcs-pcs). Os relatórios estarão disponíveis no dia seguinte.

Para ver os resultados da sua classificação do [!UICONTROL Predictive Audiences], vá para **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** e clique no seu modelo na lista.

Use as opções de filtro no lado esquerdo para pesquisar o nome do modelo ou filtrar os resultados com base no tipo de modelo.

![filtro-de-públicos-preditivos](assets/predictive-audiences-filter-models.png)

A tabela de modelos mostra as seguintes informações:

* **[!UICONTROL ID]**: a ID do modelo identifica exclusivamente cada modelo na sua conta do Audience Manager;
* **[!UICONTROL Name]**: o nome fornecido na etapa de criação do modelo;
* **[!UICONTROL Description]**: a descrição fornecida na etapa de criação do modelo;
* **[!UICONTROL Model Type]**: o tipo de cada modelo ([!UICONTROL Look-Alike Modeling] ou [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**: o status de cada modelo:
   * **[!UICONTROL Pending]**: o modelo está sendo inicializado e começará a produzir resultados em breve;
   * **[!UICONTROL Active]**: o modelo está sendo executado com êxito e produzindo resultados;
   * **[!UICONTROL Warning]**: o modelo não produziu resultados devido a dados insuficientes (ou seja, população de linhas de base baixa, perfis de usuário não são ricos);
   * **[!UICONTROL Error]**: falha ao executar o modelo. Você deve entrar em contato com o representante da Adobe.

## Relatório de visão geral do modelo{#model-report}

Depois de escolher um modelo, a página de relatórios será carregada. Na parte superior da página, você pode ver os 5 maiores segmentos preditivos, com base na percepção em tempo real de 1 dia, que o modelo classificou seu público-alvo. A categoria **[!UICONTROL Other]** inclui o restante das personas, que não foram incluídas nos 5 maiores segmentos preditivos.

O Audience Manager exibe um gráfico de rosca codificado por cores e um gráfico de linha do tempo para o seu [!UICONTROL Predictive Audiences].

Clicar nas guias de personas na parte superior da página adiciona ou remove essas personas do gráfico e do.

O gráfico de rosca mostra um detalhamento do seu público-alvo com base em persona, enquanto o gráfico mostra a tendência da população em tempo real de 1 dia dos seus segmentos preditivos nos últimos 6 dias.

Se o status do modelo for [!UICONTROL Pending], [!UICONTROL Warning] ou [!UICONTROL Error], o status do modelo será exibido em vez dos gráficos.

![relatório-persona-inteligente](assets/predictive-audiences-report.png)

A tabela de relatórios mostra as seguintes informações para cada segmento do [!UICONTROL Predictive Audiences].

1. **[!UICONTROL SEGMENT ID]**: a ID do segmento criado automaticamente associado a cada persona;
1. **[!UICONTROL NAME]**: o nome de pessoa;
1. **[!UICONTROL STATUS]**: o status do segmento [!UICONTROL Predictive Audiences]:
   * **[!UICONTROL Succeeded]**: usuários estão sendo classificados neste segmento;
   * **[!UICONTROL Pending]**: o segmento ainda está sendo inicializado;
   * **[!UICONTROL Insufficient Training Data]**: os usuários não estão sendo classificados neste segmento devido a dados insuficientes. A população total da linha de base é muito baixa e não fornece dados suficientes para aprender.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: o número de realizações de segmento para cada persona, nas últimas 24 horas.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: a porcentagem de realizações de segmento para cada persona, nas últimas 24 horas, da população total de modelo.

## Características influentes{#influential-traits}

[!UICONTROL Influential Traits] são características que o algoritmo [!UICONTROL Predictive Audiences] descobriu serem os preditores mais fortes para determinar a classificação pessoal de um visitante.

Seu sinal indica se a presença da característica aumenta(+) ou diminui(-) a probabilidade do usuário pertencer à persona selecionada.

Para exibir as características influentes de todas as suas personas, clique em [!UICONTROL View All Influential Traits].

A janela [!UICONTROL Influential Traits] mostra as seguintes informações para cada persona do modelo selecionado:

![características influentes](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: a ID de característica de cada característica influente para a persona selecionada;
1. **[!UICONTROL NAME]**: o nome de cada característica influente para a persona selecionada;
1. **[!UICONTROL DESCRIPTION]**: a descrição de cada característica influente para a persona selecionada;
1. **[!UICONTROL WEIGHT]**: o peso de cada característica influente para a persona selecionada. [!UICONTROL Influential Traits] são por padrão classificados por peso, em ordem decrescente.  O valor dos pesos indica seu poder preditivo. O sinal indica se a presença da característica aumenta(+) ou diminui(-) a probabilidade de pertencer a uma persona.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: o número de realizações de características exclusivas para cada característica influente para a persona selecionada, nos últimos 30 dias.
