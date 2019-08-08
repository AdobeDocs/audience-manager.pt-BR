---
description: No Construtor de destinos, a seção Configuração contém os campos Domínio do cookie e Publicar dados em. Eles permitem que você crie regras para determinar se um destino define um cookie ou retorna um cookie. Domínio do cookie e os Dados de publicação funcionam de forma independente entre si e são opcionais. É possível criar um destino de cookie sem usar qualquer um deles.
seo-description: No Construtor de destinos, a seção Configuração contém os campos Domínio do cookie e Publicar dados em. Eles permitem que você crie regras para determinar se um destino define um cookie ou retorna um cookie. Domínio do cookie e os Dados de publicação funcionam de forma independente entre si e são opcionais. É possível criar um destino de cookie sem usar qualquer um deles.
seo-title: Configurações opcionais para destinos de cookies
solution: Audience Manager
title: Configurações opcionais para destinos de cookies
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# Configurações opcionais para destinos de cookies {#optional-settings-cookies}

Em [!UICONTROL Destination Builder], [!UICONTROL Configuration section] contém os campos [!UICONTROL Cookie Domain] e os [!UICONTROL Publish Data To] campos. Eles permitem que você crie regras para determinar se um destino define um cookie ou retorna um cookie. [!UICONTROL Cookie Domain] e [!UICONTROL Publish Data To] trabalhar independentemente entre si e são opcionais. É possível criar um destino de cookie sem usar qualquer um deles.

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
   <td colname="col2"> <p>O campo <span class="wintitle"> Domínio</span> do cookie aceita uma sequência de texto simples que permite definir cookies em um domínio especificado ou em todos os domínios. Ao usar este recurso: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Defina apenas um domínio para cada destino de cookie. Não digite vários domínios no campo <span class="wintitle"> Domínio</span> do cookie. Crie outro <span class="wintitle"> destino</span> em vez disso. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">Não use caracteres curingas. </li> 
     </ul> </p> <p> Deixe o <span class="wintitle"> campo Domínio</span> do cookie em branco para definir um cookie em todos os domínios. Esta é a configuração padrão. </p> <p>Para definir cookies em um domínio e subdomínios específicos: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Digite o nome do domínio no campo <span class="wintitle"> Domínio</span> do cookie. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Inicie o nome do domínio com um período. Por exemplo <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">The <code> https://www</code> prefix is not required. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exemplo</b> </p> </td> 
   <td colname="col2"> <p>Como exemplo simples, digamos que temos um site fictício chamado sports. com. Sports.com tem domínios para golf, beisebol e futebol. Para definir um cookie em todos os domínios de esportes, você digita isso na caixa <span class="wintitle"> Domínio</span> do cookie, como mostrado abaixo: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Isso instrui <span class="keyword"> o Audience Manager</span> a definir um cookie em qualquer domínio que contenha o padrão <code><i>something</i></code>. sports. com. Veja abaixo um conjunto mais complexo de exemplos. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemplos de domínio de cookie complexos

Esses exemplos mostram se [!DNL Audience Manager] um cookie será definido com base na forma como a [!UICONTROL Cookie Domain] opção é configurada.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Site </th> 
   <th colname="col2" class="entry">Domínio do cookie: .sports.com <p>Conjunto de cookies </p> </th> 
   <th colname="col3" class="entry">Domínio do cookie: .golf.sports.com <p>Conjunto de cookies </p> </th> 
   <th colname="col4" class="entry">Domínio do cookie: Em branco <p>Conjunto de cookies </p> </th> 
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

As [!UICONTROL Publish Data To] configurações retornam um cookie se o domínio atender aos critérios definidos pelas opções selecionadas. As opções incluem:

* **[!UICONTROL All of our domains]**: (Padrão) Retorna um [!DNL cookie] para qualquer domínio.
* **[!UICONTROL Only the selected domains]**: Retorna um cookie apenas para os domínios selecionados na lista de domínios.
* **[!UICONTROL All of our domains except the selected domains]**: Impede que os domínios selecionados recebam [!DNL cookie]a. Todos os outros domínios podem receber [!DNL cookie]a.

>[!MORE_ LIKE_ THIS]
>
>* [Criar um destino do cookie](../../features/destinations/create-cookie-destination.md)