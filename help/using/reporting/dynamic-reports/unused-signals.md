---
description: Este relatório retorna uma contagem de frequência de todas as informações não utilizadas coletadas no inventário e enviadas para o Audience Manager.
seo-description: Este relatório retorna uma contagem de frequência de todas as informações não utilizadas coletadas no inventário e enviadas para o Audience Manager.
seo-title: Relatório de sinais não usados
solution: Audience Manager
title: Relatório de sinais não usados
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 2%

---


# Relatório de sinais não usados{#unused-signals-report}

Este relatório retorna uma contagem de frequência de todas as informações não utilizadas coletadas no inventário e enviadas para o Audience Manager. Para acessar esse relatório, navegue até **Analytics > Relatórios de Audiência > Outros relatórios > Sinais** não usados.

>[!NOTE]
>
>Se aparecer a mensagem &quot;Você não tem acesso aos Relatórios de Audiência&quot;, entre em contato com seu consultor de Audience Manager ou com o Atendimento ao cliente para fornecer o relatório.

![Captura de tela do Relatório de Sinais não usados](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## Visão geral

Um sinal é a informação transmitida pelo seu sítio Web [!DNL Audience Manager] sob a forma de pares [](../../reference/key-value-pairs-explained.md) chave-valor (por exemplo, `color=blue, price>100, gender=female`, etc.).

Os sinais não utilizados consistem em dados que você coleta, mas que não foram mapeados para um traço. O [!UICONTROL Unused Signals] relatório mostra os dados em uma tabela por data, chave, valor e contagem de frequência. Qualquer sinal não mapeado passado para pelo [!DNL Audience Manager] menos 100 vezes por dia se qualifica para o [!UICONTROL Unused Signals] relatório.

Revise este relatório para ajudar a identificar sinais órfãos que podem ser mapeados para características novas ou existentes.

>[!NOTE]
>
>Especifique um nome de chave ou valor nos campos de pesquisa para limitar os resultados a registros específicos.

## Casos de uso

<table id="table_E5EE0EC078E14EF4B197243488517A2D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemplos </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Garanta a uniformidade da característica ou adicione valores relacionados a uma única chave</b> </p> </td> 
   <td colname="col2"> <p>Revise o relatório para considerar variações de valor diferentes para um sinal específico. </p> <p>Por exemplo, digamos que você tenha uma característica para o estado "Carolina do Norte" definida em um par chave-valor como <code> c_state = North Carolina</code>. O relatório pode ajudá-lo a encontrar variantes de nomes e adicioná-las à característica (por exemplo, <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Como alternativa, você pode detectar variantes de nome no relatório e substituí-las por um valor uniforme em todos os sites. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Criar novas características</b> </p> </td> 
   <td colname="col2"> <p>Revise o relatório para ver quais novos valores são passados em uma chave específica. Talvez você queira criar novos pares de valores chave com base nesses novos valores. </p> <p> <p>Observação:  Verifique o relatório quinzenalmente para obter valores que mudam frequentemente (por exemplo, shows, campanhas, celebridades etc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Localizar Valores Não Mapeados</b> </p> </td> 
   <td colname="col2"> <p>Revise o relatório para o número 1. O número 1 em um relatório de Sinais <span class="wintitle"></span> não usados representa um valor nulo. Isso não é necessariamente ruim. Isso simplesmente significa que uma chave específica não tem um mapeamento de valor associado. Quando você vir vários 1 valores para uma variável importante, verifique com a equipe do site para certificar-se de que todas as páginas estão marcadas corretamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Práticas recomendadas

Execute e verifique o [!UICONTROL Unused Signals] relatório:

* Depois de criar uma característica ou atualizar regras de característica. Isso ajuda a garantir que suas características e regras sejam configuradas corretamente. O número 1 nos resultados indica que uma nova característica pode não estar configurada corretamente.
* Semanalmente ou mensalmente. As revisões programadas ajudam a garantir que os mapeamentos de características estejam atualizados.

>[!NOTE]
>
>Ao pesquisar valores não utilizados no relatório, considere a seguinte particularidade. Há uma diferença na expressão entre os dois exemplos abaixo:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Ambos os exemplos mostram uma característica que contém dois pares de valores chave v e a. A primeira expressão se traduz em: a característica contém a tecla v com o valor 1 [!UICONTROL AND NOT] a tecla com o valor 23. A segunda expressão contém a tecla v com o valor 1 e [!UICONTROL AND] a tecla a com o valor [!UICONTROL NOT EQUAL] 23.
* Considerando as duas expressões diferentes acima, digamos que você pesquise nos valores [!UICONTROL Unused Signals Report] que são passados para a chave com qualquer valor diferente de 23, você só obterá resultados no primeiro caso porque os valores para a chave não foram enviados PARA TODAS. No segundo caso, valores diferentes de 23 foram enviados, de modo que a tecla a não é usada.

## Criação de características em massa

Entre em contato com seu representante de Soluções de Parceiro se precisar criar em massa muitas características com base nos dados obtidos do [!UICONTROL Unused Signals] relatório.
