---
description: Crie e gerencie as características ou segmentos usados na modelagem algorítmica, também chamada de modelagem assemelhada. Os recursos do modelo estão localizados em Dados de público-alvo > Modelos.
keywords: peso relativo, sósia
seo-description: Crie e gerencie as características ou segmentos usados na modelagem algorítmica, também chamada de modelagem assemelhada. Os recursos do modelo estão localizados em Dados de público-alvo > Modelos.
seo-title: Sobre Modelos Algorítmicos
solution: Audience Manager
title: Sobre Modelos Algorítmicos
topic: API DIL
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
translation-type: tm+mt
source-git-commit: 73d670225fb4170d02428a1dd163f442540e3415

---


# Sobre Modelos Algorítmicos {#about-algorithmic-models}

Crie e gerencie as características ou segmentos usados na modelagem algorítmica, também chamada de modelagem assemelhada. Os recursos do modelo estão localizados em **[!UICONTROL Audience Data > Models]**.

<!-- c_models.xml -->

## Como entender os modelos algorítmicos {#understanding-models}

As seções abaixo representam uma revisão da modelagem algorítmica em [!DNL Audience Manager]. Eles descrevem como a modelagem funciona, os benefícios e o fluxo de trabalho.

<!-- understanding-models.xml -->

## Localizar novos usuários com modelagem algorítmica {#find-new-users}

A modelagem algorítmica ajuda a descobrir públicos novos e exclusivos por meio da análise automatizada de dados. O processo é iniciado quando você seleciona uma característica ou segmento, um intervalo de tempo e fontes de dados originais e de terceiros. Suas escolhas fornecem as entradas para o modelo algorítmico. Quando o processo de análise é executado, ele procura usuários elegíveis com base em características compartilhadas da população selecionada. Após a conclusão, esses dados estão disponíveis no Construtor [de](../../features/traits/about-trait-builder.md) características, onde você pode usá-los para criar características com base na [precisão e no alcance](../../features/traits/trait-accuracy-reach.md). Além disso, é possível criar segmentos que combinam características algorítmicas com características baseadas em regras e adicionar outros requisitos de qualificação com expressões booleanas e operadores de comparação. A modelagem algorítmica oferece uma maneira dinâmica de extrair valor de todos os dados de características disponíveis.

## Benefícios {#advantages}

Os principais benefícios do uso da [!DNL Audience Manager] modelagem incluem:

* **** Precisão dos dados: O algoritmo é executado regularmente, o que ajuda a manter os resultados atualizados e relevantes.
* **** Automação: Não é necessário gerenciar um grande conjunto de regras estáticas. O algoritmo encontrará públicos para você.
* **** Economize tempo e reduza o esforço: Com nosso processo de modelagem, você não precisa adivinhar quais características/segmentos podem funcionar ou gastar recursos de tempo em campanhas para descobrir novos públicos. O modelo pode fazer isso por você.
* **** Confiabilidade: A modelagem funciona com processos de detecção e qualificação do lado do servidor que avaliam seus próprios dados e dados selecionados de terceiros aos quais você tem acesso. Isso significa que você não precisa ver os visitantes do site para qualificá-los para uma característica.

## Fluxo de trabalho {#workflow}

Você gerencia modelos em **[!UICONTROL Audience Data > Models]**. Em um nível superior, o processo de fluxo de trabalho envolve o seguinte:

* Selecione os dados da linha de base que deseja que o algoritmo avalie. Isso inclui características ou segmentos, intervalo de tempo e fontes de dados (seus próprios dados e dados de terceiros aos quais você já tem acesso [!DNL Audience Manager]). No fluxo de trabalho de criação de modelo, você pode excluir as características que não deseja interferir no modelo.
* Salve seu modelo. Depois de salvo, o processo de avaliação algorítmica é executado automaticamente. Entretanto, observe que esse processo pode levar até 7 dias para ser concluído. [!DNL Audience Manager] envia um email quando o algoritmo terminar e os resultados estiverem disponíveis para a criação de características.
* Crie características algorítmicas em [!UICONTROL Trait Builder].
* Combine características em segmentos em [!UICONTROL Segment Builder].
* Crie e envie dados de segmento para um destino.

## Solução de problemas {#troubleshooting}

Desativamos qualquer modelo algorítmico que não gera dados para três execuções consecutivas. Observe que não é possível definir o status do modelo de volta para ativo depois. Para garantir que seus modelos gerem dados, recomendamos que você crie modelos a partir de fontes de dados com características suficientes para acumular dados a partir delas.

>[!MORE_LIKE_THIS]
>
>* [Destinos](../../features/destinations/destinations.md)
>* [Características](../../features/traits/trait-details-page.md)
>* [Segmentos](../../features/segments/segments-purpose.md)


## Compreensão de TraitWeight {#understanding-traitweight}

[!UICONTROL TraitWeight] é um algoritmo proprietário projetado para descobrir novas características automaticamente. Ele compara os dados de características de seus traços e segmentos atuais com todos os outros dados primários e de terceiros aos quais você tem acesso [!DNL Audience Manager]. Consulte esta seção para obter uma descrição do processo de descoberta de [!UICONTROL TraitWeight] algoritmos.

<!-- traitweight.xml -->

![](assets/algo_model.png)

As etapas a seguir descrevem o processo de [!UICONTROL TraitWeight] avaliação.

### Etapa 1: Criar uma linha de base para comparação de características

Para criar uma linha de base, [!UICONTROL TraitWeight] mede todas as características associadas a um público-alvo por um intervalo de 30, 60 ou 90 dias. Em seguida, classifica traços de acordo com sua frequência e sua correlação. A contagem de frequências mede a uniformidade. A correlação mede a probabilidade de uma característica estar presente apenas no público-alvo de referência. Supõe-se que as características que aparecem com frequência exibem uma elevada compatibilidade, uma característica importante usada para definir uma pontuação ponderada quando combinada com características descobertas em suas fontes de dados selecionadas.

### Etapa 2: Localizar as mesmas características na fonte de dados

Depois de criar uma linha de base para comparação, o algoritmo procura por características idênticas nas fontes de dados selecionadas. Nesta etapa, [!UICONTROL TraitWeight] realiza uma contagem de frequência de todas as características descobertas e as compara à linha de base. No entanto, ao contrário da linha de base, características incomuns são classificadas como maiores do que as que aparecem com mais frequência. Diz-se que traços raros exibem um alto grau de especificidade. [!UICONTROL TraitWeight] avalia as combinações de características de linha de base comuns e características de fonte de dados pouco comuns (altamente específicas) como mais influentes ou desejáveis do que as características comuns a ambos os conjuntos de dados. De fato, nosso modelo reconhece essas grandes características comuns e não atribui prioridade excessiva a conjuntos de dados com altas correlações. Características raras têm prioridade mais alta porque têm mais probabilidade de representar usuários novos e únicos do que características com alta compatibilidade em todos os sentidos.

### Etapa 3: Atribuir peso

Nesse passo, [!UICONTROL TraitWeight] classifica traços recém-descobertos em ordem de influência ou desejabilidade. A escala de peso é uma porcentagem que vai de 0% a 100%. Características classificadas mais próximas a 100% significa que são mais parecidas com o público-alvo na sua população de referência. Além disso, características pesadas são importantes porque representam usuários novos e únicos que podem se comportar de forma semelhante ao público-alvo estabelecido. Lembre-se, [!UICONTROL TraitWeight] considera os traços com alta compatibilidade na linha de base e alta especificidade nas fontes de dados comparadas mais valiosos do que os traços comuns em cada conjunto de dados.

### Etapa 4: Usuários de Pontuação

Cada usuário nas fontes de dados selecionadas recebe uma pontuação do usuário que é igual à soma de todos os pesos das características influentes no perfil do usuário. As pontuações do usuário são normalizadas entre 0 e 100%.

### Etapa 5: Exibir e trabalhar com resultados

O Audience Manager exibe os resultados ponderados do modelo [!UICONTROL Trait Builder]. Quando você deseja criar uma característica algorítmica, [!UICONTROL Trait Builder] permite criar características com base na pontuação ponderada gerada pelo algoritmo durante uma execução de dados. Você pode escolher uma precisão maior para qualificar somente usuários que tenham pontuações muito altas e, portanto, sejam muito semelhantes ao público-alvo da linha de base, em vez do restante do público-alvo. Se quiser atingir um público maior (alcance), você pode diminuir a precisão.

### Etapa 6: Reavaliar a importância de uma característica nos ciclos de processamento

Periodicamente, [!UICONTROL TraitWeight] reavalia a importância de um traço com base no tamanho e mudança na população desse traço. Isso acontece quando o número de usuários qualificados para essa característica aumenta ou diminui com o tempo. Esse comportamento é mais claramente visto em traços que se tornam muito grandes. Por exemplo, suponha que o algoritmo use a característica A para modelagem. À medida que a população do traço A aumenta, [!UICONTROL TraitWeight] reavalia a importância desse traço e pode atribuir uma pontuação menor ou ignorá-lo. Neste caso, o traço A é muito comum ou grande para dizer algo significativo sobre sua população. Depois de [!UICONTROL TraitWeight] reduzir o valor da característica A (ou ignorá-la no modelo), a população do traço algorítmico diminui. A lista de características influentes reflete a evolução da população de referência. Use a lista de características influentes para entender por que essas alterações estão ocorrendo.

Links relacionados:

* [Construtor de modelos](../../features/algorithmic-models/create-model.md)
* [Precisão e alcance](../../features/traits/trait-accuracy-reach.md)

## Atualizar Programação para Modelos e Características Algorítmicas {#update-schedule}

Criação e atualização de agendamentos para modelos e características algorítmicas novos ou existentes.

<!-- c_model_update_schedule.xml -->

### Criação e atualização do modelo algorítmico

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
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 17 h EST (novembro - março) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 18 PM EDT (março - novembro) </li> 
     </ul> </p> <p>Os modelos construídos ou clonados após o prazo de criação são processados no dia seguinte. </p> <p>Se a primeira execução de um modelo não gerar dados, ele será executado uma segunda vez, no dia seguinte. Se a segunda tentativa também não gerar dados, haverá uma terceira tentativa, no dia seguinte. O modelo parará de ser executado se a terceira tentativa também não gerar dados. Nesse caso, desativaremos o modelo. Consulte mais em <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Solução de problemas de modelos</a>algorítmicos. </p> </td>
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

### Criação e atualização de características algorítmicas

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

## Exibição de lista de modelos {#models-list-view}

A exibição de lista é um espaço de trabalho central que ajuda a criar, revisar e gerenciar modelos.

<!-- c_models_list_view.xml -->

A página de lista Modelos contém recursos e ferramentas que ajudam a:

* Crie novos modelos.
* Gerenciar modelos existentes (editar, pausar, excluir ou clonar).
* Procure modelos por nome.
* Crie características algorítmicas usando qualquer modelo.

## Exibição de resumo de modelos {#models-summary-view}

A página de resumo exibe detalhes do modelo, como nome, alcance/precisão, histórico de processamento e características criadas a partir do modelo. A página também inclui configurações que permitem criar e gerenciar modelos. Clique em um nome de modelo na lista de resumo para ver seus detalhes.

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
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Lista as 50 principais características influentes que são melhor representadas na população da linha de base do modelo. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Classifica cada traço em ordem de sua classificação de peso <span class="wintitle"></span> relativo. O peso <span class="wintitle"> relativo</span> classifica os traços recém-descobertos em ordem de influência ou desejabilidade. A escala de peso é uma porcentagem que vai de 0% a 100%. Características classificadas mais próximas a 100% significa que são mais parecidas com o público-alvo na sua população de referência. Consulte <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Entendendo TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Mostra os únicos de 30 dias e a população total de características para cada característica. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Características usando modelo</span> </p> </td>
   <td colname="col2"> <p>Mostra uma lista das características algorítmicas com base no modelo selecionado. Clique em um nome de característica ou ID de característica para obter mais informações sobre a característica. Selecione <b><span class="uicontrol"> Criar nova característica com modelo</span></b> para acessar o processo de criação de característica algorítmica. </p> <p>A etiqueta da seção muda com base no nome do modelo. Por exemplo, digamos que você crie um modelo e o nomeie Modelo A. Quando você carrega a página de resumo, o nome desta seção é alterado para <span class="wintitle"> Características usando o modelo A</span>. </p> </td>
  </tr>
 </tbody>
</table>