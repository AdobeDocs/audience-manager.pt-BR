---
description: Os sinais são a menor unidade de informação do Audience Manager. Elas representam as interações do usuário ou a atividade do usuário em suas propriedades online e são enviadas para o Audience Manager para serem usadas em regras de características.
seo-description: Os sinais são a menor unidade de informação do Audience Manager. Elas representam as interações do usuário ou a atividade do usuário em suas propriedades online e são enviadas para o Audience Manager para serem usadas em regras de características.
seo-title: Noções básicas sobre sinais
title: Noções básicas sobre sinais
uuid: 04a0554e-954e-484a-8838-9161ef416872
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Noções básicas sobre sinais

Os sinais são a menor unidade de informação do Audience Manager. Elas representam as interações do usuário ou a atividade do usuário em suas propriedades on-line e são enviadas ao Audience Manager para serem usadas nas regras de características.

[!DNL Audience Manager] usa pares de valores chave para representar sinais. Por exemplo, o sinal a seguir pode indicar que um visitante acessou uma página da Web que contém produtos eletrônicos:

* `page = electronics`

O Painel de [Sinais](../../features/data-explorer/data-explorer-signals-dashboard.md) mostra vários tipos de atributos de sinal que você pode usar para criar novas características. Esta é uma exibição detalhada das propriedades de sinal disponíveis:

* *O par* de valor chave mostra o par de valor chave do sinal recebido por [!DNL Audience Manager].
* *O tipo* de sinal descreve a categoria de cada sinal. Os sinais pertencem a uma das seguintes categorias:
   * [Arquivos](/help/using/integration/media-data-integration/actionable-log-files.md)de registro acionáveis: Sinais em tempo real recebidos dos ficheiros de registro de desempenho da sua mídia;
   * [!DNL Adobe Analytics]: sinais em tempo real recebidos da sua [!DNL Adobe Analytics] conta;
   * Dados gerais em linha: dados em tempo real gerados pela atividade do público-alvo e não incluídos em arquivos de registro acionáveis e [!DNL Adobe Analytics];
   * Registros a bordo: dados recebidos através de transferências de dados em lote.
* *A Fonte* do sinal depende do tipo de sinal:
   * Para sinais a bordo, a fonte do sinal é o nome da fonte de dados.
   * Para sinais originários de [!DNL Adobe Analytics], a fonte de dados sempre será um conjunto de relatórios.
   * Para arquivos de registro acionáveis e dados gerais on-line, nenhuma informação sobre a fonte do sinal é exibida.
* *A Contagem* Total mostra o número total de vezes que um sinal em tempo real foi recebido [!DNL Audience Manager] nos últimos 7 dias.
* *Incluído em Características* , mostra se o sinal faz parte de qualquer característica. Clique na seta para ver as características que incluem o sinal correspondente. Para sinais que não fazem parte de nenhuma característica, o valor da coluna muda para [!UICONTROL Create Onboarded Trait] ou [!UICONTROL Create Rule-Based Trait].

## Frequência de atualização de dados de sinal

Devido à grande quantidade de dados que o Audience Manager processa diariamente, [!UICONTROL Data Explorer] atualiza os dados de sinal exibidos em intervalos de tempo fixos, dependendo do tipo de sinal:

* Os dados de sinal em tempo real (arquivos de registro acionáveis, [!DNL Adobe Analytics] dados e dados on-line gerais) são atualizados a cada 4 a 6 horas.
* Os dados de sinal a bordo são atualizados a cada 24 horas.

## Conceitos relacionados

[Sinais, características e segmentos](/help/using/reference/signal-trait-segment.md)