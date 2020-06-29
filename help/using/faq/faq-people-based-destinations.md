---
description: 'Respostas a perguntas comuns sobre destinos baseados em pessoas.  '
seo-description: 'Respostas a perguntas comuns sobre destinos baseados em pessoas.  '
seo-title: Perguntas frequentes sobre destinos baseados em pessoas
solution: Audience Manager
title: Perguntas frequentes sobre destinos baseados em pessoas
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 0%

---


# Perguntas frequentes sobre destinos baseados em pessoas {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Availability {#availability}

**Não consigo ver[!DNL People-Based Destinations]na minha conta de Audience Manager. O que preciso saber sobre a disponibilidade?**

[!DNL People-Based Destinations] é um recurso de Audience Manager premium que está disponível na compra. Entre em contato com seu representante de vendas da Adobe para obter detalhes sobre preços e disponibilidade.

## Integração de dados {#data-onboarding}

**Como posso integrar endereços de email de clientes no Audience Manager, para que possa usá-los no[!DNL People-Based Destinations]?**

Há duas maneiras de trazer seus dados offline para o Audience Manager [!DNL People-Based Destinations].

* **Use a sincronização** de ID baseada em arquivo. Consulte Requisitos de [nome e conteúdo para arquivos](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) de sincronização de ID para obter detalhes sobre a aparência dos arquivos de sincronização de ID. Ao usar esse método, você pode público alvo todos os endereços de email com hash do seu [!DNL CRM] banco de dados.
* **Use as IDs** declaradas para declarar endereços de email com hash ao transmitir IDs autenticadas do cliente. Ao usar esse método, o Audience Manager ativa somente os endereços de email com hash de usuários que se autenticaram on-line. Os endereços de email ativados pelo Facebook são apenas aqueles nas chamadas de evento de ID declaradas. Outros endereços de email associados à ID do cliente não são ativados em tempo real.

**É possível coletar endereços de email em hash por meio de um formulário da Web ou aplicativo móvel ou eles precisam ser exibidos em um arquivo em lote?**

Você pode coletar endereços de email com hash por meio da autenticação da Web usando [!DNL ECID] com IDs [declaradas](../features/declared-ids.md). O arquivo em lote também permite coletar endereços de email com hash que não podem ser enviados por meio de autenticação (por exemplo, usuários dormentes em seus ([!DNL CRM]) e ativá-los em destinos baseados em pessoas.

**Como a ingestão de endereços de email com hash por meio de formulários da Web é diferente do carregamento de endereços de email com hash por meio de arquivos em lote?**

A ingestão de dados offline foi projetada para suportar casos de uso sem autenticação, e uma nova regra de mesclagem de perfis ([!UICONTROL All Cross-Device Profiles]) que é executada em todos os [!DNL CRM] perfis offline independentemente da autenticação está disponível como parte do [!DNL People-Based Destinations]. Este método destina-se a complementar a ingestão de audiências autenticadas de fontes online.

**Qual é a frequência máxima na qual posso enviar/atualizar endereços de email com hash?**

* Ao usar IDs declaradas, o Audience Manager envia os endereços de email com hash para o destino em tempo real.
* Ao assimilar dados por meio de arquivos de sincronização de ID, o Audience Manager os processa diariamente.

**Como faço para saber se o hash do endereço de email está sendo feito corretamente?**

O Audience Manager não está ingerindo o endereço de email bruto e não podemos validar se o hash foi executado corretamente. Consulte [Pré-requisitos e Considerações](../features/destinations/people-based-destinations-prerequisites.md) para obter detalhes sobre como você deve executar hash nos dados integrados.

## Regras de mesclagem de Perfis {#profile-merge-rules}

**Existe uma nova regra de união de perfis que eu possa usar com[!DNL People-Based Destinations]?**

Sim. Os clientes que compram também [!DNL People-Based Destinations] recebem acesso a uma nova regra de mesclagem de perfis para segmentação offline. A regra é chamada [!DNL All Cross-Device Profiles] e é usada para segmentação offline somente. Ao se inscrever para [!DNL People-Based Destinations], esta é a quarta regra de mesclagem de perfil que você pode criar, além das três regras baseadas em autenticação existentes.

**Preciso duplicado meus segmentos de audiência existentes para ativá-los no[!DNL People-Based Destinations]?**

Depende do caso de uso. Se você planeja ativar segmentos primários existentes em canais baseados em pessoas, não é necessário criar novos segmentos. Você pode mapear os segmentos para um destino baseado em pessoas.

Se você planeja ativar novas audiências offline em canais baseados em pessoas, é necessário criar novos segmentos primários usando a regra de [!DNL All Cross-Device Profiles] mesclagem.
>[!NOTE]
>
> Você só pode mapear segmentos com dados primários para [!DNL People-Based Destinations]. Nossas plataformas de destino não aceitam segmentos com dados de terceiros e segundos.

## Taxas de correspondência {#match-rates}

**Você[!DNL People-Based Destinations]tem visibilidade sobre as taxas de correspondência ou audiências endereçáveis?**

Não. Ao enviar segmentos de audiência para [!DNL People-Based Destinations], a correspondência de audiência ocorre no lado do parceiro. A Adobe não tem acesso a essas métricas. Audience Manager mostra a audiência máxima compartilhável para cada destino e a contagem em tempo real de pessoas que pertencem a um segmento. Essas informações podem ajudá-lo com planejamento e previsão de campanhas.

**Como as taxas corresponderiam usando uma comparação[!DNL People-Based Destinations]teórica com outros métodos de envio de audiências para plataformas de destino?**

Desde que o endereço de email tenha hash e seja assimilado corretamente, não deve haver diferença na taxa de correspondência entre [!DNL People-Based Destinations] e outros métodos. A única razão pela qual uma taxa de correspondência seria inferior a 100% é se os endereços de email trazidos para o Audience Manager não puderem ser combinados com um endereço de email na base de usuários da plataforma de destino.

**Coleciono endereços de email de trabalho de meus clientes, que são diferentes dos endereços de email pessoais usados nas redes sociais. Como você faz a correspondência de identidades em vários endereços de email?**

O Audience Manager pode coletar e enviar até 10 emails por usuário para plataformas de destino, mas os endereços de email precisam ser capturados por meio de arquivos de sincronização. Depois que o Audience Manager envia os endereços de email para as plataformas de destino, cabe às plataformas combinar os endereços de email com sua própria base de usuários. Algumas plataformas podem ter gráficos adicionais de endereço de email para corresponder a endereços enviados de Audience Manager para perfis de usuários.

## Controles da exportação de dados {#data-export-controls}

**Como[!DNL Data Export Controls]trabalhar com[!DNL People-Based Destinations]?**

[!DNL Data Export Controls] bloqueará quaisquer segmentos que contenham dados de terceiros e de segundo para os quais os usuários tentarem enviar [!DNL People-Based Destinations]. [!DNL People-Based Destinations] permite que somente dados primários sejam usados para definição de metas. [!DNL Data Export Controls] também bloqueie segmentos usando [!DNL Profile Merge Rules] gráficos de dispositivos. [!DNL People-Based Destinations] são criados com as etiquetas de exportação de dados apropriadas marcadas e não é possível substituir as configurações de exportação.

## Perguntas específicas do parceiro {#partner-specific-questions}

### [!DNL Facebook]

**O que preciso fazer antes de enviar segmentos de audiência para[!DNL Facebook]?**

Antes de poder usar [!DNL People-Based Destinations] para enviar segmentos de audiência para [!DNL Facebook], é necessário executar as seguintes tarefas de configuração:

1. Adicione a conta comercial da Adobe Experience Cloud como um parceiro de publicidade em sua [!DNL Facebook Ad Account]conta. Use `business ID=206617933627973`. Consulte Adicionar parceiros ao seu gerente de negócios para obter detalhes.

   >[!IMPORTANT]
   >
   > Ao configurar as permissões para a Adobe Experience Cloud, você deve ativar a permissão Gerenciar campanhas. Isso é necessário para a [!DNL People-Based Destinations] integração.

1. Leia e assine o [!DNL Facebook Custom Audiences Terms of Service]. Para fazer isso, vá para `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, onde `accountID` está seu [!DNL Facebook Ad Account ID].

**É[!DNL People-Based Destinations]compatível com o direcionamento de audiência em outros[!DNL Facebook]aplicativos, como[!DNL Instagram]?**

Você pode usar [!DNL People-Based Destinations] a família [!DNL Facebook]de aplicativos suportados por [!DNL Custom Audiences], incluindo [!DNL Facebook], [!DNL Instagram]e [!DNL Audience Network] [!DNL Messenger]. A seleção do aplicativo no qual você deseja executar a campanha é indicada no nível de posicionamento em [!DNL Facebook Ads Manager].

**Qual é a diferença entre[!DNL People-Based Destinations]e[!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] aproveita a [!DNL Custom Audiences (CA)] integração com [!DNL Facebook]. A diferença entre [!DNL WCA] e [!DNL CA] integrações é a chave que os clientes usam ao enviar audiências para [!DNL Facebook]. [!DNL WCA] usa o [!DNL Facebook] pixel (que seria uma ID de usuário do site) ao [!DNL People-Based Destinations] usar endereços de email com hash para integrar-se com [!DNL CA].

Você pode usar a integração do Audience Manager [!DNL Facebook][!DNL WCA] através do [!DNL URL Destinations] recurso sem custo extra.

Estas duas integrações são complementares; você pode usar ambos para garantir uma melhor cobertura da audiência. Como exemplo, [!DNL WCA] pode ser usado para a prospecção quando uma empresas está procurando visitantes de sites de públicos alvos que não registraram uma conta, enquanto [!DNL People-Based Destinations] pode ajudá-lo a público alvo de clientes existentes que forneceram seu endereço de email, mas talvez não visitaram o site.
