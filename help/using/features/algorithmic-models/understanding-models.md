---
description: Crie e gerencie as características ou segmentos usados na modelagem por semelhança.
keywords: peso relativo, semelhança
seo-description: Crie e gerencie as características ou segmentos usados na modelagem por semelhança.
seo-title: Sobre a modelagem semelhante
solution: Audience Manager
title: Sobre a modelagem semelhante
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Modelos algorítmicos
exl-id: a24b11ce-6087-4095-a6c2-6815e2211ba5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1595'
ht-degree: 1%

---

# Entendendo [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Encontrar novos usuários com [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] ajuda você a descobrir públicos novos e exclusivos por meio da análise de dados automatizada. O processo é iniciado ao selecionar um [!UICONTROL trait] ou [!UICONTROL segment], um intervalo de tempo e [!UICONTROL data sources] próprio e de terceiros. Suas escolhas fornecem as entradas para o modelo algorítmico. Quando o processo de análise é executado, ele busca usuários qualificados com base em características compartilhadas da população selecionada. Após a conclusão, esses dados estão disponíveis no [Construtor de características](../../features/traits/about-trait-builder.md), onde você pode usá-los para criar características com base em [precisão e alcance](../../features/traits/trait-accuracy-reach.md). Além disso, é possível criar segmentos que combinam características algorítmicas com [!UICONTROL rules-based traits] e adicionar outros requisitos de qualificação com expressões [!DNL Boolean] e operadores de comparação. [!UICONTROL Look-Alike Modeling] O oferece uma maneira dinâmica de extrair valor de todos os dados de características disponíveis.

## Benefícios {#advantages}

Os principais benefícios de usar [!UICONTROL Look-Alike Modeling] incluem:

* **Precisão dos dados:** o algoritmo é executado regularmente, o que ajuda a manter os resultados atualizados e relevantes.
* **Automação:** não é necessário gerenciar um grande conjunto de regras estáticas. O algoritmo encontrará públicos para você.
* **Economize tempo e reduza o esforço:** com nosso processo de modelagem, não é necessário adivinhar o que  [!UICONTROL traits]/[!UICONTROL segments] pode funcionar ou gastar recursos de tempo em campanhas para descobrir novos públicos-alvo. O modelo pode fazer isso por você.
* **Confiabilidade:** a modelagem funciona com processos de detecção e qualificação do lado do servidor que avaliam seus próprios dados e selecionam dados de terceiros aos quais você tem acesso. Isso significa que você não precisa ver os visitantes em seu site para qualificá-los para uma característica.

## Fluxo de trabalho {#workflow}

Você gerencia modelos em **[!UICONTROL Audience Data > Models]**. Em um alto nível, o processo do workflow envolve o seguinte:

* Selecione os dados da linha de base que o algoritmo deve avaliar. Isso inclui [!UICONTROL trait] ou [!UICONTROL segment], intervalo de tempo e [!UICONTROL data sources] (seus próprios dados e dados de terceiros aos quais você já tem acesso por meio de [!DNL Audience Manager]). No fluxo de trabalho de criação do modelo, você pode excluir o [!UICONTROL traits] que não deseja interferir no modelo.
* Salve o modelo. Depois de salvo, o processo de avaliação algorítmica é executado automaticamente. No entanto, observe que pode levar até 7 dias para que esse processo seja concluído. [!DNL Audience Manager] envia um email quando o algoritmo é concluído e os resultados estão disponíveis para  [!UICONTROL trait] criação.
* Crie algoritmos [!UICONTROL traits] em [!UICONTROL Trait Builder].
* Combine [!UICONTROL traits] em [!UICONTROL segments] em [!UICONTROL Segment Builder].
* Crie e envie [!UICONTROL segment] dados para um [!UICONTROL destination].

## Solução de problemas {#troubleshooting}

Desativamos qualquer [!UICONTROL Look-Alike Model] que não gere dados por três execuções consecutivas. Observe que não é possível definir o status do modelo como ativo posteriormente. Para garantir que seus modelos gerem dados, recomendamos criar modelos a partir de fontes de dados com [!UICONTROL traits] suficiente para acumular dados do .

## Entendendo [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] é um algoritmo proprietário projetado para descobrir novos  [!UICONTROL traits] automaticamente. Ele compara os dados [!UICONTROL trait] de seus [!UICONTROL traits] e [!UICONTROL segments] atuais com todos os outros dados primários e de terceiros aos quais você tem acesso por meio de [!DNL Audience Manager]. Consulte esta seção para obter uma descrição do processo de descoberta algorítmica [!UICONTROL TraitWeight].

![](assets/algo_model.png)

As etapas a seguir descrevem o processo de avaliação [!UICONTROL TraitWeight].

### Etapa 1: Criar uma linha de base para [!UICONTROL Trait] comparação

Para criar uma linha de base, [!UICONTROL TraitWeight] mede todos os [!UICONTROL traits] associados a um público-alvo para um intervalo de 30, 60 ou 90 dias. Em seguida, ele classifica [!UICONTROL traits] de acordo com sua frequência e sua correlação. A contagem de frequência mede a uniformidade. A correlação mede a probabilidade de um [!UICONTROL trait] estar presente somente no público-alvo da linha de base. [!UICONTROL Traits] que aparecem frequentemente exibem alta uniformidade, uma característica importante usada para definir uma pontuação ponderada quando combinada com  [!UICONTROL traits] descoberta em seu  [!UICONTROL data sources]selecionado.

### Etapa 2: Encontre o mesmo [!UICONTROL Traits] no [!UICONTROL Data Source]

Depois que ele cria uma linha de base para comparação, o algoritmo procura [!UICONTROL traits] idêntico no [!UICONTROL data sources] selecionado. Nesta etapa, [!UICONTROL TraitWeight] executa uma contagem de frequência de todos os [!UICONTROL traits] descobertos e os compara à linha de base. No entanto, ao contrário da linha de base, pouco comuns [!UICONTROL traits] são classificadas como mais altas do que as que aparecem com mais frequência. Diz-se que [!UICONTROL traits] raras exibem um alto grau de especificidade. [!UICONTROL TraitWeight] Avalia combinações de linha de base comum  [!UICONTROL traits] e pouco frequentes (altamente específicas)  [!UICONTROL data source] [!UICONTROL traits] como mais influentes ou desejáveis do que  [!UICONTROL traits] comuns a ambos os conjuntos de dados. Na verdade, nosso modelo reconhece esses [!UICONTROL traits] grandes e comuns e não atribui prioridade excessiva a conjuntos de dados com altas correlações. Raros [!UICONTROL traits] têm prioridade mais alta porque têm mais probabilidade de representar usuários novos e exclusivos do que [!UICONTROL traits] com alta compatibilidade em todos os sentidos.

### Etapa 3: Atribuir peso

Nesta etapa, [!UICONTROL TraitWeight] classifica [!UICONTROL traits] recentemente descoberto em ordem de influência ou conveniência. A escala de peso é uma porcentagem que vai de 0% a 100%. [!UICONTROL Traits] Classificado mais próximo de 100% significa que são mais parecidas com o público-alvo na sua população de linha de base. Além disso, os [!UICONTROL traits] pesados são valiosos porque representam usuários novos e exclusivos que podem se comportar de forma semelhante ao público-alvo estabelecido na linha de base. Lembre-se, [!UICONTROL TraitWeight] considera [!UICONTROL traits] com alta compatibilidade na linha de base e alta especificidade nas fontes de dados comparadas como mais valiosa do que [!UICONTROL traits] comum em cada conjunto de dados.

### Etapa 4: Usuários de pontuação

Cada usuário no [!UICONTROL data sources] selecionado recebe uma pontuação de usuário igual à soma de todos os pesos do [!UICONTROL traits] influente no perfil desse usuário. As pontuações do usuário são normalizadas entre 0 e 100%.

### Etapa 5: Exibir e trabalhar com resultados

[!DNL Audience Manager] exibe os resultados do modelo ponderado em  [!UICONTROL Trait Builder]. Quando quiser criar um [!UICONTROL algorithmic trait], [!UICONTROL Trait Builder] permite criar [!UICONTROL traits] com base na pontuação ponderada gerada pelo algoritmo durante uma execução de dados. Você pode escolher uma precisão maior para qualificar somente usuários que tenham pontuações de usuário muito altas e, portanto, sejam muito semelhantes ao público-alvo da linha de base, em vez do resto do público-alvo. Se quiser alcançar um público maior (alcance), você pode diminuir a precisão.

### Etapa 6: Reavalie a significância de um [!UICONTROL Trait] em ciclos de processamento

Periodicamente, [!UICONTROL TraitWeight] reavalia a importância de um [!UICONTROL trait] com base no tamanho e na alteração na população desse [!UICONTROL trait]. Isso acontece quando o número de usuários qualificados para esse [!UICONTROL trait] aumenta ou diminui com o tempo. Esse comportamento é mais claramente visto em características que se tornam muito grandes. Por exemplo, suponha que o algoritmo use [!UICONTROL trait A] para modelagem. À medida que a população de [!UICONTROL trait A] aumenta, [!UICONTROL TraitWeight] reavalia a importância desse [!UICONTROL trait] e pode atribuir uma pontuação menor ou ignorá-la. Nesse caso, [!UICONTROL trait A] é muito comum ou grande para dizer algo significativo sobre sua população. Depois de [!UICONTROL TraitWeight] reduzir o valor de [!UICONTROL trait A] (ou ignorá-lo no modelo), o preenchimento da característica algorítmica diminui. A lista de influentes [!UICONTROL traits] reflete a evolução da população da linha de base. Use a lista do [!UICONTROL traits] influente para entender por que essas alterações estão ocorrendo.

Links relacionados:

* [Construtor de modelos](../../features/algorithmic-models/create-model.md)
* [Precisão e alcance](../../features/traits/trait-accuracy-reach.md)

## Atualizar Agendamento para [!UICONTROL Look-Alike Models] e [!UICONTROL Traits] {#update-schedule}

Criação e atualização de agendamentos para [!UICONTROL algorithmic models] e [!UICONTROL traits] novas ou existentes.

### [!UICONTROL Look-Alike Model] Cronograma de criação e atualização

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> Tipo de atividade </th>
   <th colname="col2" class="entry"> Descrição </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>Criar ou clonar um modelo</b> </td>
   <td colname="col2"> <p>Para modelos semelhantes novos ou clonados do [!UICONTROL], o processo de criação é executado uma vez por dia em: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 17 PM EST (novembro - março) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 18 PM EDT (março - novembro) </li> 
     </ul> </p> <p>Os modelos construídos ou clonados após o prazo de criação são processados no dia seguinte. </p> <p>Se a primeira execução de um modelo não gerar dados, ela será executada uma segunda vez, no dia seguinte. Se a segunda tentativa também não gerar dados, haverá uma terceira tentativa, no dia seguinte. O modelo parará de ser executado se a terceira tentativa também não gerar dados. Nesse caso, desativaremos o modelo. Veja mais em <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Solução de problemas de modelos semelhantes</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Atualizar um modelo</b> </td> 
   <td colname="col2"> <p>Em condições ideais, os modelos existentes são executados em dias da semana, pelo menos uma vez a cada 7 dias. Por exemplo, se você criar um modelo (até o prazo final) na segunda-feira, ele será atualizado na segunda-feira seguinte, o mais tardar. </p> <p>Um modelo será executado novamente se atender a qualquer uma das seguintes condições: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Sua última execução não foi bem-sucedida. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Ele foi executado com êxito antes E não foi executado nos últimos 7 dias E o modelo tem pelo menos uma característica ativa anexada a ele. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] Cronograma de criação e atualização

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de atividade </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Criar uma característica</b> </td> 
   <td colname="col2"> <p>O processo de criação de características é executado todos os dias, de segunda a sexta-feira. Geralmente, novas características algorítmicas aparecem na interface do usuário em 48 horas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Atualizar uma característica</b> </td> 
   <td colname="col2"> <p>As características existentes são atualizadas pelo menos uma vez a cada 7 dias e seguem o agendamento para atualizações do modelo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exibição da lista de modelos {#models-list-view}

A exibição de lista é um espaço de trabalho central que ajuda a criar, revisar e gerenciar modelos.

A página de lista [!UICONTROL Models] contém recursos e ferramentas que ajudam a:

* Crie novos modelos.
* Gerenciar modelos existentes (editar, pausar, excluir ou clonar).
* Procure por modelos por nome.
* Crie [!UICONTROL algorithmic traits] usando qualquer modelo.

## Visualização do resumo dos modelos {#models-summary-view}

A página de resumo exibe detalhes do modelo, como nome, alcance/precisão, histórico de processamento e [!UICONTROL traits] criados a partir do modelo. A página também inclui configurações que permitem criar e gerenciar modelos. Clique em um nome de modelo na lista de resumo para ver seus detalhes.

A página de resumo do modelo inclui as seguintes seções.

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Seção </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle"> Informações básicas</span> </p> </td>
   <td colname="col2"> <p>Inclui informações básicas sobre o modelo, como seu nome e quando foi executado pela última vez. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Alcance e precisão do modelo</span> </p> </td> 
   <td colname="col2"> <p>Mostra a precisão <a href="../../features/traits/trait-accuracy-reach.md"> e os dados de alcance</a> para a última execução do modelo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Histórico de processamento do modelo</span> </p> </td> 
   <td colname="col2"> <p>Exibe a data e a hora de processamento das últimas 10 execuções e se os dados foram gerados nessas execuções. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Características influentes</span> </p> </td> 
   <td colname="col2"> <p>A tabela <span class="wintitle"> Características influentes</span>: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Lista as 50 principais características influentes que são melhor representadas na população de linha de base do modelo. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Classifica cada característica em ordem de sua classificação <span class="wintitle"> Peso relativo</span>. O <span class="wintitle"> Peso relativo</span> classifica características recém-descobertas em ordem de influência ou conveniência. A escala de peso é uma porcentagem que vai de 0% a 100%. Características classificadas mais próximas de 100% significa que são mais parecidas com o público-alvo na sua população de linha de base. Consulte <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Entendendo o TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Mostra os únicos de 30 dias e a população total de características para cada característica. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Características usando modelo</span> </p> </td>
   <td colname="col2"> <p>Mostra uma lista de características algorítmicas com base no modelo selecionado. Clique em um nome de característica ou ID de característica para obter mais informações sobre a característica. Selecione <b><span class="uicontrol"> Criar nova característica com modelo</span></b> para ir para o processo de criação de característica algorítmica. </p> <p>O rótulo da seção muda com base no nome do modelo. Por exemplo, digamos que você crie um modelo e o nomeie como Modelo A. Ao carregar a página de resumo, o nome desta seção é alterado para <span class="wintitle"> Características usando o modelo A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Destinos ](../../features/destinations/destinations.md)
* [Características ](../../features/traits/trait-details-page.md)
* [Segmentos ](../../features/segments/segments-purpose.md)

