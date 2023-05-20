---
description: Leia abaixo para obter uma visão geral das necessidades do cliente que você precisa atender antes de se inscrever para Destinos com base em pessoas.
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: Pré-requisitos e considerações
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: cd40e1e3cc2199d1937950934d674cfad301f3e8
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 3%

---

# Pré-requisitos e considerações {#prerequisites-considerations}

>[!IMPORTANT]
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e pelo uso desse recurso. Nada contido aqui é aconselhamento jurídico. Consulte seu próprio serviço jurídico para obter orientação jurídica.

Leia abaixo para obter uma visão geral dos requisitos do cliente que você precisa atender antes de se inscrever no [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Leia este artigo com atenção antes de passar para a fase de implementação.

## Inscrever-se para [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] O é um recurso premium que melhora a experiência do Audience Manager, permitindo ativar segmentos de público-alvo primários em ambientes baseados em pessoas, direcionando o público-alvo com ofertas personalizadas em redes sociais ou por meio de marketing por email.

Entre em contato com o representante da Adobe para aproveitar esse recurso premium.

## Pré-requisitos específicos do parceiro {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Antes que você possa usar [!UICONTROL People-Based Destinations] para enviar seu público-alvo primário [!UICONTROL segments] para [!DNL Facebook], certifique-se de atender aos seguintes requisitos:

1. Seu [!DNL Facebook] a conta de usuário deve ter o **Gerenciar campanhas** permissão ativada para a conta de anúncio que você planeja usar.
2. Adicione o **Adobe Experience Cloud** conta comercial como um parceiro de publicidade em sua [!DNL Facebook Ad Account]. Use `business ID=206617933627973`. Consulte [Adicionar parceiros ao seu gerente de negócios](https://www.facebook.com/business/help/1717412048538897) para obter detalhes.
   >[!IMPORTANT]
   > Ao configurar as permissões para o Adobe Experience Cloud, você deve ativar o **Gerenciar campanhas** permissão. Isso é necessário para a integração de [!UICONTROL People-Based Destinations].
3. Leia e assine o [!DNL Facebook Custom Audiences] Termos de serviço. Para fazer isso, acesse `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, onde `accountID` é a sua [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn] {#linkedin}

Antes que você possa usar [!UICONTROL People-Based Destinations] para enviar segmentos de público-alvo primários para o [!DNL LinkedIn], verifique se [!DNL LinkedIn Campaign Manager] a conta tem o [!DNL Creative Manager] ou um nível de permissão superior.

Para saber como editar suas [!DNL LinkedIn Campaign Manager] permissões do usuário, consulte [Adicionar, editar e remover permissões de usuário em contas publicitárias](https://www.linkedin.com/help/lms/answer/5753) na documentação do LinkedIn.

Consulte [Como entender e configurar o destino com base em pessoas do LinkedIn](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) para obter instruções em vídeo.

### [!DNL Google Customer Match] {#gcm}

Antes que você possa usar [!UICONTROL People-Based Destinations] para enviar seus segmentos de público-alvo primários para um [!DNL Google Customer Match] destino, leia e siga a política de uso da Google [!DNL Customer Match], delineado no [Documentação de suporte do Google](https://support.google.com/google-ads/answer/6299717).

Em seguida, verifique se [!DNL Google] a conta do está configurada para um [!DNL Standard] ou um nível de permissão superior. Consulte a [Documentação do Google Ads](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&amp;rd=1) para obter detalhes.

Os clientes com contas em conformidade são automaticamente permitidos listados pela Google.

## Integração de dados {#data-onboarding}

Assimilação de dados para [!UICONTROL People-Based Destinations] Atualmente, o suporta até 10 endereços de email com hash vinculados a uma ID do cliente ([!DNL CRM ID]), por transferência em lote. Fazer upload de mais de 10 endereços de email com hash vinculados a uma ID do cliente faz com que o Audience Manager assimile 10 deles, em uma ordem específica.

Fazer upload de mais de 10 endereços de email com hash vinculados a uma ID do cliente em várias transferências em lote faz com que o Audience Manager mantenha os 10 endereços de email adicionados mais recentes.

## Privacidade de dados {#data-privacy}

Embora [!UICONTROL People-Based Destinations] Com a sua permissão para direcionar públicos-alvo com base em endereços de email com hash carregados por você, você permanece proibido de carregar qualquer informação de visitante diretamente identificável no Audience Manager. Na fase de integração de dados, é necessário garantir que os endereços de email que você planeja usar sejam atribuídos a [!DNL SHA256] algoritmo. Caso contrário, você não poderá usá-los no [!UICONTROL People-Based Destinations].

## Hash de dados versus criptografia {#data-hashing-encryption}

A criptografia é uma função bidirecional. Qualquer informação criptografada também pode ser descriptografada, usando a chave de descriptografia correta. A criptografia de dados no contexto de Audience Manager apresenta sérios riscos, já que qualquer forma criptografada de informações de identificação pessoal também pode ser descriptografada. Ao contrário da criptografia, [!UICONTROL People-Based Destinations] foram projetados para trabalhar com dados com hash em vez disso.

Hash é uma função unidirecional que embaralha a entrada para produzir um resultado único. Usando algoritmos de hash adequados, como [!DNL SHA256], não há como reverter a função de hash e revelar as informações não embaralhadas. Os endereços de email que você integrará no Audience Manager devem ter o hash com o [!DNL SHA256] algoritmo. Dessa forma, você pode garantir que nenhum endereço de email com hash atinja o Audience Manager.

## Requisitos de hash {#hashing-requirements}

Ao criar o hash dos endereços de email, verifique se os seguintes requisitos estão sendo cumpridos:

* Cortar todos os espaços à esquerda e à direita da cadeia de caracteres de email; exemplo: `johndoe@example.com`, não `<space>johndoe@example.com<space>`;
* Ao aplicar hash às cadeias de caracteres de email, certifique-se de aplicar hash à cadeia de caracteres em minúsculas;
   * Exemplo: `example@email.com`, não `EXAMPLE@EMAIL.COM`;
* Verifique se a cadeia de caracteres com hash está em minúsculas
   * Exemplo: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, não `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Não salve a corda.

Assista ao vídeo abaixo para entender os requisitos de hash do [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

O Adobe Experience Cloud oferece a opção de aplicar hash às IDs do cliente por meio do [!DNL Adobe Experience Platform Identity Service (ECID)]. Consulte [Suporte a hash SHA 256 para setCustomerIDs](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) para obter informações detalhadas sobre como usar a ECID para aplicar hash às IDs do cliente.

## Obter permissão do usuário {#obtaining-user-permission}

Desde [!UICONTROL People-Based Destinations] O ajuda a ativar dados de público-alvo primários em canais com base em pessoas. É sua responsabilidade informar e obter os consentimentos necessários de seus clientes sobre como você usará os dados deles para publicidade ou outros fins.

Antes de se inscrever para [!UICONTROL People-Based Destinations], obtenha o consentimento dos clientes antes de usar suas informações para fins de publicidade.

Caso seus clientes queiram recusar as campanhas publicitárias, consulte [Gerenciamento de recusa](../../overview/data-security-and-privacy/data-privacy-requests.md) para obter detalhes sobre como interromper a coleta de dados pelo Audience Manager.

## Impondo a ativação de dados primários {#enforcing-first-party-activation}

Ao usar [!UICONTROL People-Based Destinations], você só pode usar dados primários para ativar segmentos de público-alvo em canais com base em pessoas. Não é possível usar dados secundários ou de terceiros para ativação de público-alvo em canais com base em pessoas.

Ao usar [!UICONTROL People-Based Destinations], use [Controles da exportação de dados](../data-export-controls.md) para rotular o [!UICONTROL data sources] e [!UICONTROL destinations] de acordo com as diretrizes e requisitos das plataformas de destino e dos provedores de dados.

## Integração de IDs com hash autenticadas por meio do direcionamento de ID declarada {#onboard-authenticated-declared-id}

Há duas maneiras de trazer seus dados offline para o Audience Manager para [!UICONTROL People-Based Destinations].

* [Enviar dados em lote](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) para Audience Manager para assimilar endereços de email com hash. Com esse método, você pode optar por usar os endereços de email com hash de sua [!DNL CRM] banco de dados em [!UICONTROL People-Based Destinations]. Além disso, ao usar esse método, você também pode qualificar os endereços de email com hash do [características integradas](../traits/trait-and-segment-qualification-reference.md).
* Uso [IDs declaradas](../declared-ids.md) para declarar endereços de email com hash ao transmitir IDs autenticadas do cliente. Ao usar esse método, o Audience Manager, em seu nome, envia somente para [!UICONTROL People-Based Destinations] os endereços de email com hash de usuários que autenticaram online. Os endereços de email ativados por meio de canais com base em pessoas são apenas os que estão nas chamadas de evento de ID declaradas. Outros endereços de email associados à ID do cliente não são enviados em tempo real.
