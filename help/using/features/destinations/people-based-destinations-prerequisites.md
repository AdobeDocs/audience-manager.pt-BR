---
description: 'Leia abaixo para obter uma visão geral dos requisitos do cliente que você precisa atender antes de se inscrever em Destinos baseados em pessoas.  '
seo-description: 'Leia abaixo para obter uma visão geral dos requisitos do cliente que você precisa atender antes de se inscrever em Destinos baseados em pessoas.  '
seo-title: Pré-requisitos e Considerações para Destinos Baseados em Pessoas
solution: Audience Manager
title: Pré-requisitos e considerações
translation-type: tm+mt
source-git-commit: ad9c077f538759e195a83d47e0ef36ccffa25c7e

---


# Pré-requisitos e considerações {#prerequisites-considerations}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a guiá-lo pela configuração e uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

Leia abaixo para obter uma visão geral dos requisitos do cliente que você precisa atender antes de se inscrever [!DNL People-Based Destinations].

>[!IMPORTANT]
> Leia este artigo cuidadosamente antes de passar para a fase de implementação.

## Inscrição para destinos baseados em pessoas {#signing-up}

[!DNL People-Based Destinations] é um recurso premium que aprimora sua experiência com o Audience Manager, permitindo que você ative seus segmentos de público-alvo primário em ambientes baseados em pessoas, direcionando seu público-alvo com ofertas personalizadas em redes sociais ou por meio de marketing por email.

Entre em contato com seu representante da Adobe para aproveitar esse recurso premium.

## Pré-requisitos específicos do parceiro {#partner-prerequisites}

### [!DNL Facebook]

Before you can use  to send your first-party audience segments to , make sure you meet the following requirements:[!DNL People-Based Destinations][!DNL Facebook]

1. Sua conta [!DNL Facebook] de usuário deve ter a permissão **Gerenciar campanhas** ativada para a conta de anúncio que você planeja usar.
1. Adicione a conta comercial da **Adobe Experience Cloud** como um parceiro de publicidade em seu [!DNL Facebook Ad Account]site. Use `business ID=206617933627973`. Consulte [Adicionar parceiros ao seu gerente](https://www.facebook.com/business/help/708679622611131) de negócios para obter detalhes.
   >[!IMPORTANT]
   > Ao configurar as permissões para a Adobe Experience Cloud, você deve ativar a permissão **Gerenciar campanhas** . Isso é necessário para a [!DNL People-Based Destinations] integração.
1. Leia e assine os [!DNL Facebook Custom Audiences] Termos de serviço. Para fazer isso, vá para `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, onde `accountID` está seu [!DNL Facebook Ad Account ID].

## Integração de dados {#data-onboarding}

A ingestão de dados para [!DNL People-Based Destinations] atualmente suporta até 10 endereços de email com hash vinculados a uma ID do cliente ([!DNL CRM ID]), por transferência em lote. Uploading more than 10 hashed email addresses linked to one customer ID causes Audience Manager to ingest 10 of them, in no specific order.

Uploading more than 10 hashed email addresses linked to one customer ID in multiple batch transfers causes Audience Manager to retain the most recent 10 email addresses added.

## Privacidade de dados {#data-privacy}

Although  allow you to target audiences based on hashed email addresses uploaded by you, you remain prohibited from uploading any directly identifiable visitor information into Audience Manager. [!DNL People-Based Destinations] Na fase de integração de dados, é necessário garantir que os endereços de email que você pretende usar estejam com hash com o [!DNL SHA256] algoritmo. Caso contrário, você não poderá usá-los em [!DNL People-Based Destinations].

## Hashes de dados versus criptografia {#data-hashing-encryption}

A criptografia é uma função bidirecional. Todas as informações criptografadas também podem ser descriptografadas, usando a chave de decodificação correta. Encrypting data in the context of Audience Manager poses serious risks, since any encrypted form of personally identifiable information can also be decrypted. Ao contrário da criptografia, [!DNL People-Based Destinations] são criados para trabalhar com dados com hash.

Hashing is a one-way function that scrambles the input to produce a unique result. Usando algoritmos de hash adequados, como [!DNL SHA256], não há como reverter a função de hash e revelar as informações desembaralhadas. The email addresses that you will onboard to Audience Manager must be hashed with the  algorithm. [!DNL SHA256] Dessa forma, você pode garantir que nenhum endereço de email sem hash chegue ao Audience Manager.

## Requisitos de hash {#hashing-requirements}

Ao atualizar os endereços de email, certifique-se de cumprir os seguintes requisitos:

* Aparar todos os espaços à esquerda e à direita da string de email; exemplo: `johndoe@example.com`, não `<space>johndoe@example.com<space>`;
* Ao executar o hash das strings de email, certifique-se de executar o hash da string em minúsculas;
   * Exemplo: `example@email.com`, não `EXAMPLE@EMAIL.COM`;
* Certifique-se de que a cadeia de caracteres com hash esteja em minúsculas
   * Exemplo: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, não `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Não salve a corda.

A Adobe Experience Cloud oferece a opção de hash de IDs de clientes por meio do Serviço da Experience Cloud ID. Consulte Suporte de hash [SHA256 para setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) para obter informações detalhadas sobre como usar ECID para hash de IDs de clientes.

## Obtendo permissão do usuário {#obtaining-user-permission}

Como [!DNL People-Based Destinations] ajuda a ativar os dados de público-alvo primário em canais baseados em pessoas, é sua responsabilidade informar e obter quaisquer consentimentos necessários de seus clientes sobre como você usará seus dados para fins publicitários ou outros.

Antes de se inscrever para [!DNL People-Based Destinations], certifique-se de obter o consentimento dos clientes antes de usar suas informações para fins publicitários.

In case your customers wish to opt-out of advertising campaigns, see Opt-out Management for details on how to stop Audience Manager from collecting data any further.[](../../overview/data-security-and-privacy/opt-out-management.md)

## Impondo a ativação de dados primários {#enforcing-first-party-activation}

Ao usar [!DNL People-Based Destinations], você só pode usar dados primários para ativar segmentos de público-alvo em canais baseados em pessoas. Não é possível usar dados de terceiros ou segundos para a ativação do público-alvo em canais baseados em pessoas.

## IDs com hash autenticadas onboard por meio da segmentação de ID declarada {#onboard-authenticated-declared-id}

Há duas maneiras de trazer seus dados offline para o Audience Manager para [!DNL People-Based Destinations].

* [Envie dados](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) em lote para o Audience Manager para assimilar endereços de email com hash. Com esse método, você pode optar por usar os endereços de email com hash do seu [!DNL CRM] banco de dados em [!DNL People-Based Destinations]. Além disso, ao usar esse método, você também pode qualificar os endereços de email com hash para características [integradas](../traits/trait-qualification-reference.md).
* Use as IDs [](../declared-ids.md) declaradas para declarar endereços de email com hash ao transmitir IDs autenticadas do cliente. When using this method, Audience Manager, on your behalf, only sends to  the hashed email addresses from users who have authenticated online. [!DNL People-Based Destinations] The email addresses activated through people-based channels are only the ones in the declared ID event calls. Outros endereços de email associados à ID do cliente não são enviados em tempo real.
