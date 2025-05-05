---
description: Saiba como habilitar o compartilhamento de dados e como os públicos-alvo são compartilhados entre o Audience Manager e o Adobe Experience Platform
solution: Audience Manager
title: compartilhamento de segmento Experience Platform com Audience Manager e outras soluções Experience Cloud
keywords: Compartilhamento de público-alvo da AEP, segmentos da AEP, segmentos da Platform, compartilhamento de segmento, compartilhamento de público-alvo, segmentos compartilhados, compartilhamento de segmento da AEP no AAM
feature: Experience Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: d21d0574ee0338dbd5e11c60e0d64042182aa18b
workflow-type: tm+mt
source-wordcount: '1799'
ht-degree: 1%

---

# compartilhamento de segmento Experience Platform com Audience Manager e outras soluções Experience Cloud

## Visão geral {#overview}

A funcionalidade de compartilhamento de público-alvo entre o Audience Manager e o Adobe Experience Platform permite que você compartilhe suas características e segmentos de Audience Manager com o Adobe Experience Platform e os segmentos de Experience Platform com o Audience Manager.

Você precisa do destino [[!DNL Audience Manager source connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=pt-BR) e do [Experience Cloud Audiences](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html?lang=pt-BR) no Experience Platform para habilitar o compartilhamento de público entre o Audience Manager e o Adobe Experience Platform.

Você pode usar características e segmentos de Audience Manager no Experience Platform para adicionar dados de Audience Manager aos perfis de clientes e se beneficiar do [serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=pt-BR) de Experience Platform.

No Audience Manager, você pode usar segmentos de Experience Platform para casos de uso da Plataforma de gerenciamento de dados, como:
* Adicione [dados de terceiros](/help/using/overview/data-types-collected.md#third-party-data) aos seus segmentos;
* [Modelagem algorítmica](/help/using/features/algorithmic-models/understanding-models.md);
* Ative seus segmentos para destinos que ainda não são suportados no Experience Platform [catálogo de destinos](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html?lang=pt-BR).

Além disso, seus segmentos de Experience Platform são compartilhados com outras soluções de Experience Cloud, através dos [Serviços principais](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html?lang=pt-BR).

>[!IMPORTANT]
>
> * Você precisa de uma licença de Audience Manager para habilitar os casos de uso da Plataforma de gerenciamento de dados mencionados acima.
> * Você *não precisa* de uma licença de Audience Manager para compartilhar segmentos de Experience Platform com a Adobe Advertising Cloud, Adobe Target, Marketo e outras soluções de Experience Cloud, por meio da integração dos Serviços principais.

Consulte a tabela abaixo para obter uma visão geral dos casos de uso de compartilhamento de público-alvo:

| **Caso de uso** | **Adobe Experience Platform** | **Audience Manager** | **Principais serviços** |
|---------|----------|---------|---------|
| **Compartilhamento de público-alvo** | <ul><li>Enriqueça os perfis do cliente com dados de Audience Manager</li><li>Usar dados de Audience Manager na segmentação de Experience Platform</li></ul> | <ul><li>Adicionar dados de terceiros a segmentos</li><li>Modelagem algorítmica</li><li>Ativação para destinos adicionais</li></ul> | Use segmentos de Experience Platform em outras soluções de Experience Cloud, como Adobe Target, Advertising Cloud ou Marketo. |

{style="table-layout:auto"}

## Segmentos e características do Audience Manager no Adobe Experience Platform {#aam-segments-traits-in-aep}

As seções abaixo descrevem como ativar o compartilhamento de dados de Audience Manager para Experience Platform e como usar características e segmentos de Audience Manager no Experience Platform.

### Habilitar compartilhamento de dados do Audience Manager para o Experience Platform {#enable-aam-to-aep-data}

Para enviar segmentos e características de Audience Manager para Experience Platform, você deve configurar o conector de origem de Audience Manager no catálogo de origens de Experience Platform. Esse é um fluxo de trabalho de autoatendimento que não requer o envolvimento de equipes de atendimento ao cliente ou de engenharia do Adobe. Para configurar o conector de origem do Audience Manager, leia:

* [origem do Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=pt-BR)
* [Criar uma conexão de origem do Adobe Audience Manager na interface](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=pt-BR)

>[!IMPORTANT]
>
>O Adobe incentiva os clientes a configurar a conexão sem selecionar as opções **[!UICONTROL Select all segments]** e **[!UICONTROL Select all traits]**, conforme mostrado abaixo. A assimilação de populações consideráveis de segmentos de Audience Manager tem um impacto direto na contagem total de perfis ao enviar pela primeira vez um segmento de Audience Manager para a Platform usando a origem de Audience Manager. Isso significa que selecionar todos os segmentos pode levar a uma contagem de perfis que excede seu direito de uso de licença.
>
>![Captura de tela mostrando as opções Selecionar todos os segmentos e Selecionar todas as características desmarcadas no fluxo de trabalho para conexão com o conector de origem do Audience Manager.](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Usar características e segmentos de Audience Manager no Experience Platform {#use-aam-data-in-aep}

Depois de configurar o conector de origem do Audience Manager para importar características e segmentos do Audience Manager, seus dados de Audience Manager aparecem no Experience Platform como **Públicos-alvo** no fluxo de trabalho do segmento. Para obter mais informações sobre os segmentos de Audience Manager e características no Experience Platform, leia:

* [Visão geral do Serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=pt-BR#audiences)
* [guia do usuário do Construtor de segmentos do Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=pt-BR#audiences)

## Segmentos do Adobe Experience Platform no Audience Manager {#aep-segments-in-aam}

As seções abaixo descrevem como habilitar o compartilhamento de dados de Experience Platform para Audience Manager e como usar segmentos de Experience Platform no Audience Manager.

### Habilitar compartilhamento de dados do Experience Platform para o Audience Manager {#enable-aep-to-aam-data}

>[!IMPORTANT]
>
> Esta seção descreve a integração de compartilhamento de segmento herdado do Experience Platform para o Audience Manager. Agora é possível configurar essa integração sem o suporte dos representantes do cliente do Adobe. Para obter mais informações, leia a documentação de destino [Experience Cloud Audiences](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html?lang=pt-BR).

>[!NOTE]
>
> Entre em contato com o Gerente de sucesso do cliente do Adobe ou com o Atendimento ao cliente para desbloquear o acesso a essa funcionalidade.

Para enviar segmentos do Experience Platform para o Audience Manager, entre em contato com o Atendimento ao cliente ou com o Gerente de sucesso do cliente. As equipes de Atendimento ao cliente e Gerenciamento de suporte ao cliente devem registrar um tíquete (consulte o modelo de tíquete AAM-52354) para habilitar a conexão da Platform com o Audience Manager.

Certifique-se de compartilhar os planos para os dados que vão da plataforma ao Audience Manager, para garantir que a conexão esteja configurada corretamente. Por exemplo, se você precisar que os dados regionais sejam compartilhados para segmentos enviados para o Adobe Target, essas informações precisarão ser comunicadas no ticket. A conexão de compartilhamento de dados do Experience Platform para o Audience Manager é configurada dentro de seis dias úteis a partir da data de envio da solicitação.

### Usar segmentos de Experience Platform no Audience Manager {#use-aep-data-in-aam}

Os segmentos criados no Experience Platform aparecem na interface do Audience Manager como sinais, características e segmentos, com as seguintes regras de composição:

* Sinal: Para cada segmento de Experience Platform, você deve ver sinais no formato `segID = segment ID`.
* Característica: a regra de característica é a ID do segmento Experience Platform.
* Segmento: o segmento consiste na característica descrita acima.

### Sinais {#aep-segments-as-aam-signals}

Selecione **[!UICONTROL Audience Data > Signals > General Online Data]** e pesquise por `SegId` para encontrar sinais provenientes do Experience Platform. Você pode usar essa tela para fins de depuração, para verificar se a integração entre o Experience Platform e o Audience Manager foi configurada corretamente.

![Consulte os sinais de Experience Platform no Audience Manager do painel de Sinais](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Características {#aep-segments-as-aam-traits}

O Audience Manager cria automaticamente uma pasta de características chamada **Experience Platform Características** no armazenamento de características.

![Características do painel de Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

É possível usar características criadas automaticamente em segmentos ao lado de outras características. Por exemplo, você pode misturar características criadas de segmentos de Experience Platform com características de terceiros adquiridas por meio do [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Para obter um exemplo de uma característica criada automaticamente a partir de um segmento de Experience Platform, consulte a captura de tela abaixo:

![Característica do Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Número do item | Nome | Descrição |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | As características criadas a partir de segmentos de Experience Platform são criadas como características integradas no Audience Manager. |
| 2 | [!UICONTROL Data Source] | Criado automaticamente. Todas as características e segmentos criados automaticamente a partir de segmentos de Experience Platform são armazenados na fonte de dados **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | O código de integração corresponde à ID de segmento no Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | A expressão de característica é `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Um segmento criado automaticamente que usa essa característica como composição. |

{style="table-layout:auto"}

### Segmentos {#aep-segments-as-aam-segments}

O Audience Manager cria automaticamente uma pasta de segmentos chamada **Experience Platform Segmentos** no armazenamento de segmentos.

![Captura de tela do painel](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Para obter um exemplo de um segmento criado automaticamente a partir de um segmento Experience Platform, consulte a captura de tela abaixo:

![Captura de tela do segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Número do item | Nome | Descrição |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | O código de integração corresponde à ID de segmento no Experience Platform. |
| 2 | [!UICONTROL Data Source] | Criado automaticamente. Todas as características e segmentos criados automaticamente a partir de segmentos de Experience Platform são armazenados na fonte de dados **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indica que os segmentos criados automaticamente seguem a política de mesclagem configurada no Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | O segmento consiste na característica descrita na [seção de Características](#aep-segments-as-aam-traits). |

{style="table-layout:auto"}

## Suporte ao controle de exportação de dados Audience Manager no Experience Platform {#aam-data-export-control-in-aep}

Para impor a conformidade com o uso de dados no Experience Platform, todos os conjuntos de dados e campos aplicáveis devem receber os [rótulos de uso de dados](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=pt-BR) apropriados. Além disso, as [políticas de uso de dados](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=pt-BR) devem ser habilitadas para ações de marketing específicas contra esses rótulos, conforme descrito pela [estrutura DULE (Rotulagem e Imposição de Uso de Dados)](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=pt-BR#dule-framework).

No processo de compartilhamento de público entre Audience Manager e Experience Platform, os Controles de exportação de dados aplicados aos segmentos Audience Manager são traduzidos em rótulos equivalentes e ações de marketing reconhecidas pela Governança de dados Experience Platform, e vice-versa.

>[!NOTE]
>
>Para obter informações mais gerais sobre Controles da Exportação de Dados, consulte a [documentação sobre Controles da Exportação de Dados](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html?lang=pt-BR).
>
>Este documento fornece uma referência sobre como os Controles de exportação de dados de Audience Manager específicos são mapeados para rótulos de uso de dados e ações de marketing na Platform.

### Controles da exportação de dados para rótulos de uso de dados

A tabela a seguir descreve como os Controles de exportação de dados específicos são mapeados para rótulos de uso de dados reconhecidos:

| Controle da exportação de dados | Rótulo de uso de dados |
| --- | --- |
| Não pode ser usado com informações de identificação pessoal | C3: Os dados não podem ser combinados nem usados com informações diretamente identificáveis |
| Não pode ser usado para direcionamento de anúncios externos | C5: Os dados não podem ser usados para direcionamento de conteúdo ou anúncios entre sites com base em interesses |
| Não pode ser usado para direcionamento de anúncios no local | C6: Os dados não podem ser usados para direcionamento de anúncios no local |
| Não pode ser usado para personalização no site | C7: os dados não podem ser usados para direcionamento de conteúdo no site |

{style="table-layout:auto"}

### Controles da exportação de dados para ações de marketing

A tabela a seguir descreve como Rótulos de exportação de dados específicos são mapeados para ações de marketing reconhecidas:

| Rótulo de exportação de dados | Ação de marketing |
| --- | --- |
| Esse destino pode permitir uma combinação com informações de identificação pessoal (PII) | Combinar com PII |
| Esse destino pode ser usado para direcionamento de anúncios fora do site | Direcionamento entre sites |
| Esse destino pode ser usado para direcionamento de anúncios no local | Advertising no local |
| Esse destino pode ser usado para personalização de anúncios no local | Personalization no local |

{style="table-layout:auto"}

## Entender as diferenças de população de segmentos entre Audience Manager e Experience Platform {#aep-aam-segment-population-differences}

Os números de população do segmento podem variar entre os segmentos Audience Manager e Experience Platform. Embora os números de segmentos para públicos semelhantes ou idênticos devam ser próximos, as diferenças nas populações podem ser causadas por fatores listados abaixo.

### Avaliação de segmento no Experience Platform

O Audience Manager atualiza os números de relatório na interface uma vez por dia. O tempo dessa atualização raramente se alinha ao tempo da avaliação do segmento no Experience Platform.

### Diferenças entre as regras de mesclagem de perfis e as políticas de mesclagem

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) em Audience Manager e [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html?lang=pt-BR) em Experience Platform funcionam de forma diferente, e o gráfico de identidade usado para cada um varia. Por esse motivo, são esperadas algumas diferenças entre as populações do segmento.

>[!NOTE]
>
> Ao compartilhar segmentos do Experience Platform para o Audience Manager, a [política de mesclagem padrão](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=pt-BR#default-merge-policy) da sua organização da Platform tem prioridade sobre a [política de mesclagem usada pelo segmento](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=pt-BR#merge-policies) compartilhado com o Audience Manager. Por exemplo, se a política de mesclagem do segmento compartilhado permite a [compilação de ID](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=pt-BR#configure), mas a política de mesclagem padrão da organização não permite, isso pode resultar em diferenças de população entre a Platform e o Audience Manager.

### Composição do segmento no Experience Platform

A integração entre o Adobe Experience Platform e o Audience Manager compartilha vários [namespaces de identidade](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=pt-BR#identity-types) padrão para todos os clientes: ECID, IDFA, GAID, endereços de email com hash (EMAIL_LC_SHA256) e AdCloud ID. Se os segmentos de Experience Platform usarem qualquer um desses itens como identidade principal para os perfis qualificados, os perfis serão contados em características e segmentos de Audience Manager.

>[!NOTE]
>
> Os públicos-alvo no Experience Platform com identidades destacadas de emails brutos nunca aparecem no Audience Manager.

Por exemplo, se você tivesse um segmento Experience Platform &quot;Todos os meus clientes&quot; e os perfis qualificados fossem IDs de CRM, ECID, IDFA, endereços de email brutos e com hash, o segmento correspondente no Audience Manager incluiria apenas perfis destacados de ECID, IDFA e endereços de email com hash. A população do segmento no Audience Manager seria menor que a do Experience Platform.

![Experience Platform para compartilhamento de segmento Audience Manager - composição de segmento](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Visão geral do Serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=pt-BR#audiences)
>* [guia do usuário do Construtor de segmentos do Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=pt-BR#audiences)
>* [Conector Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=pt-BR)
