---
description: Destinos baseados em pessoas oferta várias estratégias de implementação, dependendo de como os dados do cliente estão estruturados. Este artigo fornece uma visão geral das etapas de implementação que você precisa seguir para Destinos baseados em pessoas, dependendo do seu cenário.
seo-description: 'Destinos baseados em pessoas oferta várias estratégias de implementação, dependendo de como os dados do cliente estão estruturados. Este artigo fornece uma visão geral das etapas de implementação que você precisa seguir para Destinos baseados em pessoas, dependendo do seu cenário.  '
seo-title: Diretrizes de implementação de destinos baseados em pessoas
solution: Audience Manager
title: Orientação de implementação
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1379'
ht-degree: 2%

---


# Diretrizes de implementação {#implementation-guidance}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo durante a configuração e o uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

[!DNL People-Based Destinations] oferta várias estratégias de implementação, dependendo de como os dados do cliente estão estruturados. Este artigo fornece uma visão geral das etapas de implementação que você precisa seguir para [!DNL People-Based Destinations], dependendo do seu cenário.

## Visão geral {#overview}

A configuração de [!DNL People-Based Destinations] o orienta por várias seções do Audience Manager e requer configurações e métodos de integração de dados diferentes, dependendo do tipo de dados do cliente que você já possui no Audience Manager e do tipo de direcionamento de audiência que deseja executar.

>[!IMPORTANT]
> Antes de configurar [!DNL People-Based Destinations], leia este artigo com cuidado e completamente. Depois de ler este guia, você deve ter uma compreensão clara do cenário que estará ativando por meio de [!DNL People-Based Destinations].

Há seis aspectos de implementação que você precisa esclarecer antes de usar [!DNL People-Based Destinations]. Este artigo o ajudará a entender qual é a configuração atual, para que você possa seguir corretamente as etapas de implementação do cenário.

![pbd-implementação](assets/pbd-implementation.png)

## 1. Definindo o Caso de Uso {#defining-your-use-case}

Antes de começar a implementar [!DNL People-Based Destinations], é necessário definir claramente o caso de uso para o qual você usará esse recurso. Você pode usar [!DNL People-Based Destinations] para público alvo de audiências de duas formas, com base na atividade da audiência:

**A) direcionamento de Audiência com base na sua atividade** combinada de usuário online e offline. Nesse cenário, você deseja combinar dados de audiência existentes do Audience Manager com dados do seu sistema interno [!DNL CRM] e enviar os segmentos de audiência resultantes para [!DNL People-Based Destinations]. Este é um exemplo que ilustra este cenário:

Sua empresa, uma companhia aérea, tem níveis de clientes diferentes (Bronze, Prata e Ouro) e você deseja fornecer a cada um dos níveis ofertas personalizadas por meio de plataformas sociais. Use o Audience Manager para analisar a atividade do cliente em seu site. No entanto, nem todos os clientes usam o aplicativo móvel da companhia aérea e alguns deles não fizeram logon no site da empresa. Os dados do cliente estão limitados, na maioria das vezes, a IDs de associação e endereços de email.

Para público alvo-los nas mídias sociais e canais semelhantes baseados em pessoas, você pode trazer seus [endereços de email com hash](people-based-destinations-prerequisites.md) para o Audience Manager e combiná-los com suas características de atividade online existentes, para criar novos segmentos de audiência. Em seguida, você pode usar esses segmentos para público alvo de sua audiência por [!DNL People-Based Destinations].

**B) Direcionamento de Audiência baseado exclusivamente na atividade** do usuário offline. Nesse cenário, seu sistema [!DNL CRM] contém seus endereços de email de cliente e outros atributos do cliente, mas os clientes não interagiram com seu site, portanto, você não tem nenhuma atividade do cliente no Audience Manager. Este é um exemplo que ilustra este cenário:

Sua empresa, um provedor de serviços de telecom, mantém os dados do cliente, como endereços de email e planos de telecom adquiridos em um [!DNL CRM] interno. Você deseja público alvo clientes existentes em plataformas sociais para oferta-los em pacotes de atualização com base em suas subscrições existentes. Para fazer isso, você pode assimilar seus endereços de email do cliente em hash no Audience Manager e criar segmentos com base nas subscrições do cliente existente. Em seguida, você pode enviar esses segmentos para [!DNL People-Based Destinations] para público alvo de seus clientes com ofertas personalizadas.

## 2. Defina o tipo de endereços de email direcionados {#define-target-email}

A segunda etapa para definir sua estratégia de implementação é decidir que tipo de endereços de email do cliente você deseja público alvo.

**A) direcionamento de Audiência com base em seus endereços** de email autenticados. Nesse cenário, seus usuários têm várias contas associadas a vários endereços de email e você deseja público alvo-los com ofertas personalizadas, com base apenas no endereço de email que eles autenticam em seu site, em tempo real.

**B) direcionamento de Audiência com base em todos os endereços** de email associados. Nesse cenário, seus usuários têm várias contas associadas a vários endereços de email e você deseja público alvo-los em todos os endereços de email associados, independentemente da atividade autenticada.

## 3. Identifique o tipo de IDs do cliente (IDs CRM) que você possui {#identify-customer-id}

Audiências de definição de metas em [!DNL People-Based Destinations] exigem que você envie [SHA256 versões com hash](people-based-destinations-prerequisites.md) dos endereços de email do cliente. Dependendo da configuração de Audience Manager existente, você pode se encontrar em uma das duas situações a seguir:

**A) Suas IDs do cliente do Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) já têm endereços** de email em letras minúsculas e com hash. Nesse cenário, você pode usar essas IDs existentes para público alvo de suas audiências em [!DNL People-Based Destinations].

**B) As IDs do cliente do seu Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) não são endereços** de email em letras minúsculas e com hash. Nesse cenário, as IDs de cliente existentes não podem ser enviadas para [!DNL People-Based Destinations]. Para usar [!DNL People-Based Destinations], é necessário executar uma sincronização de ID entre as IDs do cliente existentes e as versões em hash minúsculas dos endereços de email do cliente. Você faz isso por meio de [sincronização de ID baseada em arquivo](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ou usando [IDs declaradas](../declared-ids.md).

## 4. Qualificação de características {#trait-qualification}

Para público alvo preciso de sua audiência em [!DNL People-Based Destinations], seus usuários precisam se qualificar para características integradas ou baseadas em regras, dependendo do tipo de direcionamento de audiência que você deseja executar.

**A) Qualifique suas IDs de cliente e IDs de dispositivo em tempo real para características** baseadas em regras. Esta opção se aplica ao caso de uso A de [1. Definindo o Caso de Uso](people-based-destinations-workflow.md#defining-your-use-case). Se seu plano é público alvo de audiências com base em atividades on-line e off-line, você provavelmente já está qualificando sua audiência para [características com base em regras](../traits/trait-and-segment-qualification-reference.md).

**B) Características integradas às IDs do cliente por meio de arquivos** de dados de entrada. Esta opção se aplica ao uso do caso B de [1. Definindo o Caso de Uso](people-based-destinations-workflow.md#defining-your-use-case). Ao direcionar sua audiência com base em atividade meramente offline, é necessário qualificar as IDs do cliente para características integradas por meio de [arquivos de dados de entrada](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## 5. Criar ou rotular fontes de dados e endereços de email com hash onboard {#create-label-data-sources}

Dependendo do tipo de IDs do cliente que você tem no Audience Manager (consulte [3. Identifique o tipo de IDs do cliente (IDs CRM) que você possui](people-based-destinations-workflow.md#identify-customer-id), você se encontrará em uma das seguintes situações:

**A) Rotule uma fonte** de dados existente. Essa opção se aplica ao cenário em que as IDs do cliente do Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) já estão em minúsculas e com hash de endereços de email. Nessa situação, o que você precisa fazer é rotular sua fonte de dados na qual você armazena as IDs como uma fonte de dados [!DNL PII]. Consulte [Configurações da fonte de dados](../datasources-list-and-settings.md) para obter detalhes sobre as configurações da fonte de dados. O que você precisa fazer é verificar se a opção Não pode ser vinculada à opção de informações pessoalmente identificáveis está desmarcada.

**B) Criar uma nova fonte** de dados. Essa opção se aplica ao cenário em que as IDs do cliente do Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) não são endereços de email com hash. Nesse caso, é necessário criar uma nova fonte de dados entre dispositivos e seus endereços de email com hash a bordo. Você pode fazer isso de duas maneiras:

* Usar a sincronização de ID com base em arquivos. Consulte [Requisitos de nome e conteúdo para arquivos de sincronização de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) para obter detalhes sobre a aparência dos arquivos de sincronização de ID. Ao usar esse método, você pode público alvo todos os seus endereços de email com hash do banco de dados [!DNL CRM].
* Use [IDs declaradas](../declared-ids.md) para declarar seus endereços de email com hash ao transmitir IDs autenticadas do cliente. Ao usar esse método, o Audience Manager, em seu nome, público alvo somente seus endereços de email com hash de usuários que se autenticaram online. Os endereços de e-mail direcionados em canais baseados em pessoas são apenas aqueles nas chamadas declaradas do evento de ID. Outros endereços de email associados à ID do cliente não são ativados em tempo real.

## 6. Usar uma regra de mesclagem de Perfil para segmentação {#use-profile-merge-rules}

Dependendo do caso de uso (consulte [1. Definindo seu caso de uso](people-based-destinations-workflow.md#defining-your-use-case)), há duas maneiras de usar [!DNL Profile Merge Rules] para segmentação.

**A) Usar existentes[!DNL Profile Merge Rules]**. Esta opção se aplica ao caso de primeira utilização (direcionamento de audiência com base na atividade combinada de usuários online e offline). Nesse cenário, você já possui uma atividade de cliente no Audience Manager e já definiu pelo menos uma Regra de mesclagem de Perfil que você usou na segmentação. Nesse caso, você não precisa criar nenhum novo [!DNL Profile Merge Rules].

**B) Criar uma nova regra [!DNL All Cross-Device Profiles]  de** mesclagem. Essa opção se aplica ao segundo caso de uso (direcionamento de audiência baseado exclusivamente na atividade do usuário offline). Neste cenário, você está trazendo seus dados offline do cliente de [!DNL CRM] para o Audience Manager e deseja criar segmentos a partir desses dados. Para fazer isso, [!DNL People-Based Destinations] introduz uma nova e quarta regra de mesclagem de Perfis, chamada **[!DNL All Cross-Device Profiles]**. Essa é a regra que você precisa usar ao segmentar dados puramente offline.
