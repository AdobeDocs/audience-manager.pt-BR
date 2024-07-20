---
description: O recurso Destinos com base em pessoas oferece várias estratégias de implementação, dependendo de como os dados do cliente são estruturados. Este artigo fornece uma visão geral das etapas de implementação que você precisa seguir para Destinos com base em pessoas, dependendo do seu cenário.
seo-description: People-Based Destinations offers multiple implementation strategies, depending on how your customer data is structured. This article provides an overview of the implementation steps that you need to follow for People-Based Destinations, depending on your scenario.
seo-title: People-Based Destinations Implementation Guidance
solution: Audience Manager
title: Diretrizes de implementação
feature: People-based Destinations
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1350'
ht-degree: 2%

---

# Diretrizes de implementação {#implementation-guidance}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e pelo uso desse recurso. Nada contido aqui é aconselhamento jurídico. Consulte seu próprio serviço jurídico para obter orientação jurídica.

O [!DNL People-Based Destinations] oferece várias estratégias de implementação, dependendo de como os dados do cliente estão estruturados. Este artigo fornece uma visão geral das etapas de implementação que você precisa seguir para o [!DNL People-Based Destinations], dependendo do seu cenário.

## Visão geral {#overview}

A configuração do [!DNL People-Based Destinations] orienta você por várias seções do Audience Manager e requer diferentes configurações e métodos de integração de dados, dependendo do tipo de dados do cliente que você já tem no Audience Manager e do tipo de direcionamento de público que deseja executar.

>[!IMPORTANT]
> Antes de configurar o [!DNL People-Based Destinations], leia este artigo cuidadosamente e completamente. Depois de ler este guia, você deverá entender claramente o cenário que será ativado por meio do [!DNL People-Based Destinations].

Você precisa esclarecer seis aspectos de implementação antes de usar o [!DNL People-Based Destinations]. Este artigo ajudará você a entender qual é a configuração atual, para que possa seguir corretamente as etapas de implementação do seu cenário.

![pbd-implementation](assets/pbd-implementation.png)

## 1. Definir seu caso de uso {#defining-your-use-case}

Antes de começar a implementar o [!DNL People-Based Destinations], você precisa definir claramente o caso de uso para o qual você usará esse recurso. Você pode usar o [!DNL People-Based Destinations] para direcionar públicos de duas maneiras, com base na atividade do público:

**A) Direcionamento de público com base na sua atividade de usuário online e offline combinada**. Neste cenário, você deseja combinar dados de público existentes do Audience Manager com dados do seu sistema [!DNL CRM] interno e enviar os segmentos de público resultantes para [!DNL People-Based Destinations]. Veja um exemplo que ilustra esse cenário:

Sua empresa, uma companhia aérea, tem diferentes níveis de clientes (bronze, prata e ouro) e você deseja fornecer ofertas personalizadas a cada um desses níveis por meio de plataformas sociais. Use o Audience Manager para analisar a atividade do cliente no seu site. No entanto, nem todos os clientes usam o aplicativo móvel da companhia aérea e alguns deles não fizeram logon no site da empresa. Os dados do cliente estão limitados principalmente a IDs de associação e endereços de email.

Para direcioná-los por meio de redes sociais e canais semelhantes com base em pessoas, você pode trazer seus [endereços de email com hash](people-based-destinations-prerequisites.md) para o Audience Manager e combiná-los com suas características de atividade online existentes, para criar novos segmentos de público-alvo. Em seguida, você pode usar esses segmentos para direcionar seu público-alvo por meio do [!DNL People-Based Destinations].

**B) Direcionamento de público com base exclusivamente em sua atividade de usuário offline**. Neste cenário, o sistema [!DNL CRM] contém os endereços de email do cliente e outros atributos do cliente, mas os clientes não interagiram com o site, portanto, você não tem nenhuma atividade no Audience Manager. Veja um exemplo que ilustra esse cenário:

Sua empresa, um provedor de serviços de telecomunicações, mantém os dados do cliente, como endereços de email e planos de telecomunicações adquiridos, em um [!DNL CRM] interno. Você deseja direcionar os clientes existentes nas plataformas sociais para oferecer pacotes de atualização com base em suas assinaturas existentes. Para fazer isso, você pode assimilar seus endereços de email de clientes com hash no Audience Manager e criar segmentos com base nas assinaturas de clientes existentes. Em seguida, envie esses segmentos para [!DNL People-Based Destinations] para direcionar seus clientes com ofertas personalizadas.

## 2. Defina o tipo de Endereços de email direcionados {#define-target-email}

A segunda etapa na definição da estratégia de implementação é decidir que tipo de endereço de email do cliente você deseja direcionar.

**A) Direcionamento de público com base em seus endereços de email autenticados**. Nesse cenário, seus usuários têm várias contas associadas a vários endereços de email e você deseja direcioná-los com ofertas personalizadas, com base apenas no endereço de email que eles autenticam em seu site, em tempo real.

**B) Direcionamento de público com base em todos os seus endereços de email associados**. Nesse cenário, seus usuários têm várias contas associadas a vários endereços de email e você deseja direcioná-los em todos os endereços de email associados, independentemente da atividade autenticada.

## 3. Identifique o tipo de IDs do cliente (IDs de CRM) que você tem {#identify-customer-id}

O direcionamento de públicos-alvo no [!DNL People-Based Destinations] exige que você envie [SHA256](people-based-destinations-prerequisites.md) versões com hash dos endereços de email de seus clientes. Dependendo da configuração de Audience Manager existente, você pode se encontrar em uma das duas situações a seguir:

**A) Suas IDs de cliente do Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) já são endereços de email com hash e em minúsculas**. Neste cenário, você pode usar essas IDs existentes para direcionar seus públicos no [!DNL People-Based Destinations].

**B) Suas IDs de cliente do Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) não são endereços de email com hash e em minúsculas**. Neste cenário, suas IDs de cliente existentes não podem ser enviadas para [!DNL People-Based Destinations]. Para usar o [!DNL People-Based Destinations], você precisa executar uma sincronização de ID entre suas IDs de cliente existentes e versões em minúsculas e com hash dos endereços de email do cliente. Você faz isso por meio da [sincronização de ID com base em arquivo](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ou usando [IDs declaradas](../declared-ids.md).

## 4. Qualificação das características {#trait-qualification}

Para direcionar com precisão seu público no [!DNL People-Based Destinations], seus usuários precisam se qualificar para características integradas ou com base em regras, dependendo do tipo de direcionamento de público que você deseja executar.

**A) Qualifique as IDs do cliente e as IDs do dispositivo em tempo real para características baseadas em regras**. Esta opção se aplica ao caso de uso A de [1. Definindo Seu Caso De Uso](people-based-destinations-workflow.md#defining-your-use-case). Se seu plano é direcionar públicos com base na atividade online e offline, você provavelmente já está qualificando seu público para [características com base em regras](../traits/trait-and-segment-qualification-reference.md).

**B) Integre características em relação às IDs do cliente por meio de arquivos de dados de entrada**. Esta opção se aplica ao caso de uso B de [1. Definindo Seu Caso De Uso](people-based-destinations-workflow.md#defining-your-use-case). Ao direcionar seu público-alvo com base em atividades puramente offline, você precisa qualificar as IDs do cliente para características integradas por meio de [arquivos de dados de entrada](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## 5. Criar ou rotular fontes de dados e endereços de email com hash integrados {#create-label-data-sources}

Dependendo do tipo de IDs do cliente que você tem no Audience Manager (consulte [3. Identifique o tipo de IDs do cliente (IDs de CRM) que você tem](people-based-destinations-workflow.md#identify-customer-id). Você se encontrará em um dos seguintes cenários:

**A) Rotule uma fonte de dados existente**. Essa opção se aplica ao cenário em que suas IDs de cliente do Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) já são endereços de email com hash e em minúsculas. Nessa situação, o que você precisa fazer é rotular a fonte de dados em que você armazena as IDs como uma fonte de dados [!DNL PII]. Consulte [Configurações do Data Source](../datasources-list-and-settings.md) para obter detalhes sobre as configurações da fonte de dados. O que você precisa fazer é garantir que a opção Não pode ser vinculado a informações de identificação pessoal esteja desmarcada.

**B) Criar uma nova fonte de dados**. Essa opção se aplica ao cenário em que as IDs do cliente do Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) não são endereços de email com hash. Nesse caso, você precisa criar uma nova fonte de dados entre dispositivos e integrar seus endereços de email com hash a ela. Você pode fazer isso de duas maneiras:

* Usar a sincronização de ID com base em arquivos. Consulte [Requisitos de nome e conteúdo para arquivos de sincronização de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) para obter detalhes sobre a aparência dos arquivos de sincronização de ID. Ao usar esse método, você pode direcionar todos os seus endereços de email com hash do banco de dados do [!DNL CRM].
* Use [IDs declaradas](../declared-ids.md) para declarar seus endereços de email com hash ao transmitir IDs autenticadas do cliente. Ao usar esse método, o Audience Manager, em seu nome, direciona somente seus endereços de email com hash de usuários que autenticaram online. Os endereços de email direcionados em canais com base em pessoas são apenas os que estão nas chamadas de evento de ID declaradas. Outros endereços de email associados à ID do cliente não são ativados em tempo real.

## 6. Usar uma regra de mesclagem de perfis para segmentação {#use-profile-merge-rules}

Dependendo do seu caso de uso (consulte [1. Definindo Seu Caso de Uso (](people-based-destinations-workflow.md#defining-your-use-case)), há duas maneiras de usar o [!DNL Profile Merge Rules] para segmentação.

**A) Usar[!DNL Profile Merge Rules]** existente. Essa opção se aplica ao primeiro caso de uso (direcionamento de público com base na atividade de usuário online e offline combinada). Nesse cenário, há uma atividade do cliente existente no Audience Manager e você já definiu pelo menos uma Regra de mesclagem de perfis usada na segmentação. Nesse caso, você não precisa criar nenhum(a) novo(a) [!DNL Profile Merge Rules].

**B) Criar uma nova, [!DNL All Cross-Device Profiles] Regra de mesclagem**. Essa opção se aplica ao segundo caso de uso (direcionamento de público com base exclusivamente na atividade do usuário offline). Neste cenário, você traz os dados offline do cliente do [!DNL CRM] para o Audience Manager e deseja criar segmentos com esses dados. Para fazer isso, [!DNL People-Based Destinations] introduz uma nova quarta Regra de mesclagem de perfis, chamada **[!DNL All Cross-Device Profiles]**. Essa é a regra que você precisa usar ao segmentar dados puramente offline.
