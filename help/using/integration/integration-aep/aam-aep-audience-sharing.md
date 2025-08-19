---
description: Saiba como habilitar o compartilhamento de dados e como os públicos-alvo são compartilhados entre o Audience Manager e a Adobe Experience Platform
solution: Audience Manager
title: Compartilhamento de segmentos da Experience Platform com a Audience Manager e outras soluções da Experience Cloud
keywords: Compartilhamento de público do AEP, segmentos do AEP, segmentos da plataforma, compartilhamento de segmentos, compartilhamento de público, segmentos compartilhados, compartilhamento de segmentos do AAM AEP
feature: Experience Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: d21d0574ee0338dbd5e11c60e0d64042182aa18b
workflow-type: tm+mt
source-wordcount: '1799'
ht-degree: 1%

---

# Compartilhamento de segmentos da Experience Platform com a Audience Manager e outras soluções da Experience Cloud

## Visão geral {#overview}

A funcionalidade de compartilhamento de público-alvo entre o Audience Manager e o Adobe Experience Platform permite compartilhar suas características e segmentos do Audience Manager com a Adobe Experience Platform e segmentos do Experience Platform com a Audience Manager.

Você precisa do [[!DNL Audience Manager source connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=pt-BR) e do destino [Experience Cloud Audiences](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html?lang=pt-BR) no Experience Platform para habilitar o compartilhamento de público-alvo entre o Audience Manager e o Adobe Experience Platform.

Você pode usar características e segmentos do Audience Manager no Experience Platform para adicionar dados do Audience Manager aos perfis de clientes e se beneficiar do [serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=pt-BR) da Experience Platform.

No Audience Manager, você pode usar segmentos do Experience Platform para casos de uso da Plataforma de gerenciamento de dados, como:
* Adicione [dados de terceiros](/help/using/overview/data-types-collected.md#third-party-data) aos seus segmentos;
* [Modelagem algorítmica](/help/using/features/algorithmic-models/understanding-models.md);
* Ative seus segmentos para destinos que ainda não têm suporte no [catálogo de destinos](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html?lang=pt-BR) do Experience Platform.

Além disso, seus segmentos do Experience Platform são compartilhados com outras soluções da Experience Cloud, através dos [Serviços principais](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html?lang=pt-BR).

>[!IMPORTANT]
>
> * Você precisa de uma licença do Audience Manager para habilitar os casos de uso da Plataforma de gerenciamento de dados mencionados acima.
> * Você *não precisa* de uma licença do Audience Manager para compartilhar segmentos do Experience Platform com a Adobe Advertising Cloud, o Adobe Target, o Marketo e outras soluções da Experience Cloud, por meio da integração dos Serviços principais.

Consulte a tabela abaixo para obter uma visão geral dos casos de uso de compartilhamento de público-alvo:

| **Caso de uso** | **Adobe Experience Platform** | **Audience Manager** | **Principais serviços** |
|---------|----------|---------|---------|
| **Compartilhamento de público-alvo** | <ul><li>Enriquecer os perfis do cliente com dados do Audience Manager</li><li>Usar dados do Audience Manager na segmentação do Experience Platform</li></ul> | <ul><li>Adicionar dados de terceiros a segmentos</li><li>Modelagem algorítmica</li><li>Ativação para destinos adicionais</li></ul> | Use os segmentos do Experience Platform em outras soluções da Experience Cloud, como Adobe Target, Advertising Cloud ou Marketo. |

{style="table-layout:auto"}

## Segmentos e características do Audience Manager no Adobe Experience Platform {#aam-segments-traits-in-aep}

As seções abaixo descrevem como ativar o compartilhamento de dados do Audience Manager para o Experience Platform e como usar características e segmentos do Audience Manager no Experience Platform.

### Ativar compartilhamento de dados do Audience Manager para o Experience Platform {#enable-aam-to-aep-data}

Para enviar segmentos e características do Audience Manager para o Experience Platform, você deve configurar o conector de origem do Audience Manager no catálogo de origens do Experience Platform. Este é um fluxo de trabalho de autoatendimento que não requer o envolvimento do Atendimento ao cliente da Adobe ou das equipes de engenharia. Para configurar o conector de origem do Audience Manager, leia:

* [origem do Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=pt-BR)
* [Criar uma conexão de origem do Adobe Audience Manager na interface](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=pt-BR)

>[!IMPORTANT]
>
>A Adobe incentiva os clientes a configurar a conexão sem selecionar as opções **[!UICONTROL Select all segments]** e **[!UICONTROL Select all traits]**, conforme mostrado abaixo. A assimilação de populações consideráveis de segmentos do Audience Manager afeta diretamente sua contagem total de perfis ao enviar pela primeira vez um segmento do Audience Manager para a Platform usando a origem do Audience Manager. Isso significa que selecionar todos os segmentos pode levar a uma contagem de perfis que excede seu direito de uso de licença.
>
>![Captura de tela mostrando as opções Selecionar todos os segmentos e Selecionar todas as características desmarcadas no fluxo de trabalho para conexão com o conector de origem do Audience Manager.](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Usar características e segmentos do Audience Manager no Experience Platform {#use-aam-data-in-aep}

Depois de configurar o conector de origem do Audience Manager para importar características e segmentos do Audience Manager, seus dados do Audience Manager serão exibidos no Experience Platform como **Públicos-alvo** no fluxo de trabalho do segmento. Para obter mais informações sobre os segmentos e características do Audience Manager no Experience Platform, leia:

* [Visão geral do Serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=pt-BR#audiences)
* [guia do usuário do Construtor de segmentos do Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=pt-BR#audiences)

## Segmentos do Adobe Experience Platform no Audience Manager {#aep-segments-in-aam}

As seções abaixo descrevem como habilitar o compartilhamento de dados do Experience Platform para o Audience Manager e como usar segmentos do Experience Platform no Audience Manager.

### Ativar compartilhamento de dados do Experience Platform para o Audience Manager {#enable-aep-to-aam-data}

>[!IMPORTANT]
>
> Esta seção descreve a integração de compartilhamento de segmento herdado do Experience Platform com o Audience Manager. Agora é possível configurar essa integração sem o suporte dos representantes do cliente da Adobe. Para obter mais informações, leia a documentação de destino [Experience Cloud Audiences](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html?lang=pt-BR).

>[!NOTE]
>
> Entre em contato com o Gerente de sucesso do cliente da Adobe ou com o Atendimento ao cliente para desbloquear o acesso a essa funcionalidade.

Para enviar segmentos do Experience Platform para a Audience Manager, você deve entrar em contato com o Atendimento ao cliente ou com o Gerente de sucesso do cliente. As equipes de Atendimento ao cliente e Gerenciamento de suporte ao cliente devem registrar um tíquete (consulte o tíquete modelo AAM-52354) para habilitar a conexão da Platform com a Audience Manager.

Certifique-se de compartilhar planos para os dados que vão da Platform para o Audience Manager, para garantir que a conexão esteja configurada corretamente. Por exemplo, se você precisar que os dados regionais sejam compartilhados para segmentos enviados para o Adobe Target, essas informações precisarão ser comunicadas no ticket. A conexão de compartilhamento de dados do Experience Platform com o Audience Manager é configurada dentro de seis dias úteis a partir da data de envio da solicitação.

### Usar segmentos do Experience Platform no Audience Manager {#use-aep-data-in-aam}

Os segmentos criados no Experience Platform aparecem na interface do Audience Manager como sinais, características e segmentos, com as seguintes regras de composição:

* Sinal: Para cada segmento do Experience Platform, você deve ver sinais no formato `segID = segment ID`.
* Característica: a regra de característica é a ID do segmento do Experience Platform.
* Segmento: o segmento consiste na característica descrita acima.

### Sinais {#aep-segments-as-aam-signals}

Selecione **[!UICONTROL Audience Data > Signals > General Online Data]** e pesquise por `SegId` para encontrar sinais provenientes da Experience Platform. É possível usar essa tela para fins de depuração, a fim de verificar se a integração entre o Experience Platform e o Audience Manager foi configurada corretamente.

![Ver sinais do Experience Platform no Audience Manager no painel Sinais](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Características {#aep-segments-as-aam-traits}

O Audience Manager cria automaticamente uma pasta de características chamada **Características do Experience Platform** no armazenamento de características.

![Características do painel do Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

É possível usar características criadas automaticamente em segmentos ao lado de outras características. Por exemplo, você pode misturar características criadas de segmentos do Experience Platform com características de terceiros adquiridas por meio da [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Para obter um exemplo de uma característica criada automaticamente de um segmento do Experience Platform, consulte a captura de tela abaixo:

![Característica do Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Número do item | Nome | Descrição |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | As características criadas a partir de segmentos do Experience Platform são criadas como características integradas no Audience Manager. |
| 2 | [!UICONTROL Data Source] | Criado automaticamente. Todas as características e segmentos criados automaticamente a partir de segmentos do Experience Platform são armazenados na fonte de dados **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | O código de integração corresponde à ID de segmento no Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | A expressão de característica é `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Um segmento criado automaticamente que usa essa característica como composição. |

{style="table-layout:auto"}

### Segmentos {#aep-segments-as-aam-segments}

O Audience Manager cria automaticamente uma pasta de segmento chamada **Segmentos do Experience Platform** no armazenamento do segmento.

![Captura de tela do painel](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Para obter um exemplo de um segmento criado automaticamente a partir de um segmento do Experience Platform, consulte a captura de tela abaixo:

![Captura de tela do segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Número do item | Nome | Descrição |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | O código de integração corresponde à ID de segmento no Experience Platform. |
| 2 | [!UICONTROL Data Source] | Criado automaticamente. Todas as características e segmentos criados automaticamente a partir de segmentos do Experience Platform são armazenados na fonte de dados **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indica que os segmentos criados automaticamente seguem a política de mesclagem configurada no Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | O segmento consiste na característica descrita na [seção de Características](#aep-segments-as-aam-traits). |

{style="table-layout:auto"}

## Suporte ao Controle de exportação de dados do Audience Manager no Experience Platform {#aam-data-export-control-in-aep}

Para impor a conformidade com o uso de dados no Experience Platform, todos os conjuntos de dados e campos aplicáveis devem receber os [rótulos de uso de dados](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=pt-BR) apropriados. Além disso, as [políticas de uso de dados](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=pt-BR) devem ser habilitadas para ações de marketing específicas contra esses rótulos, conforme descrito pela [estrutura DULE (Rotulagem e Imposição de Uso de Dados)](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=pt-BR#dule-framework).

No processo de compartilhamento de público entre o Audience Manager e o Experience Platform, qualquer Controle de exportação de dados aplicado aos segmentos do Audience Manager é traduzido em rótulos equivalentes e ações de marketing reconhecidas pelo Controle de dados da Experience Platform, e vice-versa.

>[!NOTE]
>
>Para obter informações mais gerais sobre Controles da Exportação de Dados, consulte a [documentação sobre Controles da Exportação de Dados](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html?lang=pt-BR).
>
>Este documento fornece uma referência sobre como os Controles de exportação de dados específicos do Audience Manager são mapeados para rótulos de uso de dados e ações de marketing na Platform.

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

## Entender as diferenças de preenchimento de segmentos entre o Audience Manager e o Experience Platform {#aep-aam-segment-population-differences}

Os números de preenchimento do segmento podem variar entre os segmentos do Audience Manager e do Experience Platform. Embora os números de segmentos para públicos semelhantes ou idênticos devam ser próximos, as diferenças nas populações podem ser causadas por fatores listados abaixo.

### Avaliação de segmentos no Experience Platform

O Audience Manager atualiza os números de relatórios na interface uma vez por dia. O momento dessa atualização raramente se alinha ao momento da avaliação do segmento no Experience Platform.

### Diferenças entre as regras de mesclagem de perfis e as políticas de mesclagem

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) no Audience Manager e [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html?lang=pt-BR) no Experience Platform funcionam de forma diferente, e o gráfico de identidade usado para cada um varia. Por esse motivo, são esperadas algumas diferenças entre as populações do segmento.

>[!NOTE]
>
> Ao compartilhar segmentos do Experience Platform com a Audience Manager, a [política de mesclagem padrão](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=pt-BR#default-merge-policy) da sua organização da Platform tem prioridade sobre a [política de mesclagem usada pelo segmento](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=pt-BR#merge-policies) compartilhado com a Audience Manager. Por exemplo, se a política de mesclagem do segmento compartilhado permite a [compilação de ID](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=pt-BR#configure), mas a política de mesclagem padrão da organização não permite, isso pode resultar em diferenças de população entre a Platform e a Audience Manager.

### Composição de segmento no Experience Platform

A integração entre o Adobe Experience Platform e o Audience Manager compartilha vários [namespaces de identidade](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=pt-BR#identity-types) padrão para todos os clientes: ECID, IDFA, GAID, endereços de email com hash (EMAIL_LC_SHA256) e AdCloud ID. Se os segmentos do Experience Platform usarem qualquer um desses itens como identidade principal para os perfis qualificados, os perfis serão contados em Características e segmentos do Audience Manager.

>[!NOTE]
>
> Os públicos-alvo no Experience Platform com identidades destacadas de emails brutos nunca aparecem no Audience Manager.

Por exemplo, se você tivesse um segmento do Experience Platform &quot;Todos os meus clientes&quot; e os perfis qualificados fossem IDs de CRM, ECID, IDFA, endereços de email brutos e com hash, o segmento correspondente no Audience Manager incluiria apenas perfis destacados da ECID, do IDFA e de endereços de email com hash. A população do segmento no Audience Manager seria menor do que a do Experience Platform.

![Compartilhamento de segmentos do Experience Platform para o Audience Manager - composição de segmentos](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Visão geral do Serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=pt-BR#audiences)
>* [guia do usuário do Construtor de segmentos do Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=pt-BR#audiences)
>* [Conector do Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=pt-BR)
