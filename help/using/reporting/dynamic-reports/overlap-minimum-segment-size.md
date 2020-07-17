---
description: Descreve os requisitos de tamanho e tempo de criação do segmento exigidos pelo processo de atualização do relatório de sobreposição.
seo-description: Descreve os requisitos de tamanho e tempo de criação do segmento exigidos pelo processo de atualização do relatório de sobreposição.
seo-title: Agendamento de atualização de relatórios de sobreposição e tamanho mínimo de segmento
solution: Audience Manager
title: Agendamento de atualização de relatórios de sobreposição e tamanho mínimo de segmento
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 5%

---


# Relatórios de sobreposição: Atualizar agendamento e tamanho mínimo do segmento{#overlap-reports-update-schedule-and-minimum-segment-size}

Descreve os requisitos de tamanho e tempo de criação do segmento exigidos pelo processo de atualização do relatório de sobreposição.

## Atualizar Programação e Requisitos {#update-schedule}

[!UICONTROL Overlap] os relatórios são atualizados semanalmente no domingo. O pré-processamento do relatório começa no sábado. Isso afeta a forma como segmentos novos ou existentes aparecem em um relatório de sobreposição na segunda-feira. A ser incluído em um relatório de sobreposição:

* Um segmento deve conter no mínimo 70.000 usuários em tempo real nos últimos 14 dias. Leia mais sobre os requisitos [mínimos de Visitante único para características e segmentos](../../reporting/report-sampling.md#data-sampling-ratio).
* Um segmento deve ter sido criado antes das 12 horas UTC de quinta-feira (2 dias completos antes do início do processo de atualização do relatório de sobreposição semanal).
* Sua empresa deve ser um [!DNL Audience Manager] cliente completo. Entre em contato com seu [!DNL Audience Manager] consultor ou com o Atendimento ao cliente para saber mais.

## Tamanho do segmento e/ou Tempo de criação afeta o Relatórios {#segment-size}

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
   <td colname="col2"> <p>Digamos que você crie um segmento antes das 12:00 na quinta-feira UTC, mas que contenha menos de 70.000 usuários em tempo real. Esse segmento não aparecerá em um Relatório <span class="wintitle"> de</span> sobreposição até atender aos requisitos de limite do usuário. Observe também que o segmento deve atender à contagem de usuários necessária com base no período de corte de quinta-feira ou antes dele. Se ele não atender ao prazo semanal, o segmento aparecerá nos Relatórios <span class="wintitle"></span> de sobreposição da semana seguinte à próxima execução dos dados de domingo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmento criado muito tarde</b> </p> </td> 
   <td colname="col2"> <p>Digamos que você crie um segmento na sexta-feira e ele contenha mais de 70.000 usuários em tempo real. Esse segmento não aparecerá nos Relatórios <span class="wintitle"></span> de sobreposição da semana seguinte porque foi criado menos de 2 dias antes do período de atualização do relatório. No entanto, o segmento aparecerá em um Relatório <span class="wintitle"></span> de sobreposição após a próxima atualização semanal. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Relatório de sobreposição de característica por característica](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Relatório de sobreposição de segmento por característica](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Relatório de sobreposição de segmento por segmento](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

