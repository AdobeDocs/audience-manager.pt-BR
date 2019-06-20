---
description: Perguntas e problemas comuns relacionadas a relatórios.
seo-description: Perguntas e problemas comuns relacionadas a relatórios.
seo-title: Perguntas frequentes de geração de relatórios
solution: Audience Manager
title: Perguntas frequentes de geração de relatórios
uuid: 78 cd 6 c 86-8 a 4 a -4748-ab 71-b 6 e 8 d 6078 c 94
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Perguntas frequentes de geração de relatórios{#reporting-faq}

Perguntas e problemas comuns relacionadas a relatórios.

<br> 

<!-- 

faq_reports.xml

 -->

**Para novas características integradas, por[!UICONTROL Trait Graph]que a exibição às vezes é menor que os números esperados ou 0?**

Sometimes, after you upload traits, the [!UICONTROL Trait Graph] doesn&#39;t show any results or shows lower than expected numbers. Isso acontece quando o volume de dados recebidos é tão bom que o trabalho de processamento de entrada não pode concluir a assimilação dessas informações até que o prazo de relatório desse dia seja alcançado.

As a result, this data is sent to the reporting system late and won&#39;t show up in the 1-day reporting interval which is used for plotting the [!UICONTROL Trait Graph]. However, you can view this data in the 7, 14, 30, and 60-day report intervals in a [Trend](../reporting/trend-reports.md#trend-report-overview) or [General Report](../reporting/general-reports.md#general-reports-overview) on the following day.

<br> 

**Alguns segmentos estão ausentes em[!UICONTROL Overlap]um relatório. Where are they?**

Para ajudar a reduzir a demanda computacional, esses relatórios omitem dados estatisticamente irrelevantes dos resultados. Seus segmentos não estão ausentes, eles ficam perdidos porque não geram resultados significativos ou pools úteis de usuários que você pode direcionar. Consulte também:

* [Metodologias de relatórios e amostras de dados](../reporting/report-sampling.md)
* [Contagem de usuários únicos em Sobreposição e Relatórios gerais](../reporting/unique-user-counts.md).

<br> 

**Se eu executar uma campanha de marketing por email, como posso determinar se os usuários redirecionados chegam ao meu site a partir da campanha ou de outras fontes?**

Anexe uma sequência de consulta específica de campanha ao URL da seção do site que deseja monitorar. Em seguida, configure uma regra de característica para capturar essa variável. For example, if your URL passes in a campaign ID like this, `www.test123.com/electronics?campaign=123`, then create a trait rule to capture that data from the `h_referer` variable with a trait rule that looks for a header like `h_referer = 'campaign=123'`).

<br> 

**Qual é a diferença entre contagens de preenchimento do segmento em tempo real e total?**

* **Tempo real:** O número de usuários únicos que são parte do segmento e ativo em suas propriedades durante um período de tempo definido (ou seja, [!DNL Audience Manager] devem ter uma atividade gravada para esse usuário pelo período específico).

* **População do segmento total:** Um agregado de todos os usuários que estão classificados atualmente nesse segmento.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**Eu tenho um segmento formado por apenas uma característica. Quando eu olho para as métricas de Relatório, suas contagens não correspondem. Por que isso ocorre?**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**Eu coloco um arquivo e meu recibo de entrada mostra um número alto de registros processados com êxito, mas os relatórios mostram números muito mais baixos. Por quê?**

In the backend, onboarded data gets attached only to users that are still active in AAM (user must have had recent [!UICONTROL DCS] activity in the past 120 days). Therefore, if you onboard data for users that have already expired in [!DNL Audience Manager], [!UICONTROL Inbound] might tell you that a certain number of user records were onboarded, but if these users have not had any recent activity, this data is dropped when it reaches our [!UICONTROL User Profile Store] and reporting will surface that.

<br> 

**Por que os únicos exclusivos das minhas características integradas entre dispositivos são muito maiores do que o número total de registros integrados?**

Se você colocar um arquivo em um arquivo de dados entre dispositivos desativado pela ID do cliente, o Audience Manager fará uma pesquisa para obter todas as IDs de dispositivo associadas a cada uma das IDs do cliente integradas. O Audience Manager atribui as características integradas à ID do dispositivo associada à ID do cliente.

Por exemplo, suponha que você tenha feito o envio de registros 100. Para cada uma dessas IDs do cliente, em média, o AAM associou três IDs de dispositivo. Como resultado, a característica que estava incorporada é atribuída a IDs 00 IDs de dispositivo.

Há dois motivos pelos quais uma única ID de cliente entre dispositivos pode ser associada a várias IDs de dispositivo:

* Os usuários estão fazendo logon na mesma conta entre dispositivos de vários computadores/navegadores.
* Os usuários estão limpando seus cookies. Observação: Os cookies «Abandonados» são excluídos após 120 dias de inatividade do usuário.

<br> 

**Por que[!UICONTROL Total Trait Realizations]as características onduladas são sempre 0?**

[!UICONTROL Total Trait Realizations] corresponder à página carregada. [!UICONTROL Total Trait Realizations] fornecer o número de vezes que a característica específica foi acionada em tempo real. Esse número é calculado apenas para características baseadas em regras. Onboarded traits always show [!UICONTROL Total Trait Realizations] as 0.

<br> 

**Criei uma característica e[!UICONTROL Trait Graph]exibi um número maior[!UICONTROL Unique Trait Realizations]do que[!UICONTROL Total Trait Population]o. Is this normal?**

You are seeing this because the [!UICONTROL Unique Trait Realizations] are real-time metrics, but the reporting jobs we do to calculate the [!UICONTROL Total Trait Population] are not real-time. The [!UICONTROL Total Trait Population] should be larger than the [!UICONTROL Unique Trait Realizations] within a couple of days.
