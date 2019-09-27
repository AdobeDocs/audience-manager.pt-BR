---
description: No Construtor de segmentos, a recente e a frequência permitem segmentar os visitantes com base em ações que ocorrem ou se repetem em um intervalo diário definido.
seo-description: No Construtor de segmentos, a recente e a frequência permitem segmentar os visitantes com base em ações que ocorrem ou se repetem em um intervalo diário definido.
seo-title: Idade e frequência
solution: Audience Manager
title: Idade e frequência
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: 1cbff10b9e978755e139e7d5b996249de5ebb5bd

---


# Recency and Frequency {#recency-and-frequency}

Em [!UICONTROL Segment Builder], a recenticidade e a frequência permitem segmentar os visitantes com base em ações que ocorrem ou se repetem em um intervalo diário definido.

O Audience Manager define [!DNL recency] e [!DNL frequency] como:

* **[!UICONTROL Recency]** : Recentemente, um usuário visualizou ou se qualificou para uma (ou mais) característica.
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
   <td colname="col1"> <p> <b>Tipos de características</b> </p> </td> 
   <td colname="col2"> <p>Você pode aplicar controles de recenticidade somente a características com base em regras e pastas. </p> </td> 
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
   <td colname="col2"> <p>You cannot set frequency rules on individual third-party traits or trait groups that contain third-party traits. Recency and frequency applies to your own traits only. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tipos de características</b> </p> </td> 
   <td colname="col2"> <p>You can apply frequency controls to rule-based and folder traits only. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Recency Requirements</b> </p> </td> 
   <td colname="col2"> <p>You can configure frequency requirements without configuring recency requirements. <i></i> Just set a frequency value and leave the recency field blank. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Profile Merge Rules</b> </p> </td> 
   <td colname="col2"> <p>See  Trait Frequency, External Device Graphs, and Profile Merge Rules.<a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"></a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Recency Examples {#recency-examples}

Here are two examples of how recency works, depending on your selection in the UI:

### Using a less than or equal to operator (&lt;=)

![Less-than-equal-to](assets/less-than-equal-to.png)

In this example, you select the &lt;= operator, as shown in the screenshot. This qualifies your user for the segment if they qualify for any of the three traits a minimum of three times within the last five days. A linha do tempo abaixo mostra a qualificação do segmento no momento em que o segmento é criado, em 1º de outubro e dez dias depois.

![Last-five-days](assets/last-5-days.png)

### Usando um operador maior que ou igual a (=&gt;)

![Maior que igual a](assets/greater-than-equal-to.png)

Neste exemplo, você seleciona o operador =&gt;, como mostrado na captura de tela. Isso qualifica seu usuário para o segmento se ele se qualificar para qualquer uma das três características pelo menos três vezes a qualquer momento entre sua primeira qualificação na plataforma Audience Manager e o tempo limite cinco dias atrás. A linha do tempo abaixo mostra a qualificação do segmento no momento em que o segmento é criado, em 1º de outubro e dez dias depois.

![Qualificação anterior](assets/earlier-qualification.png)


## Exemplos de limite de frequência {#frequency-capping}

As expressões de limite de frequência incluem todos os usuários cujo número de realizações de características está abaixo de um valor desejado. Estes são alguns exemplos de Right e Wrong:

* Errado - A expressão `frequency([1000T]) <= 5` inclui todos os usuários que perceberam a característica com a ID "1000" no máximo cinco vezes, mas também inclui usuários que não perceberam a característica. Portanto, o Audience Manager não valida essa expressão por motivos de desempenho, pois qualificaria muitos usuários para o segmento.

* Direita - Se você quiser incluir todos os usuários que tiverem realizado a característica com a ID "1000" no máximo cinco vezes, adicione outra condição à expressão, para garantir que os usuários tenham se qualificado para a característica pelo menos uma vez:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Direita - quando você precisa que os requisitos de recenticidade/frequência sejam menores que um número específico de vezes ou dias, associe essa característica a outra com um `AND` operador. Usando o exemplo no primeiro ponto, essa expressão se torna válida quando unida a outra característica, como mostrado aqui: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Direita - Para casos de uso de limite de frequência de publicidade, é possível criar uma regra de segmento semelhante a esta: `(frequency([1000T] <= 2D) >= 5)`. Essa expressão inclui todos os usuários que perceberam a característica com a ID "1000" nos últimos 2 dias pelo menos cinco vezes. Defina o limite de frequência enviando esse segmento para o servidor de publicidade com um `NOT` conjunto definido no segmento no servidor de publicidade. Essa abordagem atinge um desempenho maior em [!DNL Audience Manager] simultâneo com o mesmo propósito para o limite de frequência.

>[!MORE_LIKE_THIS]
>
>* [Controles do Construtor de segmentos: Seção Características](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintaxe de código usada no Editor de expressão de segmento](../../features/segments/segment-code-syntax.md)

