---
description: Crie e gerencie as características ou segmentos usados na modelagem algorítmica, também conhecido como modelagem de semelhanças. Os recursos do modelo estão localizados em Dados de público-alvo > Modelos.
keywords: peso relativo, lookmode
seo-description: Crie e gerencie as características ou segmentos usados na modelagem algorítmica, também conhecido como modelagem de semelhanças. Os recursos do modelo estão localizados em Dados de público-alvo > Modelos.
seo-title: Sobre modelos algorítmicos
solution: Audience Manager
title: Sobre modelos algorítmicos
topic: API DIL
uuid: 39441 e 72-5316-453 d -9 aff -0 e 0 b 633 aabcd
translation-type: tm+mt
source-git-commit: 73d670225fb4170d02428a1dd163f442540e3415

---


# Sobre modelos algorítmicos {#about-algorithmic-models}

Crie e gerencie as características ou segmentos usados na modelagem algorítmica, também conhecido como modelagem de semelhanças. Os recursos do modelo estão localizados **[!UICONTROL Audience Data > Models]**.

<!-- c_models.xml -->

## Entendendo modelos algorítmicos {#understanding-models}

As seções abaixo representam uma análise da modelagem algorítmica. [!DNL Audience Manager] Descrevem como a modelagem funciona, os benefícios e o fluxo de trabalho.

<!-- understanding-models.xml -->

## Localizar novos usuários com modelagem algorítmica {#find-new-users}

A modelagem algorítmica ajuda a descobrir públicos novos e exclusivos por meio da análise de dados automatizada. O processo é iniciado quando você seleciona uma característica ou segmento, um intervalo de tempo e fontes de dados originais e de terceiros. Suas opções fornecem as entradas para o modelo algorítmico. Quando o processo de análise é executado, ele procura por usuários qualificados com base em características compartilhadas da população selecionada. Após a conclusão, esses dados estão disponíveis no [Construtor](../../features/traits/about-trait-builder.md) de características, onde você pode usá-lo para criar características com base na [precisão e no alcance](../../features/traits/trait-accuracy-reach.md). Além disso, é possível construir segmentos que combinam características algorítmicas com características baseadas em regras e adicionar outros requisitos de qualificação com expressões booleanas e operadores de comparação. A modelagem algorítmica fornece uma maneira dinâmica de extrair o valor de todos os dados de característica disponíveis.

## Benefícios {#advantages}

Os principais benefícios do uso [!DNL Audience Manager] de modelagem incluem:

* **Precisão dos dados:** O algoritmo é executado regularmente, o que ajuda a manter os resultados atuais e relevantes.
* **Automação:** Não é necessário gerenciar um grande conjunto de regras estáticas. O algoritmo encontrará os públicos-alvo para você.
* **Economize tempo e reduza o esforço:** Com nosso processo de modelagem, você não precisa adivinhar quais características/segmentos podem funcionar ou gastar tempo em campanhas para descobrir novos públicos. O modelo pode fazer isso para você.
* **Confiabilidade:** A modelagem funciona com processos de descoberta e descoberta do servidor que avaliam seus próprios dados e dados de terceiros aos quais você tem acesso. Isso significa que você não precisa ver os visitantes do site para qualificá-los para uma característica.

## Fluxo de trabalho {#workflow}

Você gerencia modelos. **[!UICONTROL Audience Data > Models]** Em um nível superior, o processo de fluxo de trabalho envolve:

* Selecione os dados da linha de base que deseja avaliar no algoritmo. Isso inclui uma característica ou segmento, intervalo de tempo e fontes de dados (seus próprios dados e dados de terceiros que você já tem acesso [!DNL Audience Manager]a). No fluxo de trabalho de criação de modelo, você pode excluir as características que não deseja interagir com o modelo.
* Salve o modelo. Uma vez salvo, o processo de avaliação algorítmica é executado automaticamente. No entanto, pode levar até 7 dias para concluir o processo. [!DNL Audience Manager] envia um email quando o algoritmo termina e os resultados estão disponíveis para criação de características.
* Crie características algorítmicas.[!UICONTROL Trait Builder]
* Combine características em segmentos.[!UICONTROL Segment Builder]
* Crie e envie dados de segmento para um destino.

## Solução de problemas {#troubleshooting}

Desativamos qualquer modelo algorítmico que não gere dados para três execuções consecutivas. Observe que não é possível definir o status do modelo de volta para ativo depois. Para garantir que seus modelos geram dados, recomendamos que você construa modelos de fontes de dados com características suficientes para acumular dados.

>[!MORE_ LIKE_ THIS]
>
>* [Destinos](../../features/destinations/destinations.md)
>* [Características](../../features/traits/trait-details-page.md)
>* [Segmentos](../../features/segments/segments-purpose.md)


## Noções básicas de traitweight {#understanding-traitweight}

[!UICONTROL TraitWeight] é um algoritmo proprietário projetado para descobrir novos traços automaticamente. Ele compara os dados características das características e segmentos atuais em relação a todos os dados primeiro e de terceiros que você tem acesso [!DNL Audience Manager]. Consulte esta seção para obter uma descrição do processo de descoberta [!UICONTROL TraitWeight] algorítmica.

<!-- traitweight.xml -->

![](assets/algo_model.png)

As etapas a seguir descrevem o [!UICONTROL TraitWeight] processo de avaliação.

### Etapa 1: Criar uma linha de base para comparação de características

Para construir uma linha de base, [!UICONTROL TraitWeight] mede todas as características associadas a um público-alvo para um intervalo de 30, 60 ou 90 dias. Em seguida, classifica características de acordo com sua frequência e sua correlação. A contagem de frequência mede a aridade. A Correlação mede a probabilidade de uma característica estar presente apenas no público-alvo da linha de base. As características que aparecem frequentemente são consideradas uma característica alta, uma característica importante usada para definir uma pontuação ponderada quando combinada com características descobertas nas fontes de dados selecionadas.

### Etapa 2: Localizar as mesmas características na Fonte de Dados

Depois de construir uma linha de base para comparação, o algoritmo procura traços idênticos nas fontes de dados selecionadas. Nesta etapa, [!UICONTROL TraitWeight] realiza uma contagem de frequência de todas as características descobertas e as compara à linha de base. Entretanto, diferentemente da linha de base, as características incomuns são classificadas mais altas do que as exibidas com mais frequência. Traços raros são indicados para exibir um grau maior de especificidade. [!UICONTROL TraitWeight] calcula combinações de características comuns de linha de base e características de fonte de dados incomuns (altamente específicas) como mais influentes ou desejáveis do que as características comuns a ambos os conjuntos de dados. Na verdade, nosso modelo reconhece essas características grandes e comuns e não atribui prioridade excessiva a conjuntos de dados com correlações altas. Características raras têm prioridade mais alta porque têm maior probabilidade de representar usuários novos e exclusivos do que características com alta aridade no quadro.

### Etapa 3: Atribuir espessura

Nesta etapa [!UICONTROL TraitWeight] , classifica traços recentemente descobertos em ordem de influência ou desejável. A escala de peso é uma porcentagem que é executada de 0% a 100%. As características mais próximas de 100% significam que são mais semelhantes ao público na sua população de linha de base. Além disso, características altamente ponderadas são valiosas porque representam usuários novos e exclusivos que se comportam de forma semelhante ao público-alvo estabelecido e de linha de base. Lembre-se, [!UICONTROL TraitWeight] considera características com alta aridade na linha de base e alta especificidade nas fontes de dados comparadas para serem mais valiosas do que as características comuns em cada conjunto de dados.

### Etapa 4: Usuários de pontuação

Cada usuário nas fontes de dados selecionadas recebe uma pontuação do usuário igual à soma de todos os pesos das características influentes no perfil do usuário. As pontuações do usuário são, então, normalizadas entre 0 e 100%.

### Etapa 5: Exibir e trabalhar com resultados

O Audience Manager exibe os resultados de seu modelo ponderada. [!UICONTROL Trait Builder] Quando você deseja criar uma característica algorítmica, [!UICONTROL Trait Builder] permite criar características com base na pontuação ponderada gerada pelo algoritmo durante a execução dos dados. É possível escolher uma precisão maior para qualificar somente usuários que têm pontuações muito altas de usuários e, portanto, são muito semelhantes ao público-alvo da linha de base, em vez do restante do público-alvo. Se quiser atingir um público maior (alcance), você pode reduzir a precisão.

### Etapa 6: Reavaliar a significância de uma característica nos ciclos de processamento

Periodicamente [!UICONTROL TraitWeight] , avalia novamente a importância de uma característica com base no tamanho e na alteração na população dessa característica. Isso ocorre como o número de usuários qualificados para essa característica aumenta ou diminui ao longo do tempo. Esse comportamento é visto com mais clareza em características que se tornam muito grandes. Por exemplo, suponha que o algoritmo use características A para modelagem. Como a população de característica A aumenta, [!UICONTROL TraitWeight] reavalia a importância dessa característica e pode atribuir uma pontuação mais baixa ou ignorá-la. Nesse caso, a característica A é muito comum ou grande para dizer qualquer coisa significativa sobre sua população. Depois [!UICONTROL TraitWeight] reduz o valor de Característica A (ou ignora-o no modelo), a população do mesmo diminui. A lista de características influentes reflete a evolução da população da linha de base. Use a lista de características influentes para compreender por que essas alterações ocorrem.

Links relacionados:

* [Construtor de modelo](../../features/algorithmic-models/create-model.md)
* [Precisão e alcance](../../features/traits/trait-accuracy-reach.md)

## Atualizar agendamento para modelos e características algorítmicas {#update-schedule}

Criação e atualização de cronogramas para novos modelos e características algorítmicas existentes.

<!-- c_model_update_schedule.xml -->

### Criação de modelo algorítmico e programação de atualização

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
   <td colname="col2"> <p>Para modelos algorítmicos novos ou clonados, o processo de criação é executado uma vez por dia em: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 5 PM EST (novembro - março) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 6 PM EDT (março - novembro) </li> 
     </ul> </p> <p>Os modelos construídos ou clonados após o prazo de criação são processados no dia seguinte. </p> <p>Se a primeira execução de um modelo não gerar dados, ela será executada uma segunda vez, no dia seguinte. Se a segunda tentativa também não gerar dados, haverá uma terceira tentativa, no dia seguinte. O modelo parará de ser executado se a terceira tentativa também não gerar dados. Nesse caso, desativaremos o modelo. Consulte Mais em <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Solução de problemas de modelos algorítmicos</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Atualizar um modelo</b> </td> 
   <td colname="col2"> <p>Em condições ideais, os modelos existentes são executados nos dias da semana, pelo menos uma vez a cada 7 dias. Por exemplo, se você criar um modelo (até o prazo) na segunda-feira, ele atualizará a segunda-feira a seguir na mais recente. </p> <p>Um modelo será executado novamente se atender uma das seguintes condições: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">A última execução não foi bem-sucedida. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Ela foi executada com êxito antes e não executada nos últimos 7 dias E o modelo tem pelo menos uma característica ativa anexada a ela. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Criação algorítmica e programação de atualização

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
   <td colname="col2"> <p>O processo de criação de traços é executado todos os dias, de segunda a sexta-feira. Geralmente, novas características algorítmicas aparecem na interface do usuário dentro de 48 horas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Atualizar uma característica</b> </td> 
   <td colname="col2"> <p>As características existentes são atualizadas pelo menos uma vez a cada 7 dias e seguem o cronograma para as atualizações do modelo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exibição de lista de modelos {#models-list-view}

A exibição de lista é uma área de trabalho central que ajuda a criar, analisar e gerenciar modelos.

<!-- c_models_list_view.xml -->

A página de lista Modelos contém recursos e ferramentas que ajudam você a:

* Crie novos modelos.
* Gerenciar modelos existentes (editar, pausar, excluir ou clonar).
* Pesquise por modelos por nome.
* Crie características algorítmicas usando um determinado modelo.

## Exibição de resumo de modelos {#models-summary-view}

A página de resumo exibe detalhes do modelo, como nome, alcance/precisão, histórico de processamento e características criadas do modelo. A página também inclui configurações que permitem criar e gerenciar modelos. Clique em um nome de modelo na lista de resumo para ver os detalhes.

<!-- c_models_summary.xml -->

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
   <td colname="col2"> <p>Inclui informações básicas sobre o modelo, como seu nome e quando ele é executado pela última vez. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Alcance e precisão do modelo</span> </p> </td> 
   <td colname="col2"> <p>Mostra <a href="../../features/traits/trait-accuracy-reach.md"> dados de precisão e alcance</a> para o último modelo executado. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Histórico de processamento de modelo</span> </p> </td> 
   <td colname="col2"> <p>Exibe a data e a hora de processamento para as últimas 10 execuções e se os dados foram gerados nessas execuções. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Características influentes</span> </p> </td> 
   <td colname="col2"> <p>A tabela <span class="wintitle"> Características</span> influentes: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Lista as 50 características principais principais que são mais representadas na população de linha de base do modelo. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Classifica cada característica na ordem <span class="wintitle"> de espessura</span> relativa. A Espessura <span class="wintitle"> relativa</span> classifica traços recentemente descobertos em ordem de influência ou desejável. A escala de peso é uma porcentagem que é executada de 0% a 100%. As características mais próximas de 100% significam que são mais semelhantes ao público na sua população de linha de base. Consulte <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Entendendo traitweight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Mostra os únicos de 30 dias e a população de característica total de cada característica. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Características usando modelo</span> </p> </td>
   <td colname="col2"> <p>Mostra uma lista das características algorítmicas com base no modelo selecionado. Clique em uma ID de característica ou ID de característica para obter mais informações sobre a característica. Selecione <b><span class="uicontrol"> Criar nova característica com modelo</span></b> para acessar o processo de criação algorítmica. </p> <p>O rótulo da seção muda com base no nome do modelo. Por exemplo, digamos que você crie um modelo e nomeie o modelo A. Quando você carrega a página de resumo, o nome desta seção é alterado para <span class="wintitle"> Características usando o modelo A</span>. </p> </td>
  </tr>
 </tbody>
</table>