---
description: Os Controle da exportação de dados impedem que você envie dados para destinos quando essa ação viola a privacidade dos dados ou os contratos de uso dos dados.
seo-description: Data Export Controls prevent you from sending data to destinations when this action violates data privacy or data use agreements.
seo-title: Data Export Controls
solution: Audience Manager
title: Controles da exportação de dados
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Data Export Controls
exl-id: 4369c210-bcf1-48cc-a9bb-0d122f6c03d4
source-git-commit: 26aa0a210a045b40b2329844324315a092947188
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 1%

---

# Controles da exportação de dados {#data-export-controls}

[!UICONTROL Data Export Controls] impedir o envio de dados para destinos quando essa ação viola a privacidade dos dados ou os contratos de uso de dados.

## Visão geral {#overview}

[!UICONTROL Data Export Controls] permitir que você classifique [fontes de dados](../features/datasources-list-and-settings.md#data-sources-list-and-settings) e [destinos](../features/destinations/destinations.md). As classificações aplicadas determinam quando os dados podem ou não ser exportados para um destino. Esse recurso consiste em:

* **[!UICONTROL Data Export Controls]**: É possível definir Controles da exportação de dados em *fontes de dados*. Quando configurados em uma fonte de dados, esses controles restringem como essa fonte de dados e suas características podem ser usadas.
* **[!UICONTROL Data Export Labels]**: É possível definir os Rótulos de exportação de dados em *destinos*. Quando definido em um destino, esses rótulos identificam como o destino usa dados. Consulte [Adicionar rótulos de exportação de dados a um destino](/help/using/features/destinations/add-data-export-labels.md) para saber como adicionar rótulos de exportação a um destino.

Com base nas classificações aplicadas a uma fonte de dados e destino, os controles de exportação impedem:

* Adicionar uma característica a um segmento quando a característica pertence a uma fonte de dados que tem um controle de exportação de dados incompatível com um rótulo de exportação de dados em um ou mais destinos para os quais o segmento é mapeado.
Por exemplo, digamos que um segmento seja mapeado para um destino com o rótulo de exportação **[!DNL This destination may enable a combination with personally identifiable information (PII)]**. Os controles de exportação impedem que você adicione uma característica a esse segmento se a fonte de dados à qual a característica pertence tiver um controle de exportação de dados que diz **[!DNL Cannot be tied to personally identifiable information (PII)]**.
* Envio de dados para um destino que tenha um rótulo de exportação de dados bloqueado por um controle de exportação de dados em qualquer um dos seguintes:
   * A fonte de dados de uma característica incluída;
   * A fonte de dados de uma característica usada em um segmento incluído;
   * A regra de mesclagem de perfis aproveitada por um segmento incluído;
   * Qualquer fonte de dados que a regra de mesclagem de perfis de um segmento incluído usa.

[!UICONTROL Data Export Controls] estão disponíveis automaticamente para todos os clientes do Audience Manager. No entanto, você precisa de permissões de administrador para adicionar controles de exportação a uma fonte de dados. Adicionar rótulos de exportação a um destino requer permissões de administrador *ou* privilégios suficientes para criar ou editar um destino.

## Controles e rótulos definidos {#controls-labels}

[!UICONTROL Data Export Controls] forneça os seguintes controles para ajudar a classificar fontes e destinos de dados.

Para bloquear a entrega de dados, você deve classificar uma fonte de dados com um controle de exportação e adicionar um rótulo de exportação a um destino. Se você aplicar controles de exportação somente a uma fonte de dados ou destino, esse recurso não restringirá a entrega de dados. Quando definido em ambas as fontes de dados *e* como destino, os controles de exportação limitarão as características que você pode adicionar a um segmento e impedirão o envio dos membros do segmento para um destino.

Além disso, pelo menos um rótulo de exportação deve corresponder a um controle de exportação antes que as restrições de entrega de dados entrem em vigor. Por exemplo, digamos que você adicione a variável [!UICONTROL PII] exportar controle para uma fonte de dados. Em seguida, adicione o rótulo de direcionamento no site a um destino. Nesse caso, os controles de exportação não limitarão a entrega de dados porque as configurações não correspondem. No entanto, se você adicionar a variável [!UICONTROL PII] exportar rótulo para o destino, os controles de exportação bloquearão a exportação.

>[!IMPORTANT]
>
>Não é possível bloquear a exportação de um segmento colocando um controle de exportação de dados na fonte de dados do segmento, é necessário definir o controle em:
> * As fontes de dados das características usadas no segmento;
> * A regra de mesclagem de perfis aproveitada pelo segmento;
> * Qualquer fonte de dados que a regra de mesclagem de perfis do segmento usa.


<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Controles da exportação de dados para uma fonte de dados </th> 
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
   <td colname="col1"> <b><span class="uicontrol"> Não pode ser vinculado a informações de identificação pessoal</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> Este destino pode permitir uma combinação com informações pessoalmente identificáveis (PII)</span></b> </td> 
   <td colname="col3">Quando selecionada, não é possível: 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Adicione características a segmentos mapeados a destinos que usam PII. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Mapeie segmentos criados com uma característica da fonte de dados para destinos que usam PII. </li> 
    </ul> <p>Isso geralmente é exigido por provedores de dados de terceiros e ao usar fontes de dados que contêm informações de rastreamento de anúncios/mídia. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Não pode ser usado para direcionamento de anúncios no site</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Esse destino pode ser usado para o direcionamento de anúncios no site</span></b> </td> 
   <td colname="col3">Quando selecionada, não é possível: 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Adicione características a segmentos mapeados a destinos que personalizam a entrega de anúncios com base no histórico de navegação na Web de um visitante. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Mapeie segmentos criados com uma característica da fonte de dados para destinos que personalizam a entrega de anúncios com base no histórico de navegação na Web de um visitante. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Não pode ser usado para direcionamento de anúncios fora do site</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Esse destino pode ser usado para direcionamento de anúncios fora do site</span></b> </td> 
   <td colname="col3">Quando selecionada, não é possível: 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Adicione características a segmentos mapeados a destinos que redirecionam usuários em outros sites. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Mapeie segmentos criados com uma característica da fonte de dados para destinos que redirecionam usuários em outros sites. </li> 
    </ul> <p>Geralmente é necessário trabalhar com dados de plataformas de mídia social. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Não pode ser usado para personalização no site</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Esse destino pode ser usado para personalização de anúncios no site</span></b> </td> 
   <td colname="col3">Quando selecionada, não é possível: 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Adicione características a segmentos mapeados a destinos que personalizam o conteúdo com base nos interesses do usuário ou no histórico de navegação na Web. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Mapeie segmentos criados com uma característica da fonte de dados para destinos que personalizam o conteúdo com base nos interesses do usuário ou no histórico de navegação na Web. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Fluxo de trabalho {#workflow}

Para começar, reveja a fonte de dados e a documentação de destino. Esses artigos fornecem instruções sobre como adicionar controles de exportação e rótulos às suas fontes e destinos de dados.

* [Criar uma fonte de dados](../features/manage-datasources.md#create-data-source)
* [Adicionar rótulos de exportação de dados a um destino](../features/destinations/add-data-export-labels.md)
