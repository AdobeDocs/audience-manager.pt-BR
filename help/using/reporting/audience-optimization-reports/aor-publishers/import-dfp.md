---
description: Antes do Audience Manager poder habilitar a otimização de público-alvo para editores, você deve garantir que todos os pré-requisitos descritos neste artigo sejam atendidos. Entre em contato com o Atendimento ao cliente após verificar todos os pré-requisitos.
seo-description: Antes do Audience Manager poder habilitar a otimização de público-alvo para editores, você deve garantir que todos os pré-requisitos descritos neste artigo sejam atendidos. Entre em contato com o Atendimento ao cliente após verificar todos os pré-requisitos.
seo-title: Importação de arquivos de dados DFP para o Audience Manager
solution: Audience Manager
title: Importação de arquivos de dados DFP para o Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bafe0b268
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Importação de arquivos de dados DFP para o Audience Manager{#import-dfp-data-files-into-audience-manager}

Antes do Audience Manager poder habilitar a otimização de público-alvo para editores, você deve garantir que todos os pré-requisitos descritos neste artigo sejam atendidos. Entre em contato com o Atendimento ao cliente após verificar todos os pré-requisitos.

## Pré-requisitos para a ingestão de registro DFP {#prereqs-dfp-ingestion}

Observe que o processo descrito nesta seção deve ser concluído *antes* que você passe para os pré-requisitos para a ativação da ingestão de log.

Para usar arquivos de registro DFP ( [!DNL DoubleClick For Publishers]) em [!DNL Audience Manager], primeiro defina a ID de usuário exclusiva (UUID) [do](../../../reference/ids-in-aam.md) Audience Manager na chamada de tag de anúncio. Ao fazer isso, nossa ID é incluída nos registros DFP e podemos corresponder IDs entre DFP e [!DNL Audience Manager]. Use [!DNL Audience Manager] o código ou o [!UICONTROL DIL] para definir a [!UICONTROL Audience Management Module] [!DNL Audience Manager] UUID em um cookie primário.

Veja como definir a [!DNL Audience Manager] ID na chamada de tag do anúncio, como explicado em nossa documentação:

* [Via Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
* [Por um destino de cookie](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)

Você mesmo precisa definir a [!DNL Audience Manager] ID e pode trabalhar com [!DNL Audience Manager] consultoria para verificar se tudo funciona. Você definiu a [!DNL Audience Manager] ID corretamente se:

* `'aamid'` é a chave usada como o identificador.
* O valor da ID de usuário está formatado corretamente como o UUID, conforme descrito em nosso [!DNL Audience Manager] Índice de IDs no Audience Manager [](../../../reference/ids-in-aam.md).
* Você incluiu o [!DNL Audience Manager] UUID em um campo definido em seus logs do DFP (por exemplo, CustomTargeting).

## Pré-requisitos para a ativação de ingestão de registro {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>Confirme se as etapas necessárias para definir o UUID do Audience Manager <span class="keyword"></span> (descritas acima) foram concluídas antes de passar para a Etapa 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Atendimento ao cliente ou consultoria do Audience Manager</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 2 </p> </td> 
   <td colname="col2"> <p>Seu administrador DFP cria: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Uma conta de serviço para assimilar registros DFP no <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Novas credenciais. <p>Observação:  Isso pode exigir um endereço de email exclusivo específico para este projeto e será usado ao fornecer acesso ao Google Storage Bucket. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Uma chave privada (credencial com base em JSON) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Seu administrador DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 3 </p> </td> 
   <td colname="col2"> <p>Seu administrador DFP concede acesso à API à conta de serviço. Essa etapa permite o acesso aos metadados para delinear dimensões (itens de linha, pedidos, criações). <p>Observação:  Use o acesso por email da conta de serviço que você configurou na etapa 2 para conceder permissão de acesso à API. </p> </p> </td> 
   <td colname="col3"> <p>Seu administrador DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 4 </p> </td> 
   <td colname="col2"> <p>Seu administrador DFP estabelece acesso ao Google Storage Bucket. Lembre-se: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Isso pode ser feito através de um grupo do Google. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Associe o endereço de email exclusivo atribuído à conta de serviço ao bucket de armazenamento. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Seu administrador DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 5 </p> </td> 
   <td colname="col2"> <p>Seu administrador DFP fornece a ID de rede DFP. Isso nos permite transmitir a ID da rede ao fazer chamadas para a API. </p> </td> 
   <td colname="col3"> <p>Seu administrador DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 6 </p> </td> 
   <td colname="col2"> <p>Compile os pré-requisitos em um email para o Atendimento ao cliente do AAM (aamsupport@adobe.com) para iniciar o processo de ingestão de log. Rasgue o email usando o modelo na próxima seção. </p> </td> 
   <td colname="col3"> <p>Você ou <span class="keyword"> Audience Manager</span> Consulting em seu nome </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modelo de e-mail {#email-template}

Para finalizar a ativação de ingestão de registro, envie-nos um email para aamsupport@adobe.com. Use o modelo [de email](assets/enable_dfp_ingestion.txt)anexado.
