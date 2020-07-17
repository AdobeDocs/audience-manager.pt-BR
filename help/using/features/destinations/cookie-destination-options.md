---
description: No Construtor de destinos, a seção Configuração contém os campos Domínio do cookie e Publicar dados em. Isso permite que você crie regras para determinar se um destino define um cookie ou retorna um cookie. Domínio do cookie e dados de publicação Para trabalhar independentemente uns dos outros e são opcionais. Você pode criar um destino de cookie sem usar qualquer um deles.
seo-description: No Construtor de destinos, a seção Configuração contém os campos Domínio do cookie e Publicar dados em. Isso permite que você crie regras para determinar se um destino define um cookie ou retorna um cookie. Domínio do cookie e dados de publicação Para trabalhar independentemente uns dos outros e são opcionais. Você pode criar um destino de cookie sem usar qualquer um deles.
seo-title: Configurações opcionais para destinos de cookies
solution: Audience Manager
title: Configurações opcionais para destinos de cookies
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 7%

---


# Configurações opcionais para destinos de cookies {#optional-settings-cookies}

Em [!UICONTROL Destination Builder], [!UICONTROL Configuration section] contém os campos [!UICONTROL Cookie Domain] e [!UICONTROL Publish Data To] . Isso permite que você crie regras para determinar se um destino define um cookie ou retorna um cookie. [!UICONTROL Cookie Domain] e [!UICONTROL Publish Data To] trabalharem independentemente umas das outras e forem opcionais. Você pode criar um destino de cookie sem usar qualquer um deles.

## Domínio do cookie: Sintaxe e exemplos {#cookie-domain-syntax}

<!-- cookie-destination-options.xml -->

<table id="table_4F4F7562AFEE49F8917AAE5712B5CCE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domínio do cookie </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Sintaxe</b> </p> </td> 
   <td colname="col2"> <p>O campo Domínio <span class="wintitle"></span> de cookie aceita uma sequência de caracteres de texto simples que permite definir cookies em um domínio especificado ou em todos os domínios. Ao usar este recurso: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Defina apenas um domínio para cada destino de cookie. Não digite vários domínios no campo <span class="wintitle"> Domínio</span> de cookie. Em vez disso, crie outro <span class="wintitle"> Destino</span> . </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">Não use caracteres curingas. </li> 
     </ul> </p> <p> Deixe o campo Domínio <span class="wintitle"></span> do cookie em branco para definir um cookie em todos os domínios. Essa é a configuração padrão. </p> <p>Para definir cookies em um domínio e subdomínios específicos: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Digite o nome do domínio no campo <span class="wintitle"> Domínio</span> de cookie. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Start o nome do domínio por um ponto. Por exemplo, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">The <code> https://www</code> prefix is not required. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exemplo</b> </p> </td> 
   <td colname="col2"> <p>Como exemplo simples, digamos que tenhamos um site fictício chamado Sports.com. Sports.com tem domínios para golfe, beisebol e futebol. Para definir um cookie em todos os domínios esportivos, digite-o na caixa Domínio <span class="wintitle"> do</span> cookie, como mostrado abaixo: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Isso instrui o Audience Manager <span class="keyword"> a definir um cookie em qualquer domínio que contenha o pattern</span> <code><i>something</i></code>.Sports.com. Consulte abaixo para obter um conjunto mais complexo de exemplos. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemplos complexos de domínio de cookie

Estes exemplos mostram se [!DNL Audience Manager] definirá um cookie com base em como a [!UICONTROL Cookie Domain] opção é configurada.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Site </th> 
   <th colname="col2" class="entry">Domínio do cookie: .Sports.com <p>Conjunto de cookies </p> </th> 
   <th colname="col3" class="entry">Domínio do cookie: .golf.Sports.com <p>Conjunto de cookies </p> </th> 
   <th colname="col4" class="entry">Domínio do cookie: Em branco <p>Conjunto de cookies </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Sports.com</b> </p> </td> 
   <td colname="col2"> Sim </td> 
   <td colname="col3"> Não </td> 
   <td colname="col4"> Sim </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>golf.Sports.com</b> </p> </td> 
   <td colname="col2"> Sim </td> 
   <td colname="col3"> Sim </td> 
   <td colname="col4"> Sim </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>baseball.Sport.com</b> </p> </td> 
   <td colname="col2"> Sim </td> 
   <td colname="col3"> Não </td> 
   <td colname="col4"> Sim </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Sports.golf.com</b> </p> </td> 
   <td colname="col2"> Não </td> 
   <td colname="col3"> Não </td> 
   <td colname="col4"> Sim </td> 
  </tr> 
 </tbody> 
</table>

## Publicar dados em {#publish-data-to}

As [!UICONTROL Publish Data To] configurações retornarão um cookie se o domínio atender aos critérios definidos pelas opções selecionadas. As opções incluem:

* **[!UICONTROL All of our domains]**: (Padrão) Retorna um [!DNL cookie] para qualquer domínio.
* **[!UICONTROL Only the selected domains]**: Retorna um cookie somente para os domínios selecionados na lista de domínios.
* **[!UICONTROL All of our domains except the selected domains]**: Impede que os domínios selecionados recebam um [!DNL cookie]. Todos os outros domínios podem receber um [!DNL cookie].

>[!MORELIKETHIS]
>
>* [Criar um destino de cookie](../../features/destinations/create-cookie-destination.md)