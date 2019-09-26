---
description: 'Leia abaixo para obter uma visão geral dos requisitos do cliente que você precisa atender antes de se inscrever em Destinos baseados em pessoas.  '
seo-description: 'Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.  '
seo-title: Pré-requisitos e Considerações para Destinos Baseados em Pessoas
solution: Audience Manager
title: Prerequisites and Considerations
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# Pré-requisitos e considerações {#prerequisites-considerations}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a guiá-lo pela configuração e uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

Read below for an overview of customer requirements that you need to meet before signing up for .[!DNL People-Based Destinations]

>[!IMPORTANT]
> Read through this article carefully before moving on to the implementation phase.

## Signing up for People-Based Destinations {#signing-up}

[!DNL People-Based Destinations] is a premium capability that enhances your Audience Manager experience by allowing you to activate your first-party audience segments in people-based environments, by targeting your audience with customized offers on social networks or through email marketing.

Please contact your Adobe representative to take advantage of this premium feature.

## Partner-Specific Prerequisites {#partner-prerequisites}

### [!DNL Facebook]

Antes de poder usar [!DNL People-Based Destinations] para enviar seus segmentos de público-alvo primário para [!DNL Facebook], certifique-se de atender aos seguintes requisitos:

1. Sua conta [!DNL Facebook] de usuário deve ter a permissão **Gerenciar campanhas** ativada para a conta de anúncio que você planeja usar.
1. Adicione a conta comercial da **Adobe Experience Cloud** como um parceiro de publicidade em seu [!DNL Facebook Ad Account]site. Use `business ID=206617933627973`. Consulte [Adicionar parceiros ao seu gerente](https://www.facebook.com/business/help/708679622611131) de negócios para obter detalhes.
   >[!IMPORTANT]
   > Ao configurar as permissões para a Adobe Experience Cloud, você deve ativar a permissão **Gerenciar campanhas** . Isso é necessário para a [!DNL People-Based Destinations] integração.
1. Leia e assine os [!DNL Facebook Custom Audiences] Termos de serviço. Para fazer isso, vá para `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, onde `accountID` está seu [!DNL Facebook Ad Account ID].

## Integração de dados {#data-onboarding}

A ingestão de dados para [!DNL People-Based Destinations] atualmente suporta até 10 endereços de email com hash vinculados a uma ID do cliente ([!DNL CRM ID]), por transferência em lote. Fazer upload de mais de 10 endereços de email com hash vinculados a uma ID do cliente faz com que o Audience Manager ingira 10 deles, sem ordem específica.

Uploading more than 10 hashed email addresses linked to one customer ID in multiple batch transfers causes Audience Manager to retain the most recent 10 email addresses added.

## Privacidade de dados {#data-privacy}

Although  allow you to target audiences based on hashed email addresses uploaded by you, you remain prohibited from uploading any directly identifiable visitor information into Audience Manager. [!DNL People-Based Destinations] Na fase de integração de dados, é necessário garantir que os endereços de email que você pretende usar estejam com hash com o [!DNL SHA256] algoritmo. Caso contrário, você não poderá usá-los em [!DNL People-Based Destinations].

## Hashes de dados versus criptografia {#data-hashing-encryption}

Encryption is a two-way function. Any encrypted information can also be decrypted, using the correct decryption key. Encrypting data in the context of Audience Manager poses serious risks, since any encrypted form of personally identifiable information can also be decrypted. As opposed to encryption,  are designed to work with hashed data instead.[!DNL People-Based Destinations]

Hashing is a one-way function that scrambles the input to produce a unique result. Usando algoritmos de hash adequados, como [!DNL SHA256], não há como reverter a função de hash e revelar as informações desembaralhadas. Os endereços de email que você integrará ao Audience Manager devem ser hash com o [!DNL SHA256] algoritmo. Dessa forma, você pode garantir que nenhum endereço de email sem hash chegue ao Audience Manager.

## Requisitos de hash {#hashing-requirements}

Ao atualizar os endereços de email, certifique-se de cumprir os seguintes requisitos:

* Aparar todos os espaços à esquerda e à direita da string de email; exemplo: `johndoe@example.com`, não `<space>johndoe@example.com<space>`;
* Verifique se a string com hash está toda em minúsculas; exemplo: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, não `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Não salve a corda.

A Adobe Experience Cloud oferece a opção de hash de IDs de clientes por meio do Serviço da Experience Cloud ID. Consulte Suporte de hash [SHA256 para setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) para obter informações detalhadas sobre como usar ECID para hash de IDs de clientes.

## Obtendo permissão do usuário {#obtaining-user-permission}

Como [!DNL People-Based Destinations] ajuda a ativar os dados de público-alvo primário em canais baseados em pessoas, é sua responsabilidade informar e obter quaisquer consentimentos necessários de seus clientes sobre como você usará seus dados para fins publicitários ou outros.

Antes de se inscrever para [!DNL People-Based Destinations], certifique-se de obter o consentimento dos clientes antes de usar suas informações para fins publicitários.

Caso seus clientes desejem recusar campanhas publicitárias, consulte Gerenciamento [de](../../overview/data-security-and-privacy/opt-out-management.md) recusa para obter detalhes sobre como impedir o Audience Manager de coletar dados.

## Impondo a ativação de dados primários {#enforcing-first-party-activation}

Ao usar [!DNL People-Based Destinations], você só pode usar dados primários para ativar segmentos de público-alvo em canais baseados em pessoas. Não é possível usar dados de terceiros ou segundos para a ativação do público-alvo em canais baseados em pessoas.

## IDs com hash autenticadas onboard por meio da segmentação de ID declarada {#onboard-authenticated-declared-id}

Há duas maneiras de trazer seus dados offline para o Audience Manager para [!DNL People-Based Destinations].

* [Envie dados](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) em lote para o Audience Manager para assimilar endereços de email com hash. Com esse método, você pode optar por usar os endereços de email com hash do seu [!DNL CRM] banco de dados em [!DNL People-Based Destinations]. Além disso, ao usar esse método, você também pode qualificar os endereços de email com hash para características [integradas](../traits/trait-qualification-reference.md).
* Use Declared IDs to declare hashed email addresses when passing in authenticated customer IDs. [](../declared-ids.md) When using this method, Audience Manager, on your behalf, only sends to  the hashed email addresses from users who have authenticated online. [!DNL People-Based Destinations] Os endereços de email ativados por canais baseados em pessoas são apenas aqueles nas chamadas de evento de ID declaradas. Outros endereços de email associados à ID do cliente não são enviados em tempo real.
