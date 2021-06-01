---
description: Os sinais são a menor unidade de informação do Audience Manager. Elas representam as interações do usuário ou a atividade do usuário em suas propriedades online e são repassadas para o Audience Manager para serem usadas nas regras de características.
seo-description: Os sinais são a menor unidade de informação do Audience Manager. Elas representam as interações do usuário ou a atividade do usuário em suas propriedades online e são repassadas para o Audience Manager para serem usadas nas regras de características.
seo-title: Compreensão de sinais
title: Compreensão de sinais
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: 'Data Explorer '
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# Compreensão de sinais

Os sinais são a menor unidade de informação do Audience Manager. Elas representam as interações do usuário ou a atividade do usuário nas propriedades online e são repassadas para o Audience Manager para serem usadas nas regras de características.

[!DNL Audience Manager] O usa pares de valor chave para representar sinais. Por exemplo, o sinal a seguir pode indicar que um visitante chegou a uma página da Web contendo produtos eletrônicos:

* `page = electronics`

O [Painel de sinais](../../features/data-explorer/data-explorer-signals-dashboard.md) mostra vários tipos de atributos de sinal que você pode usar para criar novas características. Veja a seguir uma exibição detalhada das propriedades de sinal disponíveis:

* *O* par de valor-chave mostra o par de valor-chave do sinal recebido por  [!DNL Audience Manager].
* *O* tipo de sinal descreve a categoria de cada sinal. Os sinais estão em uma das seguintes categorias:
   * [Arquivos](/help/using/integration/media-data-integration/actionable-log-files.md) de log acionáveis: sinais em tempo real recebidos dos seus ficheiros de registro de desempenho de suportes de dados;
   * [!DNL Adobe Analytics]: Sinais em tempo real recebidos da sua  [!DNL Adobe Analytics] conta;
   * Dados gerais em linha: dados em tempo real gerados pela atividade do público-alvo e não incluídos em arquivos de log acionáveis e [!DNL Adobe Analytics];
   * Registros integrados: dados recebidos por meio de transferências de dados em lote.
* *A* Fonte do sinal depende do tipo de sinal:
   * Para sinais integrados, a fonte de sinal é o nome da fonte de dados.
   * Para sinais originados de [!DNL Adobe Analytics], a fonte de dados sempre será um conjunto de relatórios.
   * Para arquivos de log acionáveis e dados gerais on-line, nenhuma informação da fonte de sinal é exibida.
* *Total de* contagens mostra o número total de vezes que um sinal em tempo real foi recebido pelo  [!DNL Audience Manager] nos últimos 7 dias.
* *Incluído em* Características mostra se o sinal faz parte de qualquer característica. Clique na seta para ver as características que incluem o sinal correspondente. Para sinais que não fazem parte de nenhuma característica, o valor da coluna muda para [!UICONTROL Create Onboarded Trait] ou [!UICONTROL Create Rule-Based Trait].

## Frequência de atualização de dados de sinal

Devido à grande quantidade de dados que o Audience Manager processa diariamente, [!UICONTROL Data Explorer] atualiza os dados de sinal exibidos em intervalos de tempo fixos, dependendo do tipo de sinal:

* Os dados de sinal em tempo real (arquivos de log acionáveis, [!DNL Adobe Analytics] dados e dados gerais on-line) são atualizados a cada 4 a 6 horas.
* Os dados de sinal integrado são atualizados a cada 24 horas.

## Conceitos relacionados

[Sinais, características e segmentos](/help/using/reference/signal-trait-segment.md)
