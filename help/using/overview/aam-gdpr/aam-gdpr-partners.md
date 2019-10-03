---
description: Esta página descreve as informações fornecidas diretamente pelos nossos parceiros, conforme elas ficam disponíveis, juntamente com quaisquer implicações relacionadas à sua prática do Audience Manager. As principais implicações para os parceiros que efetuaram estas atualizações são o resultado do RGPD (Regulamento geral de proteção de dados), que entrou em vigor em 25 de maio de 2018 e do novo Quadro IAB de Transparência e Consentimento do RGPD (Quadro IAB).
seo-description: Esta página descreve as informações fornecidas diretamente pelos nossos parceiros, conforme elas ficam disponíveis, juntamente com quaisquer implicações relacionadas à sua prática do Audience Manager. As principais implicações para os parceiros que efetuaram estas atualizações são o resultado do RGPD (Regulamento geral de proteção de dados), que entrou em vigor em 25 de maio de 2018 e do novo Quadro IAB de Transparência e Consentimento do RGPD (Quadro IAB).
seo-title: Considerações sobre RGPD para Destinos
solution: Audience Manager
title: Considerações sobre RGPD para Destinos
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: c238a37e1a72edb0679f657d0178e04b8d848ec2

---


# Considerações sobre RGPD para Destinos{#gdpr-considerations-for-destinations}

Esta página descreve as informações fornecidas diretamente pelos nossos parceiros, conforme elas ficam disponíveis, juntamente com quaisquer implicações relacionadas à sua prática do Audience Manager. As principais implicações para os parceiros que efetuaram estas atualizações são o resultado do RGPD (Regulamento geral de proteção de dados), que entrou em vigor em 25 de maio de 2018 e do novo Quadro IAB de Transparência e Consentimento do RGPD (Quadro IAB).

Os parceiros da Adobe são proprietários de seus processos comerciais e podem decidir atualizar seus requisitos de integração com o Audience Manager de tempos em tempos. Estamos trabalhando proativamente com nosso ecossistema de parceiros do Audience Manager para manter nossos clientes informados sobre as mudanças.

## Atualizações de parceiros do Audience Manager - Sincronizações de ID {#partner-updates-id-syncs}

Alguns parceiros, conforme listados na tabela abaixo, alteraram seus requisitos de integração com o Audience Manager para incluir suporte baseado no IAB Framework, a fim de cumprir com os padrões do RGPD.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nome do parceiro </p> </th> 
   <th colname="col2" class="entry"> <p>Impacto esperado </p> </th> 
   <th colname="col3" class="entry"> <p>Status da alteração </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>As sincronizações de ID para usuários na União Europeia são descartadas pelo parceiro </p> </td> 
   <td colname="col3"> <p>Ao vivo desde 22 de maio de 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gabinete Comercial </p> </td> 
   <td colname="col2"> <p>As sincronizações de ID para usuários na União Europeia são descartadas pelo parceiro </p> </td> 
   <td colname="col3"> <p>Ainda não vivo </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>As sincronizações de ID para usuários na União Europeia são descartadas pelo parceiro </p> </td> 
   <td colname="col3"> <p>Ainda não vivo </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>As sincronizações de ID para usuários na União Europeia são descartadas pelo parceiro </p> </td> 
   <td colname="col3"> <p>Ainda não vivo </p> </td> 
  </tr> 
 </tbody> 
</table>

## Atualização da interface do usuário do Audience Manager - Integração do Yahoo/Oath/DataX {#ui-update}

In addition to the updates to the IAB Framework mentioned above, Yahoo/Oath/DataX has added new parameters, gdpr and gdpr_mode, to their taxonomy and Audience APIs. ******** Seus parâmetros informam ao Yahoo/Oath/DataX que eles têm os direitos de processar um determinado segmento como um Processador de dados ou como um Controlador de dados. Como resultado, os clientes do Audience Manager que enviam segmentos para um destino Yahoo/Oath/DataX devem designar o parâmetro apropriado (Processador ou Controlador), com base em seu acordo com Oath.

Please reach out to your Consultant or Client Care to set the correct parameter. Adobe cannot make this update on behalf of a customer unless we receive written correspondence, requesting this update. Please reach out to your Yahoo/Oath/DataX representative to understand the full definition of these parameters.

## Audience Manager Partners With Unsegmentation Capabilities {#aam-partners-with-unsegmentation}

In order to help our customers automate GDPR requests, Audience Manager notifies our activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

However, some of our activation partners:

1. Cannot support unsegment requests from Adobe and/or
1. Are not able to receive updates from us more frequently than once in 30 days.

In those cases, you are not able to send delete requests to activation partners in an automated way through Audience Manager. Download our [Partner Excel sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-October2019.xlsx) to see which Audience Manager activation partners support unsegment.
