---
description: 'Respostas a perguntas comuns sobre Destinos com base pessoas.  '
seo-description: 'Respostas a perguntas comuns sobre Destinos com base pessoas.  '
seo-title: Perguntas frequentes sobre Destinos com base em pessoas
solution: Audience Manager
title: Perguntas frequentes sobre Destinos com base em pessoas
feature: People-based Destinations
exl-id: 56506bf0-45f1-49df-81ac-10f57a2487eb
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 94%

---

# Perguntas frequentes sobre Destinos com base em pessoas {#people-based-destinations-faq}

Respostas às perguntas comuns sobre [!DNL People-Based Destinations].

## Disponibilidade {#availability}

**Não consigo ver [!DNL People-Based Destinations] na minha conta do Audience Manager. O que preciso saber sobre disponibilidade?**

[!DNL People-Based Destinations] é um recurso premium do Audience Manager disponível na compra. Entre em contato com seu representante de vendas da Adobe para obter detalhes sobre preços e disponibilidade.

## Integração de dados {#data-onboarding}

**Como posso integrar endereços de email de clientes no Audience Manager para usar nos [!DNL People-Based Destinations]?**

Há duas maneiras de trazer seus dados offline para o Audience Manager para [!DNL People-Based Destinations].

* **Usar a sincronização de ID com base em arquivos**. Consulte [Requisitos de nome e conteúdo para arquivos de sincronização de ID](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) para obter detalhes sobre a aparência dos arquivos de sincronização de ID. Ao usar esse método, você pode direcionar todos os endereços de email com hash do seu banco de dados de [!DNL CRM].
* **Usar IDs declaradas** para declarar endereços de email com hash ao transmitir IDs autenticadas do cliente. Ao usar esse método, o Audience Manager ativa somente os endereços de email com hash de usuários que autenticaram online. Os endereços de email ativados pelo Facebook são apenas os que estão nas chamadas de evento de ID declaradas. Outros endereços de email associados à ID do cliente não são ativados em tempo real.

**É possível coletar endereços de email com hash por meio de um formulário da Web ou aplicativo móvel ou eles precisam ser exibidos em um arquivo em lote?**

Você pode coletar endereços de email com hash por meio da autenticação da Web usando a [!DNL ECID] com [IDs declaradas](../features/declared-ids.md). O arquivo em lote também permite coletar endereços de email com hash que não podem ser enviados por meio de autenticação (por exemplo, usuários dormentes em seus ([!DNL CRM]) e ativá-los em destinos com base em pessoas.

**Como a assimilação de endereços de email com hash por meio de formulários da Web é diferente do carregamento de endereços de email com hash por meio de arquivos em lote?**

A assimilação de dados offline foi projetada para atender a casos de uso sem autenticação, e uma nova regra de mesclagem de perfis ([!UICONTROL All Cross-Device Profiles]) que é executada em todos os perfis offline de [!DNL CRM] independentemente da autenticação está disponível como parte de [!DNL People-Based Destinations]. Esse método complementa a assimilação de públicos autenticados de fontes online.

**Qual é a frequência máxima na qual posso enviar/atualizar endereços de email com hash?**

* Ao usar IDs declaradas, o Audience Manager envia os endereços de email com hash para o destino em tempo real.
* Ao assimilar dados por meio de arquivos de sincronização de ID, o Audience Manager os processa diariamente.

**Como faço para saber se o hash do endereço de email está sendo feito corretamente?**

O Audience Manager não está assimilando o endereço de email bruto e não podemos validar se o hash foi executado corretamente. Consulte [Pré-requisitos e considerações](../features/destinations/people-based-destinations-prerequisites.md) para obter detalhes sobre como você deve fazer a execução de hash nos dados integrados.

## Regras de mesclagem de perfis {#profile-merge-rules}

**Existe uma nova regra de mesclagem de perfis que pode ser usada com [!DNL People-Based Destinations]?**

Sim. Os clientes que compram [!DNL People-Based Destinations] também recebem acesso a uma nova regra de mesclagem de perfis para segmentação offline. A regra é chamada [!DNL All Cross-Device Profiles] e é usada somente para segmentação offline. Ao se inscrever para [!DNL People-Based Destinations], esta é a quarta regra de mesclagem de perfis que você pode criar, além das três regras com base em autenticação existentes.

**Preciso duplicar meus segmentos de público-alvo existentes para ativá-los em [!DNL People-Based Destinations]?**

Depende do caso de uso. Se você quiser ativar segmentos primários existentes em canais com base em pessoas, não é necessário criar novos segmentos. Você pode mapear os segmentos para um destino com base em pessoas.

Se você quiser ativar novos públicos offline em canais com base em pessoas, é necessário criar novos segmentos primários usando a regra de mesclagem [!DNL All Cross-Device Profiles].
>[!NOTE]
>
> Somente é possível mapear segmentos com dados primários para [!DNL People-Based Destinations]. Nossas plataformas de destino não aceitam segmentos com dados secundários e de terceiros.

## Taxas de correspondência {#match-rates}

**Os [!DNL People-Based Destinations] têm visibilidade sobre as taxas de correspondência ou públicos endereçáveis?**

Não. Ao enviar segmentos de público-alvo para [!DNL People-Based Destinations], a correspondência de públicos-alvo ocorre no lado do parceiro. A Adobe não tem acesso a essas métricas. O Audience Manager mostra o máximo de públicos compartilháveis para cada destino e a contagem em tempo real de pessoas que pertencem a um segmento. Essas informações podem ajudar com o planejamento e a previsão de campanhas.

**Como as taxas de correspondência usando [!DNL People-Based Destinations] se comparam teoricamente a outros métodos de envio de públicos para plataformas de destino?**

Desde que o endereço de email tenha hash e seja assimilado corretamente, não deve haver diferença na taxa de correspondência entre [!DNL People-Based Destinations] e outros métodos. A única razão pela qual uma taxa de correspondência seria inferior a 100% é se os endereços de email trazidos para o Audience Manager não puderem ser combinados com um endereço de email na base de usuários da plataforma de destino.

**Coleto endereços de email comerciais de clientes, que são diferentes dos endereços de email pessoais usados nas redes sociais. Como você faz a correspondência de identidades em vários endereços de email?**

O Audience Manager pode coletar e enviar até 10 emails por usuário para plataformas de destino, mas os endereços de email precisam ser capturados por meio de arquivos de sincronização. Depois que o Audience Manager envia os endereços de email para as plataformas de destino, cabe às plataformas corresponder os endereços de email à sua base de usuários. Algumas plataformas podem ter gráficos adicionais de endereço de email para corresponder a endereços enviados do Audience Manager para perfis do usuário.

**Posso usar  [!DNL People-Based Destinations] no  [!DNL Audience Lab]?**

Não. Atualmente, todos os destinos [!DNL People-Based Destinations] são excluídos de [!DNL Audience Lab]. Considerando que [!DNL People-Based Destinations] e plataformas do lado da demanda usam IDs diferentes, você não pode testar e medir o desempenho com públicos-alvo divididos igualmente entre eles.

## Controles da exportação de dados {#data-export-controls}

**Como [!DNL Data Export Controls] trabalham com [!DNL People-Based Destinations]?**

[!DNL Data Export Controls] bloquearão qualquer segmento que contenha dados secundários e de terceiros para os quais os usuários tentarem enviar [!DNL People-Based Destinations]. [!DNL People-Based Destinations] permitem que somente dados primários sejam usados para definição de metas. [!DNL Data Export Controls] também bloqueiam segmentos usando [!DNL Profile Merge Rules] com gráficos de dispositivos. [!DNL People-Based Destinations] são criados com as etiquetas de exportação de dados apropriadas marcadas e não é possível substituir as configurações de exportação.

## Perguntas específicas do parceiro {#partner-specific-questions}

### [!DNL Facebook]

**O que preciso fazer antes de enviar segmentos de público-alvo para o [!DNL Facebook]?**

Antes de poder usar [!DNL People-Based Destinations] para enviar segmentos de público-alvo para o [!DNL Facebook], é necessário executar as seguintes tarefas de configuração:

1. Adicione a conta comercial da Adobe Experience Cloud como um parceiro de publicidade em sua conta do [!DNL Facebook Ad Account]. Use `business ID=206617933627973`. Consulte Adicionar parceiros ao seu gerente de negócios para obter detalhes.

   >[!IMPORTANT]
   >
   > Ao configurar as permissões para a Adobe Experience Cloud, você deve ativar a permissão Gerenciar campanhas. Isso é necessário para a integração de [!DNL People-Based Destinations].

1. Leia e assine o [!DNL Facebook Custom Audiences Terms of Service]. Para fazer isso, acesse `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, onde `accountID` é a sua [!DNL Facebook Ad Account ID].

**Os [!DNL People-Based Destinations] oferecem suporte ao direcionamento de público-alvo em outros aplicativos do [!DNL Facebook], como o [!DNL Instagram]?**

Você pode usar [!DNL People-Based Destinations] em toda a família de aplicativos do [!DNL Facebook] compatíveis com [!DNL Custom Audiences], como [!DNL Facebook], [!DNL Instagram], [!DNL Audience Network] e [!DNL Messenger]. A seleção do aplicativo no qual você deseja executar a campanha é indicada no nível de posicionamento no [!DNL Facebook Ads Manager].

**Qual é a diferença entre [!DNL People-Based Destinations] e [!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] usam a [!DNL Custom Audiences (CA)] integração com [!DNL Facebook]. A diferença entre as integrações de [!DNL WCA] e [!DNL CA] é a chave que os clientes usam ao enviar públicos para o [!DNL Facebook]. O [!DNL WCA] usa o pixel do [!DNL Facebook] (que seria uma ID de usuário do site), e os [!DNL People-Based Destinations] usam endereços de email com hash para integrar-se com o [!DNL CA].

Você pode usar a integração entre [!DNL Facebook] [!DNL WCA] do Audience Manager com o recurso [!DNL URL Destinations] sem custo adicional.

Estas duas integrações são complementares; você pode usar ambas para garantir uma melhor cobertura do público-alvo. Como exemplo, o [!DNL WCA] pode ser usado para prospecção quando uma empresas está procurando direcionar visitantes de sites que não registraram uma conta, enquanto o [!DNL People-Based Destinations] pode ajudar você a direcionar clientes existentes que forneceram o endereço de email, mas talvez não visitaram o site.

**A  [!DNL People-Based Destinations] integração com  [!DNL Facebook] suporte desqualifica os usuários de um público-alvo quando eles não estão mais qualificados para isso?**

Sim, a integração oferece suporte à remoção de usuários de públicos [!DNL Facebook] quando não se qualificam mais para eles.
