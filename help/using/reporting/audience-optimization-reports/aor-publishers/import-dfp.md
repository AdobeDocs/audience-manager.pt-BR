---
description: Antes do Audience Manager poder habilitar a otimização de público-alvo para editores, você deve garantir que todos os pré-requisitos descritos neste artigo sejam atendidos. Entre em contato com o Atendimento ao cliente após verificar todos os pré-requisitos.
seo-description: Before Audience Manager can enable Audience Optimization for Publishers, you must ensure that all prerequisites outlined in this article are met. Contact Customer Care after checking off all prerequisites.
seo-title: Import Google Ad Manager Data Files Into Audience Manager
solution: Audience Manager
title: Importar arquivos de dados do Google Ad Manager para o Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: Audience Optimization Reports
exl-id: 62b72dd1-e664-4c6a-8c0a-f7a662d62a47
source-git-commit: 7147091e6c253e8124f5f21a2251c1a76ac9d808
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 13%

---

# Importação de arquivos de dados do Google Ad Manager (antigo DFP) para o Audience Manager{#import-dfp-data-files-into-audience-manager}

Antes do Audience Manager poder habilitar a otimização de público-alvo para editores, você deve garantir que todos os pré-requisitos descritos neste artigo sejam atendidos. Entre em contato com o Atendimento ao cliente após verificar todos os pré-requisitos.

## Pré-requisitos para assimilação de logs do Google Ad Manager {#prereqs-dfp-ingestion}

Observe que o processo descrito nesta seção deve ser concluído *antes* você segue para os pré-requisitos da ativação de assimilação de log.

Para utilizar [!DNL Google Ad Manager] (antigo Google DFP) arquivos de registro em [!DNL Audience Manager], você deve primeiro definir nosso [ID de usuário exclusiva (UUID) do Audience Manager](../../../reference/ids-in-aam.md) na chamada de tag de publicidade. Ao fazer isso, nossa ID é incluída na variável [!DNL Google Ad Manager] registros e podemos corresponder IDs entre [!DNL Google Ad Manager] e [!DNL Audience Manager]. Uso [!DNL Audience Manager] [!UICONTROL DIL] ou o [!UICONTROL Audience Management Module] para definir o [!DNL Audience Manager] UUID em um cookie próprio.

Veja como definir a variável [!DNL Audience Manager] ID na chamada de tag de publicidade, conforme explicado em nossa documentação:

* [Por meio da tag do Google Publisher (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Por meio de um destino de cookie](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

Você precisa definir o [!DNL Audience Manager] Identifique-se e possa trabalhar com [!DNL Audience Manager] consultoria para verificar se tudo funciona. Você definiu o [!DNL Audience Manager] Identifique corretamente se:

* `'aamid'` é a chave usada como o identificador.
* O valor da ID do usuário está formatado corretamente como a variável [!DNL Audience Manager] UUID, conforme descrito em nosso [Índice de IDs no Audience Manager](../../../reference/ids-in-aam.md).
* Você incluiu o [!DNL Audience Manager] UUID em um campo definido no [!DNL Google Ad Manager] logs (por exemplo, CustomTargeting).

## Pré-requisitos para a ativação da assimilação de logs {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>Confirme se as etapas necessárias para definir o <span class="keyword"> Audience Manager</span> A UUID (descrita acima) foi concluída antes da migração para a Etapa 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> Atendimento ao cliente ou consultoria </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 2 </p> </td> 
   <td colname="col2"> <p>O administrador do Google Ad Manager cria: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Uma conta de serviço para assimilar logons do Google Ad Manager no <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Novas credenciais. <p>Observação: isso pode exigir um endereço de e-mail exclusivo específico para esse projeto e será usado ao provisionar o acesso ao Google Storage Bucket. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Uma chave privada (credencial baseada em JSON) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Seu administrador do Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 3 </p> </td> 
   <td colname="col2"> <p>O administrador do Google Ad Manager concede acesso à API para a conta de serviço. Essa etapa permite o acesso aos metadados para definir dimensões (itens de linha, pedidos, criações). <p>Observação: use o acesso a email da conta de serviço que você configurou na etapa 2 para conceder permissão de acesso à API. </p> </p> </td> 
   <td colname="col3"> <p>Seu administrador do Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 4 </p> </td> 
   <td colname="col2"> <p>O administrador do Google Ad Manager estabelece acesso ao Google Storage Bucket. Lembre-se: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Isso pode ser feito por meio de um grupo do Google. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Associe o endereço de email exclusivo atribuído à conta de serviço ao bucket de armazenamento. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Seu administrador do Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 5 </p> </td> 
   <td colname="col2"> <p>O administrador do Google Ad Manager fornece a ID de rede do Google Ad Manager. Isso nos permite transmitir a ID de rede ao fazer chamadas para a API. </p> </td> 
   <td colname="col3"> <p>Seu administrador do Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etapa 6 </p> </td> 
   <td colname="col2"> <p>Compilar os pré-requisitos e abrir um tíquete de suporte seguindo as instruções detalhadas <a href="https://experienceleague.adobe.com/docs/customer-one/using/home.html">aqui</a> para iniciar o processo de assimilação de log. </p> </td> 
   <td colname="col3"> <p>Você ou <span class="keyword"> Audience Manager</span> Consultoria em seu nome </p> </td> 
  </tr> 
 </tbody> 
</table>
