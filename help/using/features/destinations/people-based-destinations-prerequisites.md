---
description: 'Leia abaixo para obter uma visão geral dos requisitos do cliente que você precisa atender antes de se inscrever em Destinos baseados em pessoas.  '
seo-description: 'Leia abaixo para obter uma visão geral dos requisitos do cliente que você precisa atender antes de se inscrever em Destinos baseados em pessoas.  '
seo-title: Pré-requisitos e Considerações para Destinos Baseados em Pessoas
solution: Audience Manager
title: Pré-requisitos e considerações
translation-type: tm+mt
source-git-commit: 4d4915b9a99ddcdf321d9f4970321f5f54e057ea
workflow-type: tm+mt
source-wordcount: '932'
ht-degree: 0%

---


# Pré-requisitos e considerações {#prerequisites-considerations}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo durante a configuração e o uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

Leia abaixo para obter uma visão geral dos requisitos do cliente que você precisa atender antes de se inscrever [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Leia este artigo cuidadosamente antes de passar para a fase de implementação.

## Inscrever-se para [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] é um recurso premium que aprimora sua experiência com Audience Manager, permitindo ativar seus segmentos de audiência primários em ambientes baseados em pessoas, direcionando sua audiência com ofertas personalizadas em redes sociais ou por meio de marketing por email.

Entre em contato com seu representante da Adobe para aproveitar esse recurso premium.

## Pré-requisitos específicos do parceiro {#partner-prerequisites}

### [!DNL Facebook]

Antes de poder usar [!UICONTROL People-Based Destinations] para enviar sua audiência primária [!UICONTROL segments] para [!DNL Facebook], verifique se você atende aos seguintes requisitos:

1. Sua conta [!DNL Facebook] de usuário deve ter a permissão **Gerenciar campanha** ativada para a conta de anúncio que você planeja usar.
2. Adicione a conta comercial da **Adobe Experience Cloud** como um parceiro de publicidade em seu [!DNL Facebook Ad Account]site. Use `business ID=206617933627973`. Consulte [Adicionar parceiros ao seu gerente](https://www.facebook.com/business/help/1717412048538897) de negócios para obter detalhes.
   >[!IMPORTANT]
   > Ao configurar as permissões para a Adobe Experience Cloud, você deve ativar a permissão **Gerenciar campanha** . Isso é necessário para a [!UICONTROL People-Based Destinations] integração.
3. Leia e assine os [!DNL Facebook Custom Audiences] Termos de serviço. Para fazer isso, vá para `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, onde `accountID` está seu [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn]

Antes de poder usar [!UICONTROL People-Based Destinations] para enviar seus segmentos de audiência primários para [!DNL LinkedIn], verifique se sua [!DNL LinkedIn Campaign Manager] conta tem o nível de permissão [!DNL Creative Manager] ou superior.

Para saber como editar suas permissões de [!DNL LinkedIn Campaign Manager] usuário, consulte [Adicionar, editar e remover permissões de usuário em contas](https://www.linkedin.com/help/lms/answer/5753) de publicidade na documentação do LinkedIn.

## Integração de dados {#data-onboarding}

A ingestão de dados para [!UICONTROL People-Based Destinations] atualmente suporta até 10 endereços de email com hash vinculados a uma ID do cliente ([!DNL CRM ID]), por transferência em lote. Fazer upload de mais de 10 endereços de email com hash vinculados a uma ID do cliente faz com que o Audience Manager ingira 10 deles, sem ordem específica.

Fazer upload de mais de 10 endereços de email com hash vinculados a uma ID do cliente em várias transferências em lote faz com que o Audience Manager retenha os 10 endereços de email mais recentes adicionados.

## Privacidade de dados {#data-privacy}

Embora [!UICONTROL People-Based Destinations] permita que você público alvo audiências com base em endereços de email com hash carregados por você, você permanece proibido de fazer upload de qualquer informação de visitante diretamente identificável para o Audience Manager. Na fase de integração de dados, é necessário garantir que os endereços de email que você pretende usar estejam com hash com o [!DNL SHA256] algoritmo. Caso contrário, você não poderá usá-los em [!UICONTROL People-Based Destinations].

## Hashes de dados versus criptografia {#data-hashing-encryption}

A criptografia é uma função bidirecional. Todas as informações criptografadas também podem ser descriptografadas, usando a chave de decodificação correta. A criptografia de dados no contexto do Audience Manager apresenta sérios riscos, já que qualquer forma criptografada de informações de identificação pessoal também pode ser descriptografada. Ao contrário da criptografia, [!UICONTROL People-Based Destinations] são projetados para trabalhar com dados com hash.

O hash é uma função unidirecional que embaralha a entrada para produzir um resultado exclusivo. Usando algoritmos de hash adequados, como [!DNL SHA256], não há como reverter a função de hash e revelar as informações desembaralhadas. Os endereços de e-mail que você vai receber no Audience Manager devem ser hash com o [!DNL SHA256] algoritmo. Dessa forma, você pode garantir que nenhum endereço de email sem hash chegue ao Audience Manager.

## Requisitos de hash {#hashing-requirements}

Ao atualizar os endereços de email, certifique-se de cumprir os seguintes requisitos:

* Aparar todos os espaços à esquerda e à direita da string de email; exemplo: `johndoe@example.com`, não `<space>johndoe@example.com<space>`;
* Ao executar o hash das strings de email, certifique-se de executar o hash da string em minúsculas;
   * Exemplo: `example@email.com`, não `EXAMPLE@EMAIL.COM`;
* Certifique-se de que a cadeia de caracteres com hash esteja toda em minúsculas
   * Exemplo: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, não `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Não salve a corda.

Assista ao vídeo abaixo para entender os requisitos de hash do [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

A Adobe Experience Cloud oferece a opção de hash de IDs de clientes pelo [!DNL Adobe Experience Platform Identity Service (ECID)]. Consulte Suporte de hash [SHA256 para setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) para obter informações detalhadas sobre como usar a ECID para hash de IDs de clientes.

## Obtendo permissão do usuário {#obtaining-user-permission}

Como [!UICONTROL People-Based Destinations] ajuda a ativar dados de audiência primários em canais baseados em pessoas, é sua responsabilidade informar e obter quaisquer consentimentos necessários de seus clientes sobre como você usará seus dados para fins publicitários ou outros.

Antes de se inscrever para [!UICONTROL People-Based Destinations], certifique-se de obter o consentimento dos clientes antes de usar suas informações para fins publicitários.

Caso seus clientes queiram recusar campanhas publicitárias, consulte Gerenciamento [de](../../overview/data-security-and-privacy/data-privacy-requests.md) recusa para obter detalhes sobre como impedir que o Audience Manager colete dados.

## Aplicação da Ativação de dados primários {#enforcing-first-party-activation}

Ao usar [!UICONTROL People-Based Destinations], você só pode usar dados primários para ativar segmentos de audiência em canais baseados em pessoas. Não é possível usar dados de terceiros ou de segundos para ativações de audiência em canais baseados em pessoas.

Ao usar [!UICONTROL People-Based Destinations], use os Controles [de exportação de](../data-export-controls.md) dados para rotular seu e [!UICONTROL data sources] [!UICONTROL destinations] de acordo com as diretrizes e requisitos das plataformas de destino e provedores de dados.

## IDs com hash autenticadas onboard por meio da segmentação de ID declarada {#onboard-authenticated-declared-id}

Há duas maneiras de trazer seus dados offline para o Audience Manager [!UICONTROL People-Based Destinations].

* [Envie dados](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) em lote para o Audience Manager para assimilar endereços de email em hash. Com esse método, você pode optar por usar os endereços de email com hash do seu [!DNL CRM] banco de dados em [!UICONTROL People-Based Destinations]. Além disso, ao usar esse método, você também pode qualificar os endereços de email com hash para características [integradas](../traits/trait-and-segment-qualification-reference.md).
* Use as IDs [](../declared-ids.md) declaradas para declarar endereços de email com hash ao transmitir IDs autenticadas do cliente. Ao usar esse método, o Audience Manager, em seu nome, envia somente para [!UICONTROL People-Based Destinations] os endereços de email com hash de usuários que se autenticaram on-line. Os endereços de e-mail ativados por meio de canais baseados em pessoas são apenas aqueles nas chamadas declaradas do evento de ID. Outros endereços de email associados à ID do cliente não são enviados em tempo real.
