---
description: No Construtor de destinos, a seção Configuração contém o Domínio do cookie e os campos Publicar dados em. Isso permite criar regras para determinar se um destino define um cookie ou retorna um cookie. Domínio de cookie e Dados de publicação Para funcionar independentemente um do outro e são opcionais. Você pode criar um destino de cookie sem usar qualquer um deles.
seo-description: In Destination Builder, the Configuration section contains the Cookie Domain and Publish Data To fields. These let you create rules to determine if a destination sets a cookie or returns a cookie. Cookie Domain and Publish Data To work independently of each other and are optional. You can create a cookie destination without using either of them.
seo-title: Optional Settings for Cookie Destinations
solution: Audience Manager
title: Configurações opcionais para destinos de cookies
feature: Destination Basics
exl-id: b44f386e-4d43-41c3-b8ce-88b83d5d83c2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 7%

---

# Configurações opcionais para destinos de cookies {#optional-settings-cookies}

Entrada [!UICONTROL Destination Builder], o [!UICONTROL Configuration section] contém o [!UICONTROL Cookie Domain] e [!UICONTROL Publish Data To] campos. Isso permite criar regras para determinar se um destino define um cookie ou retorna um cookie. [!UICONTROL Cookie Domain] e [!UICONTROL Publish Data To] trabalhar independentemente uns dos outros e são opcionais. Você pode criar um destino de cookie sem usar qualquer um deles.

## Domínio do cookie: sintaxe e exemplos {#cookie-domain-syntax}

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
   <td colname="col2"> <p>A variável <span class="wintitle"> Domínio do cookie</span> aceita uma sequência de caracteres de texto simples que permite definir cookies em um domínio especificado ou em todos os domínios. Ao usar este recurso: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Defina apenas um domínio para cada destino de cookie. Não digite vários domínios no campo <span class="wintitle"> Domínio do cookie</span> campo. Criar outro <span class="wintitle"> Destino</span> em vez disso. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">Não use caracteres curingas. </li> 
     </ul> </p> <p> Deixe a <span class="wintitle"> Domínio do cookie</span> campo em branco para definir um cookie em todos os domínios. Esta é a configuração padrão. </p> <p>Para definir cookies em um domínio e subdomínios específicos: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Digite o nome do domínio no campo <span class="wintitle"> Domínio do cookie</span> campo. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Inicie o nome de domínio com um ponto. Por exemplo, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">A variável <code> https://www</code> O prefixo não é necessário. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exemplo</b> </p> </td> 
   <td colname="col2"> <p>Como um exemplo simples, digamos que tenhamos um site fictício chamado sports.com. Sports.com tem domínios para golfe, beisebol e futebol americano. Para definir um cookie em todos os domínios de esportes, digite-o na caixa <span class="wintitle"> Domínio do cookie</span> conforme mostrado abaixo: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Isso informa o <span class="keyword"> Audience Manager</span> para definir um cookie em qualquer domínio que contenha o padrão <code><i>something</i></code>.sports.com. Consulte abaixo um conjunto mais complexo de exemplos. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemplos de domínio de cookie complexo

Esses exemplos mostram se [!DNL Audience Manager] definirá um cookie com base em como a variável [!UICONTROL Cookie Domain] está configurada.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Site </th> 
   <th colname="col2" class="entry">Domínio do cookie: .sports.com <p>Conjunto de cookies </p> </th> 
   <th colname="col3" class="entry">Domínio do cookie: .golf.sports.com <p>Conjunto de cookies </p> </th> 
   <th colname="col4" class="entry">Domínio do cookie: em branco <p>Conjunto de cookies </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>sports.com</b> </p> </td> 
   <td colname="col2"> Sim </td> 
   <td colname="col3"> Não </td> 
   <td colname="col4"> Sim </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>golf.sports.com</b> </p> </td> 
   <td colname="col2"> Sim </td> 
   <td colname="col3"> Sim </td> 
   <td colname="col4"> Sim </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>baseball.sports.com</b> </p> </td> 
   <td colname="col2"> Sim </td> 
   <td colname="col3"> Não </td> 
   <td colname="col4"> Sim </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>sports.golf.com</b> </p> </td> 
   <td colname="col2"> Não </td> 
   <td colname="col3"> Não </td> 
   <td colname="col4"> Sim </td> 
  </tr> 
 </tbody> 
</table>

## Publicar dados em {#publish-data-to}

A variável [!UICONTROL Publish Data To] As configurações retornam um cookie se o domínio atender aos critérios definidos pelas opções selecionadas. As opções incluem:

* **[!UICONTROL All of our domains]**: (padrão) retorna um [!DNL cookie] para qualquer domínio.
* **[!UICONTROL Only the selected domains]**: retorna um cookie somente para os domínios selecionados na lista de domínios.
* **[!UICONTROL All of our domains except the selected domains]**: impede que os domínios selecionados recebam uma [!DNL cookie]. Todos os outros domínios podem receber uma [!DNL cookie].

>[!MORELIKETHIS]
>
>* [Criar um destino de cookie](../../features/destinations/create-cookie-destination.md)

