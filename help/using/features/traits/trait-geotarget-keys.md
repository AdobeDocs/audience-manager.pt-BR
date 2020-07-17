---
description: Descreve os pares de valores principais comuns de nível de plataforma que você pode usar para usuários públicos alvos com variáveis geográficas em todas as propriedades na sua conta do Audience Manager.
seo-description: Descreve os pares de valores principais comuns de nível de plataforma que você pode usar para usuários públicos alvos com variáveis geográficas em todas as propriedades na sua conta do Audience Manager.
seo-title: Geolocalização com chaves de nível de plataforma
solution: Audience Manager
title: Geolocalização com chaves de nível de plataforma
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 4%

---


# Geolocalização com chaves de nível de plataforma {#geotargeting-with-platform-level-keys}

Descreve os pares de valores principais comuns de nível de plataforma que você pode usar para usuários públicos alvos com variáveis geográficas em todas as propriedades na sua conta do Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Objetivo das variáveis de nível Platform {#platform-variables}

As variáveis de nível Platform permitem que você capture os dados enviados de um site específico e os disponibilize para definição de metas em todas as propriedades da sua [!DNL Audience Manager] conta. Essas variáveis são formadas por pares [de valor](../../reference/key-value-pairs-explained.md) chave com o prefixo key `d_` , conforme mostrado abaixo.

## Adicionando valores às chaves de nível Platform {#adding-values}

Para algumas chaves de nível de plataforma, você mesmo pode especificar o valor. Com outras, as chaves estão associadas aos [!DNL IP] endereços correspondentes enviados em uma chamada de evento. Em ambos os casos, ainda é necessário especificar o valor ao criar características em [!UICONTROL Trait Builder].

## Teclas de nível Platform definidas pelo usuário {#user-defined-keys}

Você especifica o valor ao criar características com esses pares de valores chave:

| Chave | Para segmentação |
|---|---|
| `d_zx` | CEP (por exemplo, `d_zx=10022`). |

## Teclas de nível Platform definidas pelo endereço IP {#keys-ip-address}

Trabalhamos com a [Digital Envoy](https://www.digitalenvoy.com/) para obter e atualizar os dados demográficos e geográficos das chaves abaixo. Os valores para essas chaves são determinados pela correspondência de [!DNL IP] endereços aos dados geográficos e demográficos correspondentes. No entanto, você ainda precisará digitar o parâmetro value ao criar o par key-value em [!UICONTROL Trait Builder].

| Chave | Para segmentação |
|--- |--- |
| d_area_code | [Códigos](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes)de área da América do Norte.  Por exemplo: <ul><li>**Características**:  d_area_code=801</li><li>**Nome** da característica: Utah</li></ul> |
| d_city | Cidades e cidades. Baixe a lista [das](assets/d_city.txt)cidades.  Por exemplo: <ul><li>Características:  d_city=bonn</li><li>Nome da característica: Bona</li></ul> **Dica**: Você pode usar `d_city` junto com `d_country` para ter certeza de que não está mirando duas cidades com o mesmo nome em diferentes países. Você pode ser ainda mais específico na definição de metas usando `d_postal_code`. |
| d_country | Os valores correspondem aos códigos ISO do país. Para obter uma lista pesquisável de códigos, consulte o Platform [de navegação on-line](https://www.iso.org/obp/ui/#home)ISO. <br>  A definição de metas para o Reino Unido é o único caso especial que não obedece à norma ISO 3166. Você deve usar &quot;UK&quot; em vez de &quot;GB&quot; para definição de metas no Reino Unido.  Para o público alvo das Antilhas Neerlandesas, o código &quot;AN&quot; está obsoleto desde 2010. A área foi dissolvida em cinco unidades territoriais distintas. A implicação é que para definir metas nas Antilhas Holandesas, você não deve usar &quot;AN&quot;, mas uma combinação dos códigos de país para &quot;CW&quot;, &quot;SX&quot; e &quot;BQ&quot;.  Por exemplo:  <br>  Características:  d_country=CZ <br>Nome da característica: República Checa <br>Características:  d_country=UK Nome da característica <br>: Reino Unido <br>Características:  d_country=CW OU d_country=SX OU d_country=BQ Nome <br>da característica: Antilhas Holandesas |
| d_dma_code | Códigos DMA da área metropolitana. Baixe a lista [da região](assets/DMAregions.csv) DMA (formato .csv).  Por exemplo: <ul><li>Características:  d_dma_code=807</li><li>Nome da característica: São Francisco</li></ul> |
| d_lat | Latitude (por exemplo, d_lat=40.75). Baixe a lista [das](assets/d_lat.txt)latitudes. |
| d_long | Longitude (por exemplo, d_long=73.98). Baixe a lista [longitudes](assets/d_long.txt). |
| d_postal_code | CEP (excluir o código estendido +4). Baixe a lista [de códigos](assets/d_postal_code.txt)postais.  Por exemplo: <ul><li>Características:  d_postal_code=84004 </li><li>Nome da característica: Alpino</li></ul> |
| d_state | Abreviação de 2 caracteres para um estado dos EUA. Baixe a lista [de códigos de](assets/d_state.txt)estados.  Por exemplo: <ul><li>Características:  d_state=NY </li><li>Nome da característica: Nova York</li></ul>d_state contém valores repetidos para diferentes estados em diferentes países. Por exemplo, d_state == &quot;on&quot; corresponde a vários estados: Ontário (no Canadá), Ondo (na Nigéria), Oshana (na Namíbia). Recomendamos unir esse sinal a outras pessoas, como d_country, para obter uma geolocalização mais específica. |
| d_region | IDs alfanuméricas regionais. Baixe a lista [da](assets/Country_RegionCodes_City.csv)região.  Em seguida, você pode usar essa lista para corresponder as IDs de região aos nomes de região. |
| d_isp | ISP/organização. Baixe a Lista [do](assets/d_isp.txt)ISP. |

A lista de [todos os sinais](assets/all.txt) baseados na localização inclui todos os sinais acima, na seguinte ordem: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Requisitos de prefixo para variáveis-chave](../../features/traits/trait-variable-prefixes.md)

