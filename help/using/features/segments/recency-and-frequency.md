---
description: No Construtor de segmentos, a recenticidade e a frequência permitem que você segmente os visitantes com base em ações que ocorrem ou se repetem por um intervalo diário.
seo-description: No Construtor de segmentos, a recenticidade e a frequência permitem que você segmente os visitantes com base em ações que ocorrem ou se repetem por um intervalo diário.
seo-title: Recenticidade e frequência
solution: Audience Manager
title: Recenticidade e frequência
uuid: faadd 18 a-bf 27-4 b 73-995 e -9809 f 52 f 5350
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Recency and Frequency {#recency-and-frequency}

In [!UICONTROL Segment Builder], recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.

Audience Manager defines [!DNL recency] and [!DNL frequency] as follows:

* **[!UICONTROL Recency]:** O número de dias durante os quais um usuário visualizou ou está qualificado para uma ou mais características.
* **[!UICONTROL Frequency]:** A taxa na qual um usuário visualizou ou está qualificado para uma ou mais características.

[!UICONTROL Recency] e [!UICONTROL Frequency] as configurações ajudam você a segmentar os visitantes com base em seu nível real (ou percebido) de interesse em um site, seção ou criação específica. Por exemplo, os usuários qualificados para um segmento com requisitos altos de recenticidade/frequência podem estar mais interessados em um site ou produto que os usuários que visitam com menos frequência ou com menos frequência.

## Location of Recency and Frequency Settings {#location}

In [!UICONTROL Segment Builder], [!UICONTROL Recency] and [!UICONTROL Frequency] settings are located in the [!UICONTROL Basic View] section of the [!UICONTROL Traits] panel. Clique no ícone de relógio para expor esses controles.

![](assets/recency_frequency.png)

## Limitations and Rules {#limitations-rules}

Analise e entenda esses limites e regras quando quiser aplicar recenticidade e frequência a características em seus segmentos.

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
   <td colname="col2"> <p>A idade deve ser maior que 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Características de terceiros</b> </p> </td> 
   <td colname="col2"> <p>Não é possível definir regras de recenticidade em grupos de características ou características de terceiros individuais que contenham características de terceiros. A atualidade e frequência se aplicam somente aos seus próprios traços. </p> </td> 
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
   <td colname="col2"> <p>Não é possível definir regras de frequência em características de terceiros ou grupos de características de terceiros que contenham características de terceiros. A atualidade e frequência se aplicam somente aos seus próprios traços. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Requisitos de idade</b> </p> </td> 
   <td colname="col2"> <p>You can configure frequency requirements <i>without</i> configuring recency requirements. Basta definir um valor de frequência e deixar o campo de tempo decorrido em branco. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regras de mesclagem de perfil</b> </p> </td> 
   <td colname="col2"> <p>See <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Trait Frequency, External Device Graphs, and Profile Merge Rules</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Frequency Capping Examples {#frequency-capping}

Expressões de limite de frequência incluem todos os usuários cujo número de experiências de característica está abaixo do valor desejado. Estes são alguns exemplos:

* The expression `frequency([1000T]) <= 5` includes all users that have realized the trait with the ID "1000" a maximum of five times, including users who have not realized the trait.
* When you need recency/frequency requirements to be less than a specific number of times or days, join that trait to another with an `AND` operator. Using the example above, this expression becomes valid when joined with another trait as shown here: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* For advertising frequency-capping use cases, you could create a segment rule similar to this: `(frequency([1000T] <= 2D) >= 5)`. Essa expressão inclui todos os usuários que viram a característica com a ID "1000" nos últimos 2 dias pelo menos cinco vezes. Set frequency capping by sending this segment to the ad server with a `NOT` set on the segment in the ad server. This approach achieves greater performance in [!DNL Audience Manager] while still serving the same purpose for frequency capping.

>[!MORE_ LIKE_ THIS]
>
>* [Controles do Construtor de segmento: Seção de características](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintaxe de código usada no Editor de expressões de segmento](../../features/segments/segment-code-syntax.md)

