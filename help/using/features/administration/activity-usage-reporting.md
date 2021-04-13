---
description: Os Relatórios de uso de atividade ajudam a visualizar e rastrear o uso da atividade para a instância do Audience Manager, para que você possa comparar seu uso real ao compromisso contratual.
keywords: atividade, uso, relatórios, compromisso
seo-description: Os Relatórios de uso de atividade ajudam a visualizar e rastrear o uso da atividade para a instância do Audience Manager, para que você possa comparar seu uso real ao compromisso contratual.
seo-title: Relatórios de uso de atividade
solution: Audience Manager
title: Relatórios de uso de atividade
feature: Uso e faturamento
exl-id: 0c5f04c6-d008-4817-9c67-cd39350b3aaf
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 6%

---

# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## Visão geral {#overview}

O [!UICONTROL Activity Usage Report] ajuda a visualizar e rastrear o uso da atividade da instância do Audience Manager, fornecendo uma ideia clara de como o uso da atividade se compara ao compromisso contratual.

Além disso, você pode baixar o [!UICONTROL Activity Usage Report] sempre que precisar, para manter registros e análise personalizada.

## Considerações {#considerations}

O [!UICONTROL Activity Usage Report] está disponível para todos os usuários do Audience Manager com [privilégios de administrador](edit-account-settings.md).

>[!IMPORTANT]
>
>O [!UICONTROL Activity Usage Report] mostra as estatísticas de uso da atividade da instância do Audience Manager. Para qualquer pesquisa de faturamento relacionada ao uso da atividade, entre em contato com o representante do Adobe.

## Casos de uso {#use-cases}

Há dois casos principais de uso do [!UICONTROL Activity Usage Report]:

* **Rastreamento do uso real da atividade da instância em relação ao compromisso** de uso da atividade: A maioria dos clientes tem um compromisso de atividade estimado mensalmente por instância do Audience Manager, que é então acumulado em um compromisso de atividade anual em todas as instâncias. Embora esse relatório não seja um relatório de faturamento, ele pode fornecer uma orientação útil sobre se você está excedendo o uso da atividade comprometida.
* **Validação para alterações** de implementação: Se você atualizou recentemente sua implementação, como configurar o encaminhamento pelo lado do  [!DNL Adobe Analytics] servidor ou alterar as configurações de chamada do  [!DNL Adobe Target] servidor, este relatório poderá ajudá-lo a verificar se o novo volume de atividade está alinhado com o volume de atividade esperado.

## Utilizar a [!UICONTROL Activity Usage Report] {#using}

Para ver o [!UICONTROL Activity Usage Report], faça logon em sua conta Audience Manager e vá para **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Em seguida, use o filtro **[!UICONTROL Reporting Interval]** para selecionar o intervalo de tempo para o qual gerar o relatório. Você pode escolher entre 30, 60, 90 dias ou um intervalo de datas personalizado.

Depois que seu relatório é carregado, você pode ver um detalhamento do [!UICONTROL Activities] para o período selecionado.

[!UICONTROL Activities] defina o total agregado de todas as interações no site e fora dele com o Audience Manager, dividido nas seguintes categorias:

* **[!UICONTROL Server Calls]**: Qualquer evento de coleta ou recuperação de dados enviado ao Audience Manager de sites, servidores, email, aplicativos móveis ou outros sistemas.
* **[!UICONTROL Pixel Calls](anteriormente conhecido como  [!UICONTROL Impression Server Calls])**: Dados coletados de anúncios (como volume de impressão de uma plataforma de direcionamento) ou chamadas de impressão de email feitas no Audience Manager. Eles exigem a presença do parâmetro `d_event` na string de consulta.
* **[!UICONTROL On-Boarded Records]**: Registros exclusivos assimilados do seu próprio CRM (relacionamento com o cliente) ou de outros arquivos de dados offline, como registros da central de atendimento, IDs de dispositivo e feeds de dados personalizados de provedores de dados externos.
* **[!UICONTROL Log File Records]**: Registros exclusivos de arquivos de log assimilados no Audience Manager de uma plataforma de direcionamento.

>[!NOTE]
>
>Um registro exclusivo define cada registro individual de dados em um arquivo armazenado pelo Adobe em nome de um cliente de Audience Manager.

Além disso, você pode usar os tipos de gráfico [!UICONTROL Activity Usage Trends] para alternar entre dois tipos de gráficos.

![aur-ui-gráficos](assets/aur-ui-graphs.png)

Você também pode passar o cursor sobre uma data específica na linha do tempo para ver o uso detalhado dessa data.

![aur-hover](assets/aur-hover.png)

## Exportar [!UICONTROL Activity Usage Reports] {#export}

Para obter uma visão geral melhor do nível de uso da atividade do Audience Manager, é possível exportar o [!UICONTROL Activity Usage Report] com base no tipo de registros que deseja incluir.

![aur-export](assets/aur-export.png)

Os relatórios **[!UICONTROL Onboarded Records Breakdown]** e **[!UICONTROL Onsite Server Calls Breakdown]** fornecem o insight mais granular dos dados de origem disponíveis para essas atividades. O volume atribuído a esses detalhamentos é baseado em sua implementação.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

Este relatório contém registros integrados detalhados por fonte de dados.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

Este relatório contém um detalhamento de chamadas de servidor de três fontes: [!UICONTROL Analytics], [!UICONTROL Target] e [!UICONTROL Other].

* **[!UICONTROL Analytics]**: São chamadas faturáveis do servidor enviadas de todas as  [!UICONTROL Adobe Analytics] instâncias para o Audience Manager, incluindo o encaminhamento pelo lado do servidor. Chamadas de servidor secundário ou chamadas de servidor duplicadas (como no caso de encaminhamento pelo lado do servidor de vários conjuntos de relatórios) não são atividades faturáveis, portanto, não são incluídas nesse detalhamento.
* **[!UICONTROL Target]**: São chamadas do lado do servidor do  [!UICONTROL Adobe Target] para o Audience Manager, para recuperar dados do segmento do Audience Manager como parte de uma integração de servidor para servidor.
* **[!UICONTROL Other]**: Inclui chamadas de qualquer outro site ou sistema (sites de parceiros, chamadas diretas do servidor, etc.), navegador/aplicativo móvel por meio de  [!DNL SDK],  [!DNL DIL], chamadas de evento e  [!DNL DCS] chamadas de . Também inclui chamadas de [!DNL Target] se configuradas como uma integração de cookie (em vez de servidor para servidor).
