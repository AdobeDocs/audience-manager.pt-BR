---
description: Este artigo explica como as ferramentas de segmento e característica do Audience Manager usam as expressões Booleanas AND, OR e NOT.
seo-description: Este artigo explica como as ferramentas de segmento e característica do Audience Manager usam as expressões Booleanas AND, OR e NOT.
seo-title: Expressões booleanas no Construtor de traços e segmentos
solution: Audience Manager
title: Expressões booleanas no Construtor de traços e segmentos
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Expressões booleanas no Construtor de traços e segmentos{#boolean-expressions-in-trait-and-segment-builder}

Este artigo explica como as ferramentas de segmento e característica do Audience Manager usam as expressões Booleanas AND, OR e NOT.

<!-- 

c_tb_boolean.xml

 -->

**Expressões Booleanas**

A lógica booleana é uma ramificação de álgebra que usa algumas expressões básicas (ou operadores) para determinar se uma instrução é verdadeira ou falsa. Os operadores mais comuns são [!UICONTROL AND], [!UICONTROL OR]e [!UICONTROL NOT]. As combinações dessas expressões ajudam você a tornar as regras de qualificação de características ou segmentos focalizadas exclusivamente adequadas aos seus requisitos de dados. A ilustração a seguir mostra como as expressões Booleanas básicas funcionam.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>O operador [!UICONTROL NOT] usa uma condição "e" implícita e às vezes é gravada como [!UICONTROL AND NOT].

**Como usar expressões booleanas no Construtor de características e segmentos**

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
   <td colname="col2"> <p>Requisitos de qualificação de público-alvo restritos e focados. </p> </td> 
   <td colname="col3"> <p>Os usuários <i>devem</i> pertencer a todas as características ou segmentos especificados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OR</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos abrangentes e menos focalizados de qualificação de público-alvo. </p> </td> 
   <td colname="col3"> <p>Os usuários <i>podem</i> pertencer a quaisquer características ou segmentos especificados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NÃO</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de qualificação de público-alvo restritos e focados. </p> <p>Útil quando há várias condições que tornam difícil ou ineficiente definir os requisitos de qualificação do público-alvo. Ocasionalmente, é mais fácil validar em relação aos requisitos que excluem em vez de incluir. </p> </td> 
   <td colname="col3"> <p>Os usuários não <i></i> devem pertencer a um segmento ou característica excluído. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Exemplo de caso de uso**

O operador [!UICONTROL AND] é útil quando você enumerou facilmente os requisitos de associação de características. Por exemplo, digamos que você precisa criar um público de "compradores de câmeras caros". Com um modelo de pixel, seria necessário criar e colocar pixels para câmeras e um valor numérico de preço na página. Por outro lado, com características você pode aplicar operadores Booleanos para lidar com ambas as condições (preço das câmeras [!UICONTROL AND] ). O resultado é a coleta eficiente de dados com menos chamadas HTTP, o que, por sua vez, ajuda a preservar a experiência do usuário em seu site.

**[!UICONTROL OR]Exemplo de caso de uso**

O [!UICONTROL OR] operador é útil quando você deseja criar sinais com requisitos amplos de qualificação de público-alvo. Se você tiver vários requisitos de qualificação de características ou segmentos, o [!UICONTROL OR] operador avaliará como true quando os visitantes do site exibirem *qualquer* dessas características. [!UICONTROL OR] pode ser mais útil quando você deseja criar rapidamente um grande público-alvo de visitantes qualificados do site.

**[!UICONTROL AND NOT]Exemplo de caso de uso**

O [!UICONTROL AND NOT] operador é útil quando é mais fácil definir um público-alvo por *exclusão* em vez de *inclusão*. Por exemplo, digamos que você esteja realizando uma venda e queira segmentar os visitantes em clientes que visualizam somente itens de preço total. Em vez de criar uma lista de sinais para todos os itens qualificados de preço total ou de venda, pode ser mais fácil qualificar os visitantes se eles *não* tiverem visto um item de preço de venda. Isso é eficiente administrativamente porque você geralmente tem menos itens de preço de venda em comparação com aqueles oferecidos pelo preço total. Com um booliano [!UICONTROL NOT], os visitantes não *devem* exibir o sinal de venda para se qualificarem para associação de público-alvo de preço total. Por outro lado, [!UICONTROL AND NOT] é o oposto do caso de [!UICONTROL AND] uso, que mostra como a associação do público-alvo é determinada pela inclusão (ou seja, o visitante se qualificou com base em 2 sinais explicitamente declarados).

>[!MORE_LIKE_THIS]
>
>* [Trabalhar com operadores de comparação no TraitBuilder](../features/traits/trait-comparison-operators.md)
>* [Ordem de operações nas expressões do TraitBuilder](../features/traits/trait-operator-precedence.md)

