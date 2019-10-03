---
description: Descreve a integração e a conformidade do Audience Manager com as práticas recomendadas geralmente aceitas relacionadas à privacidade do consumidor e aos procedimentos de recusa.
seo-description: Descreve a integração e a conformidade do Audience Manager com as práticas recomendadas geralmente aceitas relacionadas à privacidade do consumidor e aos procedimentos de recusa.
seo-title: Privacidade de dados
solution: Audience Manager
title: Privacidade de dados
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: 0eb6a6f67d87377a044b18118fac0185219b0347

---


# Privacidade de dados{#data-privacy}

Descreve a integração e a conformidade do Audience Manager com as práticas recomendadas geralmente aceitas relacionadas à privacidade do consumidor e aos procedimentos de recusa.

## Privacidade de dados {#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## Proteção da privacidade do consumidor {#consumer-privacy-protection}

O Audience Manager reconhece o pacto implícito entre os consumidores e as marcas online com as quais eles interagem. Ambas as partes beneficiam da troca transparente de elementos de dados anônimos:

* Os consumidores recebem conteúdo personalizado, ofertas de produtos com desconto e experiências otimizadas do usuário.
* As marcas recebem fluxos vitais de receita suportando vários modelos de negócios online.

No nosso apoio contínuo a este modelo, o Audience Manager continua empenhado em fornecer transparência e controle aos consumidores e em cumprir ou exceder os Princípios autorregulatórios da OBA (Online Behavioral Advertising).

## Gerenciamento de não participação {#opt-out-management}

A documentação de opção de não participação foi estendida e movida para uma parte separada da nossa documentação. Consulte Gerenciamento [de](../../overview/data-security-and-privacy/opt-out-management.md)não participação.

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

## Coletando Endereços IP e Ofuscação de Endereço IP {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**** Metodologia de ofuscação de IP: Seguindo os princípios de "Privacidade por design", o Adobe Audience Manager permite que os clientes habilitem a [!DNL IP] ofuscação da interface do usuário, globalmente em todas as regiões geográficas ou para países específicos. Quando você habilita essa configuração, o último octeto (a última parte) do [!DNL IP] endereço é imediatamente descartado quando o [!DNL IP] endereço é ingerido no Audience Manager. O Audience Manager descarta essa parte do [!DNL IP] endereço antes do processamento (incluindo antes de qualquer pesquisa geográfica ou registro opcional do [!DNL IP] endereço). Por exemplo:

* Antes: `255.255.255.255`
* Depois: `255.255.255.0`

>[!NOTE]
>
>Consulte Ofuscação [de endereço](/help/using/features/administration/ip-obfuscation.md) IP para saber como ativar a ofuscação de [!DNL IP] endereço na interface do usuário do Audience Manager.

Assista ao vídeo abaixo para entender como a ofuscação de [!DNL IP] endereços funciona no Audience Manager.

[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=por_br)

**** Segmentação geográfica: Se você ativar a ofuscação de [!DNL IP] endereço, os octeto restantes do [!DNL IP] endereço ainda poderão ser usados para segmentação geográfica e relatórios no Audience Manager. Se você não ativar a ofuscação de [!DNL IP] endereço, o Audience Manager usará o [!DNL IP] endereço completo. Você pode usar o recurso Segmentação geográfica que permite identificar um [!DNL IP] local por área geográfica em ambos os casos, mas com uma pequena perda de precisão quando a [!DNL IP] ofuscação está sendo usada. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. A obtenção de informações sobre a região e o nível do país só deve ser ligeiramente afetada. Os dados de Segmentação geográfica são granulares somente no nível da cidade ou no nível do código postal, e não no nível individual. Leia mais sobre a [geolocalização](/help/using/features/traits/trait-geotarget-keys.md) e como configurar características com variáveis geográficas.

## Conceitos relacionados {#related-concepts}

* [Gerenciamento de não participação](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [Perguntas frequentes sobre privacidade e retenção de dados](/help/using/faq/faq-privacy.md)