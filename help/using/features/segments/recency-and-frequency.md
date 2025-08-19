---
description: No Construtor de segmentos, a recenticidade e a frequência permitem segmentar visitantes com base em ações que ocorrem ou se repetem em um intervalo diário definido.
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: Recency and Frequency
solution: Audience Manager
title: Recenticidade e frequência
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 1%

---

# Recenticidade e frequência {#recency-and-frequency}

Em [!UICONTROL Segment Builder], a recenticidade e a frequência permitem segmentar visitantes com base em ações que ocorrem ou se repetem em um intervalo diário definido.

O Audience Manager define [!DNL recency] e [!DNL frequency] da seguinte maneira:

* **[!UICONTROL Recency]:** Quão recentemente um usuário visualizou ou se qualificou para um (ou mais) [!UICONTROL traits].
* **[!UICONTROL Frequency]:** A taxa na qual um usuário visualizou ou se qualificou para um (ou mais) [!UICONTROL traits].

As configurações de [!UICONTROL Recency] e [!UICONTROL Frequency] ajudam a segmentar os visitantes com base em seu nível real (ou percebido) de interesse em um site, seção ou criativo específico. Por exemplo, os usuários que se qualificam para um segmento com requisitos de alta recenticidade/frequência podem estar mais interessados em um site ou produto do que os usuários que visitam com menos frequência ou com menos frequência.

## Local das Configurações de [!UICONTROL Recency and Frequency] {#location}

Nas configurações [!UICONTROL Segment Builder], [!UICONTROL Recency] e [!UICONTROL Frequency] estão localizadas na seção [!UICONTROL Basic View] do painel [!UICONTROL Traits]. Clique no ícone do relógio para expor esses controles.

![](assets/recency_frequency.png)

## Limitações e regras {#limitations-rules}

Revise e entenda esses limites e regras quando quiser aplicar recenticidade e frequência às características em seus segmentos.

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
   <td colname="col2"> <p>A recenticidade deve ser maior que 0. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Tipos de características</b> </p> </td> 
   <td colname="col2"> <p>É possível aplicar controles de recenticidade somente a características de pastas e baseadas em regras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Características de terceiros</b> </p> </td> 
   <td colname="col2"> <p>Não é possível definir regras de recenticidade em características individuais de terceiros ou grupos de características que contenham características de terceiros. A recenticidade e a frequência se aplicam somente às suas próprias características. </p> </td> 
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
   <td colname="col2"> <p>É possível aplicar controles de frequência somente a características de pastas e baseadas em regras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Requisitos de recenticidade</b> </p> </td> 
   <td colname="col2"> <p>Você pode configurar os requisitos de frequência <i>sem</i> configurar os requisitos de recenticidade. Basta definir um valor de frequência e deixar o campo Recenticidade em branco. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regras de mesclagem de perfis</b> </p> </td> 
   <td colname="col2"> <p>Consulte <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Frequência da característica, gráficos de dispositivos externos e regras de mesclagem de perfis</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemplos de recenticidade {#recency-examples}

Veja dois exemplos de como a recenticidade funciona, dependendo da sua seleção na interface do usuário:

### Uso de um operador menor que ou igual a (&lt;=)

![Menor que ou igual a](assets/less-than-equal-to.png)

Neste exemplo, você seleciona o operador &lt;=, como mostrado na captura de tela. Isso qualifica seu usuário para o [!UICONTROL segment] se ele se qualificar para qualquer um dos três [!UICONTROL traits] pelo menos três vezes nos últimos cinco dias. A linha do tempo abaixo mostra a qualificação [!UICONTROL segment] no momento em que o [!UICONTROL segment] é criado, em 1º de outubro e dez dias depois.

![Últimos cinco dias](assets/last-5-days.png)

### Usando um operador maior que ou igual a (=>)

![Maior que-igual a](assets/greater-than-equal-to.png)

Neste exemplo, você seleciona o operador =>, como mostrado na captura de tela. Isso qualifica seu usuário para o [!UICONTROL segment] se ele se qualificar para qualquer um dos três [!UICONTROL traits] no mínimo três vezes a qualquer momento entre sua primeira qualificação na plataforma Audience Manager e o tempo limite de cinco dias atrás. A linha do tempo abaixo mostra a qualificação [!UICONTROL segment] no momento em que o [!UICONTROL segment] é criado, em 1º de outubro e dez dias depois.

![Qualificação anterior](assets/earlier-qualification.png)


## Exemplos de limite de frequência {#frequency-capping}

As expressões de limite de frequência incluem todos os usuários cujo número de [!UICONTROL trait] realizações esteja abaixo de um valor desejado. Estes são alguns exemplos certos e errados:

* Errado - A expressão `frequency([1000T]) <= 5` inclui todos os usuários que realizaram [!UICONTROL trait] com a ID &quot;1000&quot; no máximo cinco vezes, mas também inclui usuários que não realizaram [!UICONTROL trait]. Portanto, a Audience Manager não valida essa expressão por motivos de desempenho, pois qualificaria muitos usuários para o [!UICONTROL segment].

* Direita - Se você quiser incluir todos os usuários que perceberam o [!UICONTROL trait] com a ID &quot;1000&quot; no máximo cinco vezes, adicione outra condição à expressão para verificar se os usuários se qualificaram para o [!UICONTROL trait] pelo menos uma vez: `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* À direita - Quando você precisar que os requisitos de recenticidade/frequência sejam menores que um número específico de vezes ou dias, associe esse [!UICONTROL trait] a outro com um operador `AND`. Usando o exemplo no primeiro marcador, esta expressão se torna válida quando unida a outro [!UICONTROL trait], como mostrado aqui: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Certo - Para casos de uso de limite de frequência de publicidade, você pode criar uma regra de [!UICONTROL segment] semelhante a esta: `(frequency([1000T] <= 2D) >= 5)`. Esta expressão inclui todos os usuários que perceberam o [!UICONTROL trait] com a ID &quot;1000&quot; nos últimos 2 dias pelo menos cinco vezes. Defina o limite de frequência enviando este [!UICONTROL segment] para o servidor de publicidade com um `NOT` definido no [!UICONTROL segment] no servidor de publicidade. Esta abordagem obtém maior desempenho no [!DNL Audience Manager] e ainda atende à mesma finalidade para limite de frequência.

>[!MORELIKETHIS]
>
>* [Controles do Construtor de Segmentos: Seção de Características](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintaxe de código usada no Editor de expressão de segmentos](../../features/segments/segment-code-syntax.md)
