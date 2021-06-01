---
description: Descreve os requisitos de tamanho e tempo de criação do segmento exigidos pelo processo de atualização do relatório de sobreposição.
seo-description: Descreve os requisitos de tamanho e tempo de criação do segmento exigidos pelo processo de atualização do relatório de sobreposição.
seo-title: Relatórios de sobreposição Atualizar agendamento e tamanho mínimo do segmento
solution: Audience Manager
title: Relatórios de sobreposição Atualizar agendamento e tamanho mínimo do segmento
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Relatórios de sobreposição
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 5%

---

# Relatórios de sobreposição: Atualizar agendamento e tamanho mínimo do segmento{#overlap-reports-update-schedule-and-minimum-segment-size}

Descreve os requisitos de característica e tamanho do segmento e tempo de criação exigidos pelo processo de atualização do relatório de sobreposição.

## Atualizar agendamento e requisitos {#update-schedule}

[!UICONTROL Overlap] os relatórios são atualizados semanalmente no domingo. O pré-processamento do relatório começa no sábado. Isso afeta a forma como segmentos novos ou existentes aparecem em um relatório de sobreposição na segunda-feira. Para ser incluído em um relatório de sobreposição:

* Um segmento deve conter no mínimo 70.000 usuários em tempo real durante os últimos 14 dias.
* Uma característica deve conter 28.000 [realizações de característica exclusiva](/help/using/features/traits/trait-and-segment-qualification-reference.md) durante os últimos 14 dias.
* Um segmento deve ter sido criado antes das 12h Quinta-feira no UTC (2 dias completos antes do início do processo semanal de atualização do relatório de sobreposição).
* Sua empresa deve ser um cliente completo [!DNL Audience Manager]. Entre em contato com seu consultor [!DNL Audience Manager] ou com o Atendimento ao cliente para saber mais.

## O tamanho do segmento e/ou o tempo de criação afetam os relatórios {#segment-size}

Se você não vir um segmento em um dos relatórios [!UICONTROL Overlap], pode ser porque o segmento não atende a esses requisitos mínimos.

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
   <td colname="col2"> <p>Digamos que você crie um segmento antes das 12:00 UTC de quinta-feira, mas que contenha menos de 70.000 usuários em tempo real. Este segmento não aparecerá em um <span class="wintitle"> Relatório de sobreposição</span> até que ele atenda aos requisitos de limite do usuário. Observe também que o segmento deve atender à contagem de usuários necessária em ou antes do período de corte de quinta-feira. Se não atender o prazo semanal, o segmento aparecerá nos <span class="wintitle"> Relatórios de sobreposição</span> da semana após a próxima execução dos dados de domingo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmento criado muito tarde</b> </p> </td> 
   <td colname="col2"> <p>Digamos que você crie um segmento na sexta-feira e ele contenha mais de 70.000 usuários em tempo real. Esse segmento não aparecerá nos <span class="wintitle"> Relatórios de sobreposição</span> da próxima semana porque foi criado menos de 2 dias antes do período de atualização do relatório. No entanto, o segmento aparecerá em um <span class="wintitle"> Relatório de sobreposição</span> após a próxima atualização semanal. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Relatório de sobreposição de característica por característica](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
* [Relatório de sobreposição de segmento por característica](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
* [Relatório de sobreposição de segmento por segmento](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

