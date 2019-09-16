---
description: No Construtor de segmentos, a recente e a frequência permitem segmentar os visitantes com base em ações que ocorrem ou se repetem em um intervalo diário definido.
seo-description: No Construtor de segmentos, a recente e a frequência permitem segmentar os visitantes com base em ações que ocorrem ou se repetem em um intervalo diário definido.
seo-title: Idade e frequência
solution: Audience Manager
title: Idade e frequência
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Recency and Frequency {#recency-and-frequency}

Em [!UICONTROL Segment Builder], a recenticidade e a frequência permitem segmentar os visitantes com base em ações que ocorrem ou se repetem em um intervalo diário definido.

O Audience Manager define [!DNL recency] e [!DNL frequency] como:

* **[!UICONTROL Recency]** : O número de dias durante os quais um usuário visualizou ou se qualificou para uma (ou mais) característica.
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
   <td colname="col1"> <p><b>Regras de mesclagem de perfil</b> </p> </td> 
   <td colname="col2"> <p>Consulte <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Frequência de características, Gráficos de dispositivos externos e Regras</a>de mesclagem de perfis. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemplos de limite de frequência {#frequency-capping}

As expressões de limite de frequência incluem todos os usuários cujo número de realizações de características está abaixo de um valor desejado. Estes são alguns exemplos:

* A expressão `frequency([1000T]) <= 5` inclui todos os usuários que perceberam a característica com a ID "1000" no máximo cinco vezes, incluindo usuários que não perceberam a característica.
* Quando você precisar que os requisitos de recenticidade/frequência sejam menores que um número específico de vezes ou dias, associe essa característica a outra com um `AND` operador. Usando o exemplo acima, essa expressão se torna válida quando unida a outra característica, como mostrado aqui: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Para casos de uso de limite de frequência de publicidade, é possível criar uma regra de segmento semelhante a esta: `(frequency([1000T] <= 2D) >= 5)`. Essa expressão inclui todos os usuários que perceberam a característica com a ID "1000" nos últimos 2 dias pelo menos cinco vezes. Defina o limite de frequência enviando esse segmento para o servidor de publicidade com um `NOT` conjunto definido no segmento no servidor de publicidade. Essa abordagem atinge um desempenho maior em [!DNL Audience Manager] simultâneo com o mesmo propósito para o limite de frequência.

>[!MORE_LIKE_THIS]
>
>* [Controles do Construtor de segmentos: Seção Características](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintaxe de código usada no Editor de expressão de segmento](../../features/segments/segment-code-syntax.md)

