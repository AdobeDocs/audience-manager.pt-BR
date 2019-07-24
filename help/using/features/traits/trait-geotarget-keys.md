---
description: Descreve os pares de valores de plataforma em nível de plataforma comuns que podem ser usados para direcionar usuários com variáveis geográficas em todas as propriedades na conta do Audience Manager.
seo-description: Descreve os pares de valores de plataforma em nível de plataforma comuns que podem ser usados para direcionar usuários com variáveis geográficas em todas as propriedades na conta do Audience Manager.
seo-title: Geolocalização com chaves de nível de plataforma
solution: Audience Manager
title: Geolocalização com chaves de nível de plataforma
uuid: c 7 e 4 cbfe-e 564-404 e-a 565-bbe 5 fd 2 fb 519
translation-type: tm+mt
source-git-commit: c5c57423bcba8d4b3974a04c46dc7c7afc7484a0

---


# Geotargeting With Platform-level Keys {#geotargeting-with-platform-level-keys}

Descreve os pares de valores de plataforma em nível de plataforma comuns que podem ser usados para direcionar usuários com variáveis geográficas em todas as propriedades na conta do Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Purpose of Platform-level Variables {#platform-variables}

Platform-level variables let you take data passed in from a particular site and make it available for targeting across all the properties in your [!DNL Audience Manager] account. These variables are formed by [key-value pairs](../../reference/key-value-pairs-explained.md) with the key prefixed by `d_` as shown below.

## Adding Values to Platform Level Keys {#adding-values}

Para algumas chaves em nível de plataforma, você pode especificar o valor por si próprio. With others, the keys are associated with corresponding [!DNL IP] addresses passed in on an event call. In either case, you still need to specify the value when building traits in [!UICONTROL Trait Builder].

## User Defined Platform-Level Keys {#user-defined-keys}

Especifique o valor ao criar características com estes pares chave-valor:

| Chave | Para segmentação |
|---|---|
| `d_zx` | ZIP code (e.g., `d_zx=10022`). |

## Platform Level Keys Defined by IP Address {#keys-ip-address}

We work with [Digital Envoy](https://www.digitalenvoy.com/) to obtain and update the demographic and geographic data for the keys below. The values for these keys are determined by matching [!DNL IP] addresses to corresponding geographic and demographic data. However, you'll still have to enter the value parameter when creating the key-value pair in [!UICONTROL Trait Builder].

| Chave | Para segmentação |
|--- |--- |
| d_ area_ code | [Códigos de área da América do Norte](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes). Por exemplo: <ul><li>**Característica**: d_ area_ code = 801</li><li>**Nome da característica**: Utah</li></ul> |
| d_ city | Cidades e cidades. Download the [cities list](assets/d_city.txt).  Por exemplo: <ul><li>Característica: d_ city = bonn</li><li>Nome da característica: Bona</li></ul> **Dica**: Você pode usar `d_city` em conjunto `d_country` para garantir que não esteja direcionando duas cidades com o mesmo nome em países diferentes. You can be even more specific in your targeting by using `d_postal_code`. |
| d_ country | Os valores correspondem aos códigos de país ISO. For a searchable list of codes, see the [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home). <br>A definição de metas para o Reino Unido é o único caso especial que não obedece à ISO 3166. Você deve usar "UK" em vez de "GB" para segmentação no Reino Unido. Para definir as antilhas holandesas, o código «AN» foi descontinuado desde 2010. A área foi dissolvida em cinco unidades territoriais separadas. A implicação é que para segmentação nas Antilhas holandesas, você não deve usar "AN", mas uma combinação dos códigos de país para "CW," "SX," e "BQ". For example:  <br>  Trait:  d_country=CZ  <br>  Trait Name: Czech Republic <br>  Trait:  d_country=UK <br>  Trait Name: United Kingdom  <br>  Trait:  d_country=CW OR d_country=SX OR d_country=BQ  <br>  Trait Name: Netherlands Antilles |
| d_ dma_ code | Área metropolitana de códigos DMA. Download the [DMA region list](assets/DMAregions.csv) (.csv format).  Por exemplo: <ul><li>Característica: d_ dma_ code = 807</li><li>Nome da característica: São Francisco</li></ul> |
| d_ lat | Latitude (por exemplo, d_ lat = 40.75). Download the [latitudes list](assets/d_lat.txt). |
| d_ long | Longitude (por exemplo, d_ long = 73.98). Download the [longitudes list](assets/d_long.txt). |
| d_ postal_ code | Códigos ZIP (excluir o código extended 4 estendido). Download the  [postal codes list](assets/d_postal_code.txt).  Por exemplo: <ul><li>Característica: d_ postal_ code = 84004 </li><li>Nome da característica: Alpalp</li></ul> |
| d_ state | Abreviação de 2 caracteres para um estado dos EUA. Download the [states codes list](assets/d_state.txt).  Por exemplo: <ul><li>Característica: d_ state = NY </li><li>Nome da característica: Nova York</li></ul>d_ state contém valores repetidos para diferentes estados em diferentes países. Por exemplo, d_ state = = "ativado" corresponde a vários estados: Ontario (no Canadá), Ondo (na Nigéria), Oshana (na Namíbia). Recomendamos contornar esse sinal com outras pessoas, como d_ country, para direcionamento geográfico mais específico. |
| d_ region | IDs alfanuméricas regionais. Download the [region list](assets/Country_RegionCodes_City.csv).  Em seguida, você pode usar essa lista para corresponder IDs de região a nomes de região. |
| d_ isp | ISP/organização. Download the [ISP List](assets/d_isp.txt). |

The list of [all location-based signals](assets/all.csv) comprises all the signals above, in the following order: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORE_ LIKE_ THIS]
>
>* [Requisitos de prefixo para variáveis principais](../../features/traits/trait-variable-prefixes.md)

