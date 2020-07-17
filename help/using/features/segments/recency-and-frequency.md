---
description: No Construtor de segmentos, a recenticidade e a frequência permitem segmentar visitantes com base em ações que ocorrem ou se repetem em um intervalo diário definido.
seo-description: No Construtor de segmentos, a recenticidade e a frequência permitem segmentar visitantes com base em ações que ocorrem ou se repetem em um intervalo diário definido.
seo-title: Recenticidade e frequência
solution: Audience Manager
title: Recenticidade e frequência
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 3%

---


# Recenticidade e frequência {#recency-and-frequency}

Em [!UICONTROL Segment Builder], a recenticidade e a frequência permitem segmentar visitantes com base em ações que ocorrem ou se repetem em um intervalo diário definido.

Audience Manager define [!DNL recency] e [!DNL frequency] como segue:

* **[!UICONTROL Recency]:**Recentemente, um usuário visualizou ou qualificou-se para um (ou mais)[!UICONTROL traits].
* **[!UICONTROL Frequency]:**A taxa na qual um usuário visualizou ou se qualificou para um (ou mais)[!UICONTROL traits].

[!UICONTROL Recency] e [!UICONTROL Frequency] as configurações ajudam a segmentar visitantes com base em seu nível de interesse real (ou percebido) em um site, seção ou criação específica. Por exemplo, os usuários que se qualificam para um segmento com requisitos de alta recenticidade/frequência podem estar mais interessados em um site ou produto do que os usuários que visitam com menos frequência ou com menos frequência.

## Localização das [!UICONTROL Recency and Frequency] configurações {#location}

As configurações [!UICONTROL Segment Builder], [!UICONTROL Recency] e [!UICONTROL Frequency] estão localizadas na [!UICONTROL Basic View] seção do [!UICONTROL Traits] painel. Clique no ícone de relógio para expor esses controles.

![](assets/recency_frequency.png)

## Limitações e regras {#limitations-rules}

Analise e entenda esses limites e regras quando quiser aplicar recenticidade e frequência às características em seus segmentos.

### [!UICONTROL Recency] {#recency}

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

### [!UICONTROL Frequency] {#frequency}

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
   <td colname="col1"> <p> <b>Tipos de características</b> </p> </td> 
   <td colname="col2"> <p>Você pode aplicar controles de frequência somente a características com base em regras e pastas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Requisitos de recenticidade</b> </p> </td> 
   <td colname="col2"> <p>Você pode configurar os requisitos de frequência <i>sem</i> configurar os requisitos de recenticidade. Basta definir um valor de frequência e deixar o campo de recenticidade em branco. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regras de mesclagem de perfis</b> </p> </td> 
   <td colname="col2"> <p>See <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Trait Frequency, External Device Graphs, and Profile Merge Rules</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemplos de recenticidade {#recency-examples}

Estes são dois exemplos de como a atualização funciona, dependendo de sua seleção na interface do usuário:

### Usando um operador menor que ou igual a (&lt;=)

![Menor que igual a](assets/less-than-equal-to.png)

Neste exemplo, você seleciona o operador &lt;=, como mostrado na captura de tela. Isso qualifica seu usuário para o [!UICONTROL segment] caso ele se qualifice para qualquer uma das três [!UICONTROL traits] pelo menos três vezes nos últimos cinco dias. A linha do tempo abaixo mostra a [!UICONTROL segment] qualificação no momento em que [!UICONTROL segment] é criada, em 1º de outubro e dez dias depois.

![Últimos cinco dias](assets/last-5-days.png)

### Usando um operador maior que ou igual a (=>)

![Maior que igual a](assets/greater-than-equal-to.png)

Neste exemplo, você seleciona o operador =>, como mostrado na captura de tela. Isso qualifica seu usuário para o [!UICONTROL segment] caso ele se qualifice para qualquer uma das três [!UICONTROL traits] pelo menos três vezes a qualquer momento entre sua primeira qualificação na plataforma do Audience Manager e o tempo de interrupção cinco dias atrás. A linha do tempo abaixo mostra a [!UICONTROL segment] qualificação no momento em que [!UICONTROL segment] é criada, em 1º de outubro e dez dias depois.

![Qualificação anterior](assets/earlier-qualification.png)


## Exemplos de limite de frequência {#frequency-capping}

As expressões de limite de frequência incluem todos os usuários cujo número de [!UICONTROL trait] realizações está abaixo de um valor desejado. Estes são alguns exemplos de Right e Wrong:

* Errado - A expressão `frequency([1000T]) <= 5` inclui todos os usuários que perceberam o evento com a ID &quot;1000&quot; no máximo cinco vezes, mas também os usuários que não perceberam o evento [!UICONTROL trait] [!UICONTROL trait]. Portanto, o Audience Manager não valida essa expressão por motivos de desempenho, pois qualificaria muitos usuários para o [!UICONTROL segment].

* Direita - Se você quiser incluir todos os usuários que perceberam o evento com a ID &quot;1000&quot; no máximo cinco vezes, adicione outra condição à expressão, para garantir que os usuários tenham se qualificado para o [!UICONTROL trait] [!UICONTROL trait] pelo menos uma vez:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Direita - Quando você precisar que os requisitos de recenticidade/frequência sejam menores que um número específico de vezes ou dias, associe isso [!UICONTROL trait] `AND` a outro operador. Usando o exemplo no primeiro ponto, essa expressão se torna válida quando unida a outra, [!UICONTROL trait] como mostrado aqui: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Direita - Para casos de uso de limite de frequência de publicidade, é possível criar uma [!UICONTROL segment] regra semelhante a esta: `(frequency([1000T] <= 2D) >= 5)`. Essa expressão inclui todos os usuários que perceberam o evento com a ID &quot;1000&quot; nos últimos 2 dias, pelo menos cinco vezes. [!UICONTROL trait] Defina o limite de frequência enviando-o [!UICONTROL segment] para o servidor de publicidade com um `NOT` conjunto no servidor de publicidade [!UICONTROL segment] . Essa abordagem atinge um desempenho maior em [!DNL Audience Manager] simultâneo com o mesmo propósito para o limite de frequência.

>[!MORELIKETHIS]
>
>* [Controles do Construtor de segmentos: Seção Características](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintaxe de código usada no Editor de expressão de segmentos](../../features/segments/segment-code-syntax.md)

