---
description: Descreve os pares de valores principais comuns de nível de plataforma que você pode usar para direcionar usuários com variáveis geográficas em todas as propriedades na sua conta do Audience Manager.
seo-description: Descreve os pares de valores principais comuns de nível de plataforma que você pode usar para direcionar usuários com variáveis geográficas em todas as propriedades na sua conta do Audience Manager.
seo-title: Geolocalização Com Chaves De Nível De Plataforma
solution: Audience Manager
title: Geolocalização Com Chaves De Nível De Plataforma
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Geotargeting With Platform-level Keys {#geotargeting-with-platform-level-keys}

Descreve os pares de valores principais comuns de nível de plataforma que você pode usar para direcionar usuários com variáveis geográficas em todas as propriedades na sua conta do Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Objetivo das variáveis de nível de plataforma {#platform-variables}

As variáveis de nível de plataforma permitem que você capture os dados enviados de um site específico e os disponibilize para definição de metas em todas as propriedades da sua [!DNL Audience Manager] conta. Essas variáveis são formadas por pares [de valor](../../reference/key-value-pairs-explained.md) chave com o prefixo key `d_` , conforme mostrado abaixo.

## Adicionando valores às chaves de nível da plataforma {#adding-values}

Para algumas chaves de nível de plataforma, você mesmo pode especificar o valor. Com outras, as chaves estão associadas aos [!DNL IP] endereços correspondentes enviados em uma chamada de evento. Em ambos os casos, ainda é necessário especificar o valor ao criar características em [!UICONTROL Trait Builder].

## Teclas de nível de plataforma definidas pelo usuário {#user-defined-keys}

Especifique o valor ao criar características com esses pares de valores chave:

| Chave | Para segmentação |
|---|---|
| `d_zx` | CEP (por exemplo, `d_zx=10022`). |

## Chaves de nível de plataforma definidas pelo endereço IP {#keys-ip-address}

Trabalhamos com a [Digital Envoy](https://www.digitalenvoy.com/) para obter e atualizar os dados demográficos e geográficos das chaves abaixo. Os valores para essas chaves são determinados pela correspondência de [!DNL IP] endereços aos dados geográficos e demográficos correspondentes. No entanto, você ainda precisará digitar o parâmetro value ao criar o par key-value em [!UICONTROL Trait Builder].

| Chave | Para segmentação |
|--- |--- |
| d_area_code | [Códigos](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes)de área da América do Norte.  Por exemplo: <ul><li>**Características**:  d_area_code=801</li><li>**Nome** da característica: Utah</li></ul> |
| d_city | Cidades e cidades. Baixe a lista [de](assets/d_city.txt)cidades.  Por exemplo: <ul><li>Características:  d_city=bonn</li><li>Nome da característica: Bona</li></ul> **Dica**: Você pode usar `d_city` junto com `d_country` para ter certeza de que não está mirando duas cidades com o mesmo nome em diferentes países. Você pode ser ainda mais específico na definição de metas usando `d_postal_code`. |
| d_country | Os valores correspondem aos códigos ISO do país. Para obter uma lista pesquisável de códigos, consulte a Plataforma [de navegação online](https://www.iso.org/obp/ui/#home)ISO. <br>  A definição de metas para o Reino Unido é o único caso especial que não obedece à norma ISO 3166. Você deve usar "UK" em vez de "GB" para definição de metas no Reino Unido.  Para definir como meta as Antilhas Neerlandesas, o código "AN" está obsoleto desde 2010. A área foi dissolvida em cinco unidades territoriais distintas. A implicação é que para definir metas nas Antilhas Holandesas, você não deve usar "AN", mas uma combinação dos códigos de país para "CW", "SX" e "BQ".   Por exemplo:  <br>Características:  d_country=CZ <br>Nome da característica: República Checa <br>Características:  d_country=UK Nome da característica <br>: Reino Unido <br>Características:  d_country=CW OU d_country=SX OU d_country=BQ Nome <br>da característica: Antilhas Holandesas |
| d_dma_code | Códigos DMA da área metropolitana. Baixe a lista [da região](assets/DMAregions.csv) DMA (formato .csv).  Por exemplo: <ul><li>Características:  d_dma_code=807</li><li>Nome da característica: São Francisco</li></ul> |
| d_lat | Latitude (por exemplo, d_lat=40.75). Baixe a lista de [latitudes](assets/d_lat.txt). |
| d_long | Longitude (por exemplo, d_long=73.98). Baixe a lista [de](assets/d_long.txt)longitudes. |
| d_postal_code | CEP (excluir o código estendido +4). Baixe a lista [de códigos](assets/d_postal_code.txt)postais.  Por exemplo: <ul><li>Características:  d_postal_code=84004 </li><li>Nome da característica: Alpino</li></ul> |
| d_state | Abreviação de 2 caracteres para um estado dos EUA. Baixe a lista [de códigos de](assets/d_state.txt)estados.  Por exemplo: <ul><li>Características:  d_state=NY </li><li>Nome da característica: Nova York</li></ul>d_state contém valores repetidos para diferentes estados em diferentes países. Por exemplo, d_state == "on" corresponde a vários estados: Ontário (no Canadá), Ondo (na Nigéria), Oshana (na Namíbia). Recomendamos unir esse sinal a outras pessoas, como d_country, para obter uma geolocalização mais específica. |
| d_region | IDs alfanuméricas regionais. Baixe a lista [de](assets/Country_RegionCodes_City.csv)regiões.  Em seguida, você pode usar essa lista para corresponder as IDs de região aos nomes de região. |
| d_isp | ISP/organização. Baixe a lista [](assets/d_isp.txt)ISP. |

A lista de [todos os sinais](assets/all.csv) baseados na localização inclui todos os sinais acima, na seguinte ordem: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Requisitos de prefixo para variáveis-chave](../../features/traits/trait-variable-prefixes.md)

