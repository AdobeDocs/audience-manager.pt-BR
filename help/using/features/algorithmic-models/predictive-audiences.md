---
description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-title: Visão geral dos públicos preditivos
solution: Audience Manager
title: Públicos preditivos do Audience Manager
feature: Modelos algorítmicos
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1505'
ht-degree: 8%

---

# [!UICONTROL Predictive Audiences] Visão geral {#predictive-audiences}

[!UICONTROL Predictive Audiences] O ajuda a classificar um público-alvo desconhecido em personas distintas, em tempo real, usando técnicas avançadas de ciência de dados.

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e uso deste recurso. Nada neste documento é de aconselhamento jurídico. Consulte o seu advogado para obter orientação jurídica.

Em um contexto de marketing, uma pessoa é um segmento de público-alvo definido por visitantes, usuários ou possíveis compradores, que compartilham um conjunto específico de características, como demografia, hábitos de navegação, histórico de compras etc.

Os modelos de [!UICONTROL Predictive Audiences] levam esse conceito um passo além, permitindo que você use os recursos de aprendizado de máquina do Audience Manager para classificar públicos desconhecidos em personas distintas. O Audience Manager ajuda você a fazer isso calculando a propensão do seu público primário desconhecido para um conjunto de públicos originais conhecidos.

Ao criar um modelo [!UICONTROL Predictive Audiences], a primeira etapa é escolher as características ou segmentos da linha de base pelos quais deseja que o público-alvo seja classificado. Essas características ou segmentos definirão suas personas.

Durante a fase de avaliação, o modelo cria um novo segmento [!UICONTROL Predictive Audiences] para cada característica ou segmento que você definiu como linha de base. Na próxima vez que o Audience Manager visualizar um visitante do público-alvo que não está classificado para uma persona (não se qualificou para nenhuma de suas características ou segmentos de linha de base), o modelo [!UICONTROL Predictive Audiences] determinará a qual dos segmentos preditivos o visitante deve pertencer e adicionará o visitante a esse segmento.

Você pode identificar os segmentos preditivos criados pelo modelo, na página [!UICONTROL Segments] . Cada modelo [!UICONTROL Predictive Audiences] tem sua própria pasta na pasta [!UICONTROL Predictive Audiences] e você pode ver os segmentos de cada modelo clicando na pasta de modelo.

![segmentos preditivos-públicos-alvo](assets/predictive-audiences-segments.png)

## Casos de uso {#use-cases}

Para ajudá-lo a entender melhor como e quando você poderia usar [!UICONTROL Predictive Audiences], aqui estão alguns casos de uso que os clientes do Audience Manager podem resolver usando esse recurso.

### Caso de uso nº 1

Como profissional de marketing em uma empresa de comércio eletrônico, desejo classificar todos os visitantes da Web e de dispositivos móveis em várias categorias de afinidade de marca, para que possa personalizar a experiência do usuário.

### Caso de uso nº 2

Como profissional de marketing em uma empresa de mídia, desejo classificar meus visitantes móveis e da Web não autenticados por gêneros favoritos, para que possa sugerir a eles conteúdo personalizado em todos os canais.

### Caso de uso nº 3

Como anunciante de uma companhia aérea, quero certificar-me de classificar meu público com base em seu interesse em destinos de viagens, para que eu possa anunciar a eles em tempo real, dentro de uma pequena janela de redirecionamento.

### Caso de uso nº 4

Como anunciante, quero classificar meu público primário em tempo real, para que eu possa reagir rapidamente às tendências das notícias.

### Caso de uso nº 5

Como comerciante, eu desejo prever em qual fase de jornada do cliente meus visitantes de site estão, como descoberta, envolvimento, compra ou retenção, para que eu possa direcioná-los adequadamente.

### Caso de uso nº 6

Como empresa de mídia, eu quero categorizar meu público-alvo, para que eu possa vender meu espaço publicitário por preços premium, oferecendo aos meus visitantes anúncios relevantes.

## Como funcionam os modelos [!UICONTROL Predictive Audiences] {#how-predictive-audiences-models-work}

Ao criar um modelo [!UICONTROL Predictive Audiences], você passa por três etapas:

1. Primeiro, selecione um mínimo de duas características ou dois segmentos que definirão suas personas.
1. Em seguida, escolha uma característica ou segmento que defina o público-alvo que deseja classificar.
1. Finalmente, você escolhe um nome para o modelo, uma fonte de dados que armazenará os segmentos preditivos e um [!UICONTROL Profile Merge Rule] para o modelo.

### Critérios de seleção para personas {#selection-personas}

Você pode escolher qualquer uma das características ou segmentos primários para definir suas personas. No entanto, para obter os melhores resultados, veja um conjunto de práticas recomendadas:

* Escolha suas características ou segmentos de persona para que cada persona tenha pelo menos algumas centenas [IDs de dispositivo](../../reference/ids-in-aam.md).
* Se suas características forem baseadas em [IDs entre dispositivos](../../reference/ids-in-aam.md), você poderá vinculá-las em segmentos com [Regras de mesclagem de perfis](../profile-merge-rules/merge-rules-overview.md) que usam [IDs de dispositivo](../../reference/ids-in-aam.md), como [!UICONTROL Device Graph]. Isso garantirá que haja [IDs de dispositivo](../../reference/ids-in-aam.md) suficientes para que o algoritmo possa aprender.
* Recomendamos escolher características ou segmentos simples para suas personas, consistindo em 1 a 3 características.
* Escolha características ou segmentos da linha de base que tenham sobreposição mínima.
* Certifique-se de capturar características granulares em suas propriedades digitais.

### Critérios de seleção para o público-alvo {#selection-audience}

Dependendo do caso de uso, se você deseja classificar os usuários em tempo real, em lote ou ambos, escolha um público-alvo ([!UICONTROL trait] ou [!UICONTROL segment]) que tenha uma população significativa em tempo real e/ou total. Semelhante à seleção de persona, recomendamos que seu público-alvo [!UICONTROL trait] ou [!UICONTROL segment] tenha usuários com perfis avançados (conjuntos avançados de [!UICONTROL traits]).

Ao selecionar o público-alvo, analise seu caso de uso e decida quais tipos de IDs você deseja classificar: [!UICONTROL device IDs] ou [!UICONTROL cross-device IDs]. O [!UICONTROL Profile Merge Rule] selecionado ao criar o modelo define os dados que serão usados para colocar cada usuário no [!UICONTROL segments] preditivo.

Como prática recomendada, recomendamos escolher um [!UICONTROL Profile Merge Rule] que tenha a mesma configuração que seu público-alvo [!UICONTROL Profile Merge Rule], ou que inclua o tipo de perfil (perfil do dispositivo ou perfil autenticado) do seu público-alvo.

### [!UICONTROL Predictive Audiences] Fase de treinamento do modelo {#model-training}

Antes que o algoritmo possa classificar seu público primário nas personas certas, ele precisa treinar seus dados.

Para cada persona definida, o algoritmo analisa seu respectivo público-alvo e avalia qualquer atividade de característica integrada e/ou em tempo real para seus usuários nos últimos 30 dias.
Essa etapa ocorre uma vez a cada 24 horas, para levar em conta as alterações no público-alvo próprio.

### [!UICONTROL Predictive Audiences] Fase de classificação do modelo {#model-classification}

Para a classificação de público-alvo em tempo real e em lote, o modelo verifica primeiro se um usuário pertence ao público-alvo. Se o usuário se qualificar para o público-alvo e não pertencer a nenhuma das personas, o modelo atribui a ele uma pontuação de qualificação de persona.

Ao avaliar públicos primários e atribuir pontuações, o modelo usa o **[!UICONTROL Profile Merge Rule]** padrão definido em sua conta. Finalmente, o visitante é classificado na persona para a qual recebeu a pontuação mais alta.

![gráfico de públicos-alvo preditivos](assets/predictive-audiences-graph.png)

## Considerações e limitações {#considerations}

>[!IMPORTANT]
> Leia atentamente esta seção antes de passar para a fase de implementação.

Ao configurar seus modelos [!UICONTROL Predictive Audiences], lembre-se das seguintes considerações e limitações:

* Você pode criar até 10 modelos de [!UICONTROL Predictive Audiences]. 
* Para cada modelo, você pode escolher até 50 características/segmentos básicos.
* Dados secundários e de terceiros não são suportados atualmente em [!UICONTROL Predictive Audiences].
* [!UICONTROL Predictive Audiences] O executa a classificação de público-alvo com base nas características originais de todas as fontes de dados primárias.
* A avaliação de segmento para [!UICONTROL Predictive Audiences] usa o **[!UICONTROL Profile Merge Rule]** que você escolher durante a criação do modelo. Para saber mais sobre [!UICONTROL Profile Merge Rules] consulte a [documentação dedicada](../profile-merge-rules/merge-rules-overview.md).
* Algumas características e segmentos não são compatíveis como linhas de base ou público-alvo. [!UICONTROL Predictive Audiences] não serão salvos ao escolher um dos seguintes como linhas de base ou públicos-alvo:
   * Características preditivas e segmentos criados com características preditivas;
   * [Características ou segmentos ](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) da Adobe Experience Platform;
   * Características algorítmicas;
   * Características secundárias e de terceiros.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] não pode ser usado em  [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

Segmentos preditivos criados por modelos [!UICONTROL Predictive Audiences] herdam os [Controles da exportação de dados](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) das seguintes fontes de dados primários:

1. A fonte de dados primária escolhida ao criar o modelo.
1. As fontes de dados primárias do público-alvo. Especificamente, os controles de exportação de dados do [!UICONTROL traits] ou [!UICONTROL segments] que compõem seu público-alvo.
1. O [Data Export Controls](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) do [!UICONTROL Profile Merge Rule] que você selecionou para o modelo.

As [!UICONTROL traits] e [!UICONTROL segments] preditivas recém-criadas terão as mesmas restrições de privacidade que a união das fontes de dados primárias descritas acima.

As características que têm restrições adicionais que não fazem parte das restrições de privacidade do segmento [!UICONTROL Predictive Audiences] serão excluídas da fase de treinamento e não se tornarão influentes para o modelo.

## [!UICONTROL Profile Merge Rules] {#pmr}

Todos os segmentos preditivos receberão o [!UICONTROL Profile Merge Rule] selecionado ao criar o modelo. O [!UICONTROL Profile Merge Rule] que você escolher é importante pelos seguintes motivos:

* Ele define quais dispositivos e/ou perfis autenticados devem ser considerados quando o modelo analisa o [!UICONTROL traits] influente, no momento da classificação de um usuário em um [!UICONTROL segment] preditivo.
* Ele determina quais tipos [!UICONTROL trait] (nível de dispositivo ou nível entre dispositivos) devem ser usados durante a etapa de treinamento do modelo e encontrados como influentes [!UICONTROL traits]. Preditivo [!UICONTROL segments] são subconjuntos do público-alvo.
   * Se o público-alvo for um segmento, recomendamos que você selecione o mesmo [!UICONTROL Profile Merge Rule] para o modelo atribuído ao seu público-alvo, ou um [!UICONTROL Profile Merge Rule] que inclua o tipo de perfil do seu público-alvo.
   * Se o público-alvo for um [!UICONTROL trait], recomendamos selecionar um [!UICONTROL Profile Merge Rule] que possa acessar o mesmo tipo de dados que a característica do público-alvo (dados de perfil do dispositivo ou dados de perfil entre dispositivos).
* [!UICONTROL Profile Merge Rules] o uso das  [!UICONTROL Current Authenticated Profiles] opções  [!UICONTROL No Device Profile] e só é compatível com a classificação de público-alvo em tempo real. Para obter mais informações, consulte [Opções de regras de mesclagem de perfis definidas](../profile-merge-rules/merge-rule-definitions.md).

Selecionar um [!UICONTROL Profile Merge Rule] que usa dados de dispositivo e dados entre dispositivos maximiza o número de [!UICONTROL traits] que pode ser usado para treinamento de modelo e classificação de usuário no [!UICONTROL segments] preditivo.

## [!UICONTROL Role-Based Access Controls] {#rbac}

As características e os segmentos que você escolhe para personas e classificação de público-alvo estão sujeitos aos Controles de acesso com base em função do Audience Manager [.](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html)

Os usuários do Audience Manager só podem selecionar características ou segmentos para personas e públicos-alvo, que têm [permissão para visualizar](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
