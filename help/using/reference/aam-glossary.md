---
description: Definições e links para outras leituras.
seo-description: Definições e links para outras leituras.
seo-title: Glossário
solution: Audience Manager
title: Glossário
uuid: 01fc26f5-db9d-4e90-b4c1-27c6a510accc
feature: referência
translation-type: tm+mt
source-git-commit: 348881dd2f880ca50140dbe5935cff138944003e
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 99%

---


# Glossário {#glossary}

Definições e links para outras leituras.

## A-B {#a-b}

**Modelagem algorítmica**

Use [!UICONTROL Algorithmic Modeling] como meio de estender o alcance além do núcleo dos usuários identificados. O recurso ajuda você a descobrir públicos novos e exclusivos por meio da análise de dados automatizada. Gerencie o [!UICONTROL Algorithmic Models] no **[!UICONTROL Audience Data > Models]**.

Consulte [Compreensão dos modelos algorítmicos](../features/algorithmic-models/algo-models-overview.md).

**BAAAM**

[!UICONTROL Bulk Management Tools]. O [!UICONTROL Bulk Management Tools] no [!DNL Audience Manager] é um conjunto de ferramentas do Microsoft Excel que permite criar, modificar ou excluir vários objetos de uma só vez com uma única operação. É possível trabalhar com fontes de dados, sinais derivados, destinos, pastas, segmentos e características. O recurso usa uma planilha do Microsoft Excel com macros que fazem chamadas seguras e autenticadas para as APIs [!DNL Audience Manager].

Consulte [Ferramentas de gerenciamento em massa](../reference/bulk-management-tools/bulk-management-intro.md).

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]. Um arquivo [!UICONTROL CDF] representa um download em massa dos dados coletados pelo [!DNL Audience Manager] e permite que você trabalhe com dados do [!DNL Audience Manager] fora dos limites impostos pela interface do usuário. Um arquivo [!UICONTROL CDF] contém os mesmos dados que uma chamada de evento [!DNL Audience Manager] (`/event`) envia para nossos servidores. Ele inclui dados como IDs de usuário, IDs de característica, IDs de segmento e todos os outros parâmetros capturados por uma chamada de evento.

Consulte [Feeds de dados de clientes](../features/cdf-files.md).

**ID do CRM**

A ID do CRM é a ID pela qual os clientes identificam os usuários em seu próprio sistema de CRM. Em vez da ID do CRM, usamos o termo DPUUID no Audience Manager.

Consulte DPUUID no [Índice de IDs no Audience Manager](../reference/ids-in-aam.md).



**Público-alvo endereçável do cliente**

No [Público-alvo endereçável](/help/using/features/addressable-audiences.md), essa métrica representa dispositivos que:
* Perceberam uma característica com base em regras ou integrada durante a janela de retrospectiva
   **E**
* Têm uma sincronização de ID com o destino escolhido, independentemente do tempo de sincronização.



**Atributos do cliente**

Consulte [Atributos do cliente](https://docs.adobe.com/content/help/pt-BR/core-services/interface/customer-attributes/attributes.html) na documentação do produto [!DNL Experience Cloud Core Services].



**Taxa de correspondência do cliente**

Público-alvo endereçável do cliente ÷ Público-alvo total do cliente expresso como uma %. Consulte [Público-alvo endereçável](/help/using/features/addressable-audiences.md).



**Público-alvo total do cliente**

No [Público-alvo endereçável](/help/using/features/addressable-audiences.md), essa métrica representa uma contagem de dispositivos que perceberam uma característica com base em regras em suas propriedades ou uma característica integrada de seus arquivos offline durante a janela de retrospectiva.



**demdex.net**

Demdex.net é um domínio herdado controlado por [!DNL Adobe]. Ele reflete o nome original de pré-aquisição de [!DNL Audience Manager] ( [!DNL Demdex]). [!DNL Adobe] adquirido [!DNL Demdex] em 2011 e reclassificou a empresa como [!DNL Audience Manager]. Todas as chamadas HTTP para domínios `demdex.net` são enviadas para [!DNL Adobe].

Consulte [Compreensão das chamadas para o domínio Demdex](../reference/demdex-calls.md).



**DAID**

[!UICONTROL Device Advertising IDs] são identificadores de dispositivos exclusivos, usados para identificar um dispositivo móvel. Essas IDs são atribuídas pelo fabricante do dispositivo, não pela Adobe. Oferecemos suporte a IDs de dispositivos iOS e Android no [!DNL Audience Manager].

Consulte o [Índice de IDs no Audience Manager](../reference/ids-in-aam.md).



**Destino**

No [!DNL Audience Manager], um destino é qualquer outro sistema (servidor de anúncios, DSP, rede de anúncios etc.) com o qual você deseja compartilhar dados. O [!UICONTROL Destination Builder] em nossa interface de usuário fornece as ferramentas que permitem criar e gerenciar esses processos de delivery de dados. Os recursos de destino [!DNL Audience Manager] estão localizados em **[!UICONTROL Audience Data > Destinations]**.



**DIL**

A [!UICONTROL Data Integration Library] é uma biblioteca de API usada pelo [!DNL Audience Manager] para coletar dados de interação do usuário. Consulte [API da Biblioteca de integração de dados (DIL)](../dil/dil-overview.md).



**dpm**

[!UICONTROL Data Provider Match]. Informa aos sistemas internos da [!DNL Adobe] que uma chamada do [!DNL Audience Manager] ou do serviço de ID está transmitindo os dados do cliente para sincronização ou solicitando uma ID. Consulte [Compreensão das chamadas para o domínio Demdex](../reference/demdex-calls.md).

## E-F {#e-f}

**Experience Cloud ID (ECID)**

Anteriormente chamada de [!DNL Marketing Cloud] ID (MID ou MCID). A [!DNL Experience Cloud] ID é essencial para o serviço de ID. É um identificador exclusivo e persistente para os visitantes do site. Consulte Cookies e o [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/pt-BR/id-service/using/intro/cookies.html).



**Característica da pasta**

Agrupamento automático de características dentro da taxonomia de pastas. Cada pasta na sua hierarquia cria automaticamente uma característica que pode ser usada para definir segmentos.

Consulte [Características da pasta: Sobre](../features/traits/about-folder-traits.md).



**Limite de frequência**

Limite do número de vezes que um anunciante deseja exibir um anúncio específico para um usuário final. Você pode configurar várias expressões de limite de frequência no [!UICONTROL Segment Builder].

Consulte [Recenticidade e frequência](../features/segments/recency-and-frequency.md).

## G-H {#g-h}

**GAID**

ID de anúncio do Google, a ID de dispositivo exclusiva que o Google atribui a dispositivos de hardware que executam o sistema operacional Android. Consulte o [Índice de IDs no Audience Manager](../reference/ids-in-aam.md).



**GUID**

Acrônimo do Identificador único global. Não usamos o termo GUID no [!DNL Audience Manager]. No nosso caso, o GUID é o [!DNL Audience Manager] UUID.
Consulte o [Índice de IDs no Audience Manager](../reference/ids-in-aam.md).

## I-J {#i-j}

**IDFA**

Identificador para anunciantes, a ID de dispositivo exclusiva que a Apple atribui a seus produtos. Consulte o [Índice de IDs no Audience Manager](../reference/ids-in-aam.md).



**Entrada**

O processo pelo qual você pode enviar dados do público-alvo de outras fontes para o [!DNL Audience Manager]. Consulte [Envio de dados de público-alvo](/help/using/integration/sending-audience-data/send-audience-data.md).



**Código de integração**

Ao trabalhar com a interface do usuário ou a API do [!DNL Audience Manager], você tem a opção de adicionar um código de integração ao criar características, segmentos ou fontes de dados. Os códigos de integração atendem a diferentes finalidades nesses casos:

* [!UICONTROL Traits]: um código de integração é um campo para uma ID, SKU ou outro valor usado por seus processos comerciais internos. Opcional.
* [!UICONTROL Segments]: um código de integração é um campo para uma ID definida pelo usuário ou outras informações específicas da empresa. Opcional.
* [!UICONTROL Data Sources]: os códigos de integração são necessários ao criar fontes de dados entre dispositivos; use o Adobe Experience Platform Identity Service ou trabalhe com [!UICONTROL Profile Merge Rules]. Consulte [Criar uma fonte de dados](../features/manage-datasources.md#create-data-source) para obter mais informações.

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

Consulte [Modelagem algorítmica](../reference/aam-glossary.md#a-b).

## M-N {#m-n}

**MCID**, **MID**

Consulte [Experience Cloud ID](../reference/aam-glossary.md#e-f).

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]. O [!UICONTROL PCS] é um grande banco de dados que roda no Apache Cassandra. Ele armazena dados recebidos para usuários ativos de transferências de servidor para servidor e do [!DNL DCS]. Os dados do [!UICONTROL PCS] consistem em IDs de dispositivo, IDs de perfil autenticadas e suas características associadas.

Consulte [Componentes da coleta de dados](../reference/system-components/components-data-collection.md).



**Link de perfil**

Consulte [Definição das opções de regra de mesclagem de perfis](../features/profile-merge-rules/merge-rule-definitions.md).



**Regras de mesclagem de perfis**

As [!UICONTROL Profile Merge Rules] permitem controlar o tipo de dados que o [!DNL Audience Manager] usa para segmentação.

Consulte [Definição das opções de regra de mesclagem de perfis](../features/profile-merge-rules/merge-rule-definitions.md).

## Q-R {#q-r}

**Realização**

A ação pela qual um visitante do site se qualifica para uma característica. Você pode usar a ferramenta [Visualizador de perfil de visitante](../features/visitor-profile-viewer.md) para obter informações sobre a realização de características por um usuário específico.

## S-T {#s-t}

**Segmento**

Um segmento (ou público-alvo) é um conjunto de usuários que compartilham atributos semelhantes.

Consulte [Segmentos: Finalidade, composição e regras](../features/segments/segments-purpose.md).



**Público-alvo endereçável do segmento**

No [Público-alvo endereçável](/help/using/features/addressable-audiences.md), essa métrica representa o número de usuários que pertenceram ao segmento durante o período de análise do relatório e que têm uma sincronização de ID ativa no site. Os segmentos podem incluir seus próprios dados primários e dados secundários e de terceiros, por meio de características adquiridas no [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).



**População total do segmento**

No [Público-alvo endereçável](/help/using/features/addressable-audiences.md), essa métrica representa uma contagem de todos os dispositivos que eram membros do seu segmento durante o período de análise do relatório.



**Taxa de correspondência do segmento**

Público-alvo endereçável do segmento ÷ População total do segmento expresso como uma %. Consulte [Público-alvo endereçável](/help/using/features/addressable-audiences.md).



**Sinal**

Os sinais são as menores unidades de dados no [!DNL Audience Manager] e são expressos como pares de valores chave.

Consulte [Sinais, características e segmentos](../reference/signal-trait-segment.md).



**Característica**

Uma característica é uma combinação de um ou mais sinais. Consulte [Sinais, características e segmentos](../reference/signal-trait-segment.md).



**População de características**

Consulte [Dados de população de característica e segmento no Criador de segmentos](../features/segments/segment-builder-data.md).

**TTL (Tempo de vida útil)**

O TTL define quantos dias um visitante qualificado permanece em uma característica. O TTL é definido nas características e não em segmentos. Os Visitantes saem de um segmento se não visualizarem uma característica qualificada antes do final do intervalo de TTL. Leia mais na [Explicação de tempo de vida útil de segmento e característica](/help/using/features/traits/segment-ttl-explained.md).



## U-V {#u-v}

**UUID**

[!DNL Audience Manager] ID exclusiva do usuário. Consulte o [Índice de IDs no Audience Manager](../reference/ids-in-aam.md).



**ID de visitante**

O [!DNL Experience Cloud] ID Service (antiga ID de visitante) oferece uma ID persistente e universal que identifica os visitantes em todas as soluções da [!DNL Experience Cloud].

Consulte a documentação do [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/pt-BR/id-service/using/home.html).

## W-X-Y-Z {#w-z}

