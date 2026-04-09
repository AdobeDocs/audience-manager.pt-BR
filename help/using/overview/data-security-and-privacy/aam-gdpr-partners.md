---
description: Esta página descreve as informações fornecidas diretamente pelos nossos parceiros, conforme elas ficam disponíveis, juntamente com qualquer implicação relacionada à prática do Audience Manager. As principais implicações para os parceiros que fizeram estas atualizações são o resultado do GDPR (Regulamento Geral sobre a Proteção de Dados), que entrou em vigor em 25 de maio de 2018 e da nova Estrutura de transparência e consentimento do RGPD do IAB (Estrutura do IAB).
seo-description: This page outlines information provided directly by our partners, as it becomes available, along with any implications related to your Audience Manager practice. Key implications for partners making these updates are the result of GDPR (General Data Protection Regulation), which went into effect on May 25th, 2018 and the new IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-title: GDPR Considerations for Destinations
solution: Audience Manager
title: Considerações sobre o GDPR para destinos
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
feature: Data Governance & Privacy
exl-id: ff2aa030-94cd-45dc-a9a2-283b38ab5e46
TQID: https://experienceleague.adobe.com/QJr4SR9ZcwBH-xkX-0CJ23GQ09SDmkgTeN7Vl4djSb4
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 3c88464c2249b7848c9ae80ca4c0ed58fcb81070
workflow-type: tm+mt
source-wordcount: 298
ht-degree: 96%

---

# Considerações sobre o GDPR para destinos{#gdpr-considerations-for-destinations}

Esta página descreve as informações fornecidas diretamente pelos nossos parceiros, conforme elas ficam disponíveis, juntamente com qualquer implicação relacionada à prática do Audience Manager. As principais implicações para os parceiros que fizeram estas atualizações são o resultado do GDPR (Regulamento Geral sobre a Proteção de Dados), que entrou em vigor em 25 de maio de 2018 e da nova Estrutura de transparência e consentimento do RGPD do IAB (Estrutura do IAB).

Os parceiros da Adobe são proprietários de seus processos comerciais e podem decidir atualizar seus requisitos de integração com o Audience Manager ocasionalmente. Estamos trabalhando proativamente com nosso ecossistema de parceiros do Audience Manager para manter nossos clientes informados sobre as mudanças.

<!--
## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

Some partners, as listed in the table below, have changed their integration requirements with Audience Manager to include support based on the IAB Framework, in order to comply with GDPR standards.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Partner Name </p> </th> 
   <th colname="col2" class="entry"> <p>Expected Impact </p> </th> 
   <th colname="col3" class="entry"> <p>Status of the change </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Live since May 22nd 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trade Desk </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
 </tbody> 
</table>
-->

## Atualização da interface do usuário do Audience Manager - Integração do Yahoo/Oath/DataX {#ui-update}

Além das atualizações à Estrutura do IAB mencionadas acima, o Yahoo/Oath/DataX adicionou novos parâmetros, **gdpr** and **gdpr_mode**, às APIs de taxonomia e público-alvo. Seus parâmetros informam ao Yahoo/Oath/DataX que eles têm os direitos de processar um determinado segmento como um Processador de dados ou como um Controlador de dados. Como resultado, os clientes do Audience Manager que enviam segmentos para um destino Yahoo/Oath/DataX devem designar o parâmetro apropriado (Processador ou Controlador), com base no acordo feito com a Oath.

Entre em contato com seu Consultor ou com o Atendimento ao cliente para definir o parâmetro correto. A Adobe não pode fazer esta atualização em nome de um cliente, a menos que recebamos uma autorização por escrito solicitando a atualização. Entre em contato com o representante do Yahoo/Oath/DataX para entender a definição completa desses parâmetros.
