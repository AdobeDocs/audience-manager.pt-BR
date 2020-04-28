---
description: Este artigo descreve como as audiências são compartilhadas entre o Audiência Manager e a Adobe Experience Platform.
seo-description: Este artigo descreve como as audiências são compartilhadas entre o Audiência Manager e a Adobe Experience Platform.
seo-title: Compartilhamento de Audiências entre o Audiência Manager e a plataforma Adobe Experience
solution: Audience Manager
title: Compartilhamento de Audiências entre o Audiência Manager e a plataforma Adobe Experience
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
translation-type: tm+mt
source-git-commit: f191035a1ad4b83bb3d391de80e1f925d6295df7

---


# Compartilhamento de Audiências entre o Audiência Manager e a plataforma Adobe Experience {#aam-aep-audience-sharing}

>[!NOTE]
>
> Entre em contato com seu representante de vendas da Adobe para desbloquear o acesso a essa funcionalidade.

## Visão geral {#overview}

A funcionalidade de compartilhamento de audiências entre o Audiência Manager e a Adobe Experience Platform permite que você compartilhe suas características e segmentos do Audiência Manager na Adobe Experience Platform e vice-versa. Você precisa do Conector [do Gerenciador de](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) Audiências para permitir o compartilhamento de audiências entre o Audiência Manager e a plataforma Adobe Experience.

Você pode usar características e segmentos do Audiência Manager na Experience Platform para adicionar dados do Audiência Manager aos perfis do cliente e se beneficiar do serviço [de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)segmentação da Experience Platform.

No Audiência Manager, você pode usar segmentos da plataforma de experiência para casos de uso da plataforma de Gestão de dados, como:
* Adicionar dados [de](/help/using/overview/data-types-collected.md#third-party-data) terceiros aos seus segmentos;
* [Modelagem algoritmica](/help/using/features/algorithmic-models/understanding-models.md);
* Ative seus segmentos para destinos que ainda não são suportados no catálogo [de](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)destinos da plataforma de experiência.

Além disso, seus segmentos da plataforma Experience são compartilhados com outras soluções da Experience Cloud, por meio dos [principais serviços](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

<br> 

Consulte a tabela abaixo para obter uma visão geral dos casos de uso de compartilhamento de audiências:

| **Caso de uso** | **Adobe Experience Platform** | **Audience Manager** | **Principais serviços** |
---------|----------|---------|---------
| **Compartilhamento de Audiências** | <ul><li>Enriqueça os perfis dos clientes com os dados do Gerenciador de Audiências</li><li>Usar os dados do Audiência Manager na segmentação da plataforma Experience</li></ul> | <ul><li>Adicionar dados de terceiros a segmentos</li><li>Modelagem algoritmica</li><li>Ativação para destinos adicionais</li></ul> | Use os segmentos da plataforma da Experience Cloud em outras soluções da Experience Cloud, como o Adobe Público alvo ou o Analytics. |

<br> 

## Segmentos e características do Audiência Manager na Adobe Experience Platform {#aam-segments-traits-in-aep}

Seus traços e segmentos do Audiência Manager aparecem na Plataforma de experiência como **Audiência** no fluxo de trabalho do segmento. Para obter mais informações sobre seus segmentos e características do Audiência Manager na plataforma de experiência, consulte:

* [Visão geral do Serviço de segmentação](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Guia do usuário do Criador de segmentos da plataforma Experience](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Conector do gerenciador de Audiências](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Segmentos da plataforma Adobe Experience no Audiência Manager {#aep-segments-in-aam}

Os segmentos criados na plataforma Experience são exibidos na interface do Audiência Manager como características e segmentos, com as seguintes regras de composição:
* Características: A regra de característica é a ID do segmento da Plataforma de experiência.
* Segmento: O segmento consiste na característica descrita acima.

### Características {#aep-segments-as-aam-traits}

O Audiência Manager cria automaticamente uma pasta de características chamada Características **da plataforma de** experiência no seu armazenamento de características.

![Características do painel da plataforma Experience](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Você pode usar características criadas automaticamente em segmentos ao lado de outras características. Por exemplo, é possível combinar características criadas a partir de segmentos da plataforma de experiência com características de terceiros adquiridas pelo [Audiência Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Para obter um exemplo de uma característica criada automaticamente a partir de um segmento da plataforma de experiência, consulte a captura de tela abaixo:

![Características da plataforma Experience](/help/using/integration/integration-aep/assets/aep-trait.png)


| Número do item | Nome | Descrição |
---------|----------|---------
| 1 | Tipo de característica | As características criadas a partir de segmentos da plataforma de experiência são criadas como características integradas no Audiência Manager. |
| 2 | Fonte de dados | Criado automaticamente. Todas as características e segmentos criados automaticamente a partir de segmentos da plataforma de experiência são armazenados na fonte de dados Compartilhamento **de Audiência da plataforma** Adobe Experience. |
| 3 | Código de integração | O código de integração corresponde à ID do segmento na plataforma da experiência. |
| 4 | Expressão da característica | A expressão característica é `segID = segment ID in Experience Platform`. |
| 5 | Segmentos com esta característica | Um segmento criado automaticamente que usa essa característica como composição. |

<br> 

### Segmentos {#aep-segments-as-aam-segments}

O Audiência Manager cria automaticamente uma pasta de segmento chamada Segmentos **da plataforma de** experiência no armazenamento do segmento.

![Captura de tela do painel](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Para obter um exemplo de um segmento criado automaticamente a partir de um segmento da plataforma de experiência, consulte a captura de tela abaixo:

![Captura de tela do segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Número do item | Nome | Descrição |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | O código de integração corresponde à ID do segmento na plataforma da experiência. |
| 2 | [!UICONTROL Data Source] | Criado automaticamente. Todas as características e segmentos criados automaticamente a partir de segmentos da plataforma de experiência são armazenados na fonte de dados **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indica que os segmentos criados automaticamente seguem a política de mesclagem configurada na plataforma da experiência. |
| 4 | [!UICONTROL Segment Rule] | O segmento consiste na característica descrita na seção [Características](#aep-segments-as-aam-traits). |

## Entenda as diferenças de população do segmento entre o Audiência Manager e a plataforma de experiência

Os números de preenchimento do segmento podem variar entre os segmentos do Gerenciador de Audiências e da Plataforma de experiência. Embora os números de segmentos para audiências semelhantes ou idênticas devam ser próximos, as diferenças nas populações podem ser devidas a:

* Trabalhos de segmentação executam tempos. O Gerenciador de Audiências executa um trabalho de segmentação que atualiza os números na interface uma vez por dia. Esse trabalho raramente se alinha aos trabalhos de segmentação na Experience Platform.
* [As Regras](/help/using/features/profile-merge-rules/merge-rules-overview.md) de mesclagem de Perfis no Gerenciador de Audiências e [Mesclar políticas](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) na plataforma da experiência funcionam de forma diferente, e o gráfico de identidade usado para cada uma varia. Por isso, são esperadas algumas diferenças entre as populações de segmentos.


>[!MORELIKETHIS]
>
>* [Visão geral do Serviço de segmentação](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Guia do usuário do Criador de segmentos da plataforma Experience](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Conector do gerenciador de Audiências](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)


