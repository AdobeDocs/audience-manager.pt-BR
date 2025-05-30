---
description: Públicos preditivos ajudam a classificar públicos desconhecidos em personas distintas em tempo real, usando a ciência de dados.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Overview
solution: Audience Manager
title: Públicos preditivos do Audience Manager
feature: Algorithmic Models
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1470'
ht-degree: 3%

---

# Visão geral do [!UICONTROL Predictive Audiences] {#predictive-audiences}

O [!UICONTROL Predictive Audiences] ajuda você a classificar um público-alvo desconhecido em personas distintas, em tempo real, usando técnicas avançadas de ciência de dados.

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e pelo uso desse recurso. Nada contido aqui é aconselhamento jurídico. Consulte seu próprio serviço jurídico para obter orientação jurídica.

Em um contexto de marketing, uma pessoa é um segmento de público-alvo definido por visitantes, usuários ou possíveis compradores, que compartilham um conjunto específico de características, como demografia, hábitos de navegação, histórico de compras etc.

Os modelos de [!UICONTROL Predictive Audiences] levam esse conceito um passo além, permitindo que você use os recursos de aprendizado de máquina do Audience Manager para classificar públicos desconhecidos em personas distintas. O Audience Manager ajuda você a fazer isso calculando a propensão do público primário desconhecido para um conjunto de públicos originais conhecidos.

Ao criar um modelo [!UICONTROL Predictive Audiences], a primeira etapa é escolher as características ou os segmentos da linha de base pelos quais você deseja que seu público-alvo seja classificado. Essas características ou segmentos definirão suas personalidades.

Durante a fase de avaliação, o modelo cria um novo segmento [!UICONTROL Predictive Audiences] para cada característica ou segmento definido como linha de base. Na próxima vez que o Audience Manager vir um visitante de seu público-alvo que não esteja classificado para uma persona (não se qualificou para nenhuma de suas características ou segmentos de linha de base), o modelo [!UICONTROL Predictive Audiences] determinará a qual dos segmentos preditivos o visitante deve pertencer e adicionará o visitante a esse segmento.

Você pode identificar os segmentos preditivos criados pelo modelo, na página [!UICONTROL Segments]. Cada modelo [!UICONTROL Predictive Audiences] tem sua própria pasta na pasta [!UICONTROL Predictive Audiences], e você pode ver os segmentos de cada modelo clicando na pasta do modelo.

![segmentos-públicos-preditivos](assets/predictive-audiences-segments.png)

## Casos de uso {#use-cases}

Para ajudá-lo a entender melhor como e quando você pode usar o [!UICONTROL Predictive Audiences], veja alguns casos de uso que os clientes do Audience Manager podem resolver usando esse recurso.

### Caso de uso #1

Como comerciante em uma empresa de comércio eletrônico, desejo classificar todos os meus visitantes da Web e móveis em várias categorias de afinidade de marca, para que eu possa personalizar a experiência do usuário.

### Caso de uso #2

Como profissional de marketing em uma empresa de mídia, quero classificar meus visitantes móveis e da Web não autenticados por gêneros favoritos, para que eu possa sugerir a eles conteúdo personalizado em todos os canais.

### Caso de uso #3

Como anunciante de uma companhia aérea, quero me certificar de classificar meu público com base em seu interesse em destinos de viagem, para que eu possa anunciar a eles em tempo real, dentro de uma pequena janela de redirecionamento.

### Caso de uso #4

Como anunciante, quero classificar meu público primário em tempo real, para que eu possa reagir rapidamente às notícias dos &quot;trending topics&quot;.

### Caso de uso #5

Como profissional de marketing, quero prever em qual fase da jornada do cliente meus visitantes do site estão, como descoberta, envolvimento, compra ou retenção, para que eu possa direcioná-los de acordo.

### Caso de uso #6

Como empresa de mídia, quero categorizar meu público para que eu possa vender meu espaço publicitário a preços superiores, e oferecer aos meus visitantes anúncios relevantes.

## Como funcionam os modelos [!UICONTROL Predictive Audiences] {#how-predictive-audiences-models-work}

Ao criar um modelo [!UICONTROL Predictive Audiences], você deve seguir três etapas:

1. Primeiro, você seleciona no mínimo duas características ou dois segmentos que definirão suas personas.
1. Em seguida, escolha uma característica ou um segmento que defina o público-alvo que deseja classificar.
1. Finalmente, você escolhe um nome para o modelo, uma fonte de dados que armazenará os segmentos preditivos e um [!UICONTROL Profile Merge Rule] para o modelo.

### Critérios de seleção de personas {#selection-personas}

Você pode escolher qualquer uma de suas características ou segmentos primários para definir seus perfis. No entanto, para obter os melhores resultados, veja um conjunto de práticas recomendadas:

* Escolha suas características ou segmentos de persona para que cada persona tenha pelo menos algumas centenas de [IDs de dispositivo](../../reference/ids-in-aam.md).
* Se suas características se baseiam em [IDs entre dispositivos](../../reference/ids-in-aam.md), você pode agrupá-las em segmentos com [Regras de mesclagem de perfis](../profile-merge-rules/merge-rules-overview.md) que usam [IDs de dispositivos](../../reference/ids-in-aam.md), como [!UICONTROL Device Graph]. Isso garantirá que haja [IDs de dispositivo](../../reference/ids-in-aam.md) suficientes com as quais o algoritmo possa aprender.
* Recomendamos escolher características ou segmentos simples para suas personas, consistindo em 1 a 3 características.
* Escolha características ou segmentos da linha de base com sobreposição mínima.
* Certifique-se de capturar características granulares em suas propriedades digitais.

### Critérios de seleção para o público-alvo do Target {#selection-audience}

Dependendo do caso de uso, se você deseja classificar usuários em tempo real, em lote ou ambos, escolha um público-alvo ([!UICONTROL trait] ou [!UICONTROL segment]) que tenha uma população significativa em tempo real e/ou total. Semelhante à seleção de persona, recomendamos que seu público-alvo [!UICONTROL trait] ou [!UICONTROL segment] tenha usuários com perfis avançados (conjuntos avançados de [!UICONTROL traits]).

Ao selecionar o público-alvo, analise seu caso de uso e decida quais tipos de IDs você deseja classificar: [!UICONTROL device IDs] ou [!UICONTROL cross-device IDs]. O [!UICONTROL Profile Merge Rule] selecionado ao criar o modelo define os dados que serão usados para colocar cada usuário no [!UICONTROL segments] preditivo.

Como prática recomendada, recomendamos escolher um [!UICONTROL Profile Merge Rule] que tenha a mesma configuração que seu público-alvo [!UICONTROL Profile Merge Rule] ou que inclua o tipo de perfil (perfil de dispositivo ou perfil autenticado) de seu público-alvo.

### Fase de treinamento do modelo [!UICONTROL Predictive Audiences] {#model-training}

Antes que o algoritmo possa classificar o público-alvo primário nas personas certas, ele precisa treinar a si mesmo em seus dados.

Para cada persona definida, o algoritmo analisa seu respectivo público e avalia qualquer atividade em tempo real e/ou de características integradas para seus usuários nos últimos 30 dias.
Essa etapa ocorre uma vez a cada 24 horas, para levar em conta as alterações no público-alvo primário.

### Fase de Classificação do Modelo [!UICONTROL Predictive Audiences] {#model-classification}

Para classificação de público-alvo em lote e em tempo real, o modelo verifica primeiro se um usuário pertence ao público-alvo. Se o usuário se qualificar para o público-alvo de direcionamento e não pertencer a nenhuma das personas, o modelo atribuirá a ele uma pontuação de qualificação de persona.

Ao avaliar públicos-alvo primários e atribuir pontuações, o modelo usa o **[!UICONTROL Profile Merge Rule]** padrão definido na sua conta. Finalmente, o visitante é classificado na persona para a qual recebeu a pontuação mais alta.

![gráfico-de-públicos-preditivos](assets/predictive-audiences-graph.png)

## Considerações e limitações {#considerations}

>[!IMPORTANT]
> Leia esta seção com atenção antes de passar para a fase de implementação.

Ao configurar seus modelos do [!UICONTROL Predictive Audiences], lembre-se das seguintes considerações e limitações:

* Você pode criar até 10 modelos de [!UICONTROL Predictive Audiences].
* Para cada modelo, você pode escolher até 50 características/segmentos base.
* Dados secundários e de terceiros não têm suporte no [!UICONTROL Predictive Audiences].
* O [!UICONTROL Predictive Audiences] realiza a classificação de público com base em suas características próprias, de todas as suas fontes de dados originais.
* A avaliação de segmento para [!UICONTROL Predictive Audiences] usa o **[!UICONTROL Profile Merge Rule]** escolhido durante a criação do modelo. Para saber mais sobre [!UICONTROL Profile Merge Rules], consulte a [documentação](../profile-merge-rules/merge-rules-overview.md) dedicada.
* Algumas características e segmentos não são compatíveis como linhas de base ou públicos-alvo de direcionamento. [!UICONTROL Predictive Audiences] modelos não serão salvos ao escolher um dos seguintes como linhas de base ou públicos-alvo de destino:
   * Características preditivas e segmentos criados com características preditivas;
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) características ou segmentos;
   * Características algorítmicas;
   * Características secundárias e de terceiros.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] não pode ser usado em [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

Os segmentos preditivos criados por modelos [!UICONTROL Predictive Audiences] herdam os [Controles da Exportação de Dados](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html?lang=pt-BR) das seguintes fontes de dados primárias:

1. A fonte de dados primária escolhida ao criar o modelo.
1. As fontes de dados primárias do público-alvo. Especificamente, os controles de exportação de dados do [!UICONTROL traits] ou [!UICONTROL segments] que compõem o público-alvo.
1. Os [Controles da Exportação de Dados](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html?lang=pt-BR) de [!UICONTROL Profile Merge Rule] que você selecionou para o modelo.

A [!UICONTROL traits] preditiva recém-criada e a [!UICONTROL segments] terão as mesmas restrições de privacidade que a união das fontes de dados primárias descritas acima.

As características com restrições adicionais que não fazem parte das [!UICONTROL Predictive Audiences] restrições de privacidade de segmento serão excluídas da fase de treinamento e não se tornarão influentes para o modelo.

## [!UICONTROL Profile Merge Rules] {#pmr}

Todos os segmentos preditivos serão atribuídos ao [!UICONTROL Profile Merge Rule] que você selecionou ao criar o modelo. O [!UICONTROL Profile Merge Rule] escolhido é importante pelos seguintes motivos:

* Ele define quais dispositivos e/ou perfis autenticados devem ser considerados quando o modelo analisa o [!UICONTROL traits] influente, no momento de classificar um usuário em um [!UICONTROL segment] preditivo.
* Ela controla quais [!UICONTROL trait] tipos (nível de dispositivo ou nível entre dispositivos) devem ser usados durante a etapa de treinamento do modelo e exibidos como [!UICONTROL traits] influentes. A preditiva [!UICONTROL segments] é um subconjunto de seu público-alvo.
   * Se o público-alvo for um segmento, recomendamos que você selecione o mesmo [!UICONTROL Profile Merge Rule] para o modelo que foi atribuído ao seu público-alvo, ou um [!UICONTROL Profile Merge Rule] que inclua o tipo de perfil do seu público-alvo.
   * Se o público-alvo for um [!UICONTROL trait], recomendamos que você selecione um [!UICONTROL Profile Merge Rule] que possa acessar o mesmo tipo de dados que a característica do público-alvo (dados de perfil do dispositivo ou dados de perfil entre dispositivos).
* Só há suporte para [!UICONTROL Profile Merge Rules] que usa as opções [!UICONTROL Current Authenticated Profiles] e [!UICONTROL No Device Profile] para a classificação de público-alvo em tempo real. Para obter mais informações, consulte [Opções de Regras de Mesclagem de Perfis Definidas](../profile-merge-rules/merge-rule-definitions.md).

Selecionar um [!UICONTROL Profile Merge Rule] que use dados de dispositivo e dados entre dispositivos maximiza o número de [!UICONTROL traits] que poderia ser usado para treinamento de modelo e classificação de usuário no [!UICONTROL segments] preditivo.

## [!UICONTROL Role-Based Access Controls] {#rbac}

As características e os segmentos que você escolher para classificação de personas e público-alvo estão sujeitos aos [Controles de acesso com base em função](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html?lang=pt-BR) do Audience Manager.

Os usuários do Audience Manager só podem selecionar características ou segmentos para personas e públicos-alvo, que têm [permissão para visualizar](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html?lang=pt-BR#wild-card-permissions).
