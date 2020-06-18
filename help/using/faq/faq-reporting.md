---
description: Perguntas e problemas comuns relacionados ao relatórios.
seo-description: Perguntas e problemas comuns relacionados ao relatórios.
seo-title: Perguntas frequentes de geração de relatórios
solution: Audience Manager
title: Perguntas frequentes de geração de relatórios
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 1%

---


# Perguntas frequentes de geração de relatórios{#reporting-faq}

Perguntas e problemas comuns relacionados ao relatórios.

<br> 

<!-- 

faq_reports.xml

 -->

**Para novas características integradas, por que as[!UICONTROL Trait Graph]vezes exibem números menores que o esperado ou 0?**

Às vezes, depois que você carrega características, o [!UICONTROL Trait Graph] não mostra resultados ou mostra números inferiores aos esperados. Isso acontece quando o volume de dados que recebemos é tão grande que o trabalho de processamento de entrada não pode terminar de assimilar essas informações até o final do prazo de relatórios daquele dia.

Como resultado, esses dados são enviados tardiamente para o sistema do relatórios e não são exibidos no intervalo de 1 dia do relatórios usado para plotar o [!UICONTROL Trait Graph]. No entanto, você pode visualização esses dados nos intervalos de relatório de 7, 14, 30 e 60 dias em uma [Tendência](../reporting/trend-reports.md#trend-report-overview) ou Relatório [](../reporting/general-reports.md#general-reports-overview) Geral no dia seguinte.

<br> 

**Alguns segmentos estão ausentes em um[!UICONTROL Overlap]relatório. Onde eles estão?**

Para ajudar a reduzir a demanda computacional, esses relatórios omitem dados estatisticamente insignificantes dos resultados. Seus segmentos não estão faltando, eles são descartados porque não produzem resultados significativos ou pools úteis de usuários que você pode público alvo. Consulte também:

* [Metodologias de amostragem de relatórios e dados](../reporting/report-sampling.md)
* [Contagem de usuários únicos em sobreposição e relatórios](../reporting/unique-user-counts.md)gerais.

<br> 

**Se eu executar uma campanha de marketing por email, como posso determinar se os usuários redirecionados vêm para o meu site a partir dessa campanha ou de outras fontes?**

Anexe uma sequência de query específica da campanha ao URL da seção do site que você deseja monitorar. Em seguida, configure uma regra de característica para capturar essa variável. Por exemplo, se seu URL passar em uma ID de campanha como essa, `www.test123.com/electronics?campaign=123`crie uma regra de característica para capturar esses dados da `h_referer` variável com uma regra de característica que procura um cabeçalho como `h_referer = 'campaign=123'`).

<br> 

**Qual é a diferença entre a contagem de população de segmentos em tempo real e total?**

* **Tempo real:** O número de usuários únicos que fazem parte do segmento e estão ativos em suas propriedades durante um período de tempo definido (isto é, [!DNL Audience Manager] devem ter registrado a atividade desse usuário durante o período de tempo específico).

* **População total do segmento:** Um agregado de todos os usuários atualmente classificados nesse segmento.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**Eu tenho um segmento que consiste em apenas um traço. Quando eu olho para as métricas de Relatórios, suas contagens não correspondem. Por que isso ocorre?**

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

**I Inbound a file (Entrada de um arquivo) e o recibo de entrada mostra um número alto de registros processados com êxito, mas o relatórios mostra números muito menores. Por quê?**

No backend, os dados integrados são anexados somente aos usuários que ainda estão ativos no AAM (o usuário deve ter tido [!DNL DCS] atividade recente nos últimos 120 dias). Portanto, se os dados a bordo de usuários que já expiraram em [!DNL Audience Manager], [!UICONTROL Inbound] talvez informem que um determinado número de registros de usuários foram integrados, mas se esses usuários não tiverem tido nenhuma atividade recente, esses dados serão ignorados quando chegarem em nosso [!UICONTROL User Profile Store] relatórios.

<br> 

**Por que os únicos traços para meus traços integrados entre dispositivos são muito mais altos do que o número total de registros integrados?**

Se você estiver integrado em um arquivo para um provedor de dados entre dispositivos que ignorou a ID do cliente, o Audience Manager realizará uma pesquisa para obter todas as IDs de dispositivo associadas a cada uma das IDs de cliente integradas. Audience Manager, então, atribui as características integradas à ID do dispositivo associada à ID do cliente.

Por exemplo, suponha que você tenha integrado 100 registros. Para cada uma dessas IDs de cliente, em média, o AAM associou três IDs de dispositivo. Como resultado, a característica integrada é atribuída a 300 IDs de dispositivo.

Há dois motivos pelos quais uma única ID de cliente entre dispositivos pode ser associada a várias IDs de dispositivo:

* Os usuários estão fazendo logon na mesma conta entre dispositivos de vários computadores/navegadores.
* Os usuários estão limpando seus cookies. Observação: Os cookies &quot;abandonados&quot; são excluídos após 120 dias de inatividade do usuário.

<br> 

**Por que meus traços integrados são sempre 0?[!UICONTROL Total Trait Realizations]**

[!UICONTROL Total Trait Realizations] corresponde a cargas de página. [!UICONTROL Total Trait Realizations] forneça o número de vezes que um traço específico foi acionado em tempo real. Esse número é calculado somente para características com base em regras. Os traços integrados sempre são exibidos [!UICONTROL Total Trait Realizations] como 0.

<br> 

**Criei um traço e o[!UICONTROL Trait Graph]mostra um número maior de[!UICONTROL Unique Trait Realizations]que o[!UICONTROL Total Trait Population]. Isso é normal?**

Você está vendo isso porque [!UICONTROL Unique Trait Realizations] são métricas em tempo real, mas os trabalhos de relatórios que fazemos para calcular os resultados não [!UICONTROL Total Trait Population] são em tempo real. O tamanho [!UICONTROL Total Trait Population] deve ser maior do que o [!UICONTROL Unique Trait Realizations] em alguns dias.
