---
description: Perguntas e problemas comuns relacionados a relatórios.
seo-description: Perguntas e problemas comuns relacionados a relatórios.
seo-title: Perguntas frequentes sobre relatórios
solution: Audience Manager
title: Perguntas frequentes de geração de relatórios
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
feature: Referência de relatórios
exl-id: 1e6531b2-bb39-4056-9d5e-164f50955f99
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 99%

---

# Perguntas frequentes sobre relatórios {#reporting-faq}

Perguntas e problemas comuns relacionados a relatórios.

<br> 

<!-- 

faq_reports.xml

 -->

**Para novas características integradas, por que o [!UICONTROL Trait Graph] às vezes exibe números menores que o esperado ou 0?**

Às vezes, depois que você carrega características, o [!UICONTROL Trait Graph] não mostra resultados ou mostra números inferiores aos esperados. Isso acontece quando o volume de dados que recebemos é tão grande que o trabalho de processamento de entrada não pode terminar de assimilar essas informações até o final do prazo para relatórios daquele dia.

Como resultado, esses dados são enviados tardiamente para o sistema de relatórios e não são exibidos no intervalo de 1 dia do relatório usado para plotar o [!UICONTROL Trait Graph]. No entanto, você pode visualizar esses dados nos intervalos de relatório de 7, 14, 30 e 60 dias em uma [Tendência](../reporting/trend-reports.md#trend-report-overview) ou [Relatório geral](../reporting/general-reports.md#general-reports-overview) no dia seguinte.

<br> 

**Alguns segmentos estão ausentes em um relatório de [!UICONTROL Overlap]. Onde eles estão?**

Para ajudar a reduzir a demanda computacional, esses relatórios omitem dados estatisticamente insignificantes dos resultados. Os segmentos não estão ausentes, eles são descartados porque não produzem resultados significativos ou pools úteis de usuários que você pode direcionar. Consulte também:

* [Metodologias de amostragem de relatórios e dados](../reporting/report-sampling.md)
* [Contagem de usuários únicos em sobreposição e relatórios gerais](../reporting/unique-user-counts.md).

<br> 

**Se eu executar uma campanha de marketing por email, como posso determinar se os usuários redirecionados vêm para o meu site a partir dessa campanha ou de outras fontes?**

Anexe uma sequência de consulta específica da campanha ao URL da seção do site que você deseja monitorar. Em seguida, configure uma regra de característica para capturar essa variável. Por exemplo, se o URL passar em uma ID de campanha como essa, `www.test123.com/electronics?campaign=123`, crie uma regra de característica para capturar esses dados da variável `h_referer` com uma regra de característica que procura um cabeçalho como `h_referer = 'campaign=123'`).

<br> 

**Qual é a diferença entre a contagem de população de segmentos em tempo real e total?**

* **Tempo real:** o número de usuários únicos que fazem parte do segmento e estão ativos em suas propriedades durante um período de tempo definido (isto é, o [!DNL Audience Manager] deve ter registrado a atividade desse usuário durante o período de tempo específico).

* **População total do segmento:** um agregado de todos os usuários atualmente classificados nesse segmento.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**Tenho um segmento que consiste em apenas uma característica. Quando olho para as métricas de Relatórios, suas contagens não correspondem. Por que isso ocorre?**

Consulte [Dados de população de característica e segmento no Criador de segmentos](../features/segments/segment-builder-data.md).

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**Insiro um arquivo e meu recibo de entrada mostra um alto número de registros processados com êxito, mas os relatórios mostram números muito mais baixos. Por quê?**

No backend, os dados integrados são anexados somente aos usuários que ainda estão ativos no AAM (o usuário deve ter tido atividade de [!DNL DCS] recente nos últimos 120 dias). Portanto, se você integrar dados de usuários que já expiraram no [!DNL Audience Manager], o [!UICONTROL Inbound] talvez informe que um determinado número de registros de usuários foram integrados, mas se esses usuários não tiverem tido nenhuma atividade recente, esses dados serão ignorados quando chegarem em nosso [!UICONTROL User Profile Store] e os relatórios aparecerão.

<br> 

**Por que as características únicas das minhas características integradas em vários dispositivos são muito maiores que o número total de registros integrados?**

Se você integrar um arquivo para um provedor de dados entre dispositivos que ignorou a ID do cliente, o Audience Manager fará uma pesquisa para obter todas as IDs de dispositivo associadas a cada uma das IDs de cliente integradas. Em seguida, o Audience Manager atribui as características integradas à ID do dispositivo associada à ID do cliente.

Por exemplo, suponha que você tenha integrado 100 registros. Para cada uma dessas IDs de cliente, em média, o AAM associou três IDs de dispositivo. Como resultado, a característica integrada é atribuída a 300 IDs de dispositivo.

Há dois motivos pelos quais uma única ID de cliente entre dispositivos pode ser associada a várias IDs de dispositivo:

* Os usuários estão fazendo logon na mesma conta entre dispositivos de vários computadores/navegadores.
* Os usuários estão limpando os cookies. Observação: os cookies &quot;abandonados&quot; são excluídos após 120 dias de inatividade do usuário.

<br> 

**Por que [!UICONTROL Total Trait Realizations] minhas características integradas são sempre 0?**

As [!UICONTROL Total Trait Realizations] correspondem a carregamentos de página. As [!UICONTROL Total Trait Realizations] fornecem o número de vezes que uma característica específica foi acionada em tempo real. Esse número é calculado somente para características com base em regras. As características integradas sempre mostram [!UICONTROL Total Trait Realizations] como 0.

<br> 

**Criei uma característica e o [!UICONTROL Trait Graph] mostra um número maior de [!UICONTROL Unique Trait Realizations] que a [!UICONTROL Total Trait Population]. Isso é normal?**

Você está vendo isso porque [!UICONTROL Unique Trait Realizations] são métricas em tempo real, mas os trabalhos de relatórios que fazemos para calcular os resultados de [!UICONTROL Total Trait Population] não são em tempo real. A [!UICONTROL Total Trait Population] deve ser maior do que as [!UICONTROL Unique Trait Realizations] em alguns dias.
