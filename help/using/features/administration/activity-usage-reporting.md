---
description: O Relatório de uso de atividade ajuda a visualizar e rastrear o uso de atividades para sua instância do Audience Manager, para que você possa comparar seu uso real com seu compromisso contratual.
keywords: activity, usage, reporting, commitment
seo-description: O Relatório de uso de atividade ajuda a visualizar e rastrear o uso de atividades para sua instância do Audience Manager, para que você possa comparar seu uso real com seu compromisso contratual.
seo-title: Relatório de uso de atividade
solution: Audience Manager
title: Relatório de uso de atividade
topic: Activity Usage Reporting
translation-type: tm+mt
source-git-commit: 7a3914af8fb225508f57724a75fe2547aac3f241

---


# Relatório de uso de atividade

## Visão geral {#overview}

O [!UICONTROL Activity Usage Report] ajuda a visualizar e rastrear o uso de atividades da sua instância do Audience Manager, fornecendo uma ideia clara de como o uso de sua atividade se compara ao seu compromisso contratual.

Além disso, você pode baixar o arquivo [!UICONTROL Activity Usage Report] sempre que precisar para manter registros e analisar personalizados.

## Considerações {#considerations}

O [!UICONTROL Activity Usage Report] está disponível para todos os usuários do Audience Manager com privilégios [de](edit-account-settings.md)administrador.

> [!IMPORTANT]
>
> O [!UICONTROL Activity Usage Report] mostra as estatísticas de uso de atividade da sua instância do Audience Manager. Para obter qualquer pesquisa de faturamento relacionada ao uso da atividade, entre em contato com seu representante da Adobe.

## Casos de uso {#use-cases}

Há dois casos principais de uso do [!UICONTROL Activity Usage Report]:

* **Rastreamento do uso real da atividade da instância em relação ao compromisso** de uso da atividade: A maioria dos clientes tem um compromisso de atividade mensal estimado por instância do Audience Manager, que é então acumulado em um compromisso de atividade anual em todas as instâncias. Embora este relatório não seja um relatório de faturamento, ele pode fornecer orientações úteis sobre se você está excedendo o uso de atividade comprometida.
* **Validação para alterações** de implementação: Se você atualizou recentemente sua implementação, como configurar o encaminhamento pelo lado do servidor do Analytics ou alterar as configurações de chamada do servidor do Target, este relatório pode ajudá-lo a verificar se o novo volume de atividade está em conformidade com o volume de atividade esperado.

## Uso do Relatório de uso da atividade {#using}

Para ver o [!UICONTROL Activity Usage Report], faça logon na sua conta do Audience Manager e vá para **[!UICONTROL Administration]**>**[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Em seguida, use o **[!UICONTROL Reporting Interval]**filtro para selecionar o intervalo de tempo para o qual gerar o relatório. Você pode escolher entre 30, 60, 90 dias ou um intervalo de datas personalizado.

Depois que o relatório for carregado, você poderá ver o detalhamento do relatório [!UICONTROL Activities] para o período selecionado.

[!UICONTROL Activities] defina o total agregado de todas as interações no site e fora dele com o Audience Manager, divididas nas seguintes categorias:

* **[!UICONTROL Server Calls]**: Qualquer evento de coleta ou recuperação de dados enviado para o Audience Manager de sites, servidores, email, aplicativos móveis ou outros sistemas.
* **[!UICONTROL Pixel Calls](anteriormente conhecido como[!UICONTROL Impression Server Calls])**: Dados coletados de anúncios (como volume de impressão de uma plataforma de definição de metas) ou chamadas de impressão de email feitas para o Audience Manager. Isso requer a presença do `d_event` parâmetro na string de consulta.
* **[!UICONTROL On-Boarded Records]**: Registros únicos ingeridos do seu próprio CRM (Customer Relationship Management System, sistema de gerenciamento de relacionamento com o cliente) ou de outros arquivos de dados offline, como registros da central de atendimento, IDs de dispositivo e feeds de dados personalizados de provedores de dados externos.
* **[!UICONTROL Log File Records]**: Registros exclusivos de arquivos de log ingeridos no Audience Manager a partir de uma plataforma de definição de metas.

> [!NOTE]
> Um registro exclusivo define cada registro individual de dados em um arquivo armazenado pela Adobe em nome de um cliente do Audience Manager.

Além disso, você pode usar os tipos de [!UICONTROL Activity Usage Trends] gráfico para alternar entre dois tipos de gráficos.

![aur-ui-ógrafos](assets/aur-ui-graphs.png)

Você também pode passar o cursor sobre uma data específica na linha do tempo para ver o uso detalhado dessa data.

![aur-hover](assets/aur-hover.png)

## Exportar relatórios de uso de atividade {#export}

Para obter uma visão geral melhor do nível de uso da atividade do Audience Manager, é possível exportar o [!UICONTROL Activity Usage Report] com base no tipo de registros que deseja incluir.

![aur-export](assets/aur-export.png)

Os relatórios **[!UICONTROL Onboarded Records Breakdown]**e**[!UICONTROL Onsite Server Calls Breakdown]** fornecem o insight mais detalhado dos dados de origem disponíveis para essas atividades. O volume atribuído a esses detalhamentos é baseado na sua implementação.

### Detalhamento de registros integrados {#onboarded-breakdown}

Este relatório contém registros onboard detalhados por fonte de dados.

### Detalhamento de chamadas de servidor no local {#onsite-breakdown}

Este relatório contém um detalhamento de chamadas de servidor de três fontes: [!UICONTROL Analytics], [!UICONTROL Target]e [!UICONTROL Other].

* **[!UICONTROL Analytics]**: São chamadas faturáveis de servidor enviadas de todas as instâncias do Adobe Analytics para o Audience Manager, incluindo o encaminhamento pelo lado do servidor. As chamadas secundárias do servidor ou chamadas duplicadas do servidor (como no caso do encaminhamento pelo lado do servidor de vários conjuntos de relatórios) não são atividades faturáveis, portanto, não são incluídas neste detalhamento.
* **[!UICONTROL Target]**: São chamadas do lado do servidor do Adobe Target para o Audience Manager, para recuperar dados de segmento do Audience Manager como parte de uma integração servidor a servidor.
* **[!UICONTROL Other]**: Inclui chamadas de qualquer outro site ou sistema (sites de parceiros, chamadas diretas do servidor etc.), chamadas de navegador/aplicativo móvel via[!DNL SDK],[!DNL DIL], chamadas de evento e[!DNL DCS]chamadas. Também inclui chamadas de[!DNL Target]se configuradas como uma integração de cookie (em vez de servidor para servidor).
