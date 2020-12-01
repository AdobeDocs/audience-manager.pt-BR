---
description: Quando o Audience Manager envia informações de segmento para um parceiro de dados, identifica esses objetos com IDs numéricas. Como parceiro de dados, quando você compartilha essas informações com seus clientes (ou trabalha com eles), um nome e uma descrição reais fornecem uma melhor experiência para os clientes em relatórios, painéis ou outras interfaces de usuário (UI). Os parceiros de dados podem disponibilizar esses nomes amigáveis para seus clientes com os métodos manuais ou automatizados descritos nesta seção.
seo-description: Quando o Audience Manager envia informações de segmento para um parceiro de dados, identifica esses objetos com IDs numéricas. Como parceiro de dados, quando você compartilha essas informações com seus clientes (ou trabalha com eles), um nome e uma descrição reais fornecem uma melhor experiência para os clientes em relatórios, painéis ou outras interfaces de usuário (UI). Os parceiros de dados podem disponibilizar esses nomes amigáveis para seus clientes com os métodos manuais ou automatizados descritos nesta seção.
seo-title: Recuperação de metadados do segmento
solution: Audience Manager
title: Recuperação de metadados do segmento
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 1%

---


# Recuperação de metadados do segmento {#retrieving-segment-metadata}

Quando o Audience Manager envia informações de segmento para um parceiro de dados, identifica esses objetos com IDs numéricas. Como parceiro de dados, quando você compartilha essas informações com seus clientes (ou trabalha com eles), um nome e uma descrição reais fornecem uma melhor experiência para os clientes em relatórios, painéis ou outras interfaces de usuário ([!DNL UI]). Os parceiros de dados podem disponibilizar esses nomes amigáveis para seus clientes com os métodos manuais ou automatizados descritos nesta seção.

## Método manual {#manual-method}

Como parceiro de dados, você provavelmente está acostumado a obter metadados de audiência de seus clientes por meio de processos manuais. Isso pode incluir arquivos anexados a emails ou de clientes que adicionam esses dados por meio de [!DNL UI] que você criou e manteve para essa finalidade. Esses processos funcionam, mas geralmente são complicados, demorados e podem exigir o trabalho manual de entrada de dados. Esses métodos são usados com frequência para ajudar a ativar e executar uma integração rapidamente, mas não fornecem a melhor experiência do cliente a longo prazo. Como alternativa, você pode usar [!DNL Audience Manager] [!DNL API] para obter metadados de segmento automaticamente.

## Método automatizado {#automated-method}

[!DNL Audience Manager] fornece um conjunto de  [REST ](../../api/rest-api-main/rest-api-main.md) APIs que permite recuperar metadados de segmento automaticamente. Com o [!DNL API], você pode criar trabalhos que recuperam metadados de segmentos em intervalos programados ou automaticamente, sempre que processar [!DNL Audience Manager] dados e localizar uma nova ID de segmento. Consulte as etapas abaixo para obter mais informações.

### Etapa 1: Revise as APIs do Audience Manager

A seção [Introdução às APIs REST](../../api/rest-api-main/aam-api-getting-started.md) contém informações sobre requisitos gerais, autenticação, métodos disponíveis etc. Este é um bom lugar para começar se você não tiver trabalhado com o [!DNL Audience Manager] [!DNL API] antes.

### Etapa 2: Solicitar credenciais de acesso OAuth2

Você precisa de uma ID de cliente e um segredo para fazer chamadas [!DNL API]. Você pode obter uma ID de cliente e um segredo de seu especialista em integração durante o processo de configuração da integração. Você também pode enviar uma solicitação por email para [!UICONTROL Audience Manager Customer Care] em [!DNL amsupport@adobe.com].

### Etapa 3: Coletar informações específicas do cliente de cada cliente integrado

Solicite o seguinte de cada cliente integrado:

* Nome de usuário: Isso é para um usuário restrito que tem permissões somente leitura para o destino associado a uma integração específica.
* Senha: A senha do usuário.
* ID de destino: Essa é a ID (um número inteiro) associada ao destino criado para a integração servidor a servidor específica.

### Etapa 4: Recuperar metadados de segmento com uma chamada de API

Após concluir as etapas anteriores, você pode usar um método `GET` para recuperar os metadados do segmento. Para obter uma amostra de solicitação e resposta, consulte [Mapeamentos de destino de retorno](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). Essa chamada retorna dados de segmento formatados como pares de valores chave em um objeto [!DNL JSON]. Alguns dos atributos de segmento importantes retornados na resposta estão listados na tabela a seguir.

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
   <td colname="col2"> <p>Algum texto que descreve brevemente o segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementStatus</code> </p> </td> 
   <td colname="col2"> <p>O status atual do mapeamento de segmentos. As opções de status retornadas incluem: </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>