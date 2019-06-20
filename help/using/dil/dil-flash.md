---
description: Coletar dados enviados de arquivos FLA para o Analytics e trabalhar com essas informações no Audience Manager.
seo-description: Coletar dados enviados de arquivos FLA para o Analytics e trabalhar com essas informações no Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833 cfd -768 e -4 b 16-95 c 5-debd 8411 df 38
translation-type: tm+mt
source-git-commit: 49fff90fa1330c59360e16f2a56e8fba7d4c43dc

---


# Flash DIL{#flash-dil}

Coletar dados enviados de arquivos FLA para o Analytics e trabalhar com essas informações no Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] é uma biblioteca [!DNL ActionScript] de códigos que permite trabalhar com os dados de reprodução de vídeo no Audience Manager. [!DNL Flash DIL] funciona ao capturar o conteúdo SWF que a [!UICONTROL AppMeasurement] biblioteca da Adobe transmite para o Analytics. [!DNL Flash DIL] envia esses dados para o módulo de [!UICONTROL DIL] coleta de dados javascript separado, que transmite essas informações para o Audience Manager. Analytics data ( [!UICONTROL Props], [!UICONTROL eVars], events, etc.) captured from the [!DNL FLA] file is available in Audience Manager as traits or unused signals.

## Requirements for Flash DIL Data Collection {#requirements}

Implementação geral e requisitos relacionados ao código.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisitos de implementação**

[!UICONTROL Flash] a coleta de dados requer:

* The [!UICONTROL DIL] class library ( `dil.swc`). Obtain the [!UICONTROL DIL] class library from your Partner Solutions contact.

* JavaScript [!UICONTROL DIL] data collection code on the page.
* [A biblioteca do actionscript de DIL](../dil/dil-flash.md#flash-dil-actionscript) carregada no objeto Flash do qual você deseja coletar dados.
* Adobe [!DNL AppMeasurement] [!DNL AS] library (version 3.5.2, or later) loaded the [!DNL Flash] object you want to collect data from.

**Defina allowscriptaccess como`Always`ou`sameDomain`**

The `AllowScriptAccess` in HTML code that loads a SWF file controls the ability to perform outbound URL access from within the SWF file. When you configure a [!UICONTROL Flash DIL] data integration, make sure the Flash `AllowScriptAccess` parameter is set to `always` or `sameDomain`. [!UICONTROL Flash DIL] a coleta de dados não funcionará se `AllowScriptAccess` estiver definida `never`como. See [Control Access to Scripts or Host Web Page](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**Posicionamento[!UICONTROL DIL]de código JS**

Try to place the JS [!UICONTROL DIL] data collection module on the page so it loads before the [!DNL FLA] file. When the [!DNL FLA] file loads first, before [!UICONTROL DIL] data collection is ready, you can miss the initial data signals that [!UICONTROL Flash DIL] sends to that module. However, once instantiated, the [!UICONTROL DIL] data collection module will capture all subsequent SWF file data passed in by [!UICONTROL Flash DIL].

## Data Collected by Flash DIL {#data-collected}

[!UICONTROL Flash DIL] captura exibição de página, rastreamento de link, rastreamento de mídia e outros eventos de exibição de mídia da [!UICONTROL AppMeasurement] biblioteca da Adobe.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Eventos de exibição de página**

Unless specified otherwise by `s.trackVars`, [!UICONTROL Flash DIL] collects the following data from Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Eventos de rastreamento de link**

Unless specified otherwise by `s.linkTrackVars`, [!UICONTROL Flash DIL] collects the following data from Adobe [!UICONTROL AppMeasurement]:

* `pe` (Tipo de link de rastreamento chamado)
* `pev1` (URL de link)
* `pev2`(Texto do link)

**Eventos de rastreamento de mídia**

Unless specified otherwise by `s.Media.trackVars`, [!UICONTROL Flash DIL] collects all the data enumerated in the Page View Events section.

**Outros pontos de dados**

Os dados desses parâmetros são coletados por padrão:

* `mediaName` (nome do elemento de mídia/vídeo)
* `mediaAdName` (Nome do anúncio)
* `mediaAdParentName` (Nome do conteúdo de mídia primária em que o anúncio está aninhado)
* `mediaAdParentPod` (O pod ou quebra de anúncio no conteúdo principal em que o anúncio é reproduzido)
* `mediaAdParentPodPos` (A posição numérica no pod em que o anúncio é reproduzido. Mais de um anúncio pode ser reproduzido em um pod.

>[!MORE_ LIKE_ THIS]
>
>* [Guia de implementação do appmeasurement Flash, Flex e OSMF](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/flash/)


## Flash DIL Data in Audience Manager {#flash-dil-data}

The [!UICONTROL Flash DIL] module turns Adobe AppMeasurement data into Audience Manager traits and unused signals.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars], and events work like traits in Audience Manager. As características são pares de valores chave e são usados para construir segmentos. For example, in an Analytics prop like `c30=foo`, `c30` is the key (a constant) and `foo` is the value (a variable).

**Corresponder características do Audience Manager às variáveis do Analytics**

To use the Analytics data passed by [!UICONTROL Flash DIL], you should create Audience Manager traits that have the key value prefixed with `c_`.

Consulte a tabela para obter exemplos:

| Elemento de dados do Analytics | Exemplo do Analytics | Como característica do Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Dados DIL/Analytics como Sinais não usados**

Audience Manager accepts Analytics [!UICONTROL Props], [!UICONTROL eVars], and events even without a corresponding trait. In this case, the data is unavailable for trait creation and appears in the [Unused Signals report](../reporting/dynamic-reports/unused-signals.md) instead. To make the most of this information, create Audience Manager traits that match the Analytics data passed in by the [!UICONTROL Flash DIL] library.

>[!MORE_ LIKE_ THIS]
>
>* [Características](../features/traits/trait-details-page.md)
>* [Sinais, características e segmentos](../reference/signal-trait-segment.md)
>* [Pares de valores chave explicados](../reference/key-value-pairs-explained.md)
>* [Requisitos de prefixo para variáveis principais](../features/traits/trait-variable-prefixes.md)


## Flash DIL ActionScript Library {#flash-dil-actionscript}

Code for your [!DNL Flash] object to send Analytics data to Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* For each [!DNL Flash] object, the code supports one partner instance ( `d.partner`) only.
   >
   >
* Requires the Adobe [!UICONTROL AppMeasurement] [!DNL AS] library version 3.5.2 or higher.
>



```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

