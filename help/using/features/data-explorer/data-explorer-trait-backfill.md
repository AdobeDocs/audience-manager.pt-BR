---
description: Preenchimento retroativo de resultados para capturar públicos históricos e evitar perda de dados relevantes antes da data de criação de características.
seo-description: Preenchimento retroativo de resultados para capturar públicos históricos e evitar perda de dados relevantes antes da data de criação de características.
seo-title: Preenchimento retroativo de características
title: Preenchimento retroativo de características
uuid: 8 b 0 ef 4 e 6-d 16 a -4 d 1 d -94 f 1-b 84 eebffa 9 a 5
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Preenchimento retroativo de características {#backfill-trait-realizations}

Preenchimento retroativo de resultados para capturar públicos históricos e evitar perda de dados relevantes antes da data de criação de características.

[!UICONTROL Data Explorer Trait Backfill] é um recurso premium que aumenta a experiência do Audience Manager desbloquear casos de uso adicionais. O preenchimento retroativo requer mais energia de processamento e está disponível para todos os clientes do Audience Manager a um custo incremental. Entre em contato com seu representante de vendas da Adobe para obter mais detalhes.

Ao criar características de sinais não usados, você pode optar por preencher retroativamente os resultados das características durante um período específico. [!DNL Audience Manager] captura os dados históricos sobre os públicos-alvo que se qualificaram para a nova característica e os armazena no perfil correspondente. Você pode ver a **[!UICONTROL Backfill Options]**[!UICONTROL Trait Expression] seção do Construtor de **[traços](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Você pode preencher as características de característica para características com base em regras e em perfis integrados.

Veja como preencher as características de característica:

1. Vá [!UICONTROL Audience Data > Signals > Search] para amd run a Signal Search ou use o Painel [Sinais](../../features/data-explorer/data-explorer-signals-dashboard.md) para identificar os sinais a serem usados na nova característica.
1. Crie uma nova característica com base nos sinais desejados.
1. Use a **[!UICONTROL Backfill Options]****[!UICONTROL Trait Expression]** seção para selecionar o intervalo de tempo para o qual você deseja preencher o resultado retroativamente. Intervalos retroativos predefinidos incluem 1, 7, 14 e 30 dias. Você também pode escolher um intervalo de datas personalizado de até 30 dias.

   ![preenchimento retroativo](assets/signals-trait-backfill.png)

1. (Opcional) Clique **[!UICONTROL Estimate Realizations]** na **[!UICONTROL Estimated Trait Realizations]** seção para ver os valores estimados [!UICONTROL Unique Trait Realizations] e [!UICONTROL Total Trait Population] os valores para a característica retroativa nos últimos 7 dias.

   ![estimativa-característica-experiência](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >O preenchimento e a estimativa de características não estão disponíveis para características com expressões que usam os seguintes operadores:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Crie a característica.

Depois de terminar de criar a característica, você verá seus testes preenchidos retroativamente nas estatísticas de realização.

## Latência de preenchimento retroativo {#trait-backfilling-latency}

As características recém-criadas começam a capturar públicos-alvo de duas a três horas após a criação. No entanto, devido ao grande volume de dados [!DNL Audience Manager] realizados diariamente, a população preenchida retroativamente não é refletida imediatamente nos [!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Population] gráficos.

O Audience Manager atualiza o [!UICONTROL Trait Graph] com a população preenchida retroativamente dentro de 48 horas a partir da criação de características.

## Limite de preenchimento retroativo de características {#trait-backfilling-limit}

[!UICONTROL Data Explorer] permite preencher retroativamente até 50 características por mês, com o contador de preenchimento retroativo sendo redefinido no dia 1 de cada mês.

>[!NOTE]
>
>A cota de preenchimento retroativa não continua a partir de meses anteriores. Por exemplo, se você preencher retroativamente 30 características neste mês, a cota de preenchimento retroativa para o próximo mês será redefinida para 50, e não 70.

## Impacto sobre o relatório {#reporting-impact}

Os testes de característica preenchidos retroativamente são refletidos nas métricas [!UICONTROL Unique Trait Realizations] e [!UICONTROL Total Trait Population] , assim, [!DNL Audience Manager] os sinais históricos tornam os sinais históricos realizáveis.

No entanto, o [!UICONTROL Trait Graph], [!UICONTROL General Reports]e [!UICONTROL Trend Reports] não são atualizados retroativamente com as métricas históricas preenchidos antes da data de criação de características.