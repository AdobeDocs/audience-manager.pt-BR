---
description: Antes do Audience Manager poder habilitar a otimização de público-alvo para editores, você deve garantir que todos os pré-requisitos descritos neste artigo sejam atendidos. Entre em contato com o Atendimento ao cliente após verificar todos os pré-requisitos.
seo-description: Antes do Audience Manager poder habilitar a otimização de público-alvo para editores, você deve garantir que todos os pré-requisitos descritos neste artigo sejam atendidos. Entre em contato com o Atendimento ao cliente após verificar todos os pré-requisitos.
seo-title: Importar arquivos de dados do Google Ad Manager para o Audience Manager
solution: Audience Manager
title: Importar arquivos de dados do Google Ad Manager para o Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: Relatórios de otimização de público-alvo
exl-id: 62b72dd1-e664-4c6a-8c0a-f7a662d62a47
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 17%

---

# Importar arquivos de dados do Google Ad Manager (antigo DFP) para o Audience Manager{#import-dfp-data-files-into-audience-manager}

Antes do Audience Manager poder habilitar a otimização de público-alvo para editores, você deve garantir que todos os pré-requisitos descritos neste artigo sejam atendidos. Entre em contato com o Atendimento ao cliente após verificar todos os pré-requisitos.

## Pré-requisitos para a assimilação de log do Google Ad Manager {#prereqs-dfp-ingestion}

Observe que o processo descrito nesta seção deve ser concluído *antes de* você seguir para os pré-requisitos para a ativação de assimilação de log.

Para usar arquivos de log [!DNL Google Ad Manager] (antigo Google DFP) em [!DNL Audience Manager], primeiro defina nossa [ID de usuário exclusiva (UUID) do Audience Manager](../../../reference/ids-in-aam.md) na chamada de tag de anúncio. Ao fazer isso, nossa ID é incluída nos logs [!DNL Google Ad Manager] e podemos corresponder IDs entre [!DNL Google Ad Manager] e [!DNL Audience Manager]. Use o código [!DNL Audience Manager] [!UICONTROL DIL] ou [!UICONTROL Audience Management Module] para definir a UUID [!DNL Audience Manager] em um cookie primário.

Veja como definir a ID [!DNL Audience Manager] na chamada de tag do anúncio, conforme explicado em nossa documentação:

* [Por meio da tag do Google Publisher (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Por meio de um destino de cookie](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

Você precisa definir a ID [!DNL Audience Manager] por conta própria e pode trabalhar com a consultoria [!DNL Audience Manager] para verificar se tudo funciona. Você definiu a ID [!DNL Audience Manager] corretamente se:

* `'aamid'` é a chave usada como o identificador.
* O valor da ID de usuário está formatado corretamente como o [!DNL Audience Manager] UUID, conforme descrito em nosso [Índice de IDs em Audience Manager](../../../reference/ids-in-aam.md).
* Você incluiu o [!DNL Audience Manager] UUID em um campo definido em seus logs [!DNL Google Ad Manager] (por exemplo, CustomTargeting).

## Pré-requisitos para a ativação de assimilação de log {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>Confirme se as etapas necessárias para definir a UUID <span class="keyword"> Audience Manager</span> (descritas acima) foram concluídas antes de passar para a Etapa 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience </span> ManagerAtendimento ao cliente ou consultoria </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 2 </p> </td> 
   <td colname="col2"> <p>O Administrador do Google Ad Manager cria: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Uma conta de serviço para assimilar o Google Ad Manager faz logon no <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Novas credenciais. <p>Observação:  Isso pode exigir um endereço de email exclusivo específico para esse projeto e será usado ao provisionar acesso ao Google Storage Bucket. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Uma chave privada (credencial baseada em JSON) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Administrador do Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 3 </p> </td> 
   <td colname="col2"> <p>O Administrador do Google Ad Manager concede acesso à API para a conta de serviço. Esta etapa permite que o acesso aos metadados defina dimensões (itens de linha, pedidos, criações). <p>Observação:  Use o acesso de email da conta de serviço configurada na etapa 2 para conceder permissão de acesso à API. </p> </p> </td> 
   <td colname="col3"> <p>Administrador do Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 4 </p> </td> 
   <td colname="col2"> <p>O Administrador do Google Ad Manager estabelece o acesso ao Google Storage Bucket. Lembre-se: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Isso pode ser feito através de um grupo do Google. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Associe o endereço de email exclusivo atribuído à conta de serviço ao bucket de armazenamento. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Administrador do Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 5 </p> </td> 
   <td colname="col2"> <p>Seu Administrador do Google Ad Manager fornece a ID de rede do Google Ad Manager. Isso nos permite transmitir a ID de rede ao fazer chamadas para a API. </p> </td> 
   <td colname="col3"> <p>Administrador do Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 6 </p> </td> 
   <td colname="col2"> <p>Compile os pré-requisitos em um e-mail para AAM Atendimento ao cliente (aamsupport@adobe.com) para iniciar o processo de ingestão de log. Rascunhe o e-mail usando o modelo na próxima seção. </p> </td> 
   <td colname="col3"> <p>Você ou <span class="keyword"> Audience Manager</span> Consultoria em seu nome </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modelo de email {#email-template}

Para finalizar a ativação da assimilação de log, envie um email para aamsupport@adobe.com. Use o [modelo de email anexado](assets/enable_dfp_ingestion.txt).
