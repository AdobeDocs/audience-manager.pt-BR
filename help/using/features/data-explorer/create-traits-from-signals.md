---
description: Crie novas características de todos os sinais, incluindo aqueles que já estão sendo usados em características, e capture públicos futuros que se qualificem após a criação da característica.
seo-description: Crie novas características de todos os sinais, incluindo aqueles que já estão sendo usados em características, e capture públicos futuros que se qualificem após a criação da característica.
seo-title: Criar características de sinais
title: Criar características de sinais
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: 'Data Explorer '
exl-id: 14308ef0-58eb-4b76-858c-d0da560f55fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%

---

# Criar características de sinais

Crie novas características de todos os sinais, incluindo aqueles que já estão sendo usados em características, e capture públicos futuros que se qualificem após a criação da característica. Assista ao vídeo para uma rápida demonstração ou leia para informações detalhadas:

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## Criar características no Painel de sinais {#create-traits-from-signal-dashboard}

O [!UICONTROL Signal Dashboard] permite criar novas características a partir de [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals] e das pesquisas salvas.

Quando você cria uma nova característica, o tipo de característica é predefinido com base no tipo de sinal:

* **[!UICONTROL Rule-based]** Características para sinais em tempo real, ficheiros de registro acionáveis e  [!DNL Adobe Analytics] sinais;

* **[!UICONTROL Onboarded]** características de sinais integrados.

Para criar novas características a partir do **[!UICONTROL Signal Dashboard]**, identifique o sinal que deseja usar na característica e clique no link correspondente **[!UICONTROL Create Rule-Based Trait]** ou **[!UICONTROL Create Onboarded Trait]**.

![](assets/signals-create-trait.png)

Você será redirecionado para o **[Construtor de características](../../features/traits/about-trait-builder.md)** para criar suas novas características.

## Criar características da pesquisa de sinal {#create-traits-from-signal-search}

Crie características com base em sinais usados ou não utilizados que não são mostrados no [!UICONTROL Signal Dashboard].

Procure sinais específicos e crie características integradas ou baseadas em regras com base nos resultados. Veja como fazer isso:

1. Vá para **[!UICONTROL Audience Data > Signals > Search]** e execute uma pesquisa com base nos pares de valores chave que está procurando ou clique em **[!UICONTROL Search]** sem inserir nenhum par de valores chave para exibir todos os resultados.
2. Identifique os sinais que deseja usar na característica, na lista de resultados.
   * Para criar uma característica a partir de um sinal, clique no link correspondente **[!UICONTROL Create Rule-Based Trait]** ou **[!UICONTROL Create Onboarded Trait]**.
   * Para criar uma característica a partir de vários sinais, clique na caixa de seleção correspondente de cada sinal e clique em **[!UICONTROL Create Trait from Multiple Signals]**.

   >[!NOTE]
   >Você só pode criar características a partir de sinais do mesmo tipo. Não é possível criar uma característica com base em uma combinação de um sinal em tempo real e um integrado.
   >
   > ![](assets/signals-create-trait-search.png)
   >Você também pode criar características de sinais usados. Os sinais que já são usados nas características têm o número de características exibidas na coluna **[!UICONTROL Included in Traits]**. Clique na seta para ver as características que incluem o sinal.
   >
   >![](assets/signals-used-traits.png)

3. Use o **[Construtor de características](../../features/traits/about-trait-builder.md)** para criar suas novas características.
