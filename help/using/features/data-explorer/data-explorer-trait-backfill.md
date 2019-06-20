---
description: Preenchimento retroativo de resultados para capturar públicos históricos e evitar perda de dados relevantes antes da data de criação de características.
seo-description: Preenchimento retroativo de resultados para capturar públicos históricos e evitar perda de dados relevantes antes da data de criação de características.
seo-title: Preenchimento retroativo de características
title: Preenchimento retroativo de características
uuid: 8 b 0 ef 4 e 6-d 16 a -4 d 1 d -94 f 1-b 84 eebffa 9 a 5
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Backfill Trait Realizations {#backfill-trait-realizations}

Preenchimento retroativo de resultados para capturar públicos históricos e evitar perda de dados relevantes antes da data de criação de características.

[!UICONTROL Data Explorer Trait Backfill] é um recurso premium que aumenta a experiência do Audience Manager desbloquear casos de uso adicionais. O preenchimento retroativo requer mais energia de processamento e está disponível para todos os clientes do Audience Manager a um custo incremental. Entre em contato com seu representante de vendas da Adobe para obter mais detalhes.

Ao criar características de sinais não usados, você pode optar por preencher retroativamente os resultados das características durante um período específico. [!DNL Audience Manager] captura os dados históricos sobre os públicos-alvo que se qualificaram para a nova característica e os armazena no perfil correspondente. You can see the **[!UICONTROL Backfill Options]** in the [!UICONTROL Trait Expression] section of the **[Trait Builder](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Você pode preencher as características de característica para características com base em regras e em perfis integrados.

Veja como preencher as características de característica:

1. Go to [!UICONTROL Audience Data > Signals > Search] amd run a Signals Search or use the [Signals Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) to identify the signals to use in the new trait.
1. Crie uma nova característica com base nos sinais desejados.
1. Use the **[!UICONTROL Backfill Options]** in the **[!UICONTROL Trait Expression]** section to select the time interval for which you want to backfill trait realizations. Intervalos retroativos predefinidos incluem 1, 7, 14 e 30 dias. Você também pode escolher um intervalo de datas personalizado de até 30 dias.
   ![](assets/signals-trait-backfill.png)
1. (Optional) Click **[!UICONTROL Estimate Realizations]** in the **[!UICONTROL Estimated Trait Realizations]** section to see the estimated [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] values for the backfilled trait over the last 7 days.
   ![](assets/estimate-trait-realizations.png)
   >[!IMPORTANT]
   >
   >O preenchimento e a estimativa de características não estão disponíveis para características com expressões que usam os seguintes operadores:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Crie a característica.

Depois de terminar de criar a característica, você verá seus testes preenchidos retroativamente nas estatísticas de realização.

## Trait Backfilling Latency {#trait-backfilling-latency}

As características recém-criadas começam a capturar públicos-alvo de duas a três horas após a criação. However, due to the large volume of data that [!DNL Audience Manager] performs on a daily basis, the backfilled population is not immediately reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] graphs.

Audience Manager updates the [!UICONTROL Trait Graph] with the backfilled population within 48 hours from trait creation.

## Trait Backfilling Limit {#trait-backfilling-limit}

[!UICONTROL Data Explorer] permite preencher retroativamente até 50 características por mês, com o contador de preenchimento retroativo sendo redefinido no dia 1 de cada mês.

>[!NOTE]
>
>A cota de preenchimento retroativa não continua a partir de meses anteriores. Por exemplo, se você preencher retroativamente 30 características neste mês, a cota de preenchimento retroativa para o próximo mês será redefinida para 50, e não 70.

## Impact on Reporting {#reporting-impact}

Backfilled trait realizations are reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] metrics, as [!DNL Audience Manager] turns historical signals into trait realizations.

However, the [!UICONTROL Trait Graph], [!UICONTROL General Reports], and [!UICONTROL Trend Reports] are not updated retroactively with historical metrics backfilled before the trait creation date.