---
description: Este relatório retorna uma contagem de frequência de todas as informações não usadas coletadas no estoque e enviadas para o Audience Manager.
seo-description: Este relatório retorna uma contagem de frequência de todas as informações não usadas coletadas no estoque e enviadas para o Audience Manager.
seo-title: Relatório de Sinais não usados
solution: Audience Manager
title: Relatório de Sinais não usados
uuid: 04334 a 5 c -3 e 21-44 db-b 971-0 b 4457685 e 9 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Unused Signals Report{#unused-signals-report}

Este relatório retorna uma contagem de frequência de todas as informações não usadas coletadas no estoque e enviadas para o Audience Manager.

<!-- 

c_unused_signals.xml

 -->

## Relatório de Sinais não usados

A signal is information from your website passed in to [!DNL Audience Manager] in the form of [key-value pairs](../../reference/key-value-pairs-explained.md) (e.g., `color=blue, price>100, gender=female`, etc.).

Os sinais não usados consistem em dados coletados, mas não foram mapeados para uma característica. The [!UICONTROL Unused Signals] report shows data in a table by date, key, value, and frequency count. Any unmapped signal passed in to [!DNL Audience Manager] at least 100 times in a day qualifies for the [!UICONTROL Unused Signals] report.

Analise este relatório para ajudar a identificar sinais órfãos que podem ser mapeados para traços novos ou existentes.

>[!NOTE]
>
>Especifique uma chave ou nome de valor nos campos de pesquisa para limitar os resultados a registros específicos.

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
   <td colname="col1"> <p><b>Garantir a uniformidade de características ou Adicionar valores relacionados a uma única chave</b> </p> </td> 
   <td colname="col2"> <p>Analise o relatório para considerar variações de valor diferentes para um sinal específico. </p> <p>For example, say you have a trait for the state "North Carolina" defined in a key-value pair as <code> c_state = North Carolina</code>. The report can help you find name variants and add those to the trait (e.g., <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Como alternativa, você pode detectar variantes de nome com o relatório e substituir aqueles com um valor uniforme em todos os sites. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Criar novas características</b> </p> </td> 
   <td colname="col2"> <p>Analise o relatório para ver quais novos valores serão transmitidos em uma chave específica. Você pode criar novos pares de valores chave com base nesses novos valores. </p> <p> <p>Observação: Verifique o relatório em forma bi-semanal para valores que mudam frequentemente (por exemplo, exibições, campanhas, celebridades etc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Encontrar valores não mapeados</b> </p> </td> 
   <td colname="col2"> <p>Revise o relatório para o número 1. The number 1 in an <span class="wintitle"> Unused Signals</span> report represents a null value. Isso não é necessariamente ruim. Isso significa simplesmente que uma chave específica não tem um mapeamento de valor associado. Quando você vir muitos valores para uma variável importante, verifique com a equipe do site para verificar se todas as páginas estão marcadas corretamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Práticas recomendadas

Run and check the [!UICONTROL Unused Signals] report:

* Depois de criar uma característica ou atualizar as regras de característica. Isso ajuda a garantir que suas características e regras sejam definidas corretamente. O número 1 em resultados indica que uma nova característica pode não ser configurada corretamente.
* Ou mensal. As revisões programadas ajudam a garantir que os mapeamentos de características estejam atualizados.

>[!NOTE]
>
>Ao pesquisar valores não usados no relatório, considere a seguinte particularidade. Há uma diferença na expressão entre os dois exemplos abaixo:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Both examples show a trait which contains two key-value pairs v and a. The first expression translates into: the trait contains key v with the value 1 [!UICONTROL AND NOT] the key a with the value 23. The second expression contains key v with the value 1 [!UICONTROL AND] the key a with the value [!UICONTROL NOT EQUAL] 23.
* Considering the two different expressions above, let&#39;s say you search in the [!UICONTROL Unused Signals Report] for the values that get passed on key a with any value different than 23, you&#39;ll only obtain results in the first case because values for key were not sent AT ALL. No segundo caso, os valores diferentes de 23 foram enviados para que a chave a não seja usada.

## Criação de característica em massa

Contact your Partner Solutions representative if you need to bulk create a lot of traits based on data obtained from the [!UICONTROL Unused Signals] report.
