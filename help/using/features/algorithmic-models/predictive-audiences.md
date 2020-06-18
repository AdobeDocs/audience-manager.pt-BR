---
description: Audiências preditivas ajudam a classificar audiências desconhecidas em personas distintas em tempo real, usando a ciência de dados.
seo-description: Audiências preditivas ajudam a classificar audiências desconhecidas em personas distintas em tempo real, usando a ciência de dados.
seo-title: Visão geral das Audiências preditivas
solution: Audience Manager
title: Audiências Audience Manager preditivas
translation-type: tm+mt
source-git-commit: ef098c35da49ae663d201b9b7f96034fb5c76323
workflow-type: tm+mt
source-wordcount: '1261'
ht-degree: 0%

---


# [!UICONTROL Predictive Audiences] Visão geral {#predictive-audiences}

[!UICONTROL Predictive Audiences] ajuda a classificar uma audiência desconhecida em personas distintas, em tempo real, usando técnicas avançadas de ciência de dados.

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo durante a configuração e o uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

Em um contexto de marketing, uma pessoa é um segmento de audiência definido por visitantes, usuários ou compradores potenciais, que compartilham um conjunto específico de características, como demografia, hábitos de navegação, histórico de compras etc.

[!UICONTROL Predictive Audiences] os modelos levam esse conceito um passo adiante, permitindo que você use os recursos de aprendizado de máquina Audience Manager para classificar audiências desconhecidas em personas distintas. O Audience Manager ajuda você a fazer isso calculando a propensão de sua audiência primária desconhecida para um conjunto de audiências originais conhecidas.

Quando você cria um [!UICONTROL Predictive Audiences] modelo, a primeira etapa é escolher as características ou segmentos de linha de base pelos quais deseja que a audiência do público alvo seja classificada. Essas características ou segmentos definirão suas personas.

Durante a fase de avaliação, o modelo cria um novo [!UICONTROL Predictive Audiences] segmento para cada característica ou segmento que você definiu como linha de base. Na próxima vez que o Audience Manager ver um visitante da audiência do público alvo que não estiver classificado para uma pessoa (não se qualificou para nenhuma das características ou segmentos da linha de base), o [!UICONTROL Predictive Audiences] modelo determinará a quais segmentos preditivos o visitante deve pertencer e adicionará o visitante a esse segmento.

Você pode identificar os segmentos preditivos criados pelo modelo, na [!UICONTROL Segments] página. Cada [!UICONTROL Predictive Audiences] modelo tem sua própria pasta sob a [!UICONTROL Predictive Audiences] pasta e você pode ver os segmentos de cada modelo clicando na pasta do modelo.

![segmentos de audiências preditivas](assets/predictive-audiences-segments.png)

## Casos de uso {#use-cases}

Para ajudá-lo a entender melhor como e quando você poderia usar [!UICONTROL Predictive Audiences], veja alguns casos de uso que os clientes do Audience Manager podem resolver usando esse recurso.

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

## Como funcionam [!UICONTROL Predictive Audiences] os modelos {#how-predictive-audiences-models-work}

Ao criar um [!UICONTROL Predictive Audiences] modelo, você percorre três etapas:

1. Primeiro, selecione um mínimo de duas características ou dois segmentos que definirão suas personas.
1. Em seguida, escolha uma característica ou segmento que defina a audiência do público alvo que deseja classificar.
1. Por fim, escolha um nome para o modelo e selecione uma fonte de dados que armazenará os segmentos preditivos.

### Critérios de seleção para personas {#selection-personas}

Você pode escolher quaisquer características ou segmentos originais para definir suas personas. No entanto, para obter os melhores resultados, veja um conjunto de práticas recomendadas:

* Escolha suas características pessoais ou segmentos para que cada pessoa tenha pelo menos algumas centenas de IDs [de](../../reference/ids-in-aam.md)dispositivo.
* Se suas características forem baseadas em IDs [de](../../reference/ids-in-aam.md)vários dispositivos, você poderá vinculá-las em segmentos com Regras [de mesclagem de](../profile-merge-rules/merge-rules-overview.md) Perfis que usam IDs [de](../../reference/ids-in-aam.md)dispositivo, como [!UICONTROL Device Graph]. Isso garantirá que haja IDs [de](../../reference/ids-in-aam.md) dispositivo suficientes com as quais o algoritmo possa aprender.
* Recomendamos escolher características ou segmentos simples para suas pessoas, que consistem de 1 a 3 características.
* Escolha características da linha de base ou segmentos que tenham sobreposição mínima.
* Certifique-se de capturar características granulares em suas propriedades digitais.

### Critérios de seleção para a Audiência do Público alvo {#selection-audience}

Semelhante à seleção pessoal, você deve escolher seu traço ou segmento que define sua audiência de público alvo de modo que ela tenha usuários em tempo real com conjuntos avançados de características, para classificação na pessoa certa.

### [!UICONTROL Predictive Audiences] Fase de treinamento do modelo {#model-training}

Antes que o algoritmo possa classificar sua audiência primária nas pessoas certas, ele precisa treinar a si mesmo nos seus dados.

Para cada persona definida, o algoritmo analisa sua respectiva audiência e avalia qualquer atividade de característica em tempo real e/ou integrada para seus usuários nos últimos 30 dias.
Esta etapa ocorre uma vez a cada 24 horas, para levar em conta as alterações na audiência primária.

### [!UICONTROL Predictive Audiences] Fase de classificação do modelo {#model-classification}

Quando um visitante que faz parte da audiência do público alvo é visto em tempo real, o modelo avalia se o visitante faz parte da pessoa definida. Para cada visitante que não pertence a nenhuma das pessoas, o modelo atribui uma pontuação de qualificação pessoal.

Ao avaliar audiências primárias e atribuir pontuações, o modelo usa o padrão **[!UICONTROL Profile Merge Rule]** definido em sua conta. Por fim, o visitante é classificado na pessoa para a qual recebeu a pontuação mais alta.

![predictivo-audiências-gráfico](assets/predictive-audiences-graph.png)

## Considerações e limitações {#considerations}

>[!IMPORTANT]
> Leia atentamente esta seção antes de passar para a fase de implementação.

Ao configurar seus [!UICONTROL Predictive Audiences] modelos, lembre-se das seguintes considerações e limitações:

* Você pode criar até 10 [!UICONTROL Predictive Audiences] modelos.
* Para cada modelo, você pode escolher até 50 características/segmentos básicos.
* Os dados de segundo e terceiro não são suportados atualmente em [!UICONTROL Predictive Audiences].
* A classificação de Audiência é feita somente para audiências originais em tempo real. A classificação de audiência primária integrada pode ser suportada em uma atualização futura.
   >[!IMPORTANT]
   > No momento, o número [!UICONTROL Total Segment Population] de segmentos preditivos é exibido como 0 e as Transferências [de Dados de Saída em](../../integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-overview.md) Lote não são suportadas para [!UICONTROL Predictive Audiences]. Esse comportamento será alterado em uma atualização futura.
* [!UICONTROL Predictive Audiences] executa a classificação de audiência com base nas características originais, de todas as fontes de dados originais.
* A avaliação de segmentos para [!UICONTROL Predictive Audiences] usa o padrão **[!UICONTROL Profile Merge Rule]** definido na sua conta. Para saber mais sobre [!UICONTROL Profile Merge Rules] , consulte a [documentação](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/profile-merge-rules/merge-rules-overview.html)dedicada.
* Algumas características e segmentos não são suportados como audiências de linha de base ou públicos alvos. [!UICONTROL Predictive Audiences] os modelos não serão salvos ao escolher uma das seguintes opções como linhas de base ou audiências de público alvo:
   * Características preditivas e segmentos criados com características preditivas;
   * [Características ou segmentos de Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) ;
   * Características algorítmicas;
   * Características de segundo e terceiro.

## [!UICONTROL Data Export Controls] {#dec}

Segmentos preditivos criados por [!UICONTROL Predictive Audiences] modelos herdam os Controles [de exportação de](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) dados das seguintes fontes de dados primários:

1. A fonte de dados primária escolhida ao criar o modelo.
1. As fontes de dados primários da audiência do público alvo. Especificamente, os controles de exportação de dados das características ou segmentos que compõem a audiência do público alvo.

As características preditivas e os segmentos recém-criados terão as mesmas restrições de privacidade que a união das fontes de dados primárias descritas acima.

Características que têm restrições adicionais que não fazem parte das restrições de privacidade do [!UICONTROL Predictive Audiences] segmento serão excluídas da fase de treinamento e não se tornarão influentes para o modelo.

## [!UICONTROL Role-Based Access Controls] {#rbac}

As características e os segmentos que você escolhe para a classificação de audiência e estão sujeitos aos Controles de acesso [baseados em](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html)funções de Audience Manager.

Os usuários do Audience Manager podem selecionar apenas características ou segmentos para pessoas e audiências públicos alvos, que têm [permissão para visualização](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
