---
description: Crie e gerencie as características ou os segmentos usados na modelagem por semelhança.
keywords: peso relativo, semelhante
seo-description: Build and manage the traits or segments used in look-alike modeling.
seo-title: About Look-Alike Modeling
solution: Audience Manager
title: Sobre a modelagem semelhante
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
exl-id: a24b11ce-6087-4095-a6c2-6815e2211ba5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1602'
ht-degree: 0%

---

# Compreendendo [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Localizar Novos Usuários com [!UICONTROL Look-Alike Modeling] {#find-new-users}

O [!UICONTROL Look-Alike Modeling] ajuda você a descobrir públicos novos e exclusivos por meio da análise de dados automatizada. O processo é iniciado quando você seleciona um [!UICONTROL trait] ou [!UICONTROL segment], um intervalo de tempo e [!UICONTROL data sources] próprio e de terceiros. Suas opções fornecem as entradas para o modelo algorítmico. Quando o processo de análise é executado, ele procura usuários qualificados com base em características compartilhadas da população selecionada. Após a conclusão, esses dados estarão disponíveis no [Construtor de características](../../features/traits/about-trait-builder.md), onde você poderá usá-los para criar características com base na [precisão e no alcance](../../features/traits/trait-accuracy-reach.md). Além disso, você pode criar segmentos que combinam características algorítmicas com [!UICONTROL rules-based traits] e adicionar outros requisitos de qualificação com [!DNL Boolean] expressões e operadores de comparação. [!UICONTROL Look-Alike Modeling] oferece uma maneira dinâmica de extrair valor de todos os dados de características disponíveis.

## Benefícios {#advantages}

Os principais benefícios de usar o [!UICONTROL Look-Alike Modeling] incluem:

* **Precisão dos dados:** o algoritmo é executado regularmente, o que ajuda a manter os resultados atuais e relevantes.
* **Automação:** não é necessário gerenciar um grande conjunto de regras estáticas. O algoritmo encontrará públicos-alvo para você.
* **Economize tempo e reduza o esforço:** com nosso processo de modelagem, você não precisa adivinhar o que [!UICONTROL traits]/[!UICONTROL segments] pode dar certo ou gastar tempo em campanhas para descobrir novos públicos. O modelo pode fazer isso para você.
* **Confiabilidade:** a modelagem funciona com processos de descoberta e qualificação do lado do servidor que avaliam seus próprios dados e os dados de terceiros selecionados aos quais você tem acesso. Isso significa que você não precisa ver os visitantes do site para qualificá-los para uma característica.

## Fluxo de trabalho (WRK) {#workflow}

Você gerencia modelos em **[!UICONTROL Audience Data > Models]**. Em um nível superior, o processo de workflow envolve o seguinte:

* Selecione os dados da linha de base que você deseja que o algoritmo avalie. Isso inclui um [!UICONTROL trait] ou [!UICONTROL segment], intervalo de tempo e [!UICONTROL data sources] (seus próprios dados e dados de terceiros aos quais você já tem acesso até [!DNL Audience Manager]). No fluxo de trabalho de criação do modelo, você pode excluir o [!UICONTROL traits] que não deseja que interfira no modelo.
* Salve seu modelo. Depois de salvo, o processo de avaliação algorítmica é executado automaticamente. No entanto, observe que pode levar até 7 dias para que esse processo seja concluído. [!DNL Audience Manager] envia um email quando o algoritmo é concluído e os resultados estão disponíveis para a criação de [!UICONTROL trait].
* Compilação algorítmica [!UICONTROL traits] em [!UICONTROL Trait Builder].
* Combinar [!UICONTROL traits] em [!UICONTROL segments] em [!UICONTROL Segment Builder].
* Criar e enviar dados de [!UICONTROL segment] para um [!UICONTROL destination].

## Solução de problemas {#troubleshooting}

Desativamos qualquer [!UICONTROL Look-Alike Model] que não consiga gerar dados para três execuções consecutivas. Observe que não é possível definir o status do modelo novamente como ativo posteriormente. Para garantir que seus modelos gerem dados, recomendamos que você compile modelos de fontes de dados com [!UICONTROL traits] suficiente para acumular dados do.

## Compreendendo [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] é um algoritmo proprietário projetado para descobrir novos [!UICONTROL traits] automaticamente. Ele compara os dados do [!UICONTROL trait] dos [!UICONTROL traits] e do [!UICONTROL segments] atuais com todos os outros dados primários e de terceiros aos quais você tem acesso por meio do [!DNL Audience Manager]. Consulte esta seção para obter uma descrição do processo de descoberta algorítmica do [!UICONTROL TraitWeight].

![](assets/algo_model.png)

As etapas a seguir descrevem o processo de avaliação [!UICONTROL TraitWeight].

### Etapa 1: Criar uma Linha de Base para Comparação de [!UICONTROL Trait]

Para criar uma linha de base, [!UICONTROL TraitWeight] mede todos os [!UICONTROL traits] associados a um público-alvo para um intervalo de 30, 60 ou 90 dias. Em seguida, ele classifica [!UICONTROL traits] de acordo com sua frequência e sua correlação. A contagem de frequência mede a compatibilidade. A correlação mede a probabilidade de um [!UICONTROL trait] estar presente somente no público da linha de base. Diz-se que os [!UICONTROL Traits] que aparecem com frequência exibem alta semelhança, uma característica importante usada para definir uma pontuação ponderada quando combinada com [!UICONTROL traits] descobertos no [!UICONTROL data sources] selecionado.

### Etapa 2: Localizar o Mesmo [!UICONTROL Traits] no [!UICONTROL Data Source]

Depois de criar uma linha de base para comparação, o algoritmo procurará por [!UICONTROL traits] idêntico na [!UICONTROL data sources] selecionada. Nesta etapa, o [!UICONTROL TraitWeight] executa uma contagem de frequência de todos os [!UICONTROL traits] descobertos e os compara à linha de base. No entanto, ao contrário da linha de base, os [!UICONTROL traits] incomuns estão classificados acima daqueles que aparecem com mais frequência. Raros [!UICONTROL traits] exibem um alto grau de especificidade. [!UICONTROL TraitWeight] avalia as combinações de [!UICONTROL traits] de linha de base comum e [!UICONTROL data source] [!UICONTROL traits] incomum (altamente específico) como mais influentes ou desejáveis do que [!UICONTROL traits] comuns a ambos os conjuntos de dados. Na verdade, nosso modelo reconhece esses [!UICONTROL traits] grandes e comuns e não atribui prioridade em excesso a conjuntos de dados com correlações altas. Raros [!UICONTROL traits] obtêm prioridade mais alta porque têm mais probabilidade de representar usuários novos e exclusivos do que [!UICONTROL traits] com alta compatibilidade em todos os níveis.

### Etapa 3: Atribuir Peso

Nesta etapa, [!UICONTROL TraitWeight] classifica o [!UICONTROL traits] recém-descoberto em ordem de influência ou desejabilidade. A escala de peso é uma porcentagem que vai de 0% a 100%. [!UICONTROL Traits] classificado mais próximo de 100% significa que é mais parecido com o público da sua população da linha de base. Além disso, os [!UICONTROL traits] com alto peso são importantes porque representam usuários novos e exclusivos que podem se comportar de forma semelhante ao seu público-alvo estabelecido na linha de base. Lembre-se, o [!UICONTROL TraitWeight] considera [!UICONTROL traits] com alta similaridade na linha de base e alta especificidade nas fontes de dados comparadas mais valioso que [!UICONTROL traits] comum em cada conjunto de dados.

### Etapa 4: Pontuação de usuários

A cada usuário na [!UICONTROL data sources] selecionada é dada uma pontuação de usuário que é igual à soma de todos os pesos da [!UICONTROL traits] influente no perfil desse usuário. As pontuações do usuário são normalizadas entre 0 e 100%.

### Etapa 5: exibir e trabalhar com resultados

[!DNL Audience Manager] exibe seus resultados de modelo ponderados em [!UICONTROL Trait Builder]. Quando quiser criar um [!UICONTROL algorithmic trait], o [!UICONTROL Trait Builder] permite criar [!UICONTROL traits] com base na pontuação ponderada gerada pelo algoritmo durante uma execução de dados. Você pode escolher uma precisão mais alta para qualificar apenas os usuários que têm pontuações de usuário muito altas e, portanto, são muito semelhantes ao público-alvo da linha de base, em vez do restante do público-alvo. Se você quiser alcançar um público maior (alcance), diminua a precisão.

### Etapa 6: reavalie a significância de um [!UICONTROL Trait] nos ciclos de processamento

Periodicamente, [!UICONTROL TraitWeight] reavalia a importância de um [!UICONTROL trait] com base no tamanho e na alteração na população desse [!UICONTROL trait]. Isso acontece quando o número de usuários qualificados para esse [!UICONTROL trait] aumenta ou diminui com o tempo. Esse comportamento é visto com mais clareza em características que se tornam muito grandes. Por exemplo, suponha que o algoritmo use [!UICONTROL trait A] para modelagem. À medida que a população de [!UICONTROL trait A] aumenta, [!UICONTROL TraitWeight] reavalia a importância desse [!UICONTROL trait] e pode atribuir uma pontuação mais baixa ou ignorá-la. Neste caso, [!UICONTROL trait A] é muito comum ou grande para dizer algo significativo sobre sua população. Depois que [!UICONTROL TraitWeight] reduz o valor de [!UICONTROL trait A] (ou ignora no modelo), a população da característica algorítmica diminui. A lista de [!UICONTROL traits] influentes reflete a evolução da população da linha de base. Use a lista de [!UICONTROL traits] influentes para entender por que essas alterações estão ocorrendo.

Links relacionados:

* [Construtor de modelos](../../features/algorithmic-models/create-model.md)
* [Precisão e alcance](../../features/traits/trait-accuracy-reach.md)

## Atualizar Calendário para [!UICONTROL Look-Alike Models] e [!UICONTROL Traits] {#update-schedule}

Agendamentos de criação e atualização para [!UICONTROL algorithmic models] e [!UICONTROL traits] novos ou existentes.

### Agendamento de Criação e Atualização do [!UICONTROL Look-Alike Model]

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
   <td colname="col2"> <p>Para [!UICONTROL Look-Alike Models] novos ou clonados, o processo de criação é executado uma vez por dia às: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 17h EST (novembro - março) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 18h EDT (março - novembro) </li> 
     </ul> </p> <p>Os modelos criados ou clonados após o prazo de criação são processados no dia seguinte. </p> <p>Se a primeira execução de um modelo não gerar dados, ele será executado uma segunda vez, no dia seguinte. Se a segunda tentativa também não gerar dados, haverá uma terceira tentativa, no dia seguinte. O modelo parará de ser executado se a terceira tentativa também não gerar dados. Nesse caso, desativaremos o modelo. Veja mais em <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Solução de Problemas de Modelos Semelhantes</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Atualizar um Modelo</b> </td> 
   <td colname="col2"> <p>Sob condições ideais, os modelos existentes são executados em dias da semana, pelo menos uma vez a cada 7 dias. Por exemplo, se você criar um modelo (pelo prazo) na segunda-feira, ele atualizará a segunda-feira seguinte o mais tardar. </p> <p>Um modelo será executado novamente se atender a qualquer uma das seguintes condições: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Sua última execução não foi bem-sucedida. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Foi executado com sucesso antes DE E não foi executado nos últimos 7 dias E o modelo tem pelo menos uma característica ativa anexada a ele. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Agendamento de Criação e Atualização do [!UICONTROL Look-Alike Trait]

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
   <td colname="col1"> <b>Atualizar uma Característica</b> </td> 
   <td colname="col2"> <p>As características existentes são atualizadas pelo menos uma vez a cada 7 dias e seguem a programação para atualizações de modelo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exibição da lista de modelos {#models-list-view}

A exibição de lista é um espaço de trabalho central que ajuda você a criar, revisar e gerenciar modelos.

A página da lista [!UICONTROL Models] contém recursos e ferramentas que ajudam você a:

* Criar novos modelos.
* Gerenciar modelos existentes (editar, pausar, excluir ou clonar).
* Procure modelos por nome.
* Criar [!UICONTROL algorithmic traits] usando qualquer modelo fornecido.

## Exibição do resumo dos modelos {#models-summary-view}

A página de resumo exibe detalhes do modelo, como nome, alcance/precisão, histórico de processamento e [!UICONTROL traits] criado a partir do modelo. A página também inclui configurações que permitem criar e gerenciar modelos. Clique em um nome de modelo na lista de resumo para ver seus detalhes.

A página de resumo do modelo inclui as seções a seguir.

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Seção </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle"> Informações Básicas</span> </p> </td>
   <td colname="col2"> <p>Inclui informações básicas sobre o modelo, como seu nome e quando foi executado pela última vez. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Precisão e Alcance do Modelo</span> </p> </td> 
   <td colname="col2"> <p>Mostra dados de <a href="../../features/traits/trait-accuracy-reach.md"> precisão e alcance</a> para a última execução do modelo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Histórico de Processamento de Modelo</span> </p> </td> 
   <td colname="col2"> <p>Exibe a data e a hora do processamento das últimas 10 execuções e se os dados foram gerados nessas execuções. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Características influentes</span> </p> </td> 
   <td colname="col2"> <p>A tabela <span class="wintitle"> Características Influentes</span>: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Lista as 50 características influentes mais bem representadas na população da linha de base do modelo. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Classifica cada característica na ordem de sua classificação <span class="wintitle"> Peso relativo</span>. O <span class="wintitle"> Peso Relativo</span> classifica as características recém-descobertas em ordem de influência ou desejabilidade. A escala de peso é uma porcentagem que vai de 0% a 100%. As características classificadas mais próximas de 100% significam que são mais semelhantes ao público-alvo na população da linha de base. Consulte <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Entendendo TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Mostra os únicos de 30 dias e a população total de características de cada característica. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Características Usando Modelo</span> </p> </td>
   <td colname="col2"> <p>Mostra uma lista de características algorítmicas com base no modelo selecionado. Clique em um nome de característica ou ID de característica para obter mais informações sobre a característica. Selecione <b><span class="uicontrol"> Criar nova característica com modelo</span></b> para ir para o processo de criação de característica algorítmica. </p> <p>O rótulo da seção muda com base no nome do seu modelo. Por exemplo, digamos que você crie um modelo e o nomeie como Modelo A. Quando você carrega a página de resumo, o nome desta seção é alterado para <span class="wintitle"> Características usando o Modelo A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Destinos](../../features/destinations/destinations.md)
>* [Características](../../features/traits/trait-details-page.md)
>* [Segmentos](../../features/segments/segments-purpose.md)
