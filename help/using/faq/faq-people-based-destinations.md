---
description: 'Respostas a perguntas comuns sobre destinos baseados em pessoas.  '
seo-description: 'Respostas a perguntas comuns sobre destinos baseados em pessoas.  '
seo-title: Perguntas frequentes sobre destinos de pessoas
solution: Audience Manager
title: Perguntas frequentes sobre destinos de pessoas
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# Perguntas frequentes sobre destinos de pessoas {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Availability {#availability}

**Não posso visualizar[!DNL People-Based Destinations]na minha conta do Audience Manager. O que preciso saber sobre a disponibilidade?**

[!DNL People-Based Destinations] é um recurso premium do Audience Manager disponível na compra. Entre em contato com seu representante de vendas da Adobe para obter detalhes sobre os preços e a disponibilidade.

## Onboard de dados {#data-onboarding}

**Como posso usar os endereços de email do cliente no Audience Manager para que eu possa usá-los[!DNL People-Based Destinations]?**

Há duas maneiras de inserir seus dados offline para [!DNL People-Based Destinations]o Audience Manager.

* **Use a sincronização de ID com base em arquivo**. Consulte [Requisitos de nome e conteúdo para arquivos de sincronização de ID](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) para obter detalhes sobre quais arquivos de sincronização de ID devem ser semelhantes. Ao usar esse método, você pode direcionar todos os endereços de email com hash do [!DNL CRM] banco de dados.
* **Use IDs declaradas** para declarar endereços de email com hash ao passar em IDs autenticadas do cliente. Ao usar esse método, o Audience Manager ativa apenas os endereços de email com hash de usuários que têm autenticado online. Os endereços de email ativados por meio do Facebook são apenas aqueles nas chamadas declaradas do evento de ID. Outros endereços de email associados à ID do cliente não são ativados em tempo real.

**É possível coletar endereços de email com hash por meio de um formulário da Web ou aplicativo para dispositivos móveis, ou eles devem aparecer em um arquivo em lote?**

É possível coletar endereços de email com hash por meio de autenticação na Web usando [!DNL ECID] IDs [declaradas](../features/declared-ids.md). O arquivo em lote permite também coletar endereços de email com hash que não podem ser enviados por meio da autenticação (por exemplo, usuários dormant em sua ([!DNL CRM]) e ativados em destinos baseados em pessoas.

**Como assimilar endereços de email com hash por meio de formulários da Web diferente do upload de endereços de email com hash por arquivos em lote?**

A ingestão de dados offline é projetada para suportar casos de uso sem autenticação e uma nova regra de mesclagem de perfil ([!UICONTROL All Cross-Device Profiles]) que é executada em todos os perfis offline [!DNL CRM] independentemente da autenticação está disponível como parte [!DNL People-Based Destinations]de. Esse método destina-se a complementar a ingestão de públicos-alvo autenticados a partir de fontes online.

**Qual é a frequência máxima em que posso enviar/atualizar endereços de email com hash?**

* Ao usar IDs declaradas, o Audience Manager envia os endereços de email com hash para o destino em tempo real.
* Ao assimilar dados por meio de arquivos de sincronização de ID, o Audience Manager os processa diariamente.

**Como faço para saber se o hash do endereço de email foi executado corretamente?**

O Audience Manager não está assimilando o endereço de email bruto e não é possível validar se o hash foi executado corretamente. Consulte [Pré-requisitos e considerações](../features/destinations/people-based-destinations-prerequisites.md) para obter detalhes sobre como fazer hash os dados integrados.

## Regras de mesclagem de perfil {#profile-merge-rules}

**Há uma nova regra de mesclagem de perfis com a[!DNL People-Based Destinations]qual posso usar?**

Sim. Os clientes que compram também [!DNL People-Based Destinations] recebem acesso a uma nova regra de mesclagem de perfil para segmentação offline. A regra é chamada [!DNL All Cross-Device Profiles] e é usada para segmentação offline. Ao se inscrever [!DNL People-Based Destinations], esta é a quarta regra de mesclagem de perfil que pode ser criada, além das três regras existentes baseadas em autenticação.

**Preciso duplicar meus segmentos de público-alvo existentes para ativá-los[!DNL People-Based Destinations]?**

Depende do caso de uso. Se você planeja ativar segmentos primários existentes em canais baseados em pessoas, não é necessário criar novos segmentos. Você pode mapear os segmentos para um destino baseado em pessoas.

Se você planeja ativar novos públicos offline em canais baseados em pessoas, é necessário criar novos segmentos originais usando a regra [!DNL All Cross-Device Profiles] de mesclagem.
>[!NOTE]
>
> É possível mapear somente segmentos com dados primários para [!DNL People-Based Destinations]. Nossas plataformas de destino não aceitam segmentos com dados de segundo e de terceiros.

## Taxas de Correspondência {#match-rates}

**Tem visibilidade[!DNL People-Based Destinations]em taxas de correspondência ou públicos-alvo endereçáveis?**

Não. Ao enviar segmentos de público-alvo para [!DNL People-Based Destinations], a correspondência do público-alvo ocorre no parceiro. A Adobe não tem acesso a essas métricas. O Audience Manager mostra o público-alvo compartilhável máximo para cada destino e a contagem em tempo real das pessoas pertencentes a um segmento. Essas informações podem ajudá-lo com planejamento e previsão da campanha.

**Como as taxas de correspondência podem ser comparadas[!DNL People-Based Destinations]teoricamente com outros métodos de envio de público-alvo às plataformas de destino?**

Contanto que o endereço de email seja hash e assimilado corretamente, não deve haver diferença na taxa de correspondência entre [!DNL People-Based Destinations] e outros métodos. A única razão pela qual uma taxa de correspondência seria inferior a 100% seria se os endereços de email trazidos para o Audience Manager não puderem ser combinados com um endereço de email na base de usuário da plataforma de destino.

**Eu coleto endereços de email de trabalho de meus clientes, que são diferentes dos endereços de email pessoais usados em redes sociais. Como você corresponde a identidades em vários endereços de email?**

O Audience Manager pode coletar e enviar até 10 emails por usuário às plataformas de destino, mas os endereços de email precisam ser capturados por meio de arquivos de sincronização. Depois que o Audience Manager envia os endereços de email para plataformas de destino, as plataformas correspondem aos endereços de email de sua própria base de usuários. Algumas plataformas podem ter gráficos de endereço de email adicionais para corresponder aos endereços enviados do Audience Manager para perfis de usuário.

## Controles da exportação de dados {#data-export-controls}

**Como[!DNL Data Export Controls]funciona[!DNL People-Based Destinations]?**

[!DNL Data Export Controls] bloqueará todos os segmentos que contêm dados de segunda e de terceiros que os usuários tentam enviar [!DNL People-Based Destinations]. [!DNL People-Based Destinations] permitir que os dados originais sejam usados para definição de metas. [!DNL Data Export Controls] também bloqueie segmentos usando [!DNL Profile Merge Rules] gráficos de dispositivo. [!DNL People-Based Destinations] são criados com os rótulos de exportação de dados apropriados marcados e não é possível substituir as configurações de exportação.

## Perguntas específicas do parceiro {#partner-specific-questions}

### [!DNL Facebook]

**O que preciso fazer antes de enviar segmentos de público-alvo para[!DNL Facebook]?**

Antes de usar [!DNL People-Based Destinations] para enviar segmentos de público-alvo para [!DNL Facebook], você precisa executar as seguintes tarefas de configuração:

1. Adicione a conta comercial da Adobe Experience Cloud como um parceiro de publicidade em seu [!DNL Facebook Ad Account]. Use `business ID=206617933627973`. Consulte Adicionar parceiros ao seu gerente de negócios para obter mais detalhes.

   >[!IMPORTANT]
   >
   > Ao configurar as permissões para a Adobe Experience Cloud, você deve habilitar a permissão Gerenciar campanhas. Isso é necessário para [!DNL People-Based Destinations] a integração.

1. Leia e assine o [!DNL Facebook Custom Audiences Terms of Service]. Para fazer isso, vá para `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, onde `accountID` é seu [!DNL Facebook Ad Account ID].

**[!DNL People-Based Destinations]Suporta o direcionamento de público-alvo em outros[!DNL Facebook]aplicativos, como[!DNL Instagram]?**

Você pode usar [!DNL People-Based Destinations] toda [!DNL Facebook]a família de aplicativos compatíveis com [!DNL Custom Audiences], incluindo [!DNL Facebook], [!DNL Instagram][!DNL Audience Network] e [!DNL Messenger]. A seleção do aplicativo que você deseja executar campanha é indicada no nível da disposição.[!DNL Facebook Ads Manager]

**Qual é a diferença entre[!DNL People-Based Destinations]e[!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] aproveita a [!DNL Custom Audiences (CA)] integração com [!DNL Facebook]. A diferença entre [!DNL WCA] e [!DNL CA] integrações é a chave que os clientes usam ao enviar públicos-alvo para [!DNL Facebook]. [!DNL WCA] usa o [!DNL Facebook] pixel (que seria uma ID de usuário do site) ao [!DNL People-Based Destinations] usar endereços de email com hash para integração [!DNL CA].

Você pode usar [!DNL Facebook][!DNL WCA] a integração do Audience Manager através do [!DNL URL Destinations] recurso sem custo extra.

Essas duas integrações são complementares; você pode usar ambos para garantir uma melhor cobertura de público-alvo. Por exemplo, [!DNL WCA] pode ser usado para a prospecção quando uma empresa procura os visitantes do site que não registraram uma conta, enquanto [!DNL People-Based Destinations] que podem ajudar a direcionar clientes existentes que forneceram seu endereço de email, mas que talvez não tenham visitado o site.
