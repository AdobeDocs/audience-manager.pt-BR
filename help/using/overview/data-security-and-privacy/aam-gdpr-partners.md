---
description: Esta página descreve as informações fornecidas diretamente pelos nossos parceiros, conforme elas ficam disponíveis, juntamente com quaisquer implicações relacionadas à sua prática do Audience Manager. As principais implicações para os parceiros que efetuaram estas atualizações são o resultado do RGPD (Regulamento geral de proteção de dados), que entrou em vigor em 25 de maio de 2018 e do novo Quadro IAB de Transparência e Consentimento do RGPD (Quadro IAB).
seo-description: Esta página descreve as informações fornecidas diretamente pelos nossos parceiros, conforme elas ficam disponíveis, juntamente com quaisquer implicações relacionadas à sua prática do Audience Manager. As principais implicações para os parceiros que efetuaram estas atualizações são o resultado do RGPD (Regulamento geral de proteção de dados), que entrou em vigor em 25 de maio de 2018 e do novo Quadro IAB de Transparência e Consentimento do RGPD (Quadro IAB).
seo-title: Considerações sobre RGPD para Destinos
solution: Audience Manager
title: Considerações sobre RGPD para Destinos
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: 48d2060df55a693a768e956f88a5a03414435ba9

---


# Considerações sobre RGPD para Destinos{#gdpr-considerations-for-destinations}

Esta página descreve as informações fornecidas diretamente pelos nossos parceiros, conforme elas ficam disponíveis, juntamente com quaisquer implicações relacionadas à sua prática do Audience Manager. As principais implicações para os parceiros que efetuaram estas atualizações são o resultado do RGPD (Regulamento geral de proteção de dados), que entrou em vigor em 25 de maio de 2018 e do novo Quadro IAB de Transparência e Consentimento do RGPD (Quadro IAB).

Os parceiros da Adobe são proprietários de seus processos comerciais e podem decidir atualizar seus requisitos de integração com o Audience Manager de tempos em tempos. Estamos trabalhando proativamente com nosso ecossistema de parceiros do Audience Manager para manter nossos clientes informados sobre as mudanças.

<!-- ## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

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
</table> -->

## Atualização da interface do usuário do Audience Manager - Integração do Yahoo/Oath/DataX {#ui-update}

Além das atualizações à Estrutura IAB mencionadas acima, o Yahoo/Oath/DataX adicionou novos parâmetros, **gdpr** e **gdpr_mode**, às APIs de taxonomia e de público-alvo. Seus parâmetros informam ao Yahoo/Oath/DataX que eles têm os direitos de processar um determinado segmento como um Processador de dados ou como um Controlador de dados. Como resultado, os clientes do Audience Manager que enviam segmentos para um destino Yahoo/Oath/DataX devem designar o parâmetro apropriado (Processador ou Controlador), com base em seu acordo com Oath.

Entre em contato com seu Consultor ou com o Client Care para definir o parâmetro correto. A Adobe não pode fazer esta atualização em nome de um cliente, a menos que recebamos correspondência por escrito, solicitando esta atualização. Entre em contato com seu representante do Yahoo/Oath/DataX para entender a definição completa desses parâmetros.
