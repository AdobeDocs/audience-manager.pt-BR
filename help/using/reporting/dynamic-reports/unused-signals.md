---
description: Este relatório retorna uma contagem de frequência de todas as informações não utilizadas coletadas em seu inventário e enviadas ao Audience Manager.
seo-description: This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.
seo-title: Unused Signals Report
solution: Audience Manager
title: Relatório de sinais não usados
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: Overlap Reports
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
source-git-commit: 8fd148df6c19a5d8331faf66c671f91686954a77
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 1%

---

# Relatório de sinais não usados{#unused-signals-report}

Este relatório retorna uma contagem de frequência de todas as informações não utilizadas coletadas em seu inventário e enviadas ao Audience Manager. Para acessar este relatório, navegue até **Analytics > Relatórios de público-alvo > Outros relatórios > Sinais não utilizados**.

>[!NOTE]
>
>Se você vir a mensagem &quot;Você não tem acesso aos Relatórios de público-alvo&quot;, entre em contato com seu consultor da Audience Manager ou com o Atendimento ao cliente para provisionar o relatório para você.

![Captura de tela do Relatório de sinais não utilizados](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## Visão geral

Um sinal são informações do seu site passadas para [!DNL Audience Manager] na forma de [pares de valores-chave](../../reference/key-value-pairs-explained.md) (por exemplo, `color=blue, price>100, gender=female` etc.).

Os sinais não utilizados consistem em dados que você coleta, mas que não foram mapeados para uma característica. O relatório [!UICONTROL Unused Signals] mostra dados em uma tabela por data, chave, valor e contagem de frequência. Qualquer sinal não mapeado passado para [!DNL Audience Manager] pelo menos 100 vezes por dia é qualificado para o relatório [!UICONTROL Unused Signals]. Os sinais não utilizados são armazenados por 45 dias e depois descartados.

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
   <td colname="col1"> <p><b>Garantir Uniformidade de Características ou Adicionar Valores Relacionados a uma Única Chave</b> </p> </td> 
   <td colname="col2"> <p>Revise o relatório para levar em conta as diferentes variações de valor para um sinal específico. </p> <p>Por exemplo, digamos que você tenha uma característica para o estado "Carolina do Norte" definida em um par de valor-chave como <code> c_state = North Carolina</code>. O relatório pode ajudá-lo a encontrar variantes de nome e adicioná-las à característica (por exemplo, <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Como alternativa, você pode identificar variantes de nome com o relatório e substituí-las por um valor uniforme em todos os sites. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Criar novas características</b> </p> </td> 
   <td colname="col2"> <p>Revise o relatório para ver quais novos valores são transmitidos em uma chave específica. Você pode criar novos pares de valores chave com base nesses novos valores. </p> <p> <p>Observação: verifique o relatório quinzenalmente em busca de valores que mudam com frequência (por exemplo, shows, campanhas, celebridades, etc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Localizar Valores Não Mapeados</b> </p> </td> 
   <td colname="col2"> <p>Revise o relatório para o número 1. O número 1 em um relatório de <span class="wintitle"> Sinais Não Utilizados</span> representa um valor nulo. Isso não é necessariamente ruim. Simplesmente significa que uma chave específica não tem um mapeamento de valor associado. Quando você vir muitos valores 1 para uma variável importante, verifique com a equipe do site para garantir que todas as páginas sejam marcadas corretamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Práticas recomendadas

Execute e verifique o relatório [!UICONTROL Unused Signals]:

* Depois de criar uma característica ou atualizar regras de característica. Isso ajuda a garantir que suas características e regras sejam configuradas corretamente. O número 1 nos resultados indica que uma nova característica pode não ser configurada corretamente.
* Quinzenalmente ou mensalmente. As revisões programadas ajudam a garantir que os mapeamentos de características estejam atualizados.

>[!NOTE]
>
>Ao pesquisar valores não utilizados no relatório, considere a seguinte particularidade. Há uma diferença na expressão entre os dois exemplos abaixo:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T( v=1 [!UICONTROL AND] (a!=23)]
* Ambos os exemplos mostram uma característica que contém dois pares de valores-chave v e a. A primeira expressão converte em: a característica contém a chave v com o valor 1 [!UICONTROL AND NOT], a chave a com o valor 23. A segunda expressão contém a chave v com o valor 1 [!UICONTROL AND] a chave a com o valor [!UICONTROL NOT EQUAL] 23.
* Considerando as duas expressões diferentes acima, digamos que você pesquise no [!UICONTROL Unused Signals Report] os valores que são passados na chave a com qualquer valor diferente de 23, você só obterá resultados na primeira ocorrência, pois os valores para a chave não foram enviados de forma alguma. No segundo caso, valores diferentes de 23 foram enviados para que a chave a não fosse usada.

## Criação de características em massa

Entre em contato com seu representante de soluções de parceiros se precisar criar muitas características com base nos dados obtidos do relatório [!UICONTROL Unused Signals].
