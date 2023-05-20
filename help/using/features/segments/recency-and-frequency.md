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
source-wordcount: '701'
ht-degree: 2%

---

# Recenticidade e frequência {#recency-and-frequency}

Entrada [!UICONTROL Segment Builder]A recenticidade e a frequência permitem segmentar visitantes com base em ações que ocorrem ou se repetem em um intervalo diário definido.

Audience Manager define [!DNL recency] e [!DNL frequency] do seguinte modo:

* **[!UICONTROL Recency]:** Quão recentemente um usuário visualizou ou se qualificou para um (ou mais) [!UICONTROL traits].
* **[!UICONTROL Frequency]:** A taxa na qual um usuário visualizou ou se qualificou para um (ou mais) [!UICONTROL traits].

[!UICONTROL Recency] e [!UICONTROL Frequency] As configurações do ajudam a segmentar os visitantes com base no nível real (ou percebido) de interesse em um site, seção ou criativo específico. Por exemplo, os usuários que se qualificam para um segmento com requisitos de alta recenticidade/frequência podem estar mais interessados em um site ou produto do que os usuários que visitam com menos frequência ou com menos frequência.

## Localização de [!UICONTROL Recency and Frequency] Configurações {#location}

Entrada [!UICONTROL Segment Builder], [!UICONTROL Recency] e [!UICONTROL Frequency] As configurações estão localizadas no [!UICONTROL Basic View] seção do [!UICONTROL Traits] painel. Clique no ícone do relógio para expor esses controles.

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
   <td colname="col2"> <p>Você pode configurar requisitos de frequência <i>sem</i> configuração de requisitos de recenticidade. Basta definir um valor de frequência e deixar o campo Recenticidade em branco. </p> </td> 
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

![Menor que-igual a](assets/less-than-equal-to.png)

Neste exemplo, você seleciona o operador &lt;=, como mostrado na captura de tela. Isso qualifica seu usuário para o [!UICONTROL segment] se se qualificarem para qualquer um dos três [!UICONTROL traits] três vezes, no mínimo, nos últimos cinco dias. A linha do tempo abaixo mostra o [!UICONTROL segment] qualificação no momento em que a [!UICONTROL segment] é criada, em 1º de outubro e dez dias depois.

![Últimos cinco dias](assets/last-5-days.png)

### Usando um operador maior que ou igual a (=>)

![Maior que ou igual a](assets/greater-than-equal-to.png)

Neste exemplo, você seleciona o operador =>, como mostrado na captura de tela. Isso qualifica seu usuário para o [!UICONTROL segment] se se qualificarem para qualquer um dos três [!UICONTROL traits] um mínimo de três vezes a qualquer momento entre a sua primeira qualificação na plataforma Audience Manager e o momento de corte cinco dias atrás. A linha do tempo abaixo mostra o [!UICONTROL segment] qualificação no momento em que a [!UICONTROL segment] é criada, em 1º de outubro e dez dias depois.

![Qualificação anterior](assets/earlier-qualification.png)


## Exemplos de limite de frequência {#frequency-capping}

As expressões de limite de frequência incluem todos os usuários [!UICONTROL trait] realizações está abaixo do valor desejado. Estes são alguns exemplos certos e errados:

* Errado - A expressão `frequency([1000T]) <= 5` inclui todos os usuários que perceberam a [!UICONTROL trait] com a ID &quot;1000&quot; no máximo cinco vezes, mas também inclui usuários que não perceberam a [!UICONTROL trait]. Portanto, o Audience Manager não valida essa expressão por motivos de desempenho, pois qualificaria muitos usuários para a variável [!UICONTROL segment].

* Certo - Se você quiser incluir todos os usuários que perceberam a [!UICONTROL trait] com a ID &quot;1000&quot; no máximo cinco vezes, adicione outra condição à expressão para verificar se os usuários se qualificaram para a [!UICONTROL trait] pelo menos uma vez:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Certo - Quando você precisar que os requisitos de recenticidade/frequência sejam menores que um número específico de vezes ou dias, associe-se a esse [!UICONTROL trait] para outro com um `AND` operador. Usando o exemplo no primeiro marcador, essa expressão se torna válida quando unida a outra [!UICONTROL trait] como mostrado aqui: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Certo - Para casos de uso de limite de frequência de publicidade, você pode criar um [!UICONTROL segment] regra semelhante a esta: `(frequency([1000T] <= 2D) >= 5)`. Essa expressão inclui todos os usuários que perceberam a [!UICONTROL trait] com a ID &quot;1000&quot; nos últimos 2 dias pelo menos cinco vezes. Definir limite de frequência enviando este [!UICONTROL segment] ao servidor de publicidade com uma `NOT` definido no [!UICONTROL segment] no servidor de publicidade. Essa abordagem obtém maior desempenho em [!DNL Audience Manager] ao mesmo tempo que serve o mesmo propósito para o limite de frequência.

>[!MORELIKETHIS]
>
>* [Controles do Construtor de segmentos: seção Características](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintaxe de código usada no Editor de expressão de segmentos](../../features/segments/segment-code-syntax.md)

