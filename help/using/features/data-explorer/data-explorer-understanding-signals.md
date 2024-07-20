---
description: Os sinais são a menor unidade de informação no Audience Manager. Eles representam interações do usuário ou atividade do usuário em suas propriedades online e são transmitidos para o Audience Manager para serem usados nas regras de característica.
seo-description: Signals are the smallest unit of information within Audience Manager. They represent user interactions or user activity on your online properties, and get passed on to Audience Manager to be used in trait rules.
seo-title: Understanding Signals
title: Compreensão de sinais
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 1%

---

# Compreensão de sinais

Os sinais são a menor unidade de informação no Audience Manager. Eles representam interações do usuário ou atividade do usuário em suas propriedades online e são transmitidos para o Audience Manager para serem usados nas regras de característica.

[!DNL Audience Manager] usa pares de valor chave para representar sinais. Por exemplo, o sinal a seguir pode indicar que um visitante chegou a uma página da Web contendo eletrônicos:

* `page = electronics`

O [Painel de Sinais](../../features/data-explorer/data-explorer-signals-dashboard.md) mostra vários tipos de atributos de sinal que você pode usar para criar novas características. Veja a seguir uma exibição detalhada das propriedades de sinal disponíveis:

* *Par de valor-chave* mostra o par de valor-chave do sinal recebido por [!DNL Audience Manager].
* *Tipo de sinal* descreve a categoria de cada sinal. Os sinais se encaixam em uma das seguintes categorias:
   * [Arquivos de log acionáveis](/help/using/integration/media-data-integration/actionable-log-files.md): sinais em tempo real recebidos de seus arquivos de log de desempenho de mídia;
   * [!DNL Adobe Analytics]: sinais em tempo real recebidos de sua conta [!DNL Adobe Analytics];
   * Dados gerais online: dados em tempo real gerados pela sua atividade de público-alvo e não incluídos em arquivos de log acionáveis e [!DNL Adobe Analytics];
   * On-board records: dados recebidos por meio de transferências de dados em lote.
* *O Signal Source* depende do tipo de sinal:
   * Para sinais integrados, a fonte de sinal é o nome da fonte de dados.
   * Para sinais originados de [!DNL Adobe Analytics], a fonte de dados sempre será um conjunto de relatórios.
   * Para arquivos de registro acionáveis e dados gerais on-line, nenhuma informação de origem do sinal é exibida.
* *Contagens Totais* mostra o número total de vezes que um sinal em tempo real foi recebido por [!DNL Audience Manager] nos últimos 7 dias.
* *Incluído nas Características* mostra se o sinal faz parte de alguma característica. Clique na seta para ver as características que incluem o sinal correspondente. Para sinais que não fazem parte de nenhuma característica, o valor da coluna muda para [!UICONTROL Create Onboarded Trait] ou [!UICONTROL Create Rule-Based Trait].

## Frequência de atualização de dados de sinal

Devido à grande quantidade de dados que o Audience Manager processa diariamente, o [!UICONTROL Data Explorer] atualiza os dados de sinal exibidos em intervalos de tempo fixos, dependendo do tipo de sinal:

* Os dados de sinal em tempo real (arquivos de log acionáveis, dados do [!DNL Adobe Analytics] e dados online gerais) são atualizados a cada 4 a 6 horas.
* Os dados de sinal integrados são atualizados a cada 24 horas.

## Conceitos relacionados

[Sinais, características e segmentos](/help/using/reference/signal-trait-segment.md)
