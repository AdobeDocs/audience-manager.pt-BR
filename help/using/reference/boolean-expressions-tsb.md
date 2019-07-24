---
description: Este artigo explica como as ferramentas de características e segmentos do Audience Manager usam as expressões Boolean E, OR, e NOT.
seo-description: Este artigo explica como as ferramentas de características e segmentos do Audience Manager usam as expressões Boolean E, OR, e NOT.
seo-title: Expressões booleanas em características e no construtor de segmentos
solution: Audience Manager
title: Expressões booleanas em características e no construtor de segmentos
uuid: 14 f 02 d 3 f -4 c 84-41 fe-bc 91-b 34 f 0 d 49574 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Boolean Expressions in Trait and Segment Builder{#boolean-expressions-in-trait-and-segment-builder}

Este artigo explica como as ferramentas de características e segmentos do Audience Manager usam as expressões Boolean E, OR, e NOT.

<!-- 

c_tb_boolean.xml

 -->

**Expressões booleanas**

Lógica booleana é uma ramificação de algebra que usa algumas expressões básicas (ou operadores) para determinar se uma declaração é verdadeira ou falsa. The most common operators are [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT]. As combinações dessas expressões ajudam você a fazer com que as regras de qualificação ou segmentação de segmentos se adaptem exclusivamente aos seus requisitos de dados. A ilustração a seguir mostra como as expressões Boolean básicas funcionam.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>[!UICONTROL NOT] O operador usa uma condição implícita "e" e é gravado como [!UICONTROL AND NOT].

**Como usar expressões booleanas em características e no construtor de segmentos**

Você cria regras de qualificação de características e segmentos com expressões Boolean. The table below describes general best practices for creating qualification criteria with [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Expressão </th> 
   <th colname="col2" class="entry"> Use-o para criar </th> 
   <th colname="col3" class="entry"> Para qualificar-se </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> E</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos restritos de qualificação do público-alvo. </p> </td> 
   <td colname="col3"> <p>Users <i>must</i> belong to all specified traits or segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OR</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de qualificação de público-alvo ampla e menos focados. </p> </td> 
   <td colname="col3"> <p>Users <i>can</i> belong to any specified traits or segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NÃO</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos restritos de qualificação do público-alvo. </p> <p>Útil quando há várias condições que tornam os requisitos de qualificação do público-alvo difíceis ou ineficientes. Ocasionalmente, é mais fácil validar os requisitos que excluem, em vez de incluir. </p> </td> 
   <td colname="col3"> <p>Users <i>must not</i> belong to an excluded trait or segment. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Exemplo de caso de uso**

[!UICONTROL AND] O operador é útil quando você tiver enumerado os requisitos de adesão de característica facilmente. Por exemplo, digamos que você precise criar um público de "caros compradores de câmera". » Com um modelo de pixel, é necessário criar e colocar pixels para câmeras e um valor de preço numérico na sua página. By contrast, with traits you can apply Boolean operators to handle both conditions (cameras [!UICONTROL AND] price). O resultado é uma coleção de dados eficiente com menos chamadas HTTP, que, por sua vez, ajuda a preservar a experiência do usuário em seu site.

**[!UICONTROL OR]Exemplo de caso de uso**

[!UICONTROL OR] O operador é útil quando você deseja criar sinais com amplos requisitos de qualificação de público-alvo. If you have several trait or segment qualification requirements, the [!UICONTROL OR] operator will evaluate to true when your site visitors exhibit *any* of those characteristics. [!UICONTROL OR] pode ser mais útil quando você quiser criar rapidamente um amplo público-alvo de visitantes qualificados do site.

**[!UICONTROL AND NOT]Exemplo de caso de uso**

[!UICONTROL AND NOT] O operador é útil quando é mais fácil definir um público por *exclusão* , em vez *de inclusão*. Por exemplo, digamos que você esteja fazendo uma venda e queira segmentar visitantes em clientes que visualizam apenas os itens de preço completo. Rather than create a list of signals for all qualifying full or sale-price items, it may be easier to qualify visitors if they have *not* seen a sale price item. Isso é administrativamente eficiente porque você geralmente tem menos itens de preço de venda comparados aos oferecidos pelo preço total. With a Boolean [!UICONTROL NOT], visitors *must not* exhibit the sale signal to qualify for full-price audience membership. By contrast, [!UICONTROL AND NOT] is the opposite of the [!UICONTROL AND] use case, which showed how audience membership is determined by inclusion (i.e., the visitor qualified based on 2 explicitly stated signals).

>[!MORE_ LIKE_ THIS]
>
>* [Trabalhar com operadores de comparação no traitbuilder](../features/traits/trait-comparison-operators.md)
>* [Ordem de operações nas expressões do traitbuilder](../features/traits/trait-operator-precedence.md)

