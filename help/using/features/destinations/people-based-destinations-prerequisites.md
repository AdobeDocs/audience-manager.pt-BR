---
description: 'Leia abaixo para obter uma visão geral dos requisitos do cliente que você precisa atender antes de se inscrever em Destinos baseados em pessoas.  '
seo-description: 'Leia abaixo para obter uma visão geral dos requisitos do cliente que você precisa atender antes de se inscrever em Destinos baseados em pessoas.  '
seo-title: Pré-requisitos e Considerações para Destinos Baseados em Pessoas
solution: Audience Manager
title: Pré-requisitos e considerações
translation-type: tm+mt
source-git-commit: d83f4dae563c9c49ae8d46c28aa41168d746f92c

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

Antes de poder usar [!DNL People-Based Destinations] para enviar seus segmentos de público-alvo primário para [!DNL Facebook], certifique-se de atender aos seguintes requisitos:

1. Sua conta [!DNL Facebook] de usuário deve ter a permissão **Gerenciar campanhas** ativada para a conta de anúncio que você planeja usar.
1. Adicione a conta comercial da **Adobe Experience Cloud** como um parceiro de publicidade em seu [!DNL Facebook Ad Account]site. Use `business ID=206617933627973`. Consulte [Adicionar parceiros ao seu gerente](https://www.facebook.com/business/help/708679622611131) de negócios para obter detalhes.
   >[!IMPORTANT]
   > Ao configurar as permissões para a Adobe Experience Cloud, você deve ativar a permissão **Gerenciar campanhas** . Isso é necessário para a [!DNL People-Based Destinations] integração.
1. Leia e assine os [!DNL Facebook Custom Audiences] Termos de serviço. Para fazer isso, vá para `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, onde `accountID` está seu [!DNL Facebook Ad Account ID].

## Integração de dados {#data-onboarding}

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
* Não salve a corda.

Assista ao vídeo abaixo para entender os requisitos de hash do [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/?captions=por_br)

A Adobe Experience Cloud oferece a opção de hash de IDs de clientes por meio do Serviço da Experience Cloud ID. Consulte Suporte de hash [SHA256 para setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) para obter informações detalhadas sobre como usar ECID para hash de IDs de clientes.

## Obtendo permissão do usuário {#obtaining-user-permission}

Como [!DNL People-Based Destinations] ajuda a ativar os dados de público-alvo primário em canais baseados em pessoas, é sua responsabilidade informar e obter quaisquer consentimentos necessários de seus clientes sobre como você usará seus dados para fins publicitários ou outros.

Antes de se inscrever para [!DNL People-Based Destinations], certifique-se de obter o consentimento dos clientes antes de usar suas informações para fins publicitários.

Caso seus clientes desejem recusar campanhas publicitárias, consulte Gerenciamento [de](../../overview/data-security-and-privacy/data-privacy-requests.md) recusa para obter detalhes sobre como impedir o Audience Manager de coletar dados.

## Impondo a ativação de dados primários {#enforcing-first-party-activation}

Ao usar [!DNL People-Based Destinations], você só pode usar dados primários para ativar segmentos de público-alvo em canais baseados em pessoas. Não é possível usar dados de terceiros ou segundos para a ativação do público-alvo em canais baseados em pessoas.

Ao usar [!UICONTROL People-Based Destinations], use os Controles [de exportação de](../data-export-controls.md) dados para rotular suas fontes de dados e destinos de acordo com as diretrizes e requisitos das plataformas de destino e provedores de dados.

## IDs com hash autenticadas onboard por meio da segmentação de ID declarada {#onboard-authenticated-declared-id}

Há duas maneiras de trazer seus dados offline para o Audience Manager para [!DNL People-Based Destinations].

* [Envie dados](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) em lote para o Audience Manager para assimilar endereços de email com hash. Com esse método, você pode optar por usar os endereços de email com hash do seu [!DNL CRM] banco de dados em [!DNL People-Based Destinations]. Além disso, ao usar esse método, você também pode qualificar os endereços de email com hash para características [integradas](../traits/trait-qualification-reference.md).
* Use as IDs [](../declared-ids.md) declaradas para declarar endereços de email com hash ao transmitir IDs autenticadas do cliente. Ao usar esse método, o Audience Manager, em seu nome, envia somente para [!DNL People-Based Destinations] os endereços de email com hash de usuários que se autenticaram online. Os endereços de email ativados por canais baseados em pessoas são apenas aqueles nas chamadas de evento de ID declaradas. Outros endereços de email associados à ID do cliente não são enviados em tempo real.
