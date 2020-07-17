---
description: Este artigo explica como as ferramentas de segmento e característica Audience Manager usam expressões Booleanas E, OU e NÃO.
seo-description: Este artigo explica como as ferramentas de segmento e característica Audience Manager usam expressões Booleanas E, OU e NÃO.
seo-title: Expressões booleanas no Construtor de características e segmentos
solution: Audience Manager
title: Expressões booleanas no Construtor de características e segmentos
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 4%

---


# Expressões booleanas no Construtor de características e segmentos{#boolean-expressions-in-trait-and-segment-builder}

Este artigo explica como as ferramentas de segmento e característica Audience Manager usam expressões Booleanas E, OU e NÃO.

<!-- 

c_tb_boolean.xml

 -->

**Expressões booleanas**

A lógica booleana é uma ramificação de álgebra que usa algumas expressões básicas (ou operadores) para determinar se uma instrução é verdadeira ou falsa. Os operadores mais comuns são [!UICONTROL AND], [!UICONTROL OR]e [!UICONTROL NOT]. As combinações dessas expressões ajudam você a tornar as regras de qualificação de características ou segmentos focalizadas exclusivamente adequadas aos seus requisitos de dados. A ilustração a seguir mostra como as expressões Booleanas básicas funcionam.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>O operador [!UICONTROL NOT] usa uma condição &quot;e&quot; implícita e às vezes é gravada como [!UICONTROL AND NOT].

**Como usar Expressões booleanas no Construtor de características e segmentos**

Você cria regras de qualificação de características e segmentos com expressões booleanas. A tabela abaixo descreve as práticas recomendadas gerais para a criação de critérios de qualificação com [!UICONTROL AND], [!UICONTROL OR]e [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Expressão </th> 
   <th colname="col2" class="entry"> Use-o para criar </th> 
   <th colname="col3" class="entry"> Para qualificar </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> E</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de qualificação de audiências restritos e focados. </p> </td> 
   <td colname="col3"> <p>Os usuários <i>devem</i> pertencer a todas as características ou segmentos especificados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OU</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de qualificação de audiências amplos e menos focalizados. </p> </td> 
   <td colname="col3"> <p>Os usuários <i>podem</i> pertencer a quaisquer características ou segmentos especificados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NÃO</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de qualificação de audiências restritos e focados. </p> <p>Útil quando há várias condições que tornam difícil ou ineficiente definir os requisitos de qualificação da audiência. Ocasionalmente, é mais fácil validar em relação aos requisitos que excluem, em vez de incluir. </p> </td> 
   <td colname="col3"> <p>Os usuários não <i></i> devem pertencer a um segmento ou característica excluído. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Exemplo de caso de uso **

O operador [!UICONTROL AND] é útil quando você enumerou facilmente os requisitos de associação de características. Por exemplo, digamos que você precise criar uma audiência de &quot;compradores de câmeras caros&quot;. Com um modelo de pixel, seria necessário criar e colocar pixels para câmeras e um valor numérico de preço na página. Por outro lado, com características você pode aplicar operadores Booleanos para lidar com ambas as condições (preço das câmeras [!UICONTROL AND] ). O resultado é a coleta eficiente de dados com menos chamadas HTTP, o que, por sua vez, ajuda a preservar a experiência do usuário em seu site.

**[!UICONTROL OR]Exemplo de caso de uso **

O operador [!UICONTROL OR] é útil quando você deseja criar sinais com requisitos amplos de qualificação de audiência. Se você tiver vários requisitos de qualificação de características ou segmentos, o [!UICONTROL OR] operador avaliará como true quando os visitantes do site exibirem *qualquer* dessas características. [!UICONTROL OR] pode ser mais útil quando você deseja criar rapidamente uma ampla audiência de visitantes qualificados do site.

**[!UICONTROL AND NOT]Exemplo de caso de uso **

O operador [!UICONTROL AND NOT] é útil quando é mais fácil definir uma audiência por *exclusão* em vez de *inclusão*. Por exemplo, digamos que você esteja realizando uma venda e queira segmentar os visitantes em clientes que consideram somente os itens de preço total. Em vez de criar uma lista de sinais para todos os itens qualificados de preço total ou de venda, pode ser mais fácil qualificar os visitantes se eles *não* tiverem visto um item de preço de venda. Isso é eficiente administrativamente porque você geralmente tem menos itens de preço de venda em comparação com aqueles oferecidos pelo preço total. Com um booliano [!UICONTROL NOT], os visitantes não *devem* exibir o sinal de venda para se qualificar para associação de audiência de preço total. Por outro lado, [!UICONTROL AND NOT] é o oposto do caso de [!UICONTROL AND] utilização, que mostrou como a associação audiência é determinada pela inclusão (ou seja, o visitante qualificado com base em 2 sinais explicitamente declarados).

>[!MORELIKETHIS]
>
>* [Trabalhar com operadores de comparação no TraitBuilder](../features/traits/trait-comparison-operators.md)
>* [Ordem de operações nas Expressões do TraitBuilder](../features/traits/trait-operator-precedence.md)

