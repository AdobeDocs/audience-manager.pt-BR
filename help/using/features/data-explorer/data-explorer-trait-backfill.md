---
description: Realização de características de preenchimento retroativo para capturar audiências históricas e evitar a perda de dados relevantes antes de uma data de criação de característica.
seo-description: Realização de características de preenchimento retroativo para capturar audiências históricas e evitar a perda de dados relevantes antes de uma data de criação de característica.
seo-title: Realizações da característica de preenchimento retroativo
title: Realizações da característica de preenchimento retroativo
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


# Realizações da característica de preenchimento retroativo {#backfill-trait-realizations}

Realização de características de preenchimento retroativo para capturar audiências históricas e evitar a perda de dados relevantes antes de uma data de criação de característica.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] é um recurso premium que aprimora a experiência do Gerenciador de Audiências desbloqueando casos de uso adicionais. O preenchimento retroativo requer poder de processamento adicional e está disponível para todos os clientes do Audiência Manager a um custo incremental. Entre em contato com seu representante de vendas da Adobe para obter mais detalhes.

Ao criar características de sinais não utilizados, você pode optar por preencher retroativamente as realizações de características ao longo de um período de tempo específico. [!DNL Audience Manager] captura os dados históricos sobre audiências que se qualificam para a nova característica e as armazena no perfil correspondente. Você pode ver a imagem **[!UICONTROL Backfill Options]** na [!UICONTROL Trait Expression] seção do Construtor de **[características](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Você pode preencher retroativamente as realizações de características para características baseadas em regras e integradas.

Veja como preencher retroativamente as realizações de características:

1. Vá para o [!UICONTROL Audience Data > Signals > Search] amd executar uma Pesquisa de Sinais ou use o Painel [de](../../features/data-explorer/data-explorer-signals-dashboard.md) Sinais para identificar os sinais a serem usados no novo traço.
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

1. Crie o traço.

Depois de terminar de criar o traço, você verá suas execuções preenchidas retroativamente incluídas nas estatísticas de realização.

Assista ao vídeo abaixo para ver uma apresentação em vídeo de como preencher retroativamente as características.

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## Latência de preenchimento retroativo da característica {#trait-backfilling-latency}

O start de características recém-criado captura audiências duas a três horas após a criação. No entanto, devido ao grande volume de dados que [!DNL Audience Manager] são executados diariamente, a população preenchida retroativamente não é refletida imediatamente nos gráficos [!UICONTROL Unique Trait Realizations] e [!UICONTROL Total Trait Population] .

O Gerenciador de Audiências atualiza o com a população preenchida retroativamente [!UICONTROL Trait Graph] dentro de 48 horas após a criação da característica.

## Limite de preenchimento retroativo da característica {#trait-backfilling-limit}

[!UICONTROL Data Explorer] permite preencher até 50 características por mês, com o contador de preenchimento retroativo sendo redefinido no dia 1 de cada mês.

>[!NOTE]
>
>A quota de preenchimento retroativo das características não é transferida dos meses anteriores. Por exemplo, se você preencher 30 características este mês retroativamente, a cota de preenchimento retroativo característica para o mês seguinte será redefinida para 50, não 70.

## Impacto nos Relatórios {#reporting-impact}

As realizações de características preenchidas retroativamente são refletidas nas métricas [!UICONTROL Unique Trait Realizations] e [!UICONTROL Total Trait Population] , à medida que [!DNL Audience Manager] os sinais históricos se tornam realizações de características.

No entanto, as métricas [!UICONTROL Trait Graph], [!UICONTROL General Reports]e [!UICONTROL Trend Reports] não são atualizadas retroativamente com o preenchimento retroativo das métricas históricas antes da data de criação da característica.