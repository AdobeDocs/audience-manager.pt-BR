---
description: 'Leia abaixo uma visão geral dos requisitos do cliente que você precisa atender antes de se inscrever em Destinos com base em pessoas.  '
seo-description: 'Leia abaixo uma visão geral dos requisitos do cliente que você precisa atender antes de se inscrever em Destinos com base em pessoas.  '
seo-title: Pré-requisitos e considerações de destinos com base em pessoas
solution: Audience Manager
title: Pré-requisitos e considerações
feature: Destinos com base em pessoas
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1013'
ht-degree: 3%

---

# Pré-requisitos e considerações {#prerequisites-considerations}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e uso deste recurso. Nada neste documento é de aconselhamento jurídico. Consulte o seu advogado para obter orientação jurídica.

Leia abaixo uma visão geral dos requisitos do cliente que você precisa atender antes de se inscrever para [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Leia este artigo cuidadosamente antes de passar para a fase de implementação.

## Inscrever-se para [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] O é um recurso premium que melhora a experiência de Audience Manager, permitindo ativar segmentos de público-alvo primários em ambientes baseados em pessoas, direcionando o público-alvo com ofertas personalizadas em redes sociais ou por meio de marketing por email.

Entre em contato com seu representante de Adobe para aproveitar esse recurso premium.

## Pré-requisitos específicos do parceiro {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Antes de usar [!UICONTROL People-Based Destinations] para enviar o público primário [!UICONTROL segments] para [!DNL Facebook], verifique se você atende aos seguintes requisitos:

1. Sua conta de usuário [!DNL Facebook] deve ter a permissão **Gerenciar campanhas** ativada para a conta de anúncio que você planeja usar.
2. Adicione a conta comercial **Adobe Experience Cloud** como um parceiro de publicidade em seu [!DNL Facebook Ad Account]. Use `business ID=206617933627973`. Consulte [Adicionar parceiros ao seu gerente de negócios](https://www.facebook.com/business/help/1717412048538897) para obter detalhes.
   >[!IMPORTANT]
   > Ao configurar as permissões para o Adobe Experience Cloud, você deve habilitar a permissão **Gerenciar campanhas**. Isso é necessário para a integração de [!UICONTROL People-Based Destinations].
3. Leia e assine os [!DNL Facebook Custom Audiences] Termos de serviço. Para fazer isso, acesse `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, onde `accountID` é a sua [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn] {#linkedin}

Antes de usar [!UICONTROL People-Based Destinations] para enviar segmentos de público-alvo primários para [!DNL LinkedIn], verifique se a conta [!DNL LinkedIn Campaign Manager] tem o [!DNL Creative Manager] ou nível de permissão superior.

Para saber como editar suas permissões de usuário [!DNL LinkedIn Campaign Manager], consulte [Adicionar, editar e remover permissões de usuário em contas publicitárias](https://www.linkedin.com/help/lms/answer/5753) na documentação do LinkedIn.

Consulte [Entendendo e configurando o destino baseado em pessoas do LinkedIn](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) para obter instruções de vídeo.

### [!DNL Google Customer Match] {#gcm}

Antes de usar [!UICONTROL People-Based Destinations] para enviar segmentos de público-alvo primários para um destino [!DNL Google Customer Match], é obrigatório que [!DNL Google] o adicione à lista de permissões.

Entre em contato com seu representante [!DNL Google] e siga as instruções da lista de permissões descritas na documentação [Usar parceiros de Correspondência de Cliente para carregar seus dados](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507) [!DNL Google].

Depois que esse processo for concluído, você poderá criar seu [!UICONTROL People-Based Destination].

## Integração de dados {#data-onboarding}

A assimilação de dados para [!UICONTROL People-Based Destinations] suporta atualmente até 10 endereços de email com hash vinculados a uma ID de cliente ([!DNL CRM ID]), por transferência em lote. Fazer upload de mais de 10 endereços de email com hash vinculados a uma ID do cliente faz com que o Audience Manager assimile 10 deles, em uma ordem específica.

Fazer upload de mais de 10 endereços de email com hash vinculados a uma ID de cliente em várias transferências em lote faz com que o Audience Manager retenha os 10 endereços de email mais recentes adicionados.

## Privacidade de dados {#data-privacy}

Embora [!UICONTROL People-Based Destinations] permita direcionar públicos-alvo com base em endereços de email com hash carregados por você, você permanece proibido de fazer upload de qualquer informação de visitante diretamente identificável para o Audience Manager. Na fase de integração de dados, você deve garantir que os endereços de email que planeja usar sejam atribuídos a hash com o algoritmo [!DNL SHA256]. Caso contrário, você não poderá usá-los em [!UICONTROL People-Based Destinations].

## Hash de dados versus criptografia {#data-hashing-encryption}

A criptografia é uma função bidirecional. Todas as informações criptografadas também podem ser descriptografadas, usando a chave de descriptografia correta. A criptografia de dados no contexto do Audience Manager apresenta sérios riscos, já que qualquer forma criptografada de informações de identificação pessoal também pode ser descriptografada. Ao contrário da criptografia, [!UICONTROL People-Based Destinations] são projetadas para funcionar com dados com hash.

O hash é uma função unidirecional que embaralha a entrada para produzir um resultado exclusivo. Ao usar algoritmos de hash adequados, como [!DNL SHA256], não há como reverter a função de hash e revelar as informações desembaralhadas. Os endereços de email que você integrará ao Audience Manager devem ser transformados em hash com o algoritmo [!DNL SHA256]. Dessa forma, você pode garantir que nenhum endereço de email com hash chegue ao Audience Manager.

## Requisitos de hash {#hashing-requirements}

Ao fazer o hash dos endereços de email, certifique-se de estar em conformidade com os seguintes requisitos:

* Cortar todos os espaços à esquerda e à direita da string de email; exemplo: `johndoe@example.com`, não `<space>johndoe@example.com<space>`;
* Ao fazer o hash das cadeias de caracteres de email, certifique-se de fazer hash na cadeia de caracteres de minúsculas;
   * Exemplo: `example@email.com`, não `EXAMPLE@EMAIL.COM`;
* Certifique-se de que a sequência de hash esteja toda em minúsculas
   * Exemplo: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, não `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Não salve a corda.

Assista ao vídeo abaixo para entender os requisitos de hash de [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

A Adobe Experience Cloud oferece a opção de hash nas IDs do cliente por meio do [!DNL Adobe Experience Platform Identity Service (ECID)]. Consulte [Suporte a hash SHA 256 para setCustomerIDs](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) para obter informações detalhadas sobre como usar ECID para hash de IDs do cliente.

## Obter permissão de usuário {#obtaining-user-permission}

Como [!UICONTROL People-Based Destinations] ajuda a ativar dados de público-alvo primários em canais baseados em pessoas, é sua responsabilidade informar e obter quaisquer consentimentos necessários de seus clientes sobre como você usará seus dados para anúncios ou outros fins.

Antes de se inscrever para [!UICONTROL People-Based Destinations], obtenha o consentimento dos clientes antes de usar as informações para fins de publicidade.

Caso seus clientes queiram recusar campanhas publicitárias, consulte [Gerenciamento de rejeição](../../overview/data-security-and-privacy/data-privacy-requests.md) para obter detalhes sobre como impedir que o Audience Manager colete dados mais.

## Impondo a ativação de dados primários {#enforcing-first-party-activation}

Ao usar [!UICONTROL People-Based Destinations], você só pode usar dados primários para ativar segmentos de público-alvo em canais com base em pessoas. Não é possível usar dados secundários ou de terceiros para a ativação do público-alvo em canais com base em pessoas.

Ao usar [!UICONTROL People-Based Destinations], use [Controles da exportação de dados](../data-export-controls.md) para rotular seus [!UICONTROL data sources] e [!UICONTROL destinations] de acordo com as diretrizes e requisitos das plataformas de destino e provedores de dados.

## IDs com hash autenticadas onboard por meio do direcionamento de ID declarada {#onboard-authenticated-declared-id}

Há duas maneiras de trazer seus dados offline para o Audience Manager para [!UICONTROL People-Based Destinations].

* [Envie ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) dados em lote para assimilar endereços de email com hash. Com esse método, você pode optar por usar os endereços de email com hash do seu banco de dados [!DNL CRM] em [!UICONTROL People-Based Destinations]. Além disso, ao usar esse método, também é possível qualificar os endereços de email com hash para [traits integrados](../traits/trait-and-segment-qualification-reference.md).
* Use [IDs declaradas](../declared-ids.md) para declarar endereços de email com hash ao transmitir IDs autenticadas do cliente. Ao usar esse método, o Audience Manager, em seu nome, envia somente para [!UICONTROL People-Based Destinations] os endereços de email com hash de usuários que autenticaram online. Os endereços de email ativados por meio de canais com base em pessoas são apenas aqueles nas chamadas de evento de ID declaradas. Outros endereços de email associados à ID do cliente não são enviados em tempo real.
