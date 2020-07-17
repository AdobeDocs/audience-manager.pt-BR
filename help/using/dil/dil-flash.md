---
description: Colete dados enviados de arquivos FLA para a Analytics e trabalhe com essas informações no Audience Manager.
seo-description: Colete dados enviados de arquivos FLA para a Analytics e trabalhe com essas informações no Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 4%

---


# Flash DIL{#flash-dil}

Colete dados enviados de arquivos FLA para a Analytics e trabalhe com essas informações no Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] é uma biblioteca de [!DNL ActionScript] códigos que permite trabalhar com dados de reprodução de vídeo no Audience Manager. [!DNL Flash DIL] funciona capturando conteúdo SWF que a biblioteca da Adobe [!UICONTROL AppMeasurement] transmite para o Analytics. [!DNL Flash DIL] envia esses dados para o módulo separado de coleta de dados do [!UICONTROL DIL] JavaScript, que transmite essas informações para a Audience Manager. Dados Analytics ( [!UICONTROL Props], [!UICONTROL eVars], eventos etc.) captada do [!DNL FLA] ficheiro está disponível em Audience Manager como características ou sinais não utilizados.

## Requisitos para a coleta de dados do Flash DIL {#requirements}

Aplicação geral e requisitos relacionados com o código.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisitos de implementação**

[!UICONTROL Flash] a coleta de dados exige:

* A biblioteca de [!UICONTROL DIL] classes ( `dil.swc`). Obtenha a biblioteca de [!UICONTROL DIL] classes do seu contato com Soluções de Parceiros.

* Código de coleta de [!UICONTROL DIL] dados do JavaScript na página.
* [Biblioteca](../dil/dil-flash.md#flash-dil-actionscript) DIL ActionScript carregada no objeto Flash do qual você deseja coletar dados.
* A [!DNL AppMeasurement] biblioteca da Adobe [!DNL AS] (versão 3.5.2 ou posterior) carregou o [!DNL Flash] objeto do qual você deseja coletar dados.

**Defina AllowScriptAccess como`Always`ou`sameDomain`**

O código `AllowScriptAccess` em HTML que carrega um arquivo SWF controla a capacidade de executar acesso de saída ao URL a partir do arquivo SWF. Ao configurar uma integração de [!UICONTROL Flash DIL] dados, verifique se o parâmetro Flash `AllowScriptAccess` está definido como `always` ou `sameDomain`. [!UICONTROL Flash DIL] a coleta de dados não funcionará se `AllowScriptAccess` estiver definida como `never`. Consulte [Controlar acesso a scripts ou hospedar página](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html)da Web.

**Posicionamento[!UICONTROL DIL]de código JS**

Tente colocar o módulo de coleta de [!UICONTROL DIL] dados JS na página para que ele seja carregado antes do [!DNL FLA] arquivo. Quando o [!DNL FLA] arquivo é carregado primeiro, antes que a coleta [!UICONTROL DIL] de dados esteja pronta, você pode perder os sinais de dados iniciais que [!UICONTROL Flash DIL] enviam para esse módulo. No entanto, uma vez instanciado, o módulo de coleta de [!UICONTROL DIL] dados capturará todos os dados de arquivo SWF subsequentes transmitidos por [!UICONTROL Flash DIL].

## Dados coletados pelo Flash DIL {#data-collected}

[!UICONTROL Flash DIL] captura a visualização da página, o rastreamento de links, o rastreamento de mídia e outros eventos de visualização de mídia da [!UICONTROL AppMeasurement] biblioteca da Adobe.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Eventos de Visualização da página**

Salvo especificação em contrário por `s.trackVars`, [!UICONTROL Flash DIL] coleta os seguintes dados do Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Eventos de rastreamento de link**

Salvo especificação em contrário por `s.linkTrackVars`, [!UICONTROL Flash DIL] coleta os seguintes dados da Adobe [!UICONTROL AppMeasurement]:

* `pe` (Tipo de link de rastreamento chamado)
* `pev1` (URL de link)
* `pev2`(Texto do link)

**Eventos de rastreamento de mídia**

A menos que especificado de outra forma por `s.Media.trackVars`, [!UICONTROL Flash DIL] coleta todos os dados enumerados na seção Eventos de Visualização da página.

**Outros pontos de dados**

Os dados desses parâmetros são coletados por padrão:

* `mediaName` (Nome do elemento de mídia/vídeo)
* `mediaAdName` (Nome do anúncio)
* `mediaAdParentName` (Nome do conteúdo de mídia principal em que o anúncio está aninhado)
* `mediaAdParentPod` (O pod ou a quebra de anúncio dentro do conteúdo principal em que o anúncio é reproduzido)
* `mediaAdParentPodPos` (A posição numérica no pod onde o anúncio é reproduzido. Mais de um anúncio pode ser reproduzido em um pod.

## Dados Flash DIL no Audience Manager {#flash-dil-data}

O [!UICONTROL Flash DIL] módulo transforma os dados do Adobe AppMeasurement em características de Audience Manager e sinais não utilizados.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars]e eventos funcionam como características no Audience Manager. As características são pares de valores chave e são usadas para criar segmentos. Por exemplo, em uma prop do Analytics como `c30=foo`, `c30` é a chave (uma constante) e `foo` é o valor (uma variável).

**Corresponder características de Audience Manager às variáveis do Analytics**

Para usar os dados do Analytics transmitidos [!UICONTROL Flash DIL], você deve criar características de Audience Manager que tenham o valor principal com o prefixo `c_`.

Consulte a tabela para obter exemplos:

| Elemento de dados Analytics | Exemplo Analytics | Como característica Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Dados DIL/Analytics como Sinais não usados**

Audience Manager aceita Analytics [!UICONTROL Props], [!UICONTROL eVars]e eventos mesmo sem uma característica correspondente. Nesse caso, os dados não estão disponíveis para criação de característica e são exibidos no relatório [Sinais](../reporting/dynamic-reports/unused-signals.md) não usados. Para aproveitar ao máximo essas informações, crie características de Audience Manager que correspondam aos dados do Analytics transmitidos pela [!UICONTROL Flash DIL] biblioteca.

## Biblioteca Flash DIL ActionScript {#flash-dil-actionscript}

Código para o seu [!DNL Flash] objeto para enviar dados do Analytics para o Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Para cada [!DNL Flash] objeto, o código oferece suporte somente a uma instância de parceiro ( `d.partner`).
   >
   >
* Exige a versão 3.5.2 ou superior da biblioteca da Adobe [!UICONTROL AppMeasurement] [!DNL AS] .


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

