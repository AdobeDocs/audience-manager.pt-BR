---
description: Os Destinos baseados em pessoas oferecem várias estratégias de implementação, dependendo de como os dados do cliente estão estruturados. Este artigo fornece uma visão geral das etapas de implementação que você precisa seguir para Destinos baseados em pessoas, dependendo do seu cenário.
seo-description: 'Os Destinos baseados em pessoas oferecem várias estratégias de implementação, dependendo de como os dados do cliente estão estruturados. Este artigo fornece uma visão geral das etapas de implementação que você precisa seguir para Destinos baseados em pessoas, dependendo do seu cenário.  '
seo-title: Diretrizes de implementação de destinos baseados em pessoas
solution: Audience Manager
title: Orientação de implementação
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# Orientação de implementação {#implementation-guidance}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a guiá-lo pela configuração e uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

[!DNL People-Based Destinations] oferece várias estratégias de implementação, dependendo de como os dados do cliente estão estruturados. Este artigo fornece uma visão geral das etapas de implementação que devem ser seguidas [!DNL People-Based Destinations], dependendo do seu cenário.

## Visão geral {#overview}

A configuração do [!DNL People-Based Destinations] leva você por várias seções do Audience Manager e requer configurações e métodos de integração de dados diferentes, dependendo do tipo de dados do cliente que você já tem no Audience Manager e do tipo de direcionamento de público-alvo que deseja executar.

>[!IMPORTANT]
> Antes de configurar [!DNL People-Based Destinations], leia este artigo com cuidado e completamente. Depois de ler este guia, você deve ter uma compreensão clara do cenário que estará ativando [!DNL People-Based Destinations].

Há seis aspectos de implementação que você precisa esclarecer antes de usar [!DNL People-Based Destinations]. Este artigo o ajudará a entender qual é a configuração atual, para que você possa seguir corretamente as etapas de implementação do cenário.

![pbd-implementação](assets/pbd-implementation.png)

## 1. Definindo o Caso de Uso {#defining-your-use-case}

Antes de começar a implementar [!DNL People-Based Destinations], é necessário definir claramente o caso de uso para o qual você usará esse recurso. Você pode usar [!DNL People-Based Destinations] para direcionar públicos-alvo de duas formas, com base na atividade do público-alvo:

**A) Direcionamento de público-alvo com base em sua atividade** combinada on-line e off-line de usuário. Nesse cenário, você deseja combinar dados de público-alvo existentes do Audience Manager com dados do seu [!DNL CRM] sistema interno e enviar os segmentos de público-alvo resultantes para [!DNL People-Based Destinations]. Este é um exemplo que ilustra este cenário:

Sua empresa, uma companhia aérea, tem diferentes níveis de clientes (Bronze, Prata e Ouro) e você deseja fornecer a cada um dos níveis ofertas personalizadas por meio de plataformas sociais. Use o Audience Manager para analisar a atividade do cliente em seu site. No entanto, nem todos os clientes usam o aplicativo móvel da companhia aérea e alguns deles não fizeram logon no site da empresa. Os dados do cliente estão limitados, na maioria das vezes, a IDs de associação e endereços de email.

Para direcioná-los pelas mídias sociais e canais semelhantes baseados em pessoas, você pode trazer seus endereços [de email com](people-based-destinations-prerequisites.md) hash para o Audience Manager e combiná-los com suas características de atividade online existentes, para criar novos segmentos de público-alvo. Em seguida, você pode usar esses segmentos para direcionar seu público-alvo até [!DNL People-Based Destinations].

**B) Segmentação de público-alvo com base exclusivamente na atividade** de usuário offline. Nesse cenário, seu [!DNL CRM] sistema contém seus endereços de email do cliente e outros atributos do cliente, mas os clientes não interagiram com seu site, portanto, você não tem nenhuma atividade do cliente no Audience Manager. Este é um exemplo que ilustra este cenário:

Sua empresa, um provedor de serviços de telecom, mantém os dados do cliente, como endereços de email e planos de telecom adquiridos em um ambiente interno [!DNL CRM]. Você deseja direcionar clientes existentes em plataformas sociais para oferecer pacotes de atualização com base em suas assinaturas existentes. Para fazer isso, você pode assimilar seus endereços de email do cliente em hash no Audience Manager e criar segmentos com base nas assinaturas do cliente existente. Em seguida, é possível enviar esses segmentos para [!DNL People-Based Destinations] direcionar seus clientes com ofertas personalizadas.

## 2. Definir o tipo de endereços de email direcionados {#define-target-email}

A segunda etapa para definir sua estratégia de implementação é decidir que tipo de endereços de email do cliente você deseja direcionar.

**A) Direcionamento de público-alvo com base em seus endereços** de email autenticados. Nesse cenário, seus usuários têm várias contas associadas a vários endereços de email e você deseja direcioná-los a ofertas personalizadas, com base apenas no endereço de email que eles autenticam em seu site, em tempo real.

**B) Direcionamento de público-alvo com base em todos os endereços** de email associados. Nesse cenário, seus usuários têm várias contas associadas a vários endereços de email e você deseja direcioná-los para todos os endereços de email associados, independentemente da atividade autenticada.

## 3. Identifique o tipo de IDs do cliente (IDs CRM) que você possui {#identify-customer-id}

A definição de público-alvo em [!DNL People-Based Destinations] requer o envio de versões [SHA256 com hash](people-based-destinations-prerequisites.md) dos endereços de email do cliente. Dependendo da configuração existente do Audience Manager, você pode se encontrar em uma das duas situações a seguir:

**A) Suas IDs de cliente do Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) já têm endereços** de email com hash em minúsculas. Nesse cenário, você pode usar essas IDs existentes para direcionar seus públicos-alvo em [!DNL People-Based Destinations].

**B) Suas IDs de cliente do Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) não são endereços** de email com hash em minúsculas. Nesse cenário, as IDs de cliente existentes não podem ser enviadas para [!DNL People-Based Destinations]. Para usar [!DNL People-Based Destinations], é necessário executar uma sincronização de ID entre as IDs do cliente existentes e as versões com hash em minúsculas dos endereços de email do cliente. Isso é feito por meio da sincronização [de ID baseada em](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) arquivo ou usando IDs [](../declared-ids.md)declaradas.

## 4. Qualificação das características {#trait-qualification}

Para direcionar com precisão seu público-alvo, [!DNL People-Based Destinations]os usuários precisam se qualificar para características baseadas em regras ou integradas, dependendo do tipo de direcionamento de público-alvo que você deseja executar.

**A) Qualifique suas IDs de cliente e IDs de dispositivo em tempo real para características** baseadas em regras. Essa opção se aplica ao uso do caso A a partir de [1. Definindo o Caso](people-based-destinations-workflow.md#defining-your-use-case)de Uso. Se o seu plano é direcionar públicos-alvo com base em atividades online e offline, você provavelmente já está qualificando seu público-alvo para características [baseadas em](../traits/trait-qualification-reference.md)regras.

**B) Características integradas às IDs do cliente por meio de arquivos** de dados de entrada. Esta opção se aplica ao uso do caso B a partir de [1. Definindo o Caso](people-based-destinations-workflow.md#defining-your-use-case)de Uso. Ao direcionar seu público-alvo com base em atividades meramente offline, é necessário qualificar as IDs do cliente para características integradas por meio de arquivos [de dados de](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)entrada.

## 5. Criar ou rotular fontes de dados e endereços de email com hash onboard {#create-label-data-sources}

Dependendo do tipo de IDs do cliente que você tem no Audience Manager (consulte [3. Identifique o tipo de IDs do cliente (IDs de CRM) que você possui](people-based-destinations-workflow.md#identify-customer-id), você se encontrará em uma das seguintes situações:

**A) Rotule uma fonte** de dados existente. Essa opção se aplica ao cenário em que as IDs do cliente do Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) já estão em minúsculas e com hash de endereços de email. Nessa situação, o que você precisa fazer é rotular sua fonte de dados na qual você armazena as IDs como uma fonte de [!DNL PII] dados. Consulte Configurações [da fonte de](../datasources-list-and-settings.md) dados para obter detalhes sobre as configurações da fonte de dados. O que você precisa fazer é verificar se a opção Não pode ser vinculada à opção de informações pessoalmente identificáveis está desmarcada.

**B) Criar uma nova fonte** de dados. Essa opção se aplica ao cenário em que as IDs do cliente do Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) não são endereços de email com hash. Nesse caso, é necessário criar uma nova fonte de dados entre dispositivos e seus endereços de email com hash integrados. Você pode fazer isso de duas maneiras:

* Use a sincronização de ID baseada em arquivo. Consulte Requisitos de [nome e conteúdo para arquivos](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) de sincronização de ID para obter detalhes sobre a aparência dos arquivos de sincronização de ID. Ao usar esse método, você pode direcionar todos os seus endereços de email com hash do seu [!DNL CRM] banco de dados.
* Use as IDs [](../declared-ids.md) declaradas para declarar seus endereços de email com hash ao transmitir IDs autenticadas do cliente. Ao usar esse método, o Audience Manager, em seu nome, direciona somente seus endereços de email com hash de usuários que se autenticaram online. Os endereços de e-mail direcionados nos canais baseados em pessoas são apenas aqueles nas chamadas de evento de ID declaradas. Outros endereços de email associados à ID do cliente não são ativados em tempo real.

## 6. Usar uma regra de mesclagem de perfil para segmentação {#use-profile-merge-rules}

Dependendo do caso de uso (consulte [1. Definindo seu caso](people-based-destinations-workflow.md#defining-your-use-case)de uso), há duas maneiras de usar [!DNL Profile Merge Rules] para segmentação.

**A) Usar existentes[!DNL Profile Merge Rules]**. Essa opção se aplica ao caso de primeira utilização (direcionamento de público-alvo com base na atividade combinada on-line e off-line do usuário). Nesse cenário, você já possui uma atividade do cliente no Audience Manager e já definiu pelo menos uma Regra de mesclagem de perfil usada na segmentação. Neste caso, você não precisa criar nenhuma nova [!DNL Profile Merge Rules].

**B) Criar uma nova regra[!DNL All Cross-Device Profiles]de mesclagem**. Essa opção se aplica ao segundo caso de uso (direcionamento de público-alvo baseado exclusivamente na atividade offline do usuário). Neste cenário, você está trazendo seus dados de cliente offline do seu [!DNL CRM] para o Audience Manager e deseja criar segmentos a partir desses dados. Para fazer isso, [!DNL People-Based Destinations] introduz uma nova, quarta Regra de mesclagem de perfil, chamada **[!DNL All Cross-Device Profiles]**. Essa é a regra que você precisa usar ao segmentar dados puramente offline.
