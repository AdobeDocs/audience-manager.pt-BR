---
description: Este artigo explica como as ferramentas de segmento e característica Audience Manager usam as expressões booleanas AND, OR e NOT.
seo-description: Este artigo explica como as ferramentas de segmento e característica Audience Manager usam as expressões booleanas AND, OR e NOT.
seo-title: Expressões booleanas no Construtor de características e segmentos
solution: Audience Manager
title: Expressões booleanas no Construtor de características e segmentos
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: 'Referência '
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 4%

---

# Expressões booleanas no Construtor de características e segmentos{#boolean-expressions-in-trait-and-segment-builder}

Este artigo explica como as ferramentas de segmento e característica Audience Manager usam as expressões booleanas AND, OR e NOT.

<!-- 

c_tb_boolean.xml

 -->

**Expressões booleanas**

A lógica booleana é uma ramificação de álgebra que usa algumas expressões básicas (ou operadores) para determinar se uma declaração é verdadeira ou falsa. Os operadores mais comuns são [!UICONTROL AND], [!UICONTROL OR] e [!UICONTROL NOT]. As combinações dessas expressões ajudam a tornar as regras de qualificação de características ou segmentos focalizadas adequadas aos seus requisitos de dados. A ilustração a seguir mostra como as expressões booleanas básicas funcionam.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>O operador [!UICONTROL NOT] usa uma condição &quot;e&quot; implícita e, às vezes, é gravada como [!UICONTROL AND NOT].

**Como usar expressões booleanas no Construtor de características e segmentos**

Você cria regras de qualificação de características e segmentos com expressões booleanas. A tabela abaixo descreve as práticas recomendadas gerais para criar critérios de qualificação com [!UICONTROL AND], [!UICONTROL OR] e [!UICONTROL NOT].

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
   <td colname="col2"> <p>Requisitos de qualificação de público-alvo restritos e focalizados. </p> </td> 
   <td colname="col3"> <p>Os usuários <i>devem</i> pertencer a todas as características ou segmentos especificados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OU</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de qualificação de público-alvo amplos e menos focalizados. </p> </td> 
   <td colname="col3"> <p>Os usuários <i>podem</i> pertencer a quaisquer características ou segmentos especificados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NÃO</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de qualificação de público-alvo restritos e focalizados. </p> <p>Útil quando há várias condições que tornam a definição dos requisitos de qualificação de público-alvo difícil ou ineficiente. Ocasionalmente, é mais fácil validar em relação aos requisitos que excluem em vez de incluir. </p> </td> 
   <td colname="col3"> <p>Os usuários <i>não devem</i> pertencer a uma característica ou segmento excluído. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Exemplo de caso de uso**

O operador [!UICONTROL AND] é útil quando você enumerou facilmente os requisitos de associação de características. Por exemplo, digamos que você precise criar um público-alvo de &quot;compradores de câmera caros&quot;. Com um modelo de pixel, seria necessário criar e colocar pixels para câmeras e um valor numérico de preço na página. Por outro lado, com características, você pode aplicar operadores booleanos para lidar com ambas as condições (câmeras [!UICONTROL AND] preço). O resultado é uma coleta de dados eficiente com menos chamadas HTTP, o que, por sua vez, ajuda a preservar a experiência do usuário em seu site.

**[!UICONTROL OR]Exemplo de caso de uso**

O operador [!UICONTROL OR] é útil quando você deseja criar sinais com requisitos amplos de qualificação de público-alvo. Se você tiver vários requisitos de qualificação de característica ou segmento, o operador [!UICONTROL OR] será avaliado como true quando os visitantes do site exibirem *qualquer* dessas características. [!UICONTROL OR] pode ser mais útil quando você deseja criar rapidamente um grande público-alvo de visitantes qualificados do site.

**[!UICONTROL AND NOT]Exemplo de caso de uso**

O operador [!UICONTROL AND NOT] é útil quando é mais fácil definir um público por *exclusão* em vez de *inclusion*. Por exemplo, digamos que você esteja fazendo uma venda e queira segmentar os visitantes em clientes que consideram somente itens de preço total. Em vez de criar uma lista de sinais para todos os itens de preço de venda ou totais qualificados, pode ser mais fácil qualificar os visitantes se eles tiverem *not* visto um item de preço de venda. Isso é administrativamente eficiente porque você geralmente tem menos itens de preço de venda em comparação com aqueles oferecidos a todo o preço. Com um booleano [!UICONTROL NOT], os visitantes *não devem* exibir o sinal de venda para se qualificarem para associação de público-alvo de preço total. Por outro lado, [!UICONTROL AND NOT] é o oposto do [!UICONTROL AND] caso de uso, que mostrou como a associação de público-alvo é determinada pela inclusão (ou seja, o visitante se qualificou com base em 2 sinais explicitamente declarados).

>[!MORELIKETHIS]
>
>* [Trabalhar com operadores de comparação no TraitBuilder](../features/traits/trait-comparison-operators.md)
* [Ordem de operações nas expressões do TraitBuilder](../features/traits/trait-operator-precedence.md)

