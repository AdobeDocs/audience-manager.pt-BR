---
description: Descreve a integração e a conformidade do Audience Manager com as práticas recomendadas geralmente aceitas relacionadas à privacidade do consumidor e aos procedimentos de não participação.
seo-description: Descreve a integração e a conformidade do Audience Manager com as práticas recomendadas geralmente aceitas relacionadas à privacidade do consumidor e aos procedimentos de não participação.
seo-title: Privacidade de dados
solution: Audience Manager
title: Privacidade de dados
uuid: 865 e 7 b 4 e-fee 1-4 fa 4-8035-1595 fc 77 cd 96
translation-type: tm+mt
source-git-commit: e6dcd0a33489ae388df25a95d3ad4841030afe31

---


# Privacidade de dados{#data-privacy}

Descreve a integração e a conformidade do Audience Manager com as práticas recomendadas geralmente aceitas relacionadas à privacidade do consumidor e aos procedimentos de não participação.

## Privacidade de dados {#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## Consumer Privacy Protection {#consumer-privacy-protection}

O Audience Manager reconhece o pacto implícito entre os consumidores e as marcas online com as quais eles interagem. Ambas as partes se beneficiam da troca transparente de elementos de dados anônimos:

* Os consumidores recebem conteúdo personalizado, oferecem ofertas de produtos e experiências de usuário simplificadas.
* As marcas recebem fluxos de receita vitais compatíveis com diversos modelos de negócios online.

Em nosso suporte contínuo a este modelo, o Audience Manager continua compromisso com fornecer transparência e controle para os consumidores, além de atender ou exceder os Princípios autorregulatório da Publicidade comportamental online (OBA).

## Opt-Out Management {#opt-out-management}

A documentação de não participação foi estendida e movida para uma parte separada da nossa documentação. See [Opt-out Management](../../overview/data-security-and-privacy/opt-out-management.md).

<!-- 

<p>  </p>
<table id="table_A1FF33B328BD451FAFF6C6B8422F928B"> 
 <tgroup cols="2">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="2.74*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Opt-Out For </th> 
    <th colname="col2" class="entry"> Description </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
    <td colname="col2"> <p>The <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices page</a> provides 1-click features that let you control and opt-out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> business customer section</a> of the Privacy Choices page. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Browsers that do not support third-party cookies </p> </td> 
    <td colname="col2"> <p>See <a href="../../features/declared-ids.md#declared-id-targeting"> Declared ID Targeting</a>. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Mobile devices </p> </td> 
    <td colname="col2"> <p>See the opt-out and privacy settings for: </p> <p> 
      <ul id="ul_86EFAB879215403D937B5148C26A41D9"> 
       <li id="li_C0B544E8F4FE473B94A5436D3A60BDB1"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android devices</a> </li> 
       <li id="li_26C787BAB729499A9FEDF055E9AB0637"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS devices</a> </li> 
      </ul> </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->

## Collecting IP Addresses and IP Address Obfuscation {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

O endereço IP de um visitante do site do cliente é transmitido para um DCP (Data Processing Center, centro de processamento de dados) da Adobe onde o endereço IP pode ser armazenado. Dependendo da configuração de rede do visitante, o endereço IP pode não representar necessariamente o endereço IP do computador do visitante. Por exemplo, o endereço IP pode ser o endereço IP externo de um firewall NAT (Network Address Translation, tradução de endereço de rede), proxy HTTP ou gateway de Internet.

**Metodologia de ofuscação de IP:** Seguindo os princípios de «Privacidade por design», o Adobe Audience Manager permite que os clientes ativem a ofuscação de IP da interface do usuário, seja globalmente por todas as regiões geográficas ou para países específicos. Quando você ativa essa configuração, o último octeto (a última parte) do endereço IP é descartado imediatamente quando o endereço IP é assimilado no Audience Manager. O Audience Manager descarta essa parte do endereço IP antes do processamento (incluindo antes de qualquer pesquisa geográfica opcional ou registro do endereço IP). Por exemplo:

* Antes: `255.255.255.255`
* Depois: `255.255.255.0`

>[!NOTE]
>
>See [IP Address Obfuscation](/help/using/features/administration/ip-obfuscation.md) to learn how to enable IP address obfuscation in the Audience Manager UI.

**Segmentação geográfica:** Se você ativar a ofuscação de endereços IP, os octetos restantes do endereço IP ainda poderão ser usados para segmentação geográfica e relatórios no Audience Manager. Se você não ativar a ofuscação de endereços IP, o Audience Manager usará o endereço IP completo. Você pode usar o recurso Segmentação geográfica, que permite identificar um local IP por área geográfica em qualquer um dos casos, mas com uma pequena perda de precisão quando a ofuscação de IP está sendo usada. A obtenção de informações do nível da cidade provavelmente será muito afeta pela ofuscação do endereço IP. A obtenção de informações de nível de região e país deve ser ligeiramente afetada. Os dados de segmentação geográfica são granulares somente no nível da cidade ou no nível do código postal, e não no nível individual. Read more about [geo-targeting](/help/using/features/traits/trait-geotarget-keys.md) and how to set up traits with geographic variables.

## Conceitos relacionados {#related-concepts}

* [Gerenciamento de não participação](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [Perguntas frequentes sobre privacidade e retenção de dados](/help/using/faq/faq-privacy.md)