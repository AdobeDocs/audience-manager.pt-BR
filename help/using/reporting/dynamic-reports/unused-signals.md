---
description: Este relatório retorna uma contagem de frequência de todas as informações não utilizadas coletadas no inventário e enviadas para o Audience Manager.
seo-description: Este relatório retorna uma contagem de frequência de todas as informações não utilizadas coletadas no inventário e enviadas para o Audience Manager.
seo-title: Relatório de sinais não usados
solution: Audience Manager
title: Relatório de sinais não usados
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: Relatórios de sobreposição
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 2%

---

# Relatório de sinais não usados{#unused-signals-report}

Este relatório retorna uma contagem de frequência de todas as informações não utilizadas coletadas no inventário e enviadas para o Audience Manager. Para acessar esse relatório, navegue até **Analytics > Relatórios de público-alvo > Outros relatórios > Sinais não usados**.

>[!NOTE]
>
>Caso veja a mensagem &quot;Você não tem acesso aos Relatórios de público-alvo&quot;, entre em contato com o consultor da Audience Manager ou com o Atendimento ao cliente para fornecer o relatório.

![Captura de tela do Relatório de sinais não usados](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## Visão geral

Um sinal é a informação do seu site transmitida para [!DNL Audience Manager] na forma de [pares de valores chave](../../reference/key-value-pairs-explained.md) (por exemplo, `color=blue, price>100, gender=female`, etc.).

Os sinais não usados consistem em dados coletados, mas não mapeados para uma característica. O relatório [!UICONTROL Unused Signals] mostra os dados em uma tabela por data, chave, valor e contagem de frequência. Qualquer sinal não mapeado transmitido para [!DNL Audience Manager] pelo menos 100 vezes em um dia se qualifica para o relatório [!UICONTROL Unused Signals].

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
   <td colname="col1"> <p><b>Garantir a uniformidade das características ou adicionar valores relacionados a uma única chave</b> </p> </td> 
   <td colname="col2"> <p>Revise o relatório para considerar variações de valor diferentes para um sinal específico. </p> <p>Por exemplo, digamos que você tenha uma característica para o estado "Carolina do Norte" definida em um par de valores chave como <code> c_state = North Carolina</code>. O relatório pode ajudá-lo a encontrar variantes de nome e adicioná-las à característica (por exemplo, <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Como alternativa, você pode observar as variantes de nome no relatório e substituí-las por um valor uniforme em todos os sites. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Criar novas características</b> </p> </td> 
   <td colname="col2"> <p>Revise o relatório para ver quais novos valores são passados em uma chave específica. Você pode criar novos pares de valores chave com base nesses novos valores. </p> <p> <p>Observação:  Verifique o relatório quinzenalmente para ver se há valores que mudam com frequência (por exemplo, programas, campanhas, celebridades etc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Localizar Valores Não Mapeados</b> </p> </td> 
   <td colname="col2"> <p>Revise o relatório para o número 1. O número 1 em um relatório <span class="wintitle"> Sinais não usados</span> representa um valor nulo. Isso não é necessariamente ruim. Isso significa simplesmente que uma chave específica não tem um mapeamento de valor associado. Quando você vir muitos 1 valores para uma variável importante, verifique com a equipe do site para verificar se todas as páginas estão marcadas corretamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Práticas recomendadas

Execute e verifique o relatório [!UICONTROL Unused Signals]:

* Depois de criar uma característica ou atualizar as regras de característica. Isso ajuda a garantir que suas características e regras sejam configuradas corretamente. O número 1 nos resultados indica que uma nova característica pode não estar configurada corretamente.
* Semanalmente ou mensalmente. As revisões agendadas ajudam a garantir que os mapeamentos de características estejam atualizados.

>[!NOTE]
>
>Ao procurar valores não usados no relatório, considere a seguinte particularidade. Há uma diferença na expressão entre os dois exemplos abaixo:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Ambos os exemplos mostram uma característica que contém dois pares de valores chave v e a. A primeira expressão se traduz em: a característica contém a chave v com o valor 1 [!UICONTROL AND NOT] a chave a com o valor 23. A segunda expressão contém a chave v com o valor 1 [!UICONTROL AND] a chave a com o valor [!UICONTROL NOT EQUAL] 23.
* Considerando as duas expressões diferentes acima, digamos que você pesquise no [!UICONTROL Unused Signals Report] os valores que são passados na chave a com qualquer valor diferente de 23, você só obterá resultados no primeiro caso porque os valores para a chave não foram enviados AT ALL. No segundo caso, valores diferentes de 23 foram enviados, portanto, a tecla a não é usada.

## Criação de características em massa

Entre em contato com seu representante de soluções de parceiros se precisar criar muitas características em massa com base nos dados obtidos do relatório [!UICONTROL Unused Signals].
