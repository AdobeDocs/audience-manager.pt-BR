---
description: Realização de características de preenchimento retroativo para capturar públicos históricos e evitar a perda de dados relevantes antes da data de criação de uma característica.
seo-description: Realização de características de preenchimento retroativo para capturar públicos históricos e evitar a perda de dados relevantes antes da data de criação de uma característica.
seo-title: Realizações da característica de preenchimento retroativo
title: Realizações da característica de preenchimento retroativo
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Realizações da característica de preenchimento retroativo {#backfill-trait-realizations}

Realização de características de preenchimento retroativo para capturar públicos históricos e evitar a perda de dados relevantes antes da data de criação de uma característica.

[!UICONTROL Data Explorer Trait Backfill] é um recurso premium que aprimora a experiência do Audience Manager ao desbloquear casos de uso adicionais. O preenchimento retroativo requer poder de processamento adicional e está disponível para todos os clientes do Audience Manager a um custo incremental. Entre em contato com seu representante de vendas da Adobe para obter mais detalhes.

Ao criar características de sinais não utilizados, você pode optar por preencher retroativamente as realizações de características ao longo de um período de tempo específico. [!DNL Audience Manager] captura os dados históricos sobre públicos-alvo qualificados para a nova característica e os armazena no perfil correspondente. Você pode ver a imagem **[!UICONTROL Backfill Options]** na [!UICONTROL Trait Expression] seção do Construtor de **[características](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Você pode preencher retroativamente as realizações de características para características baseadas em regras e integradas.

Veja como preencher retroativamente as conclusões de características:

1. Vá para o [!UICONTROL Audience Data > Signals > Search] amd e execute uma Pesquisa de Sinais ou use o Painel [de](../../features/data-explorer/data-explorer-signals-dashboard.md) Sinais para identificar os sinais a serem usados no novo traço.
1. Crie um novo traço com base nos sinais desejados.
1. Use o **[!UICONTROL Backfill Options]** na **[!UICONTROL Trait Expression]** seção para selecionar o intervalo de tempo para o qual você deseja preencher retroativamente as realizações de características. Os intervalos predefinidos de preenchimento retroativo incluem 1, 7, 14 e 30 dias. Você também pode escolher um intervalo de datas personalizado de até 30 dias.

   ![trait-backfill](assets/signals-trait-backfill.png)

1. (Opcional) Clique **[!UICONTROL Estimate Realizations]** na **[!UICONTROL Estimated Trait Realizations]** seção para ver a estimativa [!UICONTROL Unique Trait Realizations] e os [!UICONTROL Total Trait Population] valores da característica preenchida retroativamente nos últimos 7 dias.

   ![estimativas-características](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >O preenchimento retroativo de características e a estimativa não estão disponíveis para características com expressões que usam os seguintes operadores:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Crie a característica.

Depois de terminar de criar o traço, você verá suas conclusões preenchidas retroativamente incluídas nas estatísticas de realização.

## Latência de preenchimento retroativo da característica {#trait-backfilling-latency}

As características recém-criadas começam a capturar públicos duas a três horas após a criação. No entanto, devido ao grande volume de dados que [!DNL Audience Manager] são executados diariamente, a população preenchida retroativamente não é refletida imediatamente nos gráficos [!UICONTROL Unique Trait Realizations] e [!UICONTROL Total Trait Population] .

O Audience Manager atualiza o [!UICONTROL Trait Graph] com a população preenchida retroativamente dentro de 48 horas após a criação da característica.

## Limite de preenchimento retroativo da característica {#trait-backfilling-limit}

[!UICONTROL Data Explorer] permite preencher até 50 características por mês, com o contador de preenchimento retroativo sendo redefinido no dia 1 de cada mês.

>[!NOTE]
>
>A quota de preenchimento retroativo das características não é transferida dos meses anteriores. Por exemplo, se você preencher 30 características este mês retroativamente, a cota de preenchimento retroativo característica para o mês seguinte será redefinida para 50, não 70.

## Impacto nos relatórios {#reporting-impact}

As realizações de características preenchidas retroativamente são refletidas nas métricas [!UICONTROL Unique Trait Realizations] e [!UICONTROL Total Trait Population] , à medida que [!DNL Audience Manager] os sinais históricos se tornam realizações de características.

No entanto, os [!UICONTROL Trait Graph], [!UICONTROL General Reports]e [!UICONTROL Trend Reports] não são atualizados retroativamente com as métricas históricas preenchidas retroativamente antes da data de criação da característica.