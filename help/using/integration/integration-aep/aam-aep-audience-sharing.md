---
description: Este artigo descreve como as audiências são compartilhadas entre o Audience Manager e o Adobe Experience Platform.
seo-description: Este artigo descreve como as audiências são compartilhadas entre o Audience Manager e o Adobe Experience Platform.
seo-title: Compartilhamento de públicos entre o Audience Manager e a Adobe Experience Platform
solution: Audience Manager
title: Compartilhamento de públicos entre o Audience Manager e a Adobe Experience Platform
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
feature: Integration with Platform
translation-type: tm+mt
source-git-commit: 59eda3fa250fa33ef283f09b0027845431e9517b
workflow-type: tm+mt
source-wordcount: '1485'
ht-degree: 2%

---


# Compartilhamento de segmentos de Experience Platform com Audience Manager e outras soluções de Experience Cloud {#aam-aep-audience-sharing}

>[!NOTE]
>
> Entre em contato com seu representante de vendas de Adobe para desbloquear o acesso a essa funcionalidade.

## Visão geral {#overview}

A funcionalidade de compartilhamento de audiências entre o Audience Manager e o Adobe Experience Platform permite que você compartilhe seus traços e segmentos do Audience Manager para o Adobe Experience Platform e vice-versa. Você precisa [[!DNL Audience Manager Connector]](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) ativar o compartilhamento de audiências entre o Audience Manager e o Adobe Experience Platform.

Você pode usar características e segmentos do Audience Manager no Experience Platform para adicionar dados do Audience Manager aos perfis do cliente e se beneficiar do serviço [de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)segmentação do Experience Platform.

No Audience Manager, é possível usar segmentos Experience Platform para casos de uso da Plataforma de Gestão de dados, como:
* Adicionar dados [de](/help/using/overview/data-types-collected.md#third-party-data) terceiros aos seus segmentos;
* [Modelagem algoritmica](/help/using/features/algorithmic-models/understanding-models.md);
* Ative seus segmentos para destinos que ainda não são suportados no catálogo [de](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)destinos de Experience Platform.

Além disso, seus segmentos de Experience Platform são compartilhados com outras soluções de Experience Cloud, por meio dos [principais serviços](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

>[!IMPORTANT]
>
> * Você precisa de uma licença de Audience Manager para ativar os casos de uso da Plataforma de Gestão de dados mencionados acima.
> * Você *não precisa* de uma licença de Audience Manager para compartilhar segmentos de Experience Platform com a Adobe Ad Cloud, Adobe Target e outras soluções de Experience Cloud, por meio da integração dos principais serviços.


<br> 

Consulte a tabela abaixo para obter uma visão geral dos casos de uso de compartilhamento de audiências:

| **Caso de uso** | **Adobe Experience Platform** | **Audience Manager** | **Principais serviços** |
---------|----------|---------|---------
| **Compartilhamento de audiências** | <ul><li>Enriqueça os perfis dos clientes com os dados do Audience Manager</li><li>Usar dados de Audience Manager na segmentação de Experience Platform</li></ul> | <ul><li>Adicionar dados de terceiros a segmentos</li><li>Modelagem algoritmica</li><li>Ativação para destinos adicionais</li></ul> | Use segmentos Experience Platform em outras soluções de Experience Cloud, como o Adobe Target ou o Analytics. |

<br> 

## Segmentos e características do Audience Manager no Adobe Experience Platform {#aam-segments-traits-in-aep}

Suas características e segmentos de Audience Manager aparecem no Experience Platform como **Audiências** no fluxo de trabalho do segmento. Para obter mais informações sobre seus segmentos de Audience Manager e características no Experience Platform, consulte:

* [Visão geral do Serviço de segmentação](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Guia do usuário do Construtor de segmentos de Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Conector Audience Manager](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Segmentos Adobe Experience Platform no Audience Manager {#aep-segments-in-aam}

Os segmentos criados no Experience Platform aparecem na interface do Audience Manager como sinais, características e segmentos, com as seguintes regras de composição:

* Sinal: Para cada segmento de Experience Platform, você deve ver sinais no formulário `segID = segment ID`.
* Características: A regra de característica é a ID do segmento Experience Platform.
* Segmento: O segmento consiste na característica descrita acima.

### Sinais {#aep-segments-as-aam-signals}

Selecione **[!UICONTROL Audience Data > Signals > General Online Data]** e procure por `SegId` para encontrar sinais vindos de Experience Platform. Você pode usar essa tela para fins de depuração, para verificar se a integração entre Experience Platform e Audience Manager foi configurada corretamente.

![Consulte Sinais de Experience Platform no Audience Manager no painel de Sinais](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Características {#aep-segments-as-aam-traits}

O Audience Manager cria automaticamente uma pasta de características chamada **Experience Platform Traits** no armazenamento de características.

![Características do painel Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Você pode usar características criadas automaticamente em segmentos ao lado de outras características. Por exemplo, é possível combinar características criadas a partir de segmentos Experience Platform com características de terceiros adquiridas por meio do [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Para obter um exemplo de uma característica criada automaticamente a partir de um segmento Experience Platform, consulte a captura de tela abaixo:

![Traço de Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Número do item | Nome | Descrição |
---------|----------|---------
| 1 | [!UICONTROL Trait Type] | As características criadas a partir de segmentos Experience Platform são criadas como características integradas no Audience Manager. |
| 2 | [!UICONTROL Data Source] | Criado automaticamente. Todas as características e segmentos criados automaticamente a partir de segmentos de Experience Platform são armazenados na fonte de dados **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | O código de integração corresponde à ID do segmento no Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | A expressão característica é `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Um segmento criado automaticamente que usa essa característica como composição. |

<br> 

### Segmentos {#aep-segments-as-aam-segments}

O Audience Manager cria automaticamente uma pasta de segmento chamada **Experience Platform Segments** no armazenamento do segmento.

![Captura de tela do painel](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Para ver um exemplo de um segmento criado automaticamente a partir de um segmento Experience Platform, consulte a captura de tela abaixo:

![Captura de tela do segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Número do item | Nome | Descrição |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | O código de integração corresponde à ID do segmento no Experience Platform. |
| 2 | [!UICONTROL Data Source] | Criado automaticamente. Todas as características e segmentos criados automaticamente a partir de segmentos de Experience Platform são armazenados na fonte de dados **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indica que os segmentos criados automaticamente seguem a política de mesclagem configurada no Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | O segmento consiste na característica descrita na seção [Características](#aep-segments-as-aam-traits). |

## Suporte ao Controle de exportação de dados do Audience Manager no Experience Platform {#aam-data-export-control-in-aep}

Para impor a conformidade de uso de dados no Experience Platform, todos os conjuntos de dados e campos aplicáveis devem receber os rótulos [apropriados de uso de](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html)dados. Além disso, as políticas [de uso de](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html) dados devem ser ativadas para ações de marketing específicas contra esses rótulos, conforme esboçado pela estrutura [](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework)DULE (Data Usage Labeling and Implementation).

No processo de compartilhamento de audiência entre Audience Manager e Experience Platform, todos os Controles de exportação de dados que foram aplicados aos segmentos Audience Manager são traduzidos para rótulos equivalentes e ações de marketing reconhecidas pelo Experience Platform Data Governance, e vice-versa.

>[!NOTE]
>
>Para obter informações mais gerais sobre Controles de exportação de dados, consulte a documentação [Controles de exportação de](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)dados.
>
>Este documento fornece uma referência para como os controles de exportação de dados do Audience Manager específicos mapeiam para rótulos de uso de dados e ações de marketing na Plataforma.

### Controles de exportação de dados para rótulos de uso de dados

A tabela a seguir descreve como os Controles de exportação de dados específicos mapeiam para rótulos de uso de dados reconhecidos:

| Controle de exportação de dados | Rótulo de uso de dados |
| --- | --- |
| Não é possível usar com informações de identificação pessoal | C3: Os dados não podem ser combinados ou usados de outra forma com informações diretamente identificáveis |
| Não pode ser usado para direcionamento de anúncio externo | C5: Os dados não podem ser usados para direcionamento de conteúdo ou anúncios entre sites com base em interesses |
| Não pode ser usado para direcionamento de anúncio no site | C6: Os dados não podem ser usados para direcionamento de anúncios no site |
| Não pode ser usado para personalização no site | C7: Os dados não podem ser usados para direcionamento de conteúdo no site |

### Controles de exportação de dados para ações de marketing

A tabela a seguir descreve como rótulos de exportação de dados específicos mapeiam para ações de marketing reconhecidas:

| Rótulo de exportação de dados | Ação de marketing |
| --- | --- |
| Este destino pode permitir uma combinação com informações de identificação pessoal (PII) | Combinar com PII |
| Esse destino pode ser usado para direcionamento de anúncios fora do site | Definição de metas entre sites |
| Esse destino pode ser usado para direcionamento de anúncios no site | Anúncios no site |
| Esse destino pode ser usado para personalização de anúncios no site | Personalização no site |

## Entenda as diferenças entre a população do segmento entre Audience Manager e Experience Platform {#aep-aam-segment-population-differences}

Os números de preenchimento do segmento podem variar entre seus segmentos de Audience Manager e Experience Platform. Embora os números de segmentos para audiências semelhantes ou idênticas devam ser próximos, as diferenças nas populações podem ser devidas aos fatores listados abaixo.

### Avaliação de segmentos no Experience Platform

O Audience Manager atualiza os números de relatórios na interface uma vez por dia.   O tempo desta atualização raramente se alinha com o tempo da avaliação de segmentos no Experience Platform.

### Diferenças entre Regras de mesclagem de Perfis e Políticas de mesclagem

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) no Audience Manager e [[!UICONTROL Merge Policies]](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) no Experience Platform funcionam de forma diferente, e o gráfico de identidade usado para cada um varia. Por isso, são esperadas algumas diferenças entre as populações de segmentos.

### Composição do segmento no Experience Platform

A integração entre a Adobe Experience Platform e a Audience Manager compartilha várias namespaces [de](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html#identity-types) identidade padrão para todos os clientes: ECID, IDFA, GAID, endereços de email com hash (EMAIL_LC_SHA256), AdCloud ID etc. Se seus segmentos de Experience Platform usarem qualquer uma dessas identidades como identidade primária para os perfis qualificados, os perfis serão contados em características de Audience Manager e segmentos.

Além disso, o Audience Manager pode registrar as realizações de entrada para qualquer namespace de identidade personalizada que você usa nos segmentos do Experience Platform se você já tiver uma fonte de dados correspondente no Audience Manager.

>[!NOTE]
>
> Audiências no Experience Platform com identidades destacadas por e-mails brutos nunca aparecem no Audience Manager.

Por exemplo, se você tivesse um segmento de Experience Platform &quot;Todos os meus clientes&quot; e os perfis qualificados fossem IDs de CRM, ECID, IDFA, endereços de email em bruto e com hash, o segmento correspondente no Audience Manager só incluiria perfis com chaves de CRM, ECID, IDFA e endereços de email com hash. A população de segmentos em Audience Manager seria menor que a de Experience Platform.

![Compartilhamento de segmentos Experience Platform para Audience Manager - composição de segmentos](/help/using/integration/integration-aep/assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Visão geral do Serviço de segmentação](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Guia do usuário do Construtor de segmentos de Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Conector Audience Manager](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)