---
description: Descreve os requisitos de tamanho do segmento e tempo de criação exigidos pelo processo de atualização do relatório Sobreposição.
seo-description: Descreve os requisitos de tamanho do segmento e tempo de criação exigidos pelo processo de atualização do relatório Sobreposição.
seo-title: Sobrepor agendamento de relatórios e Tamanho mínimo do segmento
solution: Audience Manager
title: Sobrepor agendamento de relatórios e Tamanho mínimo do segmento
uuid: 35 c 1 cb 39-e 28 d -4 d 20-88 c 9-5 ff 4 fe 154 e 9 e
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Overlap Reports: Update Schedule and Minimum Segment Size{#overlap-reports-update-schedule-and-minimum-segment-size}

Descreve os requisitos de tamanho do segmento e tempo de criação exigidos pelo processo de atualização do relatório Sobreposição.

## Update Schedule and Requirements {#update-schedule}

[!UICONTROL Overlap] atualizam semanalmente no domingo. O pré-processamento do relatório começa no sábado. Isso afeta a forma como os segmentos novos ou existentes aparecem em um relatório de sobreposição na segunda-feira. Para ser incluído em um relatório de sobreposição:

* Um segmento deve conter no mínimo 70,000 usuários em tempo real total nos últimos 14 dias. Read more about [Minimum Unique Visitor Requirements for Traits and Segments](../../reporting/report-sampling.md#data-sampling-ratio).
* Um segmento deve ter sido criado antes de 12 AM quinta-feira UTC (2 dias completos antes do início do processo de atualização do relatório de sobreposição semanal).
* Your company must be a Full [!DNL Audience Manager] customer. Please contact your [!DNL Audience Manager] consultant or Customer Care to find out more.

## Segment Size and/or Creation Time Affects Reporting {#segment-size}

If you do not see a segment in one of the [!UICONTROL Overlap] reports, it may be because the segment does not meet these minimum requirements.

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
   <td colname="col2"> <p>Vamos supor que você crie um segmento antes de 12 AM quinta-feira, mas contém menos de 70,000 usuários totais em tempo real. This segment won't appear in an <span class="wintitle"> Overlap Report</span> until it meets the user threshold requirements. Observe também que o segmento deve atender à contagem necessária do usuário, ou ao período de limite de quinta-feira. If it does not meet the weekly deadline, the segment will appear in the <span class="wintitle"> Overlap Reports</span> for the week after the upcoming Sunday data run. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmento criado muito tarde</b> </p> </td> 
   <td colname="col2"> <p>Vamos supor que você crie um segmento na sexta-feira e ele contenha mais de 70,000 usuários em tempo real. This segment won't appear in the <span class="wintitle"> Overlap Reports</span> for the next week because it was created less than 2 days prior to the report update period. However, the segment will appear in an <span class="wintitle"> Overlap Report</span> after the next weekly update. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Relatório de sobreposição de característica por característica](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Relatório de sobreposição de segmento por característica](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Relatório de sobreposição de segmento por segmento](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

