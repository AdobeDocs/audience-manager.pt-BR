---
description: Os Controles de exportação de dados impedem que você envie dados para destinos quando essa ação viola a privacidade dos dados ou os contratos de uso de dados.
seo-description: Os Controles de exportação de dados impedem que você envie dados para destinos quando essa ação viola a privacidade dos dados ou os contratos de uso de dados.
seo-title: Controles da exportação de dados
solution: Audience Manager
title: Controles da exportação de dados
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Data Export Controls
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 1%

---


# Controles da exportação de dados {#data-export-controls}

[!UICONTROL Data Export Controls] impedir o envio de dados para destinos quando esta ação violar a privacidade dos dados ou os contratos de uso dos dados.

## Visão geral {#overview}

[!UICONTROL Data Export Controls] permite que você classifique  [fontes ](../features/datasources-list-and-settings.md#data-sources-list-and-settings) de dados e  [destinos](../features/destinations/destinations.md). As classificações aplicadas determinam quando os dados podem ou não ser exportados para um destino. Este recurso consiste em:

* **[!UICONTROL Data Export Controls]**: É possível definir Controles de exportação de dados em fontes *de* dados. Quando definidos em uma fonte de dados, esses controles restringem a forma como essa fonte de dados e suas características podem ser usadas.
* **[!UICONTROL Data Export Labels]**: É possível definir Rótulos de exportação de dados em  *destinos*. Quando definido em um destino, esses rótulos identificam como o destino usa os dados. Consulte [Adicionar etiquetas de exportação de dados a um destino](/help/using/features/destinations/add-data-export-labels.md) para saber como adicionar etiquetas de exportação a um destino.

Com base nas classificações aplicadas a uma fonte de dados e destino, os controles de exportação o impedem de:

* Adicionar uma característica a um segmento quando a característica pertence a uma fonte de dados que tem um controle de exportação de dados incompatível com um rótulo de exportação de dados em um ou mais dos destinos para os quais o segmento está mapeado.
Por exemplo, digamos que um segmento esteja mapeado para um destino com o rótulo de exportação **[!DNL This destination may enable a combination with personally identifiable information (PII)]**. Os controles de exportação impedem que você adicione uma característica a esse segmento se a fonte de dados à qual a característica pertence tiver um controle de exportação de dados que informe **[!DNL Cannot be tied to personally identifiable information (PII)]**.
* O envio de dados para um destino tem um rótulo de exportação de dados bloqueado por um controle de exportação de dados em qualquer um dos seguintes:
   * A fonte de dados de uma característica incluída;
   * A fonte de dados de uma característica usada em um segmento incluído;
   * A regra de união de perfis aproveitada por um segmento incluído;
   * Qualquer uma das fontes de dados que uma regra de mesclagem de perfis de segmentos incluídos usa.

[!UICONTROL Data Export Controls] estão disponíveis automaticamente para todos os clientes do Audience Manager. No entanto, você precisa de permissões de administrador para adicionar controles de exportação a uma fonte de dados. A adição de rótulos de exportação a um destino requer permissões de administrador *ou* privilégios suficientes para criar ou editar um destino.

## Controles e rótulos definidos {#controls-labels}

[!UICONTROL Data Export Controls] forneça os seguintes controles para ajudar a classificar fontes de dados e destinos.

Para bloquear o delivery de dados, é necessário classificar uma fonte de dados com um controle de exportação e adicionar um rótulo de exportação a um destino. Se você aplicar controles de exportação somente a uma fonte de dados ou destino, esse recurso não restringirá o delivery de dados. Quando definido no destino *e* da fonte de dados, os controles de exportação limitarão as características que podem ser adicionadas a um segmento e impedirão o envio dos membros do segmento para um destino.

Além disso, pelo menos um rótulo de exportação deve corresponder a um controle de exportação antes que as restrições de delivery de dados entrem em vigor. Por exemplo, digamos que você adicione o controle de exportação [!UICONTROL PII] a uma fonte de dados. Em seguida, adicione o rótulo de direcionamento no site a um destino. Nesse caso, os controles de exportação não limitarão o delivery de dados porque as configurações não correspondem. No entanto, se você adicionar o rótulo de exportação [!UICONTROL PII] ao destino, os controles de exportação bloquearão a exportação.

>[!IMPORTANT]
>
>Não é possível bloquear a exportação de um segmento colocando um controle de exportação de dados na fonte de dados do segmento. É necessário definir o controle em:
> * As fontes de dados das características utilizadas no segmento;
> * A regra de união de perfis aproveitada pelo segmento;
> * Qualquer uma das fontes de dados que a regra de união de perfis do segmento usa.


<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Controles de exportação de dados para uma fonte de dados </th> 
   <th colname="col2" class="entry"> Rótulos de exportação de dados para um destino </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Sem restrição</span></b> </td> 
   <td colname="col2"> n/a </td> 
   <td colname="col3"> Por padrão, as restrições de exportação não são definidas em novas fontes de dados e destinos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Não pode ser vinculado a informações</span></b>  de identificação pessoal (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> Este destino pode permitir uma combinação com informações de identificação pessoal (PII)</span></b> </td> 
   <td colname="col3">Quando selecionado, não é possível: 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Adicione características a segmentos mapeados a destinos que usam PII. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Mapeie segmentos criados com uma característica da fonte de dados para destinos que usam PII. </li> 
    </ul> <p>Isso geralmente é exigido por provedores de dados de terceiros e ao usar fontes de dados que contêm informações de rastreamento de anúncios/mídia. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Não pode ser usado para direcionamento de anúncios no site</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Esse destino pode ser usado para direcionamento de anúncios no site</span></b> </td> 
   <td colname="col3">Quando selecionado, não é possível: 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Adicione características a segmentos mapeados a destinos que personalizam o delivery de anúncio com base em um histórico de navegação na Web do visitante. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Mapeie segmentos criados com uma característica da fonte de dados para destinos que personalizam o delivery do anúncio com base em um histórico de navegação na Web do visitante. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Não pode ser usado para direcionamento de anúncios fora do site</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Esse destino pode ser usado para direcionamento de anúncios fora do site</span></b> </td> 
   <td colname="col3">Essas restrições são usadas geralmente com Quando selecionadas, não é possível: 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Adicione características a segmentos mapeados a destinos que repúblico alvo usuários em outros sites. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Mapeie segmentos criados com uma característica da fonte de dados para destinos que repúblicos alvos usuários em outros sites. </li> 
    </ul> <p>Muitas vezes é necessário ao trabalhar com dados de plataformas de mídia social. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Não pode ser usado para personalização no site</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Esse destino pode ser usado para personalização de anúncios no site</span></b> </td> 
   <td colname="col3">Quando selecionado, não é possível: 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Adicione características a segmentos mapeados a destinos que personalizam o conteúdo com base em interesses do usuário ou histórico de navegação na Web. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Mapeie segmentos criados com uma característica da fonte de dados para destinos que personalizam o conteúdo com base nos interesses do usuário ou no histórico de navegação na Web. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Fluxo de trabalho {#workflow}

Para começar, reveja a fonte de dados e a documentação de destino. Esses artigos fornecem instruções sobre como adicionar controles de exportação e etiquetas às suas fontes de dados e destinos.

* [Criar uma fonte de dados](../features/manage-datasources.md#create-data-source)
* [Adicionar rótulos de exportação de dados a um destino](../features/destinations/add-data-export-labels.md)