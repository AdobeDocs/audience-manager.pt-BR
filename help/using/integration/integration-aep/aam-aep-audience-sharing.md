---
description: Este artigo descreve como os públicos-alvo são compartilhados entre o Audience Manager e a Adobe Experience Platform.
seo-description: Este artigo descreve como os públicos-alvo são compartilhados entre o Audience Manager e a Adobe Experience Platform.
seo-title: Compartilhamento de público-alvo entre o Audience Manager e a Adobe Experience Platform
solution: Audience Manager
title: Compartilhamento de público-alvo entre o Audience Manager e a Adobe Experience Platform
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
translation-type: tm+mt
source-git-commit: 08e0a97faa74b97bf42d5729b76ea2caa14193da

---


# Compartilhamento de público-alvo entre o Audience Manager e a Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
> A funcionalidade descrita nesta página está disponível para clientes do Audience Manager e da Adobe Experience Platform.
>
> Entre em contato com seu representante de vendas da Adobe para desbloquear o acesso a essa funcionalidade.

## Visão geral {#overview}

A funcionalidade de compartilhamento de público-alvo entre o Audience Manager e a Adobe Experience Platform permite que você compartilhe suas características e segmentos do Audience Manager na Adobe Experience Platform e vice-versa.

Você pode usar características e segmentos do Audience Manager na plataforma Experience para adicionar dados do Audience Manager aos perfis do cliente e se beneficiar do serviço [de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segmentation.md)segmentação da plataforma Experience.

No Audience Manager, é possível usar segmentos da plataforma Experience para casos de uso da Plataforma de gerenciamento de dados, como:
* Adicionar dados [de](/help/using/overview/data-types-collected.md#third-party-data) terceiros aos seus segmentos;
* [Modelagem algoritmica](/help/using/features/algorithmic-models/understanding-models.md);
* Ative seus segmentos para destinos que ainda não são suportados no catálogo [de](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)destinos da plataforma de experiência.

Além disso, seus segmentos da plataforma Experience são compartilhados com outras soluções da Experience Cloud, por meio dos [principais serviços](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

<br> 

Consulte a tabela abaixo para obter uma visão geral dos casos de uso de compartilhamento de público-alvo:

| **Caso de uso** | **Adobe Experience Platform** | **Audience Manager** | **Principais serviços** |
---------|----------|---------|---------
| **Compartilhamento de público-alvo** | <ul><li>Enriquecer perfis de clientes com dados do Audience Manager</li><li>Usar dados do Audience Manager na segmentação da plataforma Experience</li></ul> | <ul><li>Adicionar dados de terceiros a segmentos</li><li>Modelagem algoritmica</li><li>Ativação para destinos adicionais</li></ul> | Use os segmentos da plataforma Experience em outras soluções da Experience Cloud, como o Adobe Target ou o Analytics. |

<br> 

## Segmentos e características do Audience Manager na Adobe Experience Platform {#aam-segments-traits-in-aep}

Suas características e segmentos do Audience Manager aparecem na Plataforma de experiência como **Públicos** -alvo no fluxo de trabalho do segmento. Para obter mais informações sobre seus segmentos e características do Audience Manager na Experience Platform, consulte:

* [Visão geral do Serviço de segmentação](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segmentation.md)
* [Guia do usuário do Criador de segmentos da plataforma Experience](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)

<br> 

## Segmentos da plataforma Adobe Experience no Audience Manager {#aep-segments-in-aam}

Os segmentos criados na plataforma Experience são exibidos na interface do Audience Manager como características e segmentos, com as seguintes regras de composição:
* Características: A regra de característica é a ID do segmento da Plataforma de experiência.
* Segmento: O segmento consiste na característica descrita acima.

### Características {#aep-segments-as-aam-traits}

O Audience Manager cria automaticamente uma pasta de características chamada Características **da plataforma de** experiência no armazenamento de características.

![Características do painel da plataforma Experience](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Você pode usar características criadas automaticamente em segmentos ao lado de outras características. Por exemplo, é possível combinar características criadas a partir de segmentos da plataforma de experiência com características de terceiros adquiridas pelo [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Para obter um exemplo de uma característica criada automaticamente a partir de um segmento da plataforma de experiência, consulte a captura de tela abaixo:

![Características da plataforma Experience](/help/using/integration/integration-aep/assets/aep-trait.png)


| Número do item | Nome | Descrição |
---------|----------|---------
| 1 | Tipo de característica | As características criadas a partir de segmentos da plataforma de experiência são criadas como características integradas no Audience Manager. |
| 2 | Fonte de dados | Criado automaticamente. Todas as características e segmentos criados automaticamente a partir de segmentos da plataforma de experiência são armazenados na fonte de dados Compartilhamento **de público-alvo da plataforma** Adobe Experience. |
| 3 | Código de integração | O código de integração corresponde à ID do segmento na plataforma da experiência. |
| 4 | Expressão de características | A expressão de característica é `segID = segment ID in Experience Platform`. |
| 5 | Segmentos com esta característica | Um segmento criado automaticamente que usa essa característica como composição. |

<br> 

### Segmentos {#aep-segments-as-aam-segments}

O Audience Manager cria automaticamente uma pasta de segmento chamada Segmentos **da plataforma de** experiência no armazenamento do segmento.

![Captura de tela do painel](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Para obter um exemplo de um segmento criado automaticamente a partir de um segmento da plataforma de experiência, consulte a captura de tela abaixo:

![Captura de tela do segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Número do item | Nome | Descrição |
---------|----------|---------
| 1 | Código de integração | O código de integração corresponde à ID do segmento na plataforma da experiência. |
| 2 | Fonte de dados | Criado automaticamente. Todas as características e segmentos criados automaticamente a partir de segmentos da plataforma de experiência são armazenados na fonte de dados Compartilhamento **de público-alvo da plataforma** Adobe Experience. |
| 3 | Regra de mesclagem de perfil | **A Política** de mesclagem externa indica que os segmentos criados automaticamente seguem a política de mesclagem configurada na plataforma da experiência. |
| 4 | Regra de segmento | O segmento consiste na característica descrita na seção [Características](#aep-segments-as-aam-traits). |