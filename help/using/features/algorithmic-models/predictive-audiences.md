---
description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-title: Visão geral dos públicos preditivos
solution: Audience Manager
title: Públicos preditivos do Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 3c39ef38d2833d5d706641f70649251d79b2ee6f
workflow-type: tm+mt
source-wordcount: '1511'
ht-degree: 8%

---


# [!UICONTROL Predictive Audiences] Visão geral {#predictive-audiences}

[!UICONTROL Predictive Audiences] ajuda a classificar uma audiência desconhecida em personas distintas, em tempo real, usando técnicas avançadas de ciência de dados.

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo durante a configuração e o uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

Em um contexto de marketing, uma pessoa é um segmento de público-alvo definido por visitantes, usuários ou possíveis compradores, que compartilham um conjunto específico de características, como demografia, hábitos de navegação, histórico de compras etc.

Os modelos de [!UICONTROL Predictive Audiences] levam esse conceito um passo além, permitindo que você use os recursos de aprendizado de máquina do Audience Manager para classificar públicos desconhecidos em personas distintas. O Audience Manager ajuda você a fazer isso calculando a propensão do seu público primário desconhecido para um conjunto de públicos originais conhecidos.

Quando você cria um modelo [!UICONTROL Predictive Audiences], a primeira etapa é escolher as características da linha de base ou os segmentos pelos quais deseja que a audiência do público alvo seja classificada. Essas características ou segmentos definirão suas personas.

Durante a fase de avaliação, o modelo cria um novo segmento [!UICONTROL Predictive Audiences] para cada característica ou segmento definido como linha de base. Na próxima vez que o Audience Manager ver um visitante de sua audiência de público alvo que não esteja classificado para uma persona (não se qualificou para nenhuma de suas características ou segmentos de linha de base), o modelo [!UICONTROL Predictive Audiences] determinará a qual dos segmentos preditivos o visitante deve pertencer e adicionará o visitante a esse segmento.

Você pode identificar os segmentos preditivos criados pelo modelo, na página [!UICONTROL Segments]. Cada modelo [!UICONTROL Predictive Audiences] tem sua própria pasta na pasta [!UICONTROL Predictive Audiences] e você pode ver os segmentos de cada modelo clicando na pasta do modelo.

![segmentos de audiências preditivas](assets/predictive-audiences-segments.png)

## Casos de uso {#use-cases}

Para ajudá-lo a entender melhor como e quando você pode usar [!UICONTROL Predictive Audiences], veja alguns casos de uso que os clientes do Audience Manager podem resolver usando esse recurso.

### Caso de uso nº 1

Como comerciante em uma empresa de comércio eletrônico, eu quero classificar todos os meus visitantes móveis e da Web em várias categorias de afinidade de marca, para que eu possa personalizar a experiência do usuário.

### Caso de uso nº 2

Como profissional de marketing em uma empresa de mídia, eu quero classificar meus visitantes móveis e da Web não autenticados por gêneros favoritos, para que eu possa sugerir a eles conteúdo personalizado em todos os canais.

### Caso de uso nº 3

Como anunciante de uma empresa aérea, quero me certificar de classificar minha audiência com base no interesse deles em destinos de viagens, para que eu possa anunciar a eles em tempo real, dentro de uma pequena janela de redefinição de metas.

### Caso de uso nº 4

Como anunciante, quero classificar minha audiência em tempo real, para que eu possa reagir rapidamente às notícias de tendências.

### Caso de uso nº 5

Como profissional de marketing, quero prever em qual fase da jornada do cliente meus visitantes do site estão, como descoberta, envolvimento, compra ou retenção, para que eu possa público alvo-los de acordo.

### Caso de uso nº 6

Como empresa de mídia, eu quero categorizar minha audiência, para que eu possa vender meu espaço publicitário com preços premium, ao mesmo tempo em que ofereço aos meus visitantes anúncios relevantes.

## Como os modelos [!UICONTROL Predictive Audiences] funcionam {#how-predictive-audiences-models-work}

Ao criar um modelo [!UICONTROL Predictive Audiences], você percorre três etapas:

1. Primeiro, selecione um mínimo de duas características ou dois segmentos que definirão suas personas.
1. Em seguida, escolha uma característica ou segmento que defina a audiência do público alvo que deseja classificar.
1. Finalmente, você escolhe um nome para o modelo, uma fonte de dados que armazenará os segmentos preditivos e um [!UICONTROL Profile Merge Rule] para o modelo.

### Critérios de seleção para personas {#selection-personas}

Você pode escolher quaisquer características ou segmentos originais para definir suas personas. No entanto, para obter os melhores resultados, veja um conjunto de práticas recomendadas:

* Escolha seus traços pessoais ou segmentos para que cada pessoa tenha pelo menos algumas centenas [IDs de dispositivo](../../reference/ids-in-aam.md).
* Se suas características forem baseadas em [IDs de dispositivo cruzado](../../reference/ids-in-aam.md), você poderá vinculá-las em segmentos com [Regras de mesclagem de Perfis](../profile-merge-rules/merge-rules-overview.md) que usam [IDs de dispositivo](../../reference/ids-in-aam.md), como [!UICONTROL Device Graph]. Isso garantirá que haja [IDs de dispositivo](../../reference/ids-in-aam.md) suficientes para que o algoritmo possa aprender.
* Recomendamos escolher características ou segmentos simples para suas personas, que consistem de 1 a 3 características.
* Escolha características da linha de base ou segmentos que tenham sobreposição mínima.
* Certifique-se de capturar características granulares em suas propriedades digitais.

### Critérios de seleção para Audiência de Público alvo {#selection-audience}

Dependendo do caso de uso, se você deseja classificar os usuários em tempo real, em lote ou em ambos, escolha uma audiência de público alvo ([!UICONTROL trait] ou [!UICONTROL segment]) que tenha uma população significativa em tempo real e/ou total. Semelhante à seleção pessoal, recomendamos que sua audiência de públicos alvos [!UICONTROL trait] ou [!UICONTROL segment] tenha usuários com perfis ricos (conjuntos ricos de [!UICONTROL traits]).

Ao selecionar a audiência do público alvo, analise seu caso de uso e decida quais tipos de IDs você deseja classificar: [!UICONTROL device IDs] ou [!UICONTROL cross-device IDs]. O [!UICONTROL Profile Merge Rule] que você seleciona ao criar o modelo define os dados que serão usados para colocar cada usuário no preditivo [!UICONTROL segments].

Como prática recomendada, recomendamos escolher um [!UICONTROL Profile Merge Rule] que tenha a mesma configuração que sua audiência de público alvo [!UICONTROL Profile Merge Rule], ou que inclua o tipo de perfil (perfil de dispositivo ou perfil autenticado) de sua audiência de público alvo.

### [!UICONTROL Predictive Audiences] Fase de treinamento do modelo  {#model-training}

Antes que o algoritmo possa classificar sua audiência primária nas pessoas certas, ele precisa treinar a si mesmo nos seus dados.

Para cada persona definida, o algoritmo analisa sua respectiva audiência e avalia qualquer atividade de característica em tempo real e/ou integrada para seus usuários nos últimos 30 dias.
Esta etapa ocorre uma vez a cada 24 horas, para levar em conta as alterações na audiência primária.

### [!UICONTROL Predictive Audiences] Fase de classificação do modelo  {#model-classification}

Para a classificação de audiência em tempo real e em lote, o modelo verifica primeiro se um usuário pertence à audiência do público alvo. Se o usuário se qualificar para a audiência do público alvo e não pertencer a nenhuma das pessoas, o modelo atribuirá uma pontuação de qualificação pessoal.

Ao avaliar audiências primárias e atribuir pontuações, o modelo usa o padrão **[!UICONTROL Profile Merge Rule]** definido em sua conta. Por fim, o visitante é classificado na pessoa para a qual recebeu a pontuação mais alta.

![predictivo-audiências-gráfico](assets/predictive-audiences-graph.png)

## Considerações e limitações {#considerations}

>[!IMPORTANT]
> Leia atentamente esta seção antes de passar para a fase de implementação.

Ao configurar seus modelos [!UICONTROL Predictive Audiences], lembre-se das seguintes considerações e limitações:

* Você pode criar até 10 modelos de [!UICONTROL Predictive Audiences]. 
* Para cada modelo, você pode escolher até 50 características/segmentos básicos.
* Os dados de segundo e terceiro não são suportados atualmente em [!UICONTROL Predictive Audiences].
* [!UICONTROL Predictive Audiences] executa a classificação de audiência com base nas características originais, de todas as fontes de dados originais.
* A avaliação de segmento para [!UICONTROL Predictive Audiences] usa **[!UICONTROL Profile Merge Rule]** que você escolheu durante a criação do modelo. Para saber mais sobre [!UICONTROL Profile Merge Rules] consulte a [documentação dedicada](../profile-merge-rules/merge-rules-overview.md).
* Algumas características e segmentos não são suportados como audiências de linha de base ou públicos alvos. [!UICONTROL Predictive Audiences] os modelos não serão salvos ao escolher uma das seguintes opções como linhas de base ou audiências de público alvo:
   * Características preditivas e segmentos criados com características preditivas;
   * [Características ou segmentos ](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) das plataformas Adobe Experience;
   * Características algorítmicas;
   * Características de segundo e terceiro.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] não pode ser usado em  [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

Segmentos preditivos criados pelos modelos [!UICONTROL Predictive Audiences] herdam os [Controles de exportação de dados](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) das seguintes fontes de dados originais:

1. A fonte de dados primária escolhida ao criar o modelo.
1. As fontes de dados primários da audiência do público alvo. Especificamente, os controles de exportação de dados de [!UICONTROL traits] ou [!UICONTROL segments] que compõem sua audiência de público alvo.
1. Os [Controles de exportação de dados](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) de [!UICONTROL Profile Merge Rule] que você selecionou para o modelo.

As preditivas recém-criadas [!UICONTROL traits] e [!UICONTROL segments] terão as mesmas restrições de privacidade que a união das fontes de dados originais descritas acima.

Características que têm restrições adicionais que não fazem parte das [!UICONTROL Predictive Audiences] restrições de privacidade do segmento serão excluídas da fase de treinamento e não se tornarão influentes para o modelo.

## [!UICONTROL Profile Merge Rules] {#pmr}

Todos os segmentos preditivos receberão o [!UICONTROL Profile Merge Rule] que você selecionou ao criar o modelo. O [!UICONTROL Profile Merge Rule] escolhido é importante pelos seguintes motivos:

* Ele define quais dispositivos e/ou perfis autenticados devem ser considerados quando o modelo analisa o [!UICONTROL traits] influente, no momento da classificação de um usuário em um [!UICONTROL segment] preditivo.
* Ele regula quais [!UICONTROL trait] tipos (nível de dispositivo ou nível entre dispositivos) devem ser usados durante a etapa de treinamento do modelo e surgiram como influentes [!UICONTROL traits]. Preditivo [!UICONTROL segments] são subconjuntos da audiência do público alvo.
   * Se a audiência do público alvo for um segmento, recomendamos que você selecione o mesmo [!UICONTROL Profile Merge Rule] para o modelo atribuído à audiência do público alvo, ou um [!UICONTROL Profile Merge Rule] que inclua o tipo de perfil da audiência do público alvo.
   * Se a audiência do público alvo for [!UICONTROL trait], recomendamos que você selecione um [!UICONTROL Profile Merge Rule] que possa acessar o mesmo tipo de dados que a característica de audiência do público alvo (dados de perfil do dispositivo ou dados de perfil entre dispositivos).
* [!UICONTROL Profile Merge Rules] o uso  [!UICONTROL Current Authenticated Profiles] e  [!UICONTROL No Device Profile] as opções são suportados apenas para classificação de audiência em tempo real. Para obter mais informações, consulte [Opções de Regras de Mesclagem de Perfis Definidas](../profile-merge-rules/merge-rule-definitions.md).

A seleção de [!UICONTROL Profile Merge Rule] que usa dados de dispositivo e dados entre dispositivos maximiza o número de [!UICONTROL traits] que podem ser usados para treinamento de modelo e classificação de usuário no preditivo [!UICONTROL segments].

## [!UICONTROL Role-Based Access Controls] {#rbac}

As características e os segmentos escolhidos para a classificação de audiências e personas estão sujeitos a Audience Manager [Controles de acesso baseados em função](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html).

Os usuários do Audience Manager só podem selecionar características ou segmentos para audiências e públicos alvos, que têm [permissão para visualização](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
