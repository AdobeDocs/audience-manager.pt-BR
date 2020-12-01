---
description: Antes do Audience Manager poder habilitar a otimização de público-alvo para editores, você deve garantir que todos os pré-requisitos descritos neste artigo sejam atendidos. Entre em contato com o Atendimento ao cliente após verificar todos os pré-requisitos.
seo-description: Antes do Audience Manager poder habilitar a otimização de público-alvo para editores, você deve garantir que todos os pré-requisitos descritos neste artigo sejam atendidos. Entre em contato com o Atendimento ao cliente após verificar todos os pré-requisitos.
seo-title: Importar arquivos de dados do Google Ad Manager para o Audience Manager
solution: Audience Manager
title: Importar arquivos de dados do Google Ad Manager para o Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 16%

---


# Importar arquivos de dados do Google Ad Manager (antigo DFP) para o Audience Manager{#import-dfp-data-files-into-audience-manager}

Antes do Audience Manager poder habilitar a otimização de público-alvo para editores, você deve garantir que todos os pré-requisitos descritos neste artigo sejam atendidos. Entre em contato com o Atendimento ao cliente após verificar todos os pré-requisitos.

## Pré-requisitos para ingestão de log do Google Ad Manager {#prereqs-dfp-ingestion}

Observe que o processo descrito nesta seção deve ser concluído *antes de* você seguir para os pré-requisitos para a ativação de ingestão de log.

Para usar os arquivos de log [!DNL Google Ad Manager] (antigo Google DFP) em [!DNL Audience Manager], você deve primeiro definir nossa [ID de usuário exclusiva (UUID)](../../../reference/ids-in-aam.md) Audience Manager na chamada de tag do anúncio. Ao fazer isso, nossa ID é incluída nos registros [!DNL Google Ad Manager] e podemos corresponder IDs entre [!DNL Google Ad Manager] e [!DNL Audience Manager]. Use o código [!DNL Audience Manager] [!UICONTROL DIL] ou [!UICONTROL Audience Management Module] para definir o UUID [!DNL Audience Manager] em um cookie próprio.

Veja como definir a ID [!DNL Audience Manager] na chamada de tag do anúncio, conforme explicado em nossa documentação:

* [Via Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Por um destino de cookie](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

É necessário definir a ID [!DNL Audience Manager] você mesmo e pode trabalhar com a consultoria [!DNL Audience Manager] para verificar se tudo funciona. Você definiu a ID [!DNL Audience Manager] corretamente se:

* `'aamid'` é a chave usada como o identificador.
* O valor da ID de usuário está formatado corretamente como o UUID [!DNL Audience Manager], conforme descrito em nosso [Índice de IDs em Audience Manager](../../../reference/ids-in-aam.md).
* Você incluiu a UUID [!DNL Audience Manager] em um campo definido nos registros [!DNL Google Ad Manager] (por exemplo, CustomTargeting).

## Pré-requisitos para a Ativação de Ingestão de Log {#prereqs-ingestion-enablement}

<table id="table_C980A9F9B0FB4157B4908A64768B1571"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etapa </th> 
   <th colname="col2" class="entry"> Detalhes </th> 
   <th colname="col3" class="entry"> Proprietário </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Etapa 1 </p> </td> 
   <td colname="col2"> <p>Confirme se as etapas necessárias para definir o UUID <span class="keyword"> Audience Manager</span> (descritas acima) foram concluídas antes de passar para a Etapa 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audiência </span> ManagerAtendimento ao cliente ou consultoria </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 2 </p> </td> 
   <td colname="col2"> <p>Seu Administrador do Google Ad Manager cria: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Uma conta de serviço para assimilar o Google Ad Manager faz login em <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Novas credenciais. <p>Observação:  Isso pode exigir um endereço de email exclusivo específico para este projeto e será usado ao fornecer acesso ao Google Armazenamento Bucket. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Uma chave privada (credencial com base em JSON) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Seu administrador do Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 3 </p> </td> 
   <td colname="col2"> <p>Seu Administrador do Google Ad Manager concede acesso à API à conta de serviço. Essa etapa permite o acesso aos metadados para delinear dimensões (itens de linha, pedidos, criações). <p>Observação:  Use o acesso por email da conta de serviço que você configurou na etapa 2 para conceder permissão de acesso à API. </p> </p> </td> 
   <td colname="col3"> <p>Seu administrador do Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 4 </p> </td> 
   <td colname="col2"> <p>Seu Administrador do Google Ad Manager estabelece acesso ao Armazenamento Bucket do Google. Lembre-se: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Isso pode ser feito através de um grupo do Google. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Associe o endereço de email exclusivo atribuído à conta de serviço ao bucket do armazenamento. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Seu administrador do Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 5 </p> </td> 
   <td colname="col2"> <p>Seu Administrador do Google Ad Manager fornece a ID de rede do Google Ad Manager. Isso nos permite transmitir a ID da rede ao fazer chamadas para a API. </p> </td> 
   <td colname="col3"> <p>Seu administrador do Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 6 </p> </td> 
   <td colname="col2"> <p>Compile os pré-requisitos em um email para AAM Atendimento ao cliente (aamsupport@adobe.com) para iniciar o processo de ingestão de log. Rasgue o email usando o modelo na próxima seção. </p> </td> 
   <td colname="col3"> <p>Você ou <span class="keyword"> Audience Manager</span> Consultoria em seu nome </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modelo de e-mail {#email-template}

Para finalizar a ativação de ingestão de registro, envie-nos um email para aamsupport@adobe.com. Use o [modelo de e-mail anexado](assets/enable_dfp_ingestion.txt).
