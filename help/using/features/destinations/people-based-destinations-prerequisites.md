---
description: 'Leia abaixo para obter uma visão geral dos requisitos do cliente que você precisa atender antes de se inscrever em Destinos baseados em pessoas.  '
seo-description: 'Leia abaixo para obter uma visão geral dos requisitos do cliente que você precisa atender antes de se inscrever em Destinos baseados em pessoas.  '
seo-title: Pré-requisitos e Considerações para Destinos Baseados em Pessoas
solution: Audience Manager
title: Pré-requisitos e considerações
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: d3184195d6a51ff013a3d1fc8526ca9afd3386c2
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 3%

---


# Pré-requisitos e considerações {#prerequisites-considerations}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo durante a configuração e o uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

Leia abaixo para obter uma visão geral dos requisitos do cliente que você precisa atender antes de se inscrever para [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Leia este artigo cuidadosamente antes de passar para a fase de implementação.

## Inscrever-se para [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] é um recurso premium que aprimora sua experiência com Audience Manager, permitindo ativar seus segmentos de audiência primários em ambientes baseados em pessoas, direcionando sua audiência com ofertas personalizadas em redes sociais ou por meio de marketing por email.

Entre em contato com seu representante de Adobe para aproveitar esse recurso premium.

## Pré-requisitos específicos do parceiro {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Antes de usar [!UICONTROL People-Based Destinations] para enviar sua audiência primária [!UICONTROL segments] para [!DNL Facebook], certifique-se de atender aos seguintes requisitos:

1. Sua conta de usuário [!DNL Facebook] deve ter a permissão **Gerenciar campanha** ativada para a conta de anúncio que você planeja usar.
2. Adicione a conta comercial **Adobe Experience Cloud** como um parceiro de publicidade em seu [!DNL Facebook Ad Account]. Use `business ID=206617933627973`. Consulte [Adicionar parceiros ao seu Business Manager](https://www.facebook.com/business/help/1717412048538897) para obter detalhes.
   >[!IMPORTANT]
   > Ao configurar as permissões para Adobe Experience Cloud, você deve ativar a permissão **Gerenciar campanha**. Isso é necessário para a integração de [!UICONTROL People-Based Destinations].
3. Leia e assine os [!DNL Facebook Custom Audiences] Termos de serviço. Para fazer isso, acesse `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, onde `accountID` é a sua [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn] {#linkedin}

Antes de usar [!UICONTROL People-Based Destinations] para enviar seus segmentos de audiência primários para [!DNL LinkedIn], verifique se sua conta [!DNL LinkedIn Campaign Manager] tem o [!DNL Creative Manager] ou nível de permissão superior.

Para saber como editar suas [!DNL LinkedIn Campaign Manager] permissões de usuário, consulte [Adicionar, editar e remover permissões de usuário em contas de publicidade](https://www.linkedin.com/help/lms/answer/5753) na documentação do LinkedIn.

Consulte [Como entender e configurar o destino baseado em pessoas do LinkedIn](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) para obter instruções de vídeo.

### [!DNL Google Customer Match] {#gcm}

Antes de usar [!UICONTROL People-Based Destinations] para enviar seus segmentos de audiência primários para um destino [!DNL Google Customer Match], é obrigatório que [!DNL Google] o adicione à lista de permissões.

Entre em contato com seu representante [!DNL Google] e siga as instruções de lista de permissões descritas na documentação [Use parceiros de Correspondência de Cliente para fazer upload dos seus dados](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507) [!DNL Google].

Depois que esse processo for concluído, você poderá criar seu [!UICONTROL People-Based Destination].

## Integração de dados {#data-onboarding}

A ingestão de dados para [!UICONTROL People-Based Destinations] suporta atualmente até 10 endereços de email com hash ligados a uma ID de cliente ([!DNL CRM ID]), por transferência em lote. Fazer upload de mais de 10 endereços de email com hash vinculados a uma ID do cliente faz com que o Audience Manager ingira 10 deles, sem ordem específica.

Fazer upload de mais de 10 endereços de email com hash vinculados a uma ID do cliente em várias transferências em lote faz com que o Audience Manager retenha os 10 endereços de email mais recentes adicionados.

## Privacidade de dados {#data-privacy}

Embora [!UICONTROL People-Based Destinations] permita que você público alvo audiências com base em endereços de email com hash carregados por você, você continua proibido de fazer upload de qualquer informação de visitante diretamente identificável para o Audience Manager. Na fase de integração de dados, você deve garantir que os endereços de e-mail que planeja usar estejam com hash com o algoritmo [!DNL SHA256]. Caso contrário, você não poderá usá-los em [!UICONTROL People-Based Destinations].

## Hash de dados versus criptografia {#data-hashing-encryption}

A criptografia é uma função bidirecional. Todas as informações criptografadas também podem ser descriptografadas, usando a chave de decodificação correta. A criptografia de dados no contexto do Audience Manager apresenta sérios riscos, já que qualquer forma criptografada de informações de identificação pessoal também pode ser descriptografada. Ao contrário da criptografia, [!UICONTROL People-Based Destinations] são projetados para funcionar com dados com hash.

O hash é uma função unidirecional que embaralha a entrada para produzir um resultado exclusivo. Ao usar algoritmos de hash adequados, como [!DNL SHA256], não há como reverter a função de hash e revelar as informações desembaralhadas. Os endereços de e-mail que você integrará ao Audience Manager devem ser hash com o algoritmo [!DNL SHA256]. Dessa forma, você pode garantir que nenhum endereço de email sem hash chegue ao Audience Manager.

## Requisitos de hash {#hashing-requirements}

Ao atualizar os endereços de email, certifique-se de cumprir os seguintes requisitos:

* Aparar todos os espaços à esquerda e à direita da string de email; exemplo: `johndoe@example.com`, não `<space>johndoe@example.com<space>`;
* Ao executar o hash das strings de email, certifique-se de executar o hash da string em minúsculas;
   * Exemplo: `example@email.com`, não `EXAMPLE@EMAIL.COM`;
* Certifique-se de que a cadeia de caracteres com hash esteja toda em minúsculas
   * Exemplo: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, não `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Não salve a corda.

Assista ao vídeo abaixo para entender os requisitos de hash de [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

A Adobe Experience Cloud oferece a opção de hash de IDs de clientes por meio de [!DNL Adobe Experience Platform Identity Service (ECID)]. Consulte [Suporte de hash SHA256 para setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) para obter informações detalhadas sobre como usar ECID para hash de IDs de clientes.

## Obtendo permissão do usuário {#obtaining-user-permission}

Como [!UICONTROL People-Based Destinations] ajuda a ativar dados de audiência primários em canais baseados em pessoas, é sua responsabilidade informar e obter quaisquer consentimentos necessários de seus clientes sobre como você usará seus dados para fins publicitários ou outros.

Antes de se inscrever para [!UICONTROL People-Based Destinations], certifique-se de obter o consentimento de seus clientes antes de usar suas informações para fins publicitários.

Caso seus clientes queiram recusar a campanha de publicidade, consulte [Gerenciamento de não participação](../../overview/data-security-and-privacy/data-privacy-requests.md) para obter mais detalhes sobre como impedir a Audience Manager de coletar dados.

## Impondo a Ativação de dados primários {#enforcing-first-party-activation}

Ao usar [!UICONTROL People-Based Destinations], você só pode usar dados primários para ativar segmentos de audiência em canais baseados em pessoas. Não é possível usar dados de terceiros ou de segundos para ativações de audiência em canais baseados em pessoas.

Ao usar [!UICONTROL People-Based Destinations], use [Controles de exportação de dados](../data-export-controls.md) para rotular seus [!UICONTROL data sources] e [!UICONTROL destinations] de acordo com as diretrizes e os requisitos das plataformas de destino e provedores de dados.

## IDs com hash autenticadas onboard por meio da segmentação de ID declarada {#onboard-authenticated-declared-id}

Há duas maneiras de trazer seus dados offline para o Audience Manager para [!UICONTROL People-Based Destinations].

* [Envie o Audience Manager de ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) dados em lote para assimilar endereços de email com hash. Com esse método, você pode optar por usar os endereços de email com hash do banco de dados [!DNL CRM] em [!UICONTROL People-Based Destinations]. Além disso, ao usar esse método, você também pode qualificar os endereços de email com hash para [características integradas](../traits/trait-and-segment-qualification-reference.md).
* Use [IDs declaradas](../declared-ids.md) para declarar endereços de email com hash ao transmitir IDs autenticadas do cliente. Ao usar esse método, o Audience Manager, em seu nome, envia somente para [!UICONTROL People-Based Destinations] os endereços de email com hash de usuários que autenticaram online. Os endereços de e-mail ativados por meio de canais baseados em pessoas são apenas aqueles nas chamadas declaradas do evento de ID. Outros endereços de email associados à ID do cliente não são enviados em tempo real.
