---
description: Crie e gerencie as características ou segmentos usados em modelagem semelhante.
keywords: relative weight, lookalike
seo-description: Crie e gerencie as características ou segmentos usados em modelagem semelhante.
seo-title: Sobre a modelagem semelhante à aparência
solution: Audience Manager
title: Sobre a modelagem semelhante à aparência
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1590'
ht-degree: 1%

---


# Noções básicas [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Localizar novos usuários com [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] ajuda a descobrir audiências novas e únicas por meio da análise de dados automatizada. O processo é start quando você seleciona um [!UICONTROL trait] ou [!UICONTROL segment], um intervalo de tempo e um primeiro e terceiro [!UICONTROL data sources]. Suas escolhas fornecem as entradas para o modelo algorítmico. Quando o processo de análise é executado, ele procura usuários elegíveis com base em características compartilhadas da população selecionada. Após a conclusão, esses dados estão disponíveis no Construtor [de](../../features/traits/about-trait-builder.md) características, onde você pode usá-los para criar características com base na [precisão e no alcance](../../features/traits/trait-accuracy-reach.md). Além disso, você pode criar segmentos que combinam características algorítmicas com [!UICONTROL rules-based traits] e adicionar outros requisitos de qualificação com operadores de [!DNL Boolean] expressões e comparação. [!UICONTROL Look-Alike Modeling] fornece uma maneira dinâmica de extrair valor de todos os dados de características disponíveis.

## Benefícios {#advantages}

Os principais benefícios do uso [!UICONTROL Look-Alike Modeling] incluem:

* **Precisão dos dados:** O algoritmo é executado regularmente, o que ajuda a manter os resultados atualizados e relevantes.
* **Automação:** Não é necessário gerenciar um grande conjunto de regras estáticas. O algoritmo encontrará audiências para você.
* **Economize tempo e reduza o esforço:** Com nosso processo de modelagem, você não precisa adivinhar o que [!UICONTROL traits]/[!UICONTROL segments] pode funcionar ou gastar recursos de tempo no campanha para descobrir novas audiências. O modelo pode fazer isso por você.
* **Confiabilidade:** A modelagem funciona com processos de detecção e qualificação do lado do servidor que avaliam seus próprios dados e dados selecionados de terceiros aos quais você tem acesso. Isso significa que você não precisa ver os visitantes no seu site para qualificá-los para uma característica.

## Fluxo de trabalho {#workflow}

Você gerencia modelos em **[!UICONTROL Audience Data > Models]**. Em um nível superior, o processo de fluxo de trabalho envolve o seguinte:

* Selecione os dados da linha de base que deseja que o algoritmo avalie. Isso inclui um [!UICONTROL trait] ou [!UICONTROL segment], um intervalo de tempo e [!UICONTROL data sources] (seus próprios dados e dados de terceiros aos quais você já tem acesso [!DNL Audience Manager]). No fluxo de trabalho de criação de modelo, você pode excluir o modelo [!UICONTROL traits] que não deseja interferir no modelo.
* Salve seu modelo. Depois de salvo, o processo de avaliação algorítmica é executado automaticamente. Entretanto, observe que esse processo pode levar até 7 dias para ser concluído. [!DNL Audience Manager] envia um email quando o algoritmo terminar e os resultados estiverem disponíveis para [!UICONTROL trait] criação.
* Crie algoritmos [!UICONTROL traits] para [!UICONTROL Trait Builder].
* Combine [!UICONTROL traits] em [!UICONTROL segments] dentro [!UICONTROL Segment Builder].
* Crie e envie [!UICONTROL segment] dados para um [!UICONTROL destination].

## Solução de problemas {#troubleshooting}

Desativamos todos os [!UICONTROL Look-Alike Model] que falham na geração de dados para três execuções consecutivas. Observe que não é possível definir o status do modelo de volta para ativo depois. Para garantir que seus modelos gerem dados, recomendamos que você crie modelos a partir de fontes de dados com o suficiente [!UICONTROL traits] para acumular dados a partir delas.

## Noções básicas [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] é um algoritmo proprietário projetado para descobrir novas [!UICONTROL traits] automaticamente. Ele compara [!UICONTROL trait] os dados do seu atual [!UICONTROL traits] e [!UICONTROL segments] com todos os outros dados primários e de terceiros aos quais você tem acesso [!DNL Audience Manager]. Consulte esta seção para obter uma descrição do processo de descoberta de [!UICONTROL TraitWeight] algoritmos.

![](assets/algo_model.png)

As etapas a seguir descrevem o processo de [!UICONTROL TraitWeight] avaliação.

### Etapa 1: Criar uma linha de base para [!UICONTROL Trait] comparação

Para criar uma linha de base, [!UICONTROL TraitWeight] mede todos os dados [!UICONTROL traits] associados a uma audiência para um intervalo de 30, 60 ou 90 dias. Em seguida, classifica-se [!UICONTROL traits] de acordo com a sua frequência e correlação. A contagem de frequências mede a uniformidade. A correlação mede a probabilidade de uma [!UICONTROL trait] presença apenas na audiência de base. [!UICONTROL Traits] que aparecem frequentemente exibem uma elevada compatibilidade, uma característica importante usada para definir uma pontuação ponderada quando combinada com a [!UICONTROL traits] descoberta no seu [!UICONTROL data sources]selecionado.

### Etapa 2: Encontre o mesmo [!UICONTROL Traits] na [!UICONTROL Data Source]

Depois de criar uma linha de base para comparação, o algoritmo procura por idêntico [!UICONTROL traits] em sua seleção [!UICONTROL data sources]. Nesta etapa, [!UICONTROL TraitWeight] realiza uma contagem de frequência de todos os descobertos [!UICONTROL traits] e os compara à linha de base. No entanto, ao contrário da linha de base, pouco frequentes [!UICONTROL traits] são classificados como mais elevados do que os que aparecem com mais frequência. Raras [!UICONTROL traits] são ditas exibindo um alto grau de especificidade. [!UICONTROL TraitWeight] avalia as combinações de valores basais comuns [!UICONTROL traits] e pouco frequentes (altamente específicos) [!UICONTROL data source] como mais influentes ou desejáveis do que [!UICONTROL traits] [!UICONTROL traits] os comuns a ambos os conjuntos de dados. Na verdade, nosso modelo reconhece essas grandes, comuns [!UICONTROL traits] e não atribui prioridade excessiva a conjuntos de dados com altas correlações. Raras [!UICONTROL traits] recebem prioridade mais alta porque têm maior probabilidade de representar usuários novos e únicos do que [!UICONTROL traits] com alta compatibilidade em todos os sentidos.

### Etapa 3: Atribuir Peso

Nessa etapa, [!UICONTROL TraitWeight] figura a recém-descoberta [!UICONTROL traits] por ordem de influência ou desejabilidade. A escala do peso é uma porcentagem que vai de 0% a 100%. [!UICONTROL Traits] classificados mais perto de 100% significa que são mais parecidos com a audiência na população de base. Além disso, os pesados [!UICONTROL traits] são valiosos porque representam usuários novos e únicos que podem se comportar de forma semelhante à sua audiência de linha de base estabelecida. Lembre-se, [!UICONTROL TraitWeight] considera que [!UICONTROL traits] com alta compatibilidade na linha de base e alta especificidade nas fontes de dados comparadas é mais valioso do que o [!UICONTROL traits] comum em cada conjunto de dados.

### Etapa 4: Usuários de Pontuação

A cada usuário selecionado [!UICONTROL data sources] é atribuída uma pontuação de usuário igual à soma de todos os pesos do influente [!UICONTROL traits] no perfil desse usuário. As pontuações do usuário são normalizadas entre 0 e 100%.

### Etapa 5: Exibir e trabalhar com resultados

[!DNL Audience Manager] exibe os resultados do modelo ponderado em [!UICONTROL Trait Builder]. Quando você deseja criar um [!UICONTROL algorithmic trait], [!UICONTROL Trait Builder] permite que você crie [!UICONTROL traits] com base na pontuação ponderada gerada pelo algoritmo durante uma execução de dados. Você pode escolher uma precisão maior para qualificar somente usuários que tenham pontuações muito altas e, portanto, sejam muito semelhantes à audiência da linha de base, em vez do restante da audiência. Se quiser atingir uma audiência maior (alcance), você pode diminuir a precisão.

### Etapa 6: Reavaliar a importância de um [!UICONTROL Trait] ciclo de processamento entre ciclos

Periodicamente, [!UICONTROL TraitWeight] reavalia a importância de um [!UICONTROL trait] relatório com base na dimensão e mudança na população desse grupo [!UICONTROL trait]. Isso ocorre quando o número de usuários qualificados para isso [!UICONTROL trait] aumenta ou diminui ao longo do tempo. Esse comportamento é mais claramente visto em traços que se tornam muito grandes. Por exemplo, suponha que o algoritmo use [!UICONTROL trait A] para modelagem. À medida que a população de [!UICONTROL trait A] pessoas aumenta, [!UICONTROL TraitWeight] reavalia a importância disso [!UICONTROL trait] e pode atribuir uma pontuação menor ou ignorá-la. Neste caso, [!UICONTROL trait A] é demasiado comum ou grande para dizer algo significativo sobre a sua população. Depois de [!UICONTROL TraitWeight] reduzir o valor de [!UICONTROL trait A] (ou ignorá-lo no modelo), a população do traço algorítmico diminui. A lista de influência [!UICONTROL traits] reflete a evolução da população de referência. Use a lista do influente [!UICONTROL traits] para entender por que essas alterações estão ocorrendo.

Links relacionados:

* [Construtor de modelos](../../features/algorithmic-models/create-model.md)
* [Precisão e alcance](../../features/traits/trait-accuracy-reach.md)

## Atualizar agendamento para [!UICONTROL Look-Alike Models] e [!UICONTROL Traits] {#update-schedule}

Criação e atualização de agendamentos para novos [!UICONTROL algorithmic models] e existentes [!UICONTROL traits].

### [!UICONTROL Look-Alike Model] Criação e atualização da programação

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
   <td colname="col2"> <p>Para [!UICONTROL Look-Alike Models] novos ou clonados, o processo de criação é executado uma vez por dia em: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 17:00 EST (novembro - março) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 18:00 EDT (março - novembro) </li> 
     </ul> </p> <p>Os modelos construídos ou clonados após o prazo de criação são processados no dia seguinte. </p> <p>Se a primeira execução de um modelo não gerar dados, ele será executado uma segunda vez, no dia seguinte. Se a segunda tentativa também não gerar dados, haverá uma terceira tentativa, no dia seguinte. O modelo parará de ser executado se a terceira tentativa também não gerar dados. Nesse caso, desativaremos o modelo. Consulte mais em <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Solução de problemas de modelos</a>semelhantes. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Atualizar um modelo</b> </td> 
   <td colname="col2"> <p>Em condições ideais, os modelos existentes são executados em dias da semana, pelo menos uma vez a cada 7 dias. Por exemplo, se você criar um modelo (dentro do prazo) na segunda-feira, ele atualizará a segunda-feira seguinte, o mais tardar. </p> <p>Um modelo será executado novamente se atender a qualquer uma das seguintes condições: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Sua última execução não foi bem-sucedida. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Ele foi executado com sucesso antes E não foi executado nos últimos 7 dias E o modelo tem pelo menos uma característica ativa anexada a ele. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] Criação e atualização da programação

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
   <td colname="col2"> <p>As características existentes são atualizadas pelo menos uma vez a cada 7 dias e seguem o cronograma para atualizações de modelo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Visualização de Lista de modelos {#models-list-view}

A visualização de lista é um espaço de trabalho central que ajuda a criar, revisar e gerenciar modelos.

A página de [!UICONTROL Models] lista contém recursos e ferramentas que ajudam você a:

* Crie novos modelos.
* Gerenciar modelos existentes (editar, pausar, excluir ou clonar).
* Procure por modelos por nome.
* Crie [!UICONTROL algorithmic traits] usando qualquer modelo.

## Visualização de resumo de modelos {#models-summary-view}

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
   <td colname="col2"> <p>Inclui informações básicas sobre o modelo, como seu nome e quando ele foi executado pela última vez. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Alcance e precisão do modelo</span> </p> </td> 
   <td colname="col2"> <p>Mostra dados de <a href="../../features/traits/trait-accuracy-reach.md"> precisão e alcance</a> para a última execução do modelo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Histórico de processamento do modelo</span> </p> </td> 
   <td colname="col2"> <p>Exibe a data e a hora de processamento das 10 últimas execuções e se os dados foram gerados nessas execuções. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Características influentes</span> </p> </td> 
   <td colname="col2"> <p>A <span class="wintitle"> tabela Características</span> influentes: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Lista as 50 principais características influentes que são melhor representadas na população de referência do modelo. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Classifica cada característica em ordem de sua classificação de Peso <span class="wintitle"></span> relativo. O Peso <span class="wintitle"></span> Relativo classifica características recém-descobertas em ordem de influência ou desejabilidade. A escala do peso é uma porcentagem que vai de 0% a 100%. As características mais próximas de 100% significam que são mais parecidas com a audiência na população de base. Consulte <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Entendendo TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Mostra os únicos de 30 dias e a população total de características para cada característica. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Características usando modelo</span> </p> </td>
   <td colname="col2"> <p>Mostra uma lista das características algorítmicas com base no modelo selecionado. Clique em um nome de característica ou ID de característica para obter mais informações sobre a característica. Selecione <b><span class="uicontrol"> Criar nova característica com modelo</span></b> para acessar o processo de criação de característica algorítmica. </p> <p>A etiqueta da seção muda com base no nome do modelo. Por exemplo, digamos que você crie um modelo e o nomeie Modelo A. Quando você carrega a página de resumo, o nome desta seção é alterado para <span class="wintitle"> Características usando o modelo A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Destinos ](../../features/destinations/destinations.md)
>* [Características ](../../features/traits/trait-details-page.md)
>* [Segmentos ](../../features/segments/segments-purpose.md)

