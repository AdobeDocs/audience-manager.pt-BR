---
description: 'Leia abaixo para obter uma visão geral dos requisitos de clientes que você precisa atender antes de se inscrever para Destinos baseados em pessoas.  '
seo-description: 'Leia abaixo para obter uma visão geral dos requisitos de clientes que você precisa atender antes de se inscrever para Destinos baseados em pessoas.  '
seo-title: Pré-requisitos e considerações de destinos baseados em pessoas
solution: Audience Manager
title: Pré-requisitos e considerações
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# Pré-requisitos e considerações {#prerequisites-considerations}

Leia abaixo para obter uma visão geral dos requisitos de clientes que você precisa atender antes de assinar [!DNL People-Based Destinations].

>[!IMPORTANT]
> Ler com cuidado neste artigo antes de passar para a fase de implementação.

## Inscrever-se para destinos baseados em pessoas {#signing-up}

[!DNL People-Based Destinations] é um recurso premium que melhora sua experiência do Audience Manager, permitindo ativar segmentos de público-alvo primários em ambientes baseados em pessoas, ao direcionar seu público com ofertas personalizadas em redes sociais ou por meio de marketing por email.

Entre em contato com seu representante de vendas da Adobe para obter detalhes sobre como você pode se inscrever [!DNL People-Based Destinations].

## Pré-requisitos específicos do parceiro {#partner-prerequisites}

### [!DNL Facebook]

Antes de usar [!DNL People-Based Destinations] para enviar segmentos de público-alvo para [!DNL Facebook], certifique-se de atender aos seguintes requisitos:

1. Sua [!DNL Facebook] conta de usuário deve ter a **permissão Gerenciar campanhas** ativada para a conta do anúncio que você planeja usar.
1. Adicione a conta comercial **da Adobe Experience Cloud** como um parceiro de publicidade em seu [!DNL Facebook Ad Account]. Use `business ID=206617933627973`. Consulte [Adicionar parceiros ao seu gerente de negócios](https://www.facebook.com/business/help/708679622611131) para obter mais detalhes.
   >[!IMPORTANT]
   > Ao configurar as permissões para a Adobe Experience Cloud, você deve habilitar a permissão **Gerenciar campanhas** . Isso é necessário para [!DNL People-Based Destinations] a integração.
1. Leia e assine [!DNL Facebook Custom Audiences] os Termos de serviço. Para fazer isso, vá para `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, onde `accountID` é seu [!DNL Facebook Ad Account ID].

## Onboard de dados {#data-onboarding}

A ingestão de dados para [!DNL People-Based Destinations] atualmente suporta até 10 endereços de email com hash ligados a uma ID do cliente ([!DNL CRM ID]), por transferência em lote. Fazer upload de mais de 10 endereços de email com hash ligados a uma ID do cliente faz com que o Audience Manager assimilue 10 delas, sem ordem específica.

Fazer upload de mais de 10 endereços de email com hash ligados a uma ID do cliente em várias transferências em lote faz com que o Audience Manager mantenha os 10 endereços de email mais recentes adicionados.

## Privacidade de dados {#data-privacy}

Embora [!DNL People-Based Destinations] seja possível direcionar públicos-alvo com base em endereços de email, nenhuma informação de visitante diretamente identificável chega ao Audience Manager. Na fase de onboarding de dados, é necessário garantir que os endereços de e-mail que você planeja usar sejam hash com o [!DNL SHA256] algoritmo. Caso contrário, não será possível usá-los [!DNL People-Based Destinations].

## Hash de dados versus criptografia {#data-hashing-encryption}

A criptografia é uma função bidirecional. Qualquer informação criptografada também pode ser descriptografada usando a chave de decodificação correta. A criptografia de dados no contexto do Audience Manager gera um risco de privacidade grave, já que qualquer forma criptografada de informações pessoalmente identificáveis também pode ser descriptografada, revelando dados confidenciais do cliente. Ao contrário de criptografia, [!DNL People-Based Destinations] são projetadas para trabalhar com dados com hash, protegendo os dados do cliente que você usa para direcionamento.

A hash é uma função unidirecional que remove a entrada para produzir um resultado único. Usando algoritmos de hash adequados, como [!DNL SHA256], não há como reverter a função de hash e revelar as informações distorcidas. Os endereços de email que serão enviados para o Audience Manager devem ser hash com o [!DNL SHA256] algoritmo. Dessa forma, nenhuma informação de identificação pessoal chega ao Audience Manager, mantendo os dados do cliente seguros.

## Requisitos de hash {#hashing-requirements}

Ao fazer o hash dos endereços de email, certifique-se de seguir os seguintes requisitos:

* Apare todos os espaços à esquerda e à direita da string de email; exemplo: `johndoe@example.com`, não `<space>johndoe@example.com<space>`;
* Verifique se a string com hash está em minúsculas; exemplo: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, não `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Não salt a string.

A Adobe Experience Cloud oferece a você a opção de fazer hash IDs do cliente por meio do serviço da Experience Cloud ID. Consulte [SHA 256 Hashing Support for setcustomerids](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) para obter informações detalhadas sobre como usar o ECID para as IDs do cliente.

## Obter permissão do usuário {#obtaining-user-permission}

Como [!DNL People-Based Destinations] ajuda a ativar os dados de público-alvo primários em canais baseados em pessoas, é sua responsabilidade informar seus clientes sobre como você usará seus dados para fins de publicidade.

Antes de cadastrar-se [!DNL People-Based Destinations], certifique-se de obter o consentimento dos clientes antes de usar suas informações para fins de publicidade.

Caso seus clientes queiram recusar campanhas publicitárias, consulte Gerenciamento [de não participação](../../overview/data-security-and-privacy/opt-out-management.md) para obter detalhes sobre como impedir que o Audience Manager colete dados mais detalhadamente.

## Impor ativação de dados primários {#enforcing-first-party-activation}

Ao usar [!DNL People-Based Destinations], você só pode usar dados primários para ativar os segmentos do público-alvo em canais baseados em pessoas. Não é possível usar dados de segundo ou de terceiros para a ativação de público-alvo em canais baseados em pessoas.

## IDs de hash autenticadas onboard por meio de definição de metas ID declarada {#onboard-authenticated-declared-id}

Há duas maneiras de inserir seus dados offline para [!DNL People-Based Destinations]o Audience Manager.

* [Enviar dados em lote](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) para o Audience Manager para assimilar endereços de email com hash. Com esse método, você pode usar todos os endereços de email com hash do [!DNL CRM] banco de dados em [!DNL People-Based Destinations]. Além disso, ao usar esse método, também é possível qualificar os endereços de email com hash para [características onboard](../traits/trait-qualification-reference.md).
* Use [IDs declaradas](../declared-ids.md) para declarar endereços de email com hash ao passar em IDs autenticadas do cliente. Ao usar esse método, o Audience Manager envia somente [!DNL People-Based Destinations] os endereços de email com hash de usuários que se autenticaram online. Os endereços de email ativados por meio do Facebook são apenas aqueles nas chamadas declaradas do evento de ID. Outros endereços de email associados à ID do cliente não são enviados em tempo real.
