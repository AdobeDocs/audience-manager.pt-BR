---
description: Definições e ligações para posterior leitura.
seo-description: Definições e ligações para posterior leitura.
seo-title: Glossário
solution: Audience Manager
title: Glossário
uuid: 01fc26f5-db9d-4e90-b4c1-27c6a510accc
translation-type: tm+mt
source-git-commit: d5a8b763d2d0d1ceebe2252ebd283943dcbc1754

---


# Glossário{#glossary}

Definições e ligações para posterior leitura.

## A-B {#a-b}

**Modelagem algorítmica**

Use [!UICONTROL Algorithmic Modeling] como meio de estender o alcance além do núcleo dos usuários identificados. O recurso ajuda a descobrir públicos novos e exclusivos por meio da análise automatizada de dados. Gerencie [!UICONTROL Algorithmic Models] em **[!UICONTROL Audience Data > Models]**.

Consulte [Como entender os modelos](../features/algorithmic-models/understanding-models.md#understanding-models)algorítmicos.

<br> 

**BAAAM**

[!UICONTROL Bulk Management Tools]. O [!UICONTROL Bulk Management Tools] In [!DNL Audience Manager] é um conjunto de ferramentas baseado no Microsoft Excel que permite criar, modificar ou excluir vários objetos ao mesmo tempo com uma única operação. Você pode trabalhar com fontes de dados, sinais derivados, destinos, pastas, segmentos e características. O recurso usa uma planilha do Microsoft Excel com macros que fazem chamadas seguras e autenticadas para as [!DNL Audience Manager] APIs.

Consulte Ferramentas [de gerenciamento em](../reference/bulk-management-tools/bulk-management-intro.md)massa.

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]. Um [!UICONTROL CDF] arquivo representa um download em massa dos dados coletados pelo e permite que você trabalhe com [!DNL Audience Manager] [!DNL Audience Manager] dados fora dos limites impostos pela interface do usuário. Um [!UICONTROL CDF] arquivo contém os mesmos dados que uma chamada de [!DNL Audience Manager] evento ( `/event`) envia para nossos servidores. Isso inclui dados como IDs de usuário, IDs de característica, IDs de segmento e todos os outros parâmetros capturados por uma chamada de evento.

See [Customer Data Feeds](../features/cdf-files.md).

<br> 

**ID do CRM**

A ID do CRM é a ID pela qual os clientes identificam os usuários em seu próprio sistema CRM. Em vez da ID do CRM, usamos o termo DPUUID no Audience Manager.

Consulte DPUUID no [Índice de IDs no Audience Manager](../reference/ids-in-aam.md).

<br> 

**Público-alvo endereçável do cliente**

No Público-alvo [endereçável](/help/using/features/addressable-audiences.md), essa métrica representa dispositivos que:
* Tenham percebido uma característica baseada em regras ou integrada durante a janela de retrospectiva
   **E**
* Ter uma sincronização de ID com o destino escolhido, independentemente do tempo de sincronização.

<br> 

**Atributos do cliente**

See [Customer Attributes](https://marketing.adobe.com/resources/help/en_US/mcloud/attributes.html) in the [!DNL Experience Cloud Core Services] product documentation.

<br> 

**Taxa de correspondência do cliente**

Público-alvo endereçável do cliente /Público-alvo total do cliente expresso em %. See [Addressable Audience](/help/using/features/addressable-audiences.md).

<br> 

**Público-alvo total do cliente**

No Público-alvo [endereçável](/help/using/features/addressable-audiences.md), essa métrica representa uma contagem de dispositivos que perceberam uma característica baseada em regras nas suas propriedades ou uma característica integrada dos seus arquivos offline durante a janela de retrospectiva.

<br> 

**demdex.net**

Demdex.net é um domínio herdado controlado por [!DNL Adobe]. Ele reflete o nome original [!DNL Audience Manager]da pré-aquisição ( [!DNL Demdex]). [!DNL Adobe] adquirido [!DNL Demdex] em 2011 e reclassificado como [!DNL Audience Manager]. Todas as chamadas HTTP para `demdex.net` domínios são enviadas para [!DNL Adobe].

Consulte [Compreender as chamadas para o domínio Demdex](../reference/demdex-calls.md).

<br> 

**DAID**

[!UICONTROL Device Advertising IDs] são identificadores de dispositivos exclusivos, usados para identificar um dispositivo móvel. Essas IDs são atribuídas pelo fabricante do dispositivo, não pela Adobe. Oferecemos suporte a IDs de dispositivos iOS e Android em [!DNL Audience Manager].

See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Destino**

Em [!DNL Audience Manager], um destino é qualquer outro sistema (servidor de anúncios, DSP, rede de anúncios etc.) com os quais você deseja compartilhar dados. A interface [!UICONTROL Destination Builder] em nossa interface fornece as ferramentas que permitem criar e gerenciar esses processos de entrega de dados. [!DNL Audience Manager] os recursos de destino estão localizados em **[!UICONTROL Audience Data > Destinations]**.

<br> 

**DIL**

O [!UICONTROL Data Integration Library] é uma biblioteca de API usada para [!DNL Audience Manager] coletar dados de interação do usuário. See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**dpm**

[!UICONTROL Data Provider Match]. Ele informa aos [!DNL Adobe] [!DNL Audience Manager] sistemas internos que uma chamada do ou do serviço de ID está transmitindo os dados do cliente para sincronização ou solicitando uma ID. Consulte [Compreender as chamadas para o domínio Demdex](../reference/demdex-calls.md).

## E-F {#e-f}

**Experience Cloud ID (ECID)**

Anteriormente nomeada a [!DNL Marketing Cloud] ID (MID ou MCID). A [!DNL Experience Cloud] ID é central para o serviço de ID. É um identificador exclusivo e persistente para os visitantes do site. See Cookies and the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html).

<br> 

**Traço da pasta**

Agrupamento automático de características dentro da taxonomia de pastas. Cada pasta na sua hierarquia cria automaticamente uma característica que pode ser usada para definir segmentos.

Consulte Características [da pasta: Sobre](../features/traits/about-folder-traits.md).

<br> 

**Limite de frequência**

Um limite de várias vezes que um anunciante deseja exibir um anúncio específico para um usuário final. Você pode configurar várias expressões de limite de frequência em [!UICONTROL Segment Builder].

Consulte [Idade e frequência](../features/segments/recency-and-frequency.md).

## G-H {#g-h}

**GAID**

ID de anúncio do Google, a ID de dispositivo exclusiva que o Google atribui a dispositivos de hardware que executam o sistema operacional Android. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**GUID**

Um acrônimo para Identificador Global Exclusivo. Não usamos o termo GUID em [!DNL Audience Manager]. No nosso caso, o GUID é o [!DNL Audience Manager] UUID.
See [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

## I-J {#i-j}

**IDFA**

Identificador para anunciantes, a ID de dispositivo exclusiva da Apple atribui a seus produtos. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Entrada**

O processo pelo qual você pode enviar dados de público-alvo de outras fontes para [!DNL Audience Manager]. Consulte [Enviar dados](/help/using/integration/sending-audience-data/send-audience-data.md)do público-alvo.

<br> 

**Código de integração**

Ao trabalhar com a [!DNL Audience Manager] interface do usuário ou a API, você tem a opção de adicionar um código de integração ao criar características, segmentos ou fontes de dados. Os códigos de integração servem diferentes finalidades nesses casos:

* [!UICONTROL Traits]: um código de integração é um campo para uma ID, SKU ou outro valor usado por seus processos comerciais internos. Opcional.
* [!UICONTROL Segments]: um código de integração é um campo para uma ID definida pelo usuário ou outras informações específicas da empresa. Opcional.
* [!UICONTROL Data Sources]: os códigos de integração são necessários quando você deseja criar fontes de dados entre dispositivos, usar o serviço da Experience Cloud ID ou trabalhar com [!UICONTROL Profile Merge Rules]. Consulte [Criar uma fonte](../features/manage-datasources.md#create-data-source) de dados para obter mais informações.

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

Consulte Modelagem [algorítmica](../reference/aam-glossary.md#a-b).

## M-N {#m-n}

**MCID**, **MID**

Consulte a [Experience Cloud ID](../reference/aam-glossary.md#e-f).

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]. O [!UICONTROL PCS] é um grande banco de dados, funcionando no Apache Cassandra. Ele armazena dados recebidos para usuários ativos de transferências de servidor para servidor e do [!UICONTROL DCS]. [!UICONTROL PCS] os dados consistem em IDs de dispositivo, IDs de perfil autenticadas e suas características associadas.

Consulte Componentes [da coleta de](../reference/system-components/components-data-collection.md)dados.

<br> 

**Link de perfil**

See [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).

<br> 

**Regras de mesclagem de perfil**

[!UICONTROL Profile Merge Rules] permite controlar o tipo de [!DNL Audience Manager] uso de dados para segmentação.

See [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).

## Q-R {#q-r}

**Realização**

A ação pela qual um visitante em seu site se qualifica para uma característica. Você pode usar a ferramenta [Visitor Profile Viewer](../features/visitor-profile-viewer.md) para obter informações sobre a realização de características por um usuário específico.

## S-T {#s-t}

**Segmento**

Um segmento (ou público-alvo) é um conjunto de usuários que compartilham atributos comuns.

Consulte [Segmentos: Finalidade, composição e regras](../features/segments/segments-purpose.md).

<br> 

**Público-alvo endereçável do segmento**

No Público-alvo [endereçável](/help/using/features/addressable-audiences.md), essa métrica representa o número de usuários que pertenceram ao segmento durante o período de análise do relatório e que têm uma sincronização de ID ativa no site. Os segmentos podem incluir seus próprios dados primários e dados de terceiros e de terceiros, por meio de características adquiridas no [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

<br> 

**População total do segmento**

No Público-alvo [endereçável](/help/using/features/addressable-audiences.md), essa métrica representa uma contagem de todos os dispositivos que eram membros do seu segmento durante o período de análise do relatório.

<br> 

**Taxa de correspondência do segmento**

Público-alvo endereçável do segmento /População total do segmento expressa como %. See [Addressable Audience](/help/using/features/addressable-audiences.md).

<br> 

**Sinal**

Os sinais são as menores unidades de dados em [!DNL Audience Manager] e são expressos como pares de valores chave.

Consulte [Sinais, Características e Segmentos](../reference/signal-trait-segment.md).

<br> 

**Características**

Um traço é uma combinação de um ou mais sinais. Consulte [Sinais, Características e Segmentos](../reference/signal-trait-segment.md).

<br> 

**População de traços**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

**TTL (Time-to-Live)**

O TTL define quantos dias um visitante qualificado permanece em uma característica. O TTL é definido em características e não em segmentos. Os visitantes saem de um segmento se não visualizarem uma característica qualificada antes do final do intervalo TTL. Leia mais no [Segmento e analise o tempo de vida útil](/help/using/features/traits/segment-ttl-explained.md).

<br> 

## U-V {#u-v}

**UUID**

[!DNL Audience Manager] ID exclusiva do usuário. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Visitor ID**

The [!DNL Experience Cloud] ID Service (formerly visitor ID) provides a universal, persistent ID that identifies your visitors across all the solutions in the [!DNL Experience Cloud].

See the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/reference/marketing-cloud-id-service.html) documentation.

## W-X-Y-Z {#w-z}

