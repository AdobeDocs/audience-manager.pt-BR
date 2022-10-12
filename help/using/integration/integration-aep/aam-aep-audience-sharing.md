---
description: Saiba como habilitar o compartilhamento de dados e como os públicos-alvo são compartilhados entre o Audience Manager e o Adobe Experience Platform
solution: Audience Manager
title: Compartilhamento de segmento do Experience Platform com o Audience Manager e outras soluções do Experience Cloud
keywords: Compartilhamento de público da AEP, segmentos da AEP, segmentos da plataforma, compartilhamento de segmento, compartilhamento de público, compartilhamento de segmentos AAM compartilhamento de segmentos da AEP
feature: Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: 14e0ddd00d3a25674090ea9dbe485c77ad1d2aed
workflow-type: tm+mt
source-wordcount: '1862'
ht-degree: 1%

---

# Compartilhamento de segmento do Experience Platform com o Audience Manager e outras soluções do Experience Cloud

## Visão geral {#overview}

A funcionalidade de compartilhamento de público-alvo entre o Audience Manager e o Adobe Experience Platform permite compartilhar características e segmentos do Audience Manager com o Adobe Experience Platform e vice-versa. Você precisa do [[!DNL Audience Manager Connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html) para permitir o compartilhamento de público-alvo entre o Audience Manager e o Adobe Experience Platform.

Você pode usar características e segmentos do Audience Manager no Experience Platform para adicionar dados do Audience Manager aos perfis do cliente e se beneficiar do Experience Platform [serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=en).

No Audience Manager, é possível usar segmentos de Experience Platform para casos de uso da Plataforma de gerenciamento de dados, como:
* Adicionar [dados de terceiros](/help/using/overview/data-types-collected.md#third-party-data) aos seus segmentos;
* [Modelagem algoritmica](/help/using/features/algorithmic-models/understanding-models.md);
* Ative seus segmentos para destinos que ainda não são suportados no Experience Platform [catálogo de destinos](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

Além disso, seus segmentos do Experience Platform são compartilhados com outras soluções Experience Cloud, por meio de [Principais serviços](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html).

>[!IMPORTANT]
>
> * Você precisa de uma licença do Audience Manager para ativar os casos de uso da Plataforma de gerenciamento de dados mencionados acima.
> * Você *não precisam* uma licença do Audience Manager para compartilhar segmentos do Experience Platform com a Adobe Advertising Cloud, Adobe Target, Marketo e outras soluções do Experience Cloud, por meio da integração dos Serviços principais.


Consulte a tabela abaixo para obter uma visão geral dos casos de uso de compartilhamento de público-alvo:

| **Caso de uso** | **Adobe Experience Platform** | **Audience Manager** | **Principais serviços** |
|---------|----------|---------|---------|
| **Compartilhamento de público** | <ul><li>Enriqueça os perfis do cliente com dados do Audience Manager</li><li>Usar dados de Audience Manager na segmentação de Experience Platform</li></ul> | <ul><li>Adicionar dados de terceiros aos segmentos</li><li>Modelagem algoritmica</li><li>Ativação para destinos adicionais</li></ul> | Use segmentos do Experience Platform em outras soluções do Experience Cloud, como Adobe Target, Advertising Cloud ou Marketo. |

{style=&quot;table-layout:auto&quot;}

## Introdução - Como ativar o compartilhamento de dados entre o Audience Manager e o Experience Platform {#enable-data-sharing-aam-aep}

As duas seções abaixo indicam como ativar o compartilhamento de dados entre o Audience Manager e o Experience Platform.

### Ative o compartilhamento de dados do Audience Manager para o Experience Platform {#enable-aam-to-aep-data}

Para enviar segmentos e características de Audience Manager para Experience Platform, você deve configurar o conector de origem do Audience Manager no catálogo de origens do Experience Platform. Este é um fluxo de trabalho de autoatendimento que não requer o envolvimento das equipes de Atendimento ao cliente ou de engenharia do Adobe. Para configurar o conector de origem do Audience Manager, leia:

* [Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
* [Criar uma conexão de origem do Adobe Audience Manager na interface do usuário](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=en)

>[!IMPORTANT]
>
>O Adobe incentiva os clientes a configurar a conexão sem selecionar o **[!UICONTROL Select all segments]** e **[!UICONTROL Select all traits]** , conforme mostrado abaixo. A assimilação de populações de segmentos de Audience Manager consideráveis afeta diretamente a contagem total de perfis ao enviar um segmento de Audience Manager para a Platform pela primeira vez usando a fonte de Audience Manager. Isso significa que a seleção de todos os segmentos pode levar a uma contagem de Perfis além do seu direito de uso de licença.
>
>![Captura de tela mostrando as opções Select all segments e Select all traits desmarcadas no workflow para se conectar ao conector de origem do Audience Manager.](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Ative o compartilhamento de dados do Experience Platform para o Audience Manager {#enable-aep-to-aam-data}

>[!NOTE]
>
> Entre em contato com o Gerente de sucesso do cliente do Adobe ou com o Atendimento ao cliente para desbloquear o acesso a essa funcionalidade.

Para enviar segmentos do Experience Platform para o Audience Manager, você deve entrar em contato com o Atendimento ao cliente ou com o Gerente de sucesso do cliente. As equipes de Atendimento ao cliente e Gerenciamento de suporte ao cliente devem registrar um ticket (consulte ticket modelo AAM-52354) para habilitar a conexão da Plataforma ao Audience Manager.

Certifique-se de compartilhar planos para os dados que vão de Plataforma para Audience Manager, para garantir que a conexão esteja configurada corretamente. Por exemplo, se você precisar que dados regionais sejam compartilhados para segmentos enviados para a Adobe Target, essas informações precisarão ser comunicadas no ticket. A conexão de compartilhamento de dados do Experience Platform para o Audience Manager é configurada no prazo de seis dias úteis após o envio da solicitação.

## Segmentos e características do Audience Manager no Adobe Experience Platform {#aam-segments-traits-in-aep}

Após configurar o conector de origem do Audience Manager para importar características e segmentos do Audience Manager, seus dados do Audience Manager aparecem no Experience Platform como **Públicos-alvo** no fluxo de trabalho do segmento. Para obter mais informações sobre seus segmentos de Audience Manager e características no Experience Platform, leia:

* [Visão geral do serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
* [Guia do usuário do Experience Platform Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)

## Segmentos Adobe Experience Platform no Audience Manager {#aep-segments-in-aam}

Os segmentos criados no Experience Platform aparecem na interface do Audience Manager como sinais, características e segmentos, com as seguintes regras de composição:

* Sinal: Para cada segmento de Experience Platform, você deve ver sinais no formulário `segID = segment ID`.
* Característica: A regra de característica é a ID do segmento Experience Platform.
* Segmento: O segmento consiste na característica descrita acima.

### Sinais {#aep-segments-as-aam-signals}

Selecionar **[!UICONTROL Audience Data > Signals > General Online Data]** e pesquisar por `SegId` para encontrar sinais vindos de Experience Platform. Você pode usar essa tela para fins de depuração, para verificar se a integração entre o Experience Platform e o Audience Manager foi configurada corretamente.

![Consulte Sinais de Experience Platform no Audience Manager no painel Sinais](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Características  {#aep-segments-as-aam-traits}

O Audience Manager cria automaticamente uma pasta de características chamada **Características do Experience Platform** no armazenamento de características.

![Características do painel de Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Você pode usar características criadas automaticamente em segmentos ao lado de outras características. Por exemplo, você pode misturar características criadas em segmentos de Experience Platform com características de terceiros adquiridas por meio do [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Para obter um exemplo de uma característica criada automaticamente a partir de um segmento de Experience Platform, consulte a captura de tela abaixo:

![Característica do Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Número do item | Nome | Descrição |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | As características criadas a partir de segmentos Experience Platform são criadas como características integradas no Audience Manager. |
| 2 | [!UICONTROL Data Source] | Criado automaticamente. Todas as características e segmentos criados automaticamente a partir de segmentos de Experience Platform são armazenados na fonte de dados **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | O código de integração corresponde à ID do segmento no Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | A expressão de característica é `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Um segmento criado automaticamente que usa essa característica como sua composição. |

{style=&quot;table-layout:auto&quot;}

### Segmentos  {#aep-segments-as-aam-segments}

O Audience Manager cria automaticamente uma pasta de segmento chamada **Experience Platform Segmentos** no armazenamento do seu segmento.

![Captura de tela do painel](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Para obter um exemplo de um segmento criado automaticamente a partir de um segmento de Experience Platform, consulte a captura de tela abaixo:

![Captura de tela do segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Número do item | Nome | Descrição |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | O código de integração corresponde à ID do segmento no Experience Platform. |
| 2 | [!UICONTROL Data Source] | Criado automaticamente. Todas as características e segmentos criados automaticamente a partir de segmentos de Experience Platform são armazenados na fonte de dados **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indica que os segmentos criados automaticamente seguem a política de mesclagem configurada no Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | O segmento consiste na característica descrita na variável [Seção Características](#aep-segments-as-aam-traits). |

{style=&quot;table-layout:auto&quot;}

## Suporte ao Controle de exportação de dados do Audience Manager no Experience Platform {#aam-data-export-control-in-aep}

Para impor a conformidade do uso de dados no Experience Platform, todos os conjuntos de dados e campos aplicáveis devem ser fornecidos conforme necessário [rótulos de uso de dados](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html). Além disso, [políticas de uso de dados](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html) deve estar habilitado para ações de marketing específicas em relação a esses rótulos, conforme descrito pelo [Estrutura DULE (Label Using Labeling and Enforcement, Rotulagem e aplicação de uso de dados)](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html#dule-framework).

No processo de compartilhamento de público-alvo entre o Audience Manager e o Experience Platform, todos os Controles de exportação de dados que foram aplicados a segmentos do Audience Manager são traduzidos para rótulos e ações de marketing equivalentes reconhecidos pela Governança de dados do Experience Platform, e vice-versa.

>[!NOTE]
>
>Para obter informações mais gerais sobre Controles da exportação de dados, consulte [Documentação dos Controles da exportação de dados](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html).
>
>Este documento fornece uma referência para como os Controles de exportação de dados do Audience Manager são mapeados para rótulos de uso de dados e ações de marketing na plataforma.

### Controles da exportação de dados para rótulos de uso de dados

A tabela a seguir descreve como os Controles de exportação de dados específicos são mapeados para rótulos de uso de dados reconhecidos:

| Controle da exportação de dados | Rótulo de uso de dados |
| --- | --- |
| Não pode ser usado com informações de identificação pessoal | C3: Os dados não podem ser combinados ou usados com informações diretamente identificáveis |
| Não pode ser usado para direcionamento de anúncio externo | C5: Os dados não podem ser usados para direcionamento de conteúdo ou anúncios baseado em interesses entre sites |
| Não pode ser usado para direcionamento de anúncios no site | C6: Os dados não podem ser usados para o direcionamento de anúncios no site |
| Não pode ser usado para personalização no site | C7: Os dados não podem ser usados para o direcionamento no site do conteúdo |

{style=&quot;table-layout:auto&quot;}

### Controles da exportação de dados para ações de marketing

A tabela a seguir descreve como os Rótulos de exportação de dados específicos mapeiam para ações de marketing reconhecidas:

| Rótulo de exportação de dados | Ação de marketing |
| --- | --- |
| Este destino pode permitir uma combinação com informações pessoalmente identificáveis (PII) | Combinar com PII |
| Esse destino pode ser usado para direcionamento de anúncios fora do site | Direcionamento entre sites |
| Esse destino pode ser usado para o direcionamento de anúncios no site | Publicidade no site |
| Esse destino pode ser usado para personalização de anúncios no site | Personalização no site |

{style=&quot;table-layout:auto&quot;}

## Entender as diferenças de população do segmento entre Audience Manager e Experience Platform {#aep-aam-segment-population-differences}

Os números de população do segmento podem variar entre seus segmentos de Audience Manager e Experience Platform. Embora os números de segmentos para públicos semelhantes ou idênticos devam ser próximos, as diferenças nas populações podem ser devidas aos fatores listados abaixo.

### Avaliação de segmento no Experience Platform

O Audience Manager atualiza os números dos relatórios na interface uma vez por dia. O tempo dessa atualização raramente se alinha ao tempo da avaliação de segmento no Experience Platform.

### Diferenças entre as Regras de mesclagem de perfis e as Políticas de mesclagem

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) em Audience Manager e [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html) no Experience Platform funcionam de forma diferente, e o gráfico de identidade usado para cada um varia. Por esse motivo, são esperadas algumas diferenças entre as populações de segmentos.

>[!NOTE]
>
> Ao compartilhar segmentos do Experience Platform para o Audience Manager, a organização da plataforma [política de mesclagem padrão](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en#default-merge-policy) tem precedência sobre a [política de mesclagem usada pelo segmento](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#merge-policies) compartilhado com o Audience Manager. Por exemplo, se a política de mesclagem do segmento compartilhado permitir [Compilação de ID](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=en#configure), mas a política de mesclagem padrão da organização não, isso pode resultar em diferenças de população entre a Plataforma e o Audience Manager.

### Composição do segmento no Experience Platform

A integração entre o Adobe Experience Platform e o Audience Manager compartilha diversos padrões [namespaces de identidade](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#identity-types) para todos os clientes: ECID, IDFA, GAID, endereços de email com hash (EMAIL_LC_SHA256), AdCloud ID. Se os segmentos de Experience Platform usarem qualquer uma dessas características como identidade primária para os perfis qualificados, os perfis serão contados em características e segmentos de Audience Manager.

>[!NOTE]
>
> Os públicos-alvo no Experience Platform com identidades destacadas em emails brutos nunca aparecem no Audience Manager.

Por exemplo, se você tivesse um segmento Experience Platform &quot;Todos os meus clientes&quot; e os perfis qualificados fossem IDs de CRM, ECID, IDFA, endereços de email brutos e com hash, o segmento correspondente no Audience Manager incluiria apenas perfis com hash ECID, IDFA e endereços de email com hash. A população do segmento no Audience Manager seria menor que a do Experience Platform.

![Compartilhamento de segmento de Experience Platform para Audience Manager - composição de segmento](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Visão geral do serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
>* [Guia do usuário do Experience Platform Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)
>* [Conector Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

