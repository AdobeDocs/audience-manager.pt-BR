---
description: Colete dados enviados de arquivos FLA para o Analytics e trabalhe com essas informações no Audience Manager.
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 2%

---

# Flash DIL{#flash-dil}

>[!WARNING]
>
>A partir de julho de 2023, a Adobe descontinuou o desenvolvimento do [!DNL Data Integration Library (DIL)] e da extensão [!DNL DIL].
>
>Os clientes existentes podem continuar usando a implementação [!DNL DIL]. Entretanto, a Adobe não desenvolverá [!DNL DIL] além deste ponto. Os clientes são incentivados a avaliar o [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR) para sua estratégia de coleta de dados de longo prazo.
>
>Os clientes que desejam implementar novas integrações de coleta de dados após julho de 2023 devem usar o [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR).

Colete dados enviados de arquivos FLA para o Analytics e trabalhe com essas informações no Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] é uma biblioteca de código [!DNL ActionScript] que permite trabalhar com dados de reprodução de vídeo no Audience Manager. O [!DNL Flash DIL] funciona capturando o conteúdo do SWF que a biblioteca [!UICONTROL AppMeasurement] do Adobe passa para o Analytics. [!DNL Flash DIL] envia esses dados para o módulo separado de coleta de dados do JavaScript [!UICONTROL DIL], que transmite essas informações para o Audience Manager. Os dados de análise ( [!UICONTROL Props], [!UICONTROL eVars], eventos etc.) capturados do arquivo [!DNL FLA] estão disponíveis no Audience Manager como características ou sinais não usados.

## Requisitos para a coleta de dados do Flash DIL {#requirements}

Implementação geral e requisitos relacionados a código.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisitos de implementação**

[!UICONTROL Flash] coleta de dados requer:

* A biblioteca de classes [!UICONTROL DIL] ( `dil.swc`). Obtenha a biblioteca de classes [!UICONTROL DIL] do seu contato de Soluções de Parceiros.

* Código de coleta de dados do JavaScript [!UICONTROL DIL] na página.
* [Biblioteca do DIL ActionScript](../dil/dil-flash.md#flash-dil-actionscript) carregada no objeto Flash do qual você deseja coletar dados.
* A biblioteca [!DNL AppMeasurement] do Adobe [!DNL AS] (versão 3.5.2 ou posterior) carregou o objeto [!DNL Flash] do qual você deseja coletar dados.

**Definir AllowScriptAccess como `Always` ou`sameDomain`**

O `AllowScriptAccess` no código HTML que carrega um arquivo SWF controla a capacidade de executar o acesso à URL de saída de dentro do arquivo SWF. Ao configurar uma integração de dados do [!UICONTROL Flash DIL], verifique se o parâmetro Flash `AllowScriptAccess` está definido como `always` ou `sameDomain`. A coleta de dados do [!UICONTROL Flash DIL] não funcionará se `AllowScriptAccess` estiver definida como `never`. Consulte [Controlar Acesso a Scripts ou Página da Web do Host](https://helpx.adobe.com/br/flash/kb/control-access-scripts-host-web.html).

**JS [!UICONTROL DIL] Inserção De Código**

Tente colocar o módulo de coleta de dados JS [!UICONTROL DIL] na página para que seja carregado antes do arquivo [!DNL FLA]. Quando o arquivo [!DNL FLA] for carregado primeiro, antes que a coleta de dados do [!UICONTROL DIL] esteja pronta, você poderá perder os sinais de dados iniciais que o [!UICONTROL Flash DIL] envia para esse módulo. No entanto, uma vez instanciado, o módulo de coleta de dados [!UICONTROL DIL] capturará todos os dados de arquivos SWF subsequentes transmitidos por [!UICONTROL Flash DIL].

## Dados coletados pelo Flash DIL {#data-collected}

[!UICONTROL Flash DIL] captura a exibição de página, rastreamento de link, rastreamento de mídia e outros eventos de exibição de mídia da biblioteca [!UICONTROL AppMeasurement] do Adobe.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Eventos de Exibição de Página**

A menos que especificado de outra forma por `s.trackVars`, [!UICONTROL Flash DIL] coleta os seguintes dados do Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Eventos de rastreamento de links**

A menos que especificado de outra forma por `s.linkTrackVars`, [!UICONTROL Flash DIL] coleta os seguintes dados do Adobe [!UICONTROL AppMeasurement]:

* `pe` (Tipo de link de rastreamento chamado)
* `pev1` (URL do link)
* `pev2`(Texto do link)

**Eventos de Acompanhamento de Mídia**

A menos que especificado de outra forma por `s.Media.trackVars`, [!UICONTROL Flash DIL] coleta todos os dados enumerados na seção Eventos de Exibição de Página.

**Outros pontos de dados**

Os dados desses parâmetros são coletados por padrão:

* `mediaName` (Nome do elemento de mídia/vídeo)
* `mediaAdName` (Nome do anúncio)
* `mediaAdParentName` (Nome do conteúdo de mídia primário sob o qual o anúncio está aninhado)
* `mediaAdParentPod` (O pod ou ad break no conteúdo principal em que o anúncio é reproduzido)
* `mediaAdParentPodPos` (A posição numérica no pod onde o anúncio é reproduzido. Mais de um anúncio pode ser reproduzido em um pod.

## Flash DIL Data in Audience Manager {#flash-dil-data}

O módulo [!UICONTROL Flash DIL] transforma dados do Adobe AppMeasurement em características do Audience Manager e sinais não utilizados.

<!-- 

c_flash_dil_in_aam.xml

 -->

Os eventos do Analytics [!UICONTROL Props], [!UICONTROL eVars] e do funcionam como características no Audience Manager. As características são pares de valores chave e são usadas para criar segmentos. Por exemplo, em uma prop do Analytics como `c30=foo`, `c30` é a chave (uma constante) e `foo` é o valor (uma variável).

**Corresponder Características do Audience Manager às Variáveis do Analytics**

Para usar os dados do Analytics transmitidos por [!UICONTROL Flash DIL], você deve criar características do Audience Manager que tenham o valor da chave prefixado com `c_`.

Consulte a tabela para ver exemplos:

| Elemento de dados do Analytics | Exemplo do Analytics | Como característica do Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Dados do DIL/Analytics como sinais não utilizados**

A Audience Manager aceita o Analytics [!UICONTROL Props], [!UICONTROL eVars] e eventos mesmo sem uma característica correspondente. Nesse caso, os dados não estão disponíveis para a criação de características e, em vez disso, aparecem no [relatório de Sinais não utilizados](../reporting/dynamic-reports/unused-signals.md). Para aproveitar essas informações ao máximo, crie características do Audience Manager que correspondam aos dados do Analytics transmitidos pela biblioteca [!UICONTROL Flash DIL].

## Flash DIL Biblioteca do ActionScript {#flash-dil-actionscript}

Código para o objeto [!DNL Flash] enviar dados do Analytics para a Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Para cada objeto [!DNL Flash], o código dá suporte apenas a uma instância de parceiro ( `d.partner`).
>
>* Exige a biblioteca do Adobe [!UICONTROL AppMeasurement] [!DNL AS] versão 3.5.2 ou superior.

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
>* [Características](../features/traits/trait-details-page.md)
>* [Sinais, características e segmentos](../reference/signal-trait-segment.md)
>* [Explicação dos pares de valor-chave](../reference/key-value-pairs-explained.md)
>* [Requisitos de prefixo para variáveis-chave](../features/traits/trait-variable-prefixes.md)
