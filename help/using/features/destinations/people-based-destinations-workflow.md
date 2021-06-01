---
description: Os Destinos com base em pessoas oferecem várias estratégias de implementação, dependendo de como os dados do cliente são estruturados. Este artigo fornece uma visão geral das etapas de implementação que você precisa seguir para Destinos com base em pessoas, dependendo do seu cenário.
seo-description: 'Os Destinos com base em pessoas oferecem várias estratégias de implementação, dependendo de como os dados do cliente são estruturados. Este artigo fornece uma visão geral das etapas de implementação que você precisa seguir para Destinos com base em pessoas, dependendo do seu cenário.  '
seo-title: Diretrizes de implementação de destinos com base em pessoas
solution: Audience Manager
title: Diretrizes de implementação
feature: Destinos com base em pessoas
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 2%

---

# Diretrizes de implementação {#implementation-guidance}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e uso deste recurso. Nada neste documento é de aconselhamento jurídico. Consulte o seu advogado para obter orientação jurídica.

[!DNL People-Based Destinations] O oferece várias estratégias de implementação, dependendo de como os dados do cliente são estruturados. Este artigo fornece uma visão geral das etapas de implementação que você precisa seguir para [!DNL People-Based Destinations], dependendo do seu cenário.

## Visão geral {#overview}

A configuração de [!DNL People-Based Destinations] o orienta por várias seções do Audience Manager e requer configurações e métodos de integração de dados diferentes, dependendo do tipo de dados do cliente que você já tem no Audience Manager e do tipo de direcionamento de público-alvo que deseja executar.

>[!IMPORTANT]
> Antes de configurar [!DNL People-Based Destinations], leia este artigo atentamente e completamente. Depois de ler este guia, você deve ter uma compreensão clara do cenário que estará ativando por meio de [!DNL People-Based Destinations].

Há seis aspectos de implementação que você precisa esclarecer antes de usar [!DNL People-Based Destinations]. Este artigo ajudará você a entender qual é a configuração atual, para que possa seguir corretamente as etapas de implementação do seu cenário.

![pbd-implementation](assets/pbd-implementation.png)

## 1. Definir seu caso de uso {#defining-your-use-case}

Antes de começar a implementar [!DNL People-Based Destinations], é necessário definir claramente o caso de uso para o qual você usará esse recurso. Você pode usar [!DNL People-Based Destinations] para direcionar públicos de duas formas, com base na atividade do público-alvo:

**A) Direcionamento de público-alvo com base em sua atividade** combinada online e offline do usuário. Neste cenário, você deseja combinar os dados do público-alvo existentes do Audience Manager com os dados do seu sistema interno [!DNL CRM] e enviar os segmentos de público-alvo resultantes para [!DNL People-Based Destinations]. Este é um exemplo que ilustra este cenário:

Sua empresa, uma companhia aérea, tem níveis de clientes diferentes (Bronze, Silver e Gold) e você deseja fornecer a cada um dos níveis ofertas personalizadas por meio de plataformas sociais. Você usa o Audience Manager para analisar a atividade do cliente em seu site. No entanto, nem todos os clientes usam o aplicativo móvel da companhia aérea e alguns deles não fizeram logon no site da empresa. Os dados do cliente estão limitados a IDs de associação e endereços de email.

Para direcioná-los em mídias sociais e canais baseados em pessoas semelhantes, você pode trazer seus [endereços de email com hash](people-based-destinations-prerequisites.md) para o Audience Manager e combiná-los com suas características de atividade online existentes, para criar novos segmentos de público-alvo. Em seguida, você pode usar esses segmentos para direcionar seu público-alvo por meio de [!DNL People-Based Destinations].

**B) Direcionamento de público-alvo com base exclusivamente na sua atividade** de usuário offline. Nesse cenário, seu sistema [!DNL CRM] contém seus endereços de email de clientes e outros atributos de clientes, mas os clientes não interagiram com seu site, portanto, você não tem nenhuma atividade de cliente no Audience Manager. Este é um exemplo que ilustra este cenário:

Sua empresa, um provedor de serviços de telecomunicações, mantém os dados do cliente, como endereços de email e planos de telecom adquiridos em um [!DNL CRM] interno. Você deseja direcionar clientes existentes em plataformas sociais para oferecer pacotes de atualização com base em suas assinaturas existentes. Para fazer isso, você pode assimilar seus endereços de email de clientes com hash no Audience Manager e criar segmentos com base nas assinaturas de clientes existentes. Em seguida, você pode enviar esses segmentos para [!DNL People-Based Destinations] para direcionar seus clientes com ofertas personalizadas.

## 2. Defina o tipo de endereço de email direcionado {#define-target-email}

A segunda etapa na definição da estratégia de implementação é decidir que tipo de endereço de email do cliente deseja direcionar.

**A) Direcionamento de público-alvo com base em seus endereços** de email autenticados. Nesse cenário, seus usuários têm várias contas associadas a vários endereços de email e você deseja direcioná-los com ofertas personalizadas, com base apenas no endereço de email que eles autenticam em seu site, em tempo real.

**B) Direcionamento de público-alvo com base em todos os seus endereços** de email associados. Nesse cenário, seus usuários têm várias contas associadas a vários endereços de email e você deseja direcioná-las em todos os endereços de email associados, independentemente da atividade autenticada.

## 3. Identifique o tipo de IDs de cliente (IDs de CRM) que você tem {#identify-customer-id}

O direcionamento de públicos-alvo em [!DNL People-Based Destinations] requer o envio de versões [SHA256 com hash](people-based-destinations-prerequisites.md) dos endereços de email do cliente. Dependendo da configuração de Audience Manager existente, você pode se encontrar em um dos dois cenários a seguir:

**A) As IDs de cliente do Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) já têm endereços** de email com hash em letras minúsculas. Nesse cenário, você pode usar essas IDs existentes para direcionar seus públicos-alvo em [!DNL People-Based Destinations].

**B) As IDs de cliente do Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) não são endereços** de email com hash em letras minúsculas. Nesse cenário, as IDs do cliente existentes não podem ser enviadas para [!DNL People-Based Destinations]. Para usar [!DNL People-Based Destinations], é necessário executar uma sincronização de ID entre as IDs do cliente existentes e as versões com hash em minúsculas dos endereços de email do cliente. Faça isso por meio da [sincronização de ID com base em arquivo](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ou usando [IDs declaradas](../declared-ids.md).

## 4. Qualificação de característica {#trait-qualification}

Para direcionar seu público-alvo com precisão em [!DNL People-Based Destinations], seus usuários precisam se qualificar para características integradas ou com base em regras, dependendo do tipo de direcionamento de público-alvo que você deseja executar.

**A) Qualifique as IDs do cliente e as IDs do dispositivo em tempo real para características** baseadas em regras. Essa opção se aplica ao caso de uso A de [1. Definindo seu caso de uso](people-based-destinations-workflow.md#defining-your-use-case). Se seu plano é direcionar públicos-alvo com base em atividades online e offline, você provavelmente já está qualificando seu público-alvo para [características baseadas em regras](../traits/trait-and-segment-qualification-reference.md).

**B) Características integradas em relação às IDs do cliente por meio de arquivos** de dados de entrada. Essa opção se aplica ao caso de uso B de [1. Definindo seu caso de uso](people-based-destinations-workflow.md#defining-your-use-case). Ao direcionar seu público-alvo com base em atividades puramente offline, você precisa qualificar as IDs do cliente para características integradas por meio de [arquivos de dados de entrada](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## 5. Criar ou rotular fontes de dados e endereços de email com hash onboard {#create-label-data-sources}

Dependendo do tipo de IDs do cliente que você tem no Audience Manager (consulte [3. Identifique o tipo de IDs de cliente (IDs de CRM) que você possui](people-based-destinations-workflow.md#identify-customer-id), você se encontrará em um dos seguintes cenários:

**A) Rotule uma fonte** de dados existente. Essa opção se aplica ao cenário em que as IDs do cliente do Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) já estão em minúsculas e com hash de endereços de email. Nessa situação, o que você precisa fazer é rotular sua fonte de dados na qual você armazena as IDs como uma fonte de dados [!DNL PII]. Consulte [Configurações da fonte de dados](../datasources-list-and-settings.md) para obter detalhes sobre as configurações da fonte de dados. O que você precisa fazer é verificar se a opção Cannot be linked to pessoalmente identification está desmarcada.

**B) Criar uma nova fonte de dados**. Essa opção se aplica ao cenário em que as IDs do cliente do Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) não são endereços de email com hash. Nesse caso, é necessário criar uma nova fonte de dados entre dispositivos e integrar seus endereços de email com hash a ela. Você pode fazer isso de duas maneiras:

* Usar a sincronização de ID com base em arquivos. Consulte [Requisitos de nome e conteúdo para arquivos de sincronização de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) para obter detalhes sobre a aparência dos arquivos de sincronização de ID. Ao usar esse método, você pode direcionar todos os seus endereços de email com hash do seu banco de dados [!DNL CRM].
* Use [IDs declaradas](../declared-ids.md) para declarar seus endereços de email com hash ao transmitir IDs autenticadas do cliente. Ao usar esse método, o Audience Manager, em seu nome, direciona somente seus endereços de email com hash de usuários que autenticaram online. Os endereços de email direcionados em canais com base em pessoas são apenas os que estão nas chamadas de evento de ID declaradas. Outros endereços de email associados à ID do cliente não são ativados em tempo real.

## 6. Usar uma regra de mesclagem de perfis para segmentação {#use-profile-merge-rules}

Dependendo do caso de uso (consulte [1. Definir seu caso de uso](people-based-destinations-workflow.md#defining-your-use-case)), há duas maneiras de usar [!DNL Profile Merge Rules] para segmentação.

**A) Use[!DNL Profile Merge Rules]** os existentes. Essa opção se aplica ao primeiro caso de uso (direcionamento de público-alvo com base nas atividades combinadas online e offline do usuário). Neste cenário, você tem uma atividade do cliente existente no Audience Manager e já definiu pelo menos uma Regra de mesclagem de perfis que você usou na segmentação. Nesse caso, não é necessário criar um novo [!DNL Profile Merge Rules].

**B) Crie uma nova regra de  [!DNL All Cross-Device Profiles] mesclagem**. Essa opção se aplica ao segundo caso de uso (direcionamento de público-alvo baseado exclusivamente na atividade offline do usuário). Neste cenário, você está trazendo seus dados de clientes offline do [!DNL CRM] para o Audience Manager e deseja criar segmentos a partir desses dados. Para fazer isso, [!DNL People-Based Destinations] introduz uma nova e quarta Regra de mesclagem de perfis, chamada **[!DNL All Cross-Device Profiles]**. Essa é a regra que você precisa usar ao segmentar dados meramente offline.
