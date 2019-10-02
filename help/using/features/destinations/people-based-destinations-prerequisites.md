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

Read below for an overview of customer requirements that you need to meet before signing up for .[!DNL People-Based Destinations]

>[!IMPORTANT]
> Read through this article carefully before moving on to the implementation phase.

## Signing up for People-Based Destinations {#signing-up}

[!DNL People-Based Destinations] is a premium capability that enhances your Audience Manager experience by allowing you to activate your first-party audience segments in people-based environments, by targeting your audience with customized offers on social networks or through email marketing.

Please contact your Adobe representative to take advantage of this premium feature.

## Partner-Specific Prerequisites {#partner-prerequisites}

### [!DNL Facebook]

Before you can use  to send your first-party audience segments to , make sure you meet the following requirements:[!DNL People-Based Destinations][!DNL Facebook]

1. Your  user account must have the Manage campaigns permission enabled for the Ad account that you plan to use.[!DNL Facebook]****
1. Add the **Adobe Experience Cloud** business account as an advertising partner in your [!DNL Facebook Ad Account]. Use `business ID=206617933627973`. See [Add Partners to Your Business Manager](https://www.facebook.com/business/help/708679622611131) for details.
   >[!IMPORTANT]
   > When configuring the permissions for Adobe Experience Cloud, you must enable the **Manage campaigns** permission. This is required for the [!DNL People-Based Destinations] integration.
1. Read and sign the [!DNL Facebook Custom Audiences] Terms of Service. Para fazer isso, vá para `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, onde `accountID` está seu [!DNL Facebook Ad Account ID].

## Data Onboarding {#data-onboarding}

A ingestão de dados para [!DNL People-Based Destinations] atualmente suporta até 10 endereços de email com hash vinculados a uma ID do cliente ([!DNL CRM ID]), por transferência em lote. Fazer upload de mais de 10 endereços de email com hash vinculados a uma ID do cliente faz com que o Audience Manager ingira 10 deles, sem ordem específica.

Fazer upload de mais de 10 endereços de email com hash vinculados a uma ID de cliente em várias transferências em lote faz com que o Audience Manager mantenha os 10 endereços de email mais recentes adicionados.

## Privacidade de dados {#data-privacy}

Embora [!DNL People-Based Destinations] permita direcionar públicos-alvo com base em endereços de email com hash carregados por você, você permanece proibido de fazer upload de informações de visitantes diretamente identificáveis para o Audience Manager. Na fase de integração de dados, é necessário garantir que os endereços de email que você pretende usar estejam com hash com o [!DNL SHA256] algoritmo. Caso contrário, você não poderá usá-los em [!DNL People-Based Destinations].

## Hashes de dados versus criptografia {#data-hashing-encryption}

A criptografia é uma função bidirecional. Todas as informações criptografadas também podem ser descriptografadas, usando a chave de decodificação correta. A criptografia de dados no contexto do Audience Manager apresenta sérios riscos, já que qualquer forma criptografada de informações de identificação pessoal também pode ser descriptografada. Ao contrário da criptografia, [!DNL People-Based Destinations] são criados para trabalhar com dados com hash.

O hash é uma função unidirecional que embaralha a entrada para produzir um resultado exclusivo. Usando algoritmos de hash adequados, como [!DNL SHA256], não há como reverter a função de hash e revelar as informações desembaralhadas. Os endereços de email que você integrará ao Audience Manager devem ser hash com o [!DNL SHA256] algoritmo. Dessa forma, você pode garantir que nenhum endereço de email sem hash chegue ao Audience Manager.

## Requisitos de hash {#hashing-requirements}

Ao atualizar os endereços de email, certifique-se de cumprir os seguintes requisitos:

* Aparar todos os espaços à esquerda e à direita da string de email; exemplo: `johndoe@example.com`, não `<space>johndoe@example.com<space>`;
* Ao executar o hash das strings de email, certifique-se de executar o hash da string em minúsculas;
   * Exemplo: `example@email.com`, não `EXAMPLE@EMAIL.COM`;
* Certifique-se de que a cadeia de caracteres com hash esteja em minúsculas
   * Exemplo: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, não `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Do not salt the string.

A Adobe Experience Cloud oferece a opção de hash de IDs de clientes por meio do Serviço da Experience Cloud ID. Consulte Suporte de hash [SHA256 para setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) para obter informações detalhadas sobre como usar ECID para hash de IDs de clientes.

## Obtendo permissão do usuário {#obtaining-user-permission}

Como [!DNL People-Based Destinations] ajuda a ativar os dados de público-alvo primário em canais baseados em pessoas, é sua responsabilidade informar e obter quaisquer consentimentos necessários de seus clientes sobre como você usará seus dados para fins publicitários ou outros.

Antes de se inscrever para [!DNL People-Based Destinations], certifique-se de obter o consentimento dos clientes antes de usar suas informações para fins publicitários.

Caso seus clientes desejem recusar campanhas publicitárias, consulte Gerenciamento [de](../../overview/data-security-and-privacy/opt-out-management.md) recusa para obter detalhes sobre como impedir o Audience Manager de coletar dados.

## Impondo a ativação de dados primários {#enforcing-first-party-activation}

When using , you can only use first-party data to activate audience segments in people-based channels. [!DNL People-Based Destinations] You cannot use any second- or third-party data for audience activation in people-based channels.

## Onboard Authenticated Hashed IDs through Declared ID Targeting {#onboard-authenticated-declared-id}

There are two ways you can bring your offline data to Audience Manager for .[!DNL People-Based Destinations]

* [Send batch data to Audience Manager to ingest hashed email addresses. ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) With this method, you can choose to use the hashed email addresses from your  database in . [!DNL CRM][!DNL People-Based Destinations] Additionally, when using this method, you can also qualify the hashed email addresses for onboarded traits.[](../traits/trait-qualification-reference.md)
* Use Declared IDs to declare hashed email addresses when passing in authenticated customer IDs. [](../declared-ids.md) When using this method, Audience Manager, on your behalf, only sends to  the hashed email addresses from users who have authenticated online. [!DNL People-Based Destinations] The email addresses activated through people-based channels are only the ones in the declared ID event calls. Other email addresses associated with the customer ID are not sent in real-time.
