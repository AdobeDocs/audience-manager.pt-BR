---
description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: Idade e frequência
solution: Audience Manager
title: Idade e frequência
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: c7e8b67ccad4479487b471668462937c5be6be34

---


# Recency and Frequency {#recency-and-frequency}

In [!UICONTROL Segment Builder], recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.

O Audience Manager define [!DNL recency] e [!DNL frequency] como:

* **[!UICONTROL Recency]** : How recently a user viewed or qualified for one (or more) traits.
* **[!UICONTROL Frequency]** : A taxa na qual um usuário visualizou ou se qualificou para uma (ou mais) características.

[!UICONTROL Recency] e [!UICONTROL Frequency] as configurações ajudam a segmentar os visitantes com base em seu nível de interesse real (ou percebido) em um site, seção ou criação específica. Por exemplo, os usuários que se qualificam para um segmento com requisitos de alta recenticidade/frequência podem estar mais interessados em um site ou produto do que os usuários que visitam com menos frequência ou com menos frequência.

## Localização das configurações de recente e frequência {#location}

As configurações [!UICONTROL Segment Builder], [!UICONTROL Recency] e [!UICONTROL Frequency] estão localizadas na [!UICONTROL Basic View] seção do [!UICONTROL Traits] painel. Clique no ícone de relógio para expor esses controles.

![](assets/recency_frequency.png)

## Limitações e regras {#limitations-rules}

Analise e entenda esses limites e regras quando quiser aplicar recenticidade e frequência às características em seus segmentos.

### Recenticidade

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limite ou regra </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Valor Mínimo</b> </p> </td> 
   <td colname="col2"> <p>A Idade deve ser maior que 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Características de terceiros</b> </p> </td> 
   <td colname="col2"> <p>Não é possível definir regras de recenticidade em características de terceiros individuais ou grupos de características que contenham características de terceiros. A recenticidade e a frequência se aplicam somente às suas próprias características. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Frequência

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limite ou regra </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Características de terceiros</b> </p> </td> 
   <td colname="col2"> <p>Não é possível definir regras de frequência em características individuais de terceiros ou grupos de características que contenham características de terceiros. A recenticidade e a frequência se aplicam somente às suas próprias características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Requisitos de recenticidade</b> </p> </td> 
   <td colname="col2"> <p>Você pode configurar os requisitos de frequência <i>sem</i> configurar os requisitos de recenticidade. Basta definir um valor de frequência e deixar o campo de recenticidade em branco. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Profile Merge Rules</b> </p> </td> 
   <td colname="col2"> <p>Consulte <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Frequência de características, Gráficos de dispositivos externos e Regras</a>de mesclagem de perfis. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemplos de recenticidade {#recency-examples}

Estes são dois exemplos de como a atualização funciona, dependendo de sua seleção na interface do usuário:

### Usando um operador menor que ou igual a (&lt;=)

![Menor que igual a](assets/less-than-equal-to.png)

Neste exemplo, você seleciona o operador &lt;=, como mostrado na captura de tela. Isso qualifica o usuário para o segmento se ele se qualificar para qualquer uma das três características pelo menos três vezes nos últimos cinco dias. A linha do tempo abaixo mostra a qualificação do segmento no momento em que o segmento é criado, em 1º de outubro e dez dias depois.

![Últimos cinco dias](assets/last-5-days.png)

### Using a greater than or equal to operator (=&gt;)

![Greater-than-equal-to](assets/greater-than-equal-to.png)

In this example, you select the =&gt; operator, as shown in the screenshot. This qualifies your user for the segment if they qualify for any of the three traits a minimum of three times anytime between their first qualification on the Audience Manager platform and the cut-off time five days ago. The timeline below shows the segment qualification at the time the segment is created, on October 1st, and ten days later.

![Earlier-qualification](assets/earlier-qualification.png)


## Frequency Capping Examples {#frequency-capping}

Frequency-capping expressions include all the users whose number of trait realizations is below a desired value. Here are a few examples:

* The expression  includes all users that have realized the trait with the ID "1000" a maximum of five times, including users who have not realized the trait.`frequency([1000T]) <= 5`
* When you need recency/frequency requirements to be less than a specific number of times or days, join that trait to another with an  operator. `AND` Using the example above, this expression becomes valid when joined with another trait as shown here: .`frequency([1000T]) <= 5 AND isSiteVisitorTrait`

* Para casos de uso de limite de frequência de publicidade, é possível criar uma regra de segmento semelhante a esta: `(frequency([1000T] <= 2D) >= 5)`. Essa expressão inclui todos os usuários que perceberam a característica com a ID "1000" nos últimos 2 dias pelo menos cinco vezes. Set frequency capping by sending this segment to the ad server with a  set on the segment in the ad server. `NOT` This approach achieves greater performance in  while still serving the same purpose for frequency capping.[!DNL Audience Manager]

>[!MORE_LIKE_THIS]
>
>* [Controles do Construtor de segmentos: Seção Características](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintaxe de código usada no Editor de expressão de segmento](../../features/segments/segment-code-syntax.md)

