---
description: O Relatórios de uso de Atividade ajuda você a visualização e a rastrear o uso de atividade para a instância do Audience Manager, para que você possa comparar o uso real com o compromisso contratual.
keywords: activity, usage, reporting, commitment
seo-description: O Relatórios de uso de Atividade ajuda você a visualização e a rastrear o uso de atividade para a instância do Audience Manager, para que você possa comparar o uso real com o compromisso contratual.
seo-title: Relatórios de uso de Atividade
solution: Audience Manager
title: Relatórios de uso de Atividade
topic: Activity Usage Reporting
translation-type: tm+mt
source-git-commit: 0869e016d7f80710cb194449c48675b82fdfa865
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 0%

---


# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## Visão geral {#overview}

O [!UICONTROL Activity Usage Report] ajuda a visualização e rastrear o uso da atividade da instância do Audience Manager, fornecendo uma ideia clara de como o uso da atividade se compara ao compromisso contratual.

Além disso, você pode baixar o arquivo [!UICONTROL Activity Usage Report] sempre que precisar para manter registros e análise personalizada.

## Considerações {#considerations}

O [!UICONTROL Activity Usage Report] está disponível para todos os usuários do Audience Manager com privilégios [de](edit-account-settings.md)administrador.

>[!IMPORTANT]
>
>O [!UICONTROL Activity Usage Report] mostra as estatísticas de uso de atividade da sua instância de Audience Manager. Para obter informações sobre cobrança relacionadas ao uso da atividade, entre em contato com seu representante da Adobe.

## Casos de uso {#use-cases}

Há dois casos principais de uso do [!UICONTROL Activity Usage Report]:

* **Rastrear o uso real da atividade de instância em relação ao compromisso** de uso da atividade: A maioria dos clientes tem um compromisso mensal estimado de atividade por instância de Audience Manager, que é então acumulado em um compromisso anual de atividade em todas as instâncias. Embora este relatório não seja um relatório de cobrança, ele pode fornecer orientações úteis sobre se você está excedendo o uso da atividade comprometida.
* **Validação para alterações** de implementação: Se você atualizou recentemente sua implementação, como configurar o encaminhamento pelo lado do [!DNL Adobe Analytics] servidor ou alterar as configurações de chamada do [!DNL Adobe Target] servidor, este relatório pode ajudá-lo a verificar se o novo volume de atividade está em conformidade com o volume de atividade esperado.

## Utilizar a [!UICONTROL Activity Usage Report] {#using}

Para ver o [!UICONTROL Activity Usage Report], faça logon na sua conta do Audience Manager e vá para **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Em seguida, use o **[!UICONTROL Reporting Interval]** filtro para selecionar o intervalo de tempo para o qual gerar o relatório. Você pode escolher entre 30, 60, 90 dias ou um intervalo de datas personalizado.

Depois que o relatório for carregado, você poderá ver o detalhamento do relatório [!UICONTROL Activities] para o período selecionado.

[!UICONTROL Activities] defina o total da agregação de todas as interações no site e fora dele com o Audience Manager, divididas nas seguintes categorias:

* **[!UICONTROL Server Calls]**: Qualquer evento de coleta ou recuperação de dados enviado para o Audience Manager de sites, servidores, e-mail, aplicativos móveis ou outros sistemas.
* **[!UICONTROL Pixel Calls](anteriormente conhecido como[!UICONTROL Impression Server Calls])**: Dados coletados de anúncios (como volume de impressão de uma plataforma de definição de metas) ou chamadas de impressão de email feitas para o Audience Manager. Eles exigem a presença do`d_event`parâmetro na string do query.
* **[!UICONTROL On-Boarded Records]**: Registros únicos ingeridos do seu próprio CRM (Customer Relationship Management System, sistema de gerenciamento de relacionamento com o cliente) ou de outros arquivos de dados offline, como registros da central de atendimento, IDs de dispositivo e feeds de dados personalizados de provedores de dados externos.
* **[!UICONTROL Log File Records]**: Registros exclusivos de arquivos de log ingeridos no Audience Manager de uma plataforma de definição de metas.

>[!NOTE]
>
>Um registro exclusivo define cada registro individual de dados em um arquivo armazenado pela Adobe em nome de um cliente Audience Manager.

Além disso, você pode usar os tipos de [!UICONTROL Activity Usage Trends] gráfico para alternar entre dois tipos de gráficos.

![aur-ui-ógrafos](assets/aur-ui-graphs.png)

Você também pode passar o cursor sobre uma data específica na linha do tempo para ver o uso detalhado dessa data.

![aur-hover](assets/aur-hover.png)

## Exportação [!UICONTROL Activity Usage Reports] {#export}

Para obter uma visão geral melhor do nível de uso da atividade de Audience Manager, é possível exportar os dados [!UICONTROL Activity Usage Report] com base no tipo de registros que deseja incluir.

![aur-export](assets/aur-export.png)

Os relatórios **[!UICONTROL Onboarded Records Breakdown]** e **[!UICONTROL Onsite Server Calls Breakdown]** fornecem o insight mais detalhado dos dados de origem disponíveis para essas atividades. O volume atribuído a esses detalhamentos é baseado na sua implementação.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

Este relatório contém registros onboard detalhados por fonte de dados.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

Este relatório contém um detalhamento de chamadas de servidor de três fontes: [!UICONTROL Analytics], [!UICONTROL Target]e [!UICONTROL Other].

* **[!UICONTROL Analytics]**: São chamadas faturáveis do servidor passadas de todas as [!UICONTROL Adobe Analytics] instâncias para o Audience Manager, incluindo o encaminhamento pelo lado do servidor. As chamadas de servidor secundário ou de servidor de duplicado (como no caso do encaminhamento pelo lado do servidor de vários conjuntos de relatórios) não são atividades faturáveis, portanto, não são incluídas neste detalhamento.
* **[!UICONTROL Target]**: São chamadas do lado do servidor [!UICONTROL Adobe Target] para o Audience Manager, para recuperar dados do segmento do Audience Manager como parte de uma integração de servidor para servidor.
* **[!UICONTROL Other]**: Inclui chamadas de qualquer outro site ou sistema (sites de parceiros, chamadas diretas do servidor etc.), chamadas de navegador/aplicativo móvel por meio de [!DNL SDK], [!DNL DIL], chamadas de evento e [!DNL DCS] chamadas. Também inclui chamadas de [!DNL Target] se configuradas como uma integração de cookie (em vez de servidor para servidor).
