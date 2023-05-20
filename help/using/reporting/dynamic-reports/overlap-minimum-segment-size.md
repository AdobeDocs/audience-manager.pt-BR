---
description: Descreve os requisitos de tamanho de segmento e tempo de criação exigidos pelo processo de atualização do relatório de Sobreposição.
seo-description: Describes the segment size and creation time requirements required by the Overlap report update process.
seo-title: Overlap Reports  Update Schedule and Minimum Segment Size
solution: Audience Manager
title: Agendamento de atualização de relatórios de sobreposição e tamanho mínimo do segmento
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Overlap Reports
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 6%

---

# Relatórios de sobreposição: Atualizar agendamento e tamanho mínimo do segmento{#overlap-reports-update-schedule-and-minimum-segment-size}

Descreve a característica, o tamanho do segmento e os requisitos de tempo de criação exigidos pelo processo de atualização do relatório de Sobreposição.

## Atualizar programação e requisitos {#update-schedule}

[!UICONTROL Overlap] os relatórios são atualizados semanalmente no domingo. O pré-processamento do relatório começa no sábado. Isso afeta como os segmentos novos ou existentes aparecem em um relatório de sobreposição na segunda-feira. Para ser incluído em um relatório de sobreposição:

* Um segmento deve conter um mínimo de 70.000 usuários em tempo real durante os últimos 14 dias.
* Uma característica deve conter 28.000 [realizações de características únicas](/help/using/features/traits/trait-and-segment-qualification-reference.md) durante os últimos 14 dias.
* Um segmento deve ter sido criado antes das 12 horas da quinta-feira (2 dias completos antes do início do processo de atualização do relatório de sobreposição semanal).
* Sua empresa deve ser uma Full [!DNL Audience Manager] cliente. Entre em contato com [!DNL Audience Manager] ou Atendimento ao cliente para saber mais.

## O tamanho e/ou o tempo de criação do segmento afetam os relatórios {#segment-size}

Se você não vir um segmento em um dos [!UICONTROL Overlap] relatórios, pode ser porque o segmento não atende a esses requisitos mínimos.

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Tamanho do segmento muito pequeno</b> </p> </td> 
   <td colname="col2"> <p>Digamos que você crie um segmento antes das 12h da quinta-feira (UTC), mas ele contém menos de 70.000 usuários em tempo real. Este segmento não aparecerá em um <span class="wintitle"> Relatório de sobreposição</span> até atender aos requisitos do limite do usuário. Observe também que o segmento deve atender à contagem de usuários necessária no período de corte de quinta-feira ou antes dele. Se não cumprir o prazo semanal, o segmento aparecerá no <span class="wintitle"> Relatórios de sobreposição</span> para a semana após a próxima execução de dados de domingo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmento criado muito tarde</b> </p> </td> 
   <td colname="col2"> <p>Digamos que você crie um segmento na sexta-feira e ele contenha mais de 70.000 usuários em tempo real no total. Este segmento não aparecerá no <span class="wintitle"> Relatórios de sobreposição</span> para a próxima semana porque foi criada menos de 2 dias antes do período de atualização do relatório. No entanto, o segmento aparecerá em um <span class="wintitle"> Relatório de sobreposição</span> após a próxima atualização semanal. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Relatório de sobreposição de característica por característica](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Relatório de sobreposição de segmento por característica](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Relatório de sobreposição de segmento por segmento](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

