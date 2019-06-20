---
description: Quando o Audience Manager envia informações de segmento para um parceiro de dados, ele identifica esses objetos com IDs numéricas. Como parceiro de dados, ao compartilhar essas informações com seus clientes (ou trabalhar com elas mesmo), um nome e uma descrição reais fornecem uma melhor experiência para clientes em relatórios, painéis ou outras interfaces do usuário (IU). Os parceiros de dados podem disponibilizar esses nomes amigáveis para os clientes com os métodos manuais ou automatizados descritos nesta seção.
seo-description: Quando o Audience Manager envia informações de segmento para um parceiro de dados, ele identifica esses objetos com IDs numéricas. Como parceiro de dados, ao compartilhar essas informações com seus clientes (ou trabalhar com elas mesmo), um nome e uma descrição reais fornecem uma melhor experiência para clientes em relatórios, painéis ou outras interfaces do usuário (IU). Os parceiros de dados podem disponibilizar esses nomes amigáveis para os clientes com os métodos manuais ou automatizados descritos nesta seção.
seo-title: Recuperar metadados do segmento
solution: Audience Manager
title: Recuperar metadados do segmento
uuid: 719 e 2 c 41-8788-4 e 8 a -967 a-e 367421 f 9 f 84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Retrieving Segment Metadata {#retrieving-segment-metadata}

Quando o Audience Manager envia informações de segmento para um parceiro de dados, ele identifica esses objetos com IDs numéricas. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces ([!DNL UI]). Os parceiros de dados podem disponibilizar esses nomes amigáveis para os clientes com os métodos manuais ou automatizados descritos nesta seção.

## Manual method {#manual-method}

Como parceiro de dados, você provavelmente é usado para obter metadados de público-alvo de seus clientes por meio de processos manuais. This could include files attached to emails or from customers adding that data through a [!DNL UI] you&#39;ve built and maintained for this purpose. Esses processos funcionam, mas geralmente são pesados, demorados e podem exigir trabalho manual de entrada de dados. Esses métodos geralmente são usados para ajudar a fazer uma integração rápida e rápida, mas não fornecem a melhor experiência do cliente a longo prazo. As an alternative, you can use the [!DNL Audience Manager] [!DNL API] to get segment metadata automatically.

## Automated method {#automated-method}

[!DNL Audience Manager] fornece um conjunto de [apis REST](../../api/rest-api-main/rest-api-main.md) que permitem recuperar os metadados do segmento automaticamente. With the [!DNL API], you can create jobs that retrieve segment metadata at scheduled intervals or automatically, whenever you process [!DNL Audience Manager] data and find a new segment ID. Consulte as etapas abaixo para obter mais informações.

### Etapa 1: Revisar as apis do Audience Manager

The [Getting Started with REST APIs](../../api/rest-api-main/aam-api-getting-started.md) section contains information about general requirements, authentication, available methods, etc. This is a good place to begin if you haven&#39;t worked with the [!DNL Audience Manager] [!DNL API] before.

### Etapa 2: Solicitar credenciais de acesso do oauth 2

You need a client ID and secret to make [!DNL API] calls. Você pode obter uma ID do cliente e um segredo em seu especialista de integração durante o processo de integração configurado. You can also send an email request to [!UICONTROL Audience Manager Customer Care] at [!DNL amsupport@adobe.com].

### Etapa 3: Coletar informações específicas do cliente de cada cliente integrado

Solicite o seguinte a cada cliente integrado:

* Nome de usuário: Isto é para um usuário restrito que tem permissões somente leitura para o destino associado a uma integração específica.
* Senha: A senha do usuário.
* ID de destino: Essa é a ID (um número inteiro) associada ao destino criado para a integração específica entre servidor e servidor.

### Etapa 4: Recuperar metadados de segmento com uma chamada de API

After completing the previous steps, you can use a `GET` method to retrieve segment metadata. For a sample request and response, see [Return Destination Mappings](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). This call returns segment data formatted as key-value pairs in a [!DNL JSON] object. Alguns dos atributos de segmento importantes retornados na resposta são listados na tabela a seguir.

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Destinationmappingid</code> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> Audience Manager</span> segment ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementname</code> </p> </td> 
   <td colname="col2"> <p>O nome do segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementdescription</code> </p> </td> 
   <td colname="col2"> <p>Um texto que descreve brevemente o segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementstatus</code> </p> </td> 
   <td colname="col2"> <p>O status atual do mapeamento de segmento. As opções de status retornadas incluem: </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> ative</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inative</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> excluído</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>