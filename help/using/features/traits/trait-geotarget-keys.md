---
description: Descreve os pares de valores-chave comuns no nível da plataforma que podem ser usados para direcionar usuários com variáveis geográficas em todas as propriedades da sua conta do Audience Manager.
seo-description: Descreve os pares de valores-chave comuns no nível da plataforma que podem ser usados para direcionar usuários com variáveis geográficas em todas as propriedades da sua conta do Audience Manager.
seo-title: Geolocalização com chaves de nível de plataforma
solution: Audience Manager
title: Geolocalização com chaves de nível de plataforma
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: 'Características '
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 4%

---

# Geolocalização com chaves de nível de plataforma {#geotargeting-with-platform-level-keys}

Descreve os pares de valores-chave comuns no nível da plataforma que podem ser usados para direcionar usuários com variáveis geográficas em todas as propriedades da sua conta do Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Propósito das variáveis no nível da plataforma {#platform-variables}

As variáveis de nível de plataforma permitem que você pegue os dados transmitidos de um site específico e os disponibilize para definição de metas em todas as propriedades da sua conta [!DNL Audience Manager]. Essas variáveis são formadas por [pares de valores chave](../../reference/key-value-pairs-explained.md) com a chave prefixada por `d_`, conforme mostrado abaixo.

## Adicionar valores às chaves de nível de plataforma {#adding-values}

Para algumas chaves de nível de plataforma, você pode especificar o valor por conta própria. Com outras, as chaves são associadas aos endereços [!DNL IP] correspondentes passados em uma chamada de evento. Em ambos os casos, ainda é necessário especificar o valor ao criar características em [!UICONTROL Trait Builder].

## Chaves de nível de plataforma definidas pelo usuário {#user-defined-keys}

Você especifica o valor ao criar características com esses pares de valores chave:

| Chave | Para segmentação |
|---|---|
| `d_zx` | CEP (por exemplo, `d_zx=10022`). |

## Chaves de nível de plataforma definidas pelo endereço IP {#keys-ip-address}

Trabalhamos com [Digital Envoy](https://www.digitalenvoy.com/) para obter e atualizar os dados demográficos e geográficos das chaves abaixo. Os valores dessas chaves são determinados pela correspondência de [!DNL IP] endereços aos dados geográficos e demográficos correspondentes. No entanto, você ainda precisará inserir o parâmetro value ao criar o par chave-valor em [!UICONTROL Trait Builder].

| Chave | Para segmentação |
|--- |--- |
| d_area_code | [Códigos](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes) de área da América do Norte.  Por exemplo: <ul><li>**Característica**: d_area_code=801</li><li>**Nome** da característica: Utah</li></ul> |
| d_city | Cidades e cidades. Baixe a lista [cidades](assets/d_city.txt).  Por exemplo: <ul><li>Característica:  d_city=bonn</li><li>Nome da característica: Bona</li></ul> **Dica**: Você pode usar  `d_city` junto com  `d_country` o para ter certeza de que não está direcionando duas cidades com o mesmo nome em diferentes países. Você pode ser ainda mais específico em seu direcionamento usando `d_postal_code`. |
| d_country | Os valores correspondem aos códigos ISO de país. Para obter uma lista pesquisável de códigos, consulte a [Plataforma de Navegação Online ISO](https://www.iso.org/obp/ui/#home). <br>  A definição de metas para o Reino Unido é o único caso especial que não obedece à norma ISO 3166. Você deve usar &quot;UK&quot; em vez de &quot;GB&quot; para direcionamento no Reino Unido.  Para selecionar as Antilhas Holandesas, o código &quot;AN&quot; está obsoleto desde 2010. A área foi dissolvida em cinco unidades territoriais distintas. A implicação é que para definir metas nas Antilhas Holandesas, você não deve usar &quot;AN&quot;, mas uma combinação dos códigos de país para &quot;CW&quot;, &quot;SX&quot; e &quot;BQ&quot;.  Por exemplo:  <br>  Característica:  d_country=CZ <br>  Nome da característica: República Tcheca <br>  Característica:  d_country=UK <br>  Nome da característica: Reino Unido <br>  Característica:  d_country=CW OU d_country=SX OU d_country=BQ <br>  Nome da característica: Antilhas Holandesas |
| d_dma_code | Códigos de DMA da área metropolitana. Baixe a lista [DMA region](assets/DMAregions.csv) (formato .csv).  Por exemplo: <ul><li>Característica:  d_dma_code=807</li><li>Nome da característica: São Francisco</li></ul> |
| d_lat | Latitude (por exemplo, d_lat=40.75). Baixe a lista [latitudes](assets/d_lat.txt). |
| d_long | Longitude (por exemplo, d_long=73.98). Baixe a lista [longitudes](assets/d_long.txt). |
| d_postal_code | CEPs (excluir o código estendido +4). Baixe a lista [códigos postais](assets/d_postal_code.txt).  Por exemplo: <ul><li>Característica:  d_postal_code=84004 </li><li>Nome da característica: Alpina</li></ul> |
| d_state | Abreviação de 2 caracteres para um estado dos EUA. Baixe a lista de códigos [states](assets/d_state.txt).  Por exemplo: <ul><li>Característica:  d_state=NY </li><li>Nome da característica: Nova York</li></ul>d_state contém valores repetidos para estados diferentes em países diferentes. Por exemplo, d_state == &quot;on&quot; corresponde a vários estados: Ontário (no Canadá), Ondo (na Nigéria), Oshana (na Namíbia). Recomendamos associar esse sinal a outros, como d_country, para obter geolocalização mais específica. |
| d_region | IDs alfanuméricas regionais. Baixe a lista [region](assets/Country_RegionCodes_City.csv).  Em seguida, é possível usar essa lista para corresponder as IDs de região aos nomes de região. |
| d_isp | ISP/organização. Baixe a [Lista ISP](assets/d_isp.txt). |

A lista de [todos os sinais baseados em localização](assets/all.txt) inclui todos os sinais acima, na seguinte ordem: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Requisitos de prefixo para variáveis-chave](../../features/traits/trait-variable-prefixes.md)

