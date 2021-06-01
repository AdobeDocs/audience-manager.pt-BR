---
description: Colete dados enviados de arquivos FLA para o Analytics e trabalhe com essas informações no Audience Manager.
seo-description: Colete dados enviados de arquivos FLA para o Analytics e trabalhe com essas informações no Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: DIL Flash
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: Implementação de DIL
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 4%

---

# Flash DIL{#flash-dil}

Colete dados enviados de arquivos FLA para o Analytics e trabalhe com essas informações no Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] é uma biblioteca de  [!DNL ActionScript] códigos que permite trabalhar com dados de reprodução de vídeo no Audience Manager. [!DNL Flash DIL] O funciona capturando o conteúdo SWF que a  [!UICONTROL AppMeasurement] biblioteca do Adobe transmite para o Analytics. [!DNL Flash DIL] O envia esses dados para o módulo de coleta de dados  [!UICONTROL DIL] JavaScript separado, que passa essas informações para o Audience Manager. Dados do Analytics ( [!UICONTROL Props], [!UICONTROL eVars], eventos etc.) capturado do arquivo [!DNL FLA] está disponível no Audience Manager como características ou sinais não utilizados.

## Requisitos para a coleta de dados do DIL do Flash {#requirements}

Implementação geral e requisitos relacionados ao código.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisitos de implementação**

[!UICONTROL Flash] a coleta de dados exige:

* A biblioteca de classe [!UICONTROL DIL] ( `dil.swc`). Obtenha a biblioteca de classes [!UICONTROL DIL] do contato de Soluções de Parceiros.

* Código de coleta de dados do JavaScript [!UICONTROL DIL] na página.
* [Biblioteca DIL ActionScript ](../dil/dil-flash.md#flash-dil-actionscript) carregada no objeto Flash do qual você deseja coletar dados.
* Adobe [!DNL AppMeasurement] [!DNL AS] biblioteca (versão 3.5.2 ou posterior) carregou o objeto [!DNL Flash] do qual deseja coletar dados.

**Defina AllowScriptAccess como  `Always` ou`sameDomain`**

O `AllowScriptAccess` no código HTML que carrega um arquivo SWF controla a capacidade de executar acesso ao URL de saída a partir do arquivo SWF. Ao configurar uma integração de dados [!UICONTROL Flash DIL], verifique se o parâmetro `AllowScriptAccess` do Flash está definido como `always` ou `sameDomain`. [!UICONTROL Flash DIL] a coleta de dados não funcionará se  `AllowScriptAccess` estiver definida como  `never`. Consulte [Controlar o Acesso a Scripts ou Hospedar Página da Web](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**Posicionamento  [!UICONTROL DIL] de código JS**

Tente colocar o módulo de coleta de dados JS [!UICONTROL DIL] na página para que ele seja carregado antes do arquivo [!DNL FLA]. Quando o arquivo [!DNL FLA] é carregado primeiro, antes que [!UICONTROL DIL] a coleta de dados esteja pronta, você pode perder os sinais de dados iniciais que [!UICONTROL Flash DIL] envia para esse módulo. No entanto, uma vez instanciado, o módulo de coleta de dados [!UICONTROL DIL] capturará todos os dados de arquivo SWF subsequentes passados por [!UICONTROL Flash DIL].

## Dados coletados pelo DIL de Flash do {#data-collected}

[!UICONTROL Flash DIL] captura a exibição de página, o rastreamento de link, o rastreamento de mídia e outros eventos de exibição de mídia da  [!UICONTROL AppMeasurement] biblioteca de Adobe.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Eventos de exibição de página**

Salvo especificação em contrário de `s.trackVars`, [!UICONTROL Flash DIL] coleta os seguintes dados do Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Eventos de rastreamento de link**

Salvo especificação em contrário de `s.linkTrackVars`, [!UICONTROL Flash DIL] coleta os seguintes dados do Adobe [!UICONTROL AppMeasurement]:

* `pe` (Tipo de link de rastreamento chamado)
* `pev1` (URL de link)
* `pev2`(Texto do link)

**Eventos de rastreamento de mídia**

A menos que especificado de outra forma por `s.Media.trackVars`, [!UICONTROL Flash DIL] coleta todos os dados enumerados na seção Eventos de exibição de página.

**Outros pontos de dados**

Os dados desses parâmetros são coletados por padrão:

* `mediaName` (Nome do elemento de mídia/vídeo)
* `mediaAdName` (Nome do anúncio)
* `mediaAdParentName` (Nome do conteúdo da mídia principal no qual o anúncio está aninhado)
* `mediaAdParentPod` (O pod ou o ad break no conteúdo principal em que o anúncio é reproduzido)
* `mediaAdParentPodPos` (A posição numérica no pod em que o anúncio é reproduzido. Mais de uma publicidade pode ser reproduzida em um pod.

## Dados do DIL de Flash do no Audience Manager {#flash-dil-data}

O módulo [!UICONTROL Flash DIL] transforma os dados do Adobe AppMeasurement em características Audience Manager e sinais não utilizados.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars] e eventos funcionam como características no Audience Manager. As características são pares de valores chave e são usadas para criar segmentos. Por exemplo, em uma prop do Analytics como `c30=foo`, `c30` é a chave (uma constante) e `foo` é o valor (uma variável).

**Corresponder características do Audience Manager às variáveis do Analytics**

Para usar os dados do Analytics transmitidos por [!UICONTROL Flash DIL], você deve criar características do Audience Manager que tenham o valor principal prefixado com `c_`.

Consulte a tabela para obter exemplos:

| Elemento de dados do Analytics | Exemplo do Analytics | Como característica Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Dados do DIL/Analytics como sinais não usados**

O Audience Manager aceita o Analytics [!UICONTROL Props], [!UICONTROL eVars] e eventos, mesmo sem uma característica correspondente. Nesse caso, os dados não estão disponíveis para a criação de características e aparecem no [Unused Signals report](../reporting/dynamic-reports/unused-signals.md) em vez disso. Para aproveitar ao máximo essas informações, crie Audience Manager características que correspondam aos dados do Analytics passados pela biblioteca [!UICONTROL Flash DIL].

## Biblioteca de ActionScript do DIL do Flash {#flash-dil-actionscript}

Código do seu objeto [!DNL Flash] para enviar dados do Analytics para o Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Para cada objeto [!DNL Flash] , o código oferece suporte somente a uma instância do parceiro ( `d.partner`).
   >
   >
* Exige a biblioteca Adobe [!UICONTROL AppMeasurement] [!DNL AS] versão 3.5.2 ou superior.


```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

>[!MORELIKETHIS]
>
>* [Características ](../features/traits/trait-details-page.md)
* [Sinais, características e segmentos](../reference/signal-trait-segment.md)
* [Explicação dos pares de valor-chave](../reference/key-value-pairs-explained.md)
* [Requisitos de prefixo para variáveis-chave](../features/traits/trait-variable-prefixes.md)

