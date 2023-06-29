---
description: Colete dados enviados de arquivos FLA para o Analytics e trabalhe com essas informações no Audience Manager.
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 3%

---

# Flash DIL{#flash-dil}

>[!WARNING]
>
>A partir de julho de 2023, a Adobe interrompeu o desenvolvimento do [!DNL Data Integration Library (DIL)] e a variável [!DNL DIL] extensão.
><br>
>Os clientes existentes podem continuar usando seus [!DNL DIL] execução. No entanto, o Adobe não estará em desenvolvimento [!DNL DIL] além deste ponto. Os clientes são incentivados a avaliar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para a sua estratégia de recolha de dados a longo prazo.
><br>
>Os clientes que desejam implementar novas integrações de coleta de dados após julho de 2023 devem usar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) em vez disso.

Colete dados enviados de arquivos FLA para o Analytics e trabalhe com essas informações no Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] é um [!DNL ActionScript] biblioteca de código que permite trabalhar com dados de reprodução de vídeo no Audience Manager. [!DNL Flash DIL] funciona capturando o conteúdo SWF no Adobe [!UICONTROL AppMeasurement] A biblioteca do é transmitida para o Analytics. [!DNL Flash DIL] O envia esses dados para o [!UICONTROL DIL] Módulo de coleção de dados JavaScript, que passa essas informações para o Audience Manager. Dados do Analytics ( [!UICONTROL Props], [!UICONTROL eVars], eventos etc.) capturada do [!DNL FLA] O arquivo está disponível no Audience Manager como características ou sinais não usados.

## Requisitos para a coleta de dados do DIL do Flash {#requirements}

Implementação geral e requisitos relacionados a código.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisitos de implementação**

[!UICONTROL Flash] a coleta de dados exige:

* A variável [!UICONTROL DIL] biblioteca de classes ( `dil.swc`). Obtenha o [!UICONTROL DIL] biblioteca de classes do seu contato de soluções de parceiros.

* JavaScript [!UICONTROL DIL] código de coleta de dados na página.
* [biblioteca de ActionScript DIL](../dil/dil-flash.md#flash-dil-actionscript) carregado no objeto de Flash do qual você deseja coletar dados.
* Adobe [!DNL AppMeasurement] [!DNL AS] A biblioteca do (versão 3.5.2 ou posterior) carregou o [!DNL Flash] objeto do qual você deseja coletar dados.

**Definir AllowScriptAccess como `Always` ou`sameDomain`**

A variável `AllowScriptAccess` no código HTML que carrega um arquivo SWF, controla a capacidade de executar o acesso ao URL de saída a partir do arquivo SWF. Ao configurar um [!UICONTROL Flash DIL] integração de dados, verifique se o Flash `AllowScriptAccess` está definido como `always` ou `sameDomain`. [!UICONTROL Flash DIL] a coleta de dados não funcionará se `AllowScriptAccess` está definida como `never`. Consulte [Página Controlar Acesso a Scripts ou Host da Web](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS [!UICONTROL DIL] Inserção de código**

Tente colocar o JS [!UICONTROL DIL] módulo de coleção de dados na página, de modo que seja carregado antes da variável [!DNL FLA] arquivo. Quando a variável [!DNL FLA] o arquivo é carregado primeiro, antes de [!UICONTROL DIL] a coleta de dados estiver pronta, você poderá perder os sinais de dados iniciais que [!UICONTROL Flash DIL] envia para esse módulo. No entanto, uma vez instanciado, o [!UICONTROL DIL] o módulo de coleta de dados capturará todos os dados subsequentes do arquivo SWF transmitidos por [!UICONTROL Flash DIL].

## Dados coletados pelo DIL do Flash {#data-collected}

[!UICONTROL Flash DIL] captura a exibição de página, rastreamento de links, rastreamento de mídia e outros eventos de exibição de mídia do Adobe [!UICONTROL AppMeasurement] biblioteca.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Eventos de exibição de página**

Salvo especificação em contrário de `s.trackVars`, [!UICONTROL Flash DIL] O coleta os seguintes dados do Adobe AppMeasurement:

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

Salvo especificação em contrário de `s.Media.trackVars`, [!UICONTROL Flash DIL] O coleta todos os dados enumerados na seção Eventos de exibição de página.

**Outros pontos de dados**

Os dados desses parâmetros são coletados por padrão:

* `mediaName` (Nome do elemento de mídia/vídeo)
* `mediaAdName` (Nome do anúncio)
* `mediaAdParentName` (Nome do conteúdo de mídia principal sob o qual o anúncio está aninhado)
* `mediaAdParentPod` (O pod ou ad break no conteúdo principal em que o anúncio é reproduzido)
* `mediaAdParentPodPos` (A posição numérica no pod onde o anúncio é reproduzido. Mais de um anúncio pode ser reproduzido em um pod.

## Dados do DIL do Flash no Audience Manager {#flash-dil-data}

A variável [!UICONTROL Flash DIL] O módulo transforma os dados do Adobe AppMeasurement em Audience Manager e sinais não utilizados.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars], e os eventos funcionam como características no Audience Manager. As características são pares de valores chave e são usadas para criar segmentos. Por exemplo, em uma propriedade do Analytics como `c30=foo`, `c30` é a chave (uma constante) e `foo` é o valor (uma variável).

**Combinar características de Audience Manager com variáveis do Analytics**

Para usar os dados do Analytics transmitidos por [!UICONTROL Flash DIL], você deve criar características de Audience Manager que tenham o valor principal prefixado com `c_`.

Consulte a tabela para ver exemplos:

| Elemento de dados do Analytics | Exemplo do Analytics | Como característica de Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Dados do DIL/Analytics como sinais não utilizados**

Audience Manager aceita o Analytics [!UICONTROL Props], [!UICONTROL eVars]e eventos mesmo sem uma característica correspondente. Nesse caso, os dados não estão disponíveis para a criação de características e aparecem no [Relatório de sinais não usados](../reporting/dynamic-reports/unused-signals.md) em vez disso. Para aproveitar essas informações ao máximo, crie características de Audience Manager que correspondam aos dados do Analytics enviados pelo [!UICONTROL Flash DIL] biblioteca.

## Biblioteca de ActionScript de DIL do Flash {#flash-dil-actionscript}

Código para o seu [!DNL Flash] objeto para enviar dados do Analytics para o Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Para cada [!DNL Flash] , o código suporta uma instância de parceiro ( `d.partner`) somente.
>
>* Requer o Adobe [!UICONTROL AppMeasurement] [!DNL AS] versão da biblioteca 3.5.2 ou superior.

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
>* [Sinais, características e segmentos](../reference/signal-trait-segment.md)
>* [Explicação dos pares de valor-chave](../reference/key-value-pairs-explained.md)
>* [Requisitos de prefixo para variáveis-chave](../features/traits/trait-variable-prefixes.md)
