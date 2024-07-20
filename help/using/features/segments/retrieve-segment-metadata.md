---
description: Quando o Audience Manager envia informações de segmento para um parceiro de dados, ele identifica esses objetos com IDs numéricas. Como parceiro de dados, quando você compartilha essas informações com seus clientes (ou trabalha com eles mesmo), um nome e uma descrição reais fornecem uma experiência melhor para os clientes em relatórios, painéis ou outras interfaces de usuário (IU). Os parceiros de dados podem disponibilizar esses nomes amigáveis aos seus clientes com os métodos manuais ou automatizados descritos nesta seção.
seo-description: When Audience Manager sends segment information to a data partner, it identifies these objects with numeric IDs. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces (UI). Data partners can make these friendly names available to their customers with either the manual or automated methods described in this section.
seo-title: Retrieving Segment Metadata
solution: Audience Manager
title: Recuperação de metadados do segmento
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
exl-id: 64922cf8-f7bf-4e33-871f-d33626b06360
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---

# Recuperação de metadados do segmento {#retrieving-segment-metadata}

Quando o Audience Manager envia informações de segmento para um parceiro de dados, ele identifica esses objetos com IDs numéricas. Como parceiro de dados, quando você compartilha essas informações com seus clientes (ou trabalha com eles), um nome e uma descrição reais fornecem uma experiência melhor para os clientes em relatórios, painéis ou outras interfaces de usuário ([!DNL UI]). Os parceiros de dados podem disponibilizar esses nomes amigáveis aos seus clientes com os métodos manuais ou automatizados descritos nesta seção.

## Método manual {#manual-method}

Como parceiro de dados, você provavelmente está acostumado a obter metadados de público-alvo de seus clientes por meio de processos manuais. Isso pode incluir arquivos anexados a emails ou de clientes que adicionam esses dados por meio de um [!DNL UI] que você criou e manteve para essa finalidade. Esses processos funcionam, mas geralmente são complicados, demorados e podem exigir trabalho manual de entrada de dados. Esses métodos geralmente são usados para ajudar a colocar uma integração em funcionamento rapidamente, mas não fornecem a melhor experiência do cliente a longo prazo. Como alternativa, você pode usar o [!DNL Audience Manager] [!DNL API] para obter metadados de segmento automaticamente.

## Método automatizado {#automated-method}

[!DNL Audience Manager] fornece um conjunto de [APIs REST](../../api/rest-api-main/rest-api-main.md) que permitem recuperar metadados de segmento automaticamente. Com o [!DNL API], você pode criar trabalhos que recuperam metadados de segmento em intervalos agendados ou automaticamente, sempre que processar dados do [!DNL Audience Manager] e encontrar uma nova ID de segmento. Consulte as etapas abaixo para obter mais informações.

### Etapa 1: Revise as APIs de Audience Manager

A seção [Introdução às REST APIs](../../api/rest-api-main/aam-api-getting-started.md) contém informações sobre requisitos gerais, autenticação, métodos disponíveis, etc. Este é um bom local para começar se você ainda não trabalhou com o [!DNL Audience Manager] [!DNL API].

### Etapa 2: solicitar credenciais de acesso do OAuth2

Você precisa de uma ID de cliente e um segredo para fazer chamadas de [!DNL API]. Você pode obter uma ID de cliente e um segredo do especialista em integração durante o processo de configuração da integração. Você também pode enviar uma solicitação de email para [!UICONTROL Audience Manager Customer Care] em [!DNL amsupport@adobe.com].

### Etapa 3: Coletar informações específicas do cliente de cada cliente integrado

Solicite o seguinte de cada cliente integrado:

* Nome do usuário: destinado a um usuário restrito que tem permissões somente leitura para o destino associado a uma integração específica.
* Senha: A senha do usuário.
* ID de destino: é a ID (um número inteiro) associada ao destino criado para a integração específica de servidor para servidor.

### Etapa 4: recuperar metadados de segmento com uma chamada de API

Após concluir as etapas anteriores, você pode usar um método `GET` para recuperar metadados de segmento. Para obter uma solicitação e resposta de exemplo, consulte [Mapeamentos de Destino de Retorno](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). Esta chamada retorna dados de segmento formatados como pares de valores chave em um objeto [!DNL JSON]. Alguns dos atributos de segmento importantes retornados na resposta do estão listados na tabela a seguir.

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> destinationMappingId</code> </p> </td> 
   <td colname="col2"> <p>A ID do segmento <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>O nome do segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementDescription</code> </p> </td> 
   <td colname="col2"> <p>Um texto que descreve brevemente o segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementStatus</code> </p> </td> 
   <td colname="col2"> <p>O status atual do mapeamento de segmento. As opções de status retornadas incluem: </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
