---
description: Esta página descreve as informações fornecidas diretamente pelos parceiros, conforme elas estão disponíveis, juntamente com quaisquer implicações relacionadas à prática do Audience Manager. As principais implicações para os parceiros que fazem essas atualizações são o resultado do RGPD (Regulamento Geral de Proteção de Dados), que entrou em vigor em 25 de maio de 2018 e a nova IAB Framework & Transparency Framework (IAB Framework).
seo-description: Esta página descreve as informações fornecidas diretamente pelos parceiros, conforme elas estão disponíveis, juntamente com quaisquer implicações relacionadas à prática do Audience Manager. As principais implicações para os parceiros que fazem essas atualizações são o resultado do RGPD (Regulamento Geral de Proteção de Dados), que entrou em vigor em 25 de maio de 2018 e a nova IAB Framework & Transparency Framework (IAB Framework).
seo-title: Considerações do RGPD para destinos
solution: Audience Manager
title: Considerações do RGPD para destinos
uuid: e 8 a 40060-086 c -4 f 03-b 48 c -9 c 903 acb 7891
translation-type: tm+mt
source-git-commit: 69be038d0f2d31b6b5eda20041082c1890abc38f

---


# GDPR Considerations for Destinations{#gdpr-considerations-for-destinations}

Esta página descreve as informações fornecidas diretamente pelos parceiros, conforme elas estão disponíveis, juntamente com quaisquer implicações relacionadas à prática do Audience Manager. As principais implicações para os parceiros que fazem essas atualizações são o resultado do RGPD (Regulamento Geral de Proteção de Dados), que entrou em vigor em 25 de maio de 2018 e a nova IAB Framework &amp; Transparency Framework (IAB Framework).

A Adobe possui seus processos comerciais e pode decidir atualizar seus requisitos de integração com o Audience Manager ocasionalmente. Estamos trabalhando proativamente com o ecossistema de parceiro do Audience Manager para manter nossos clientes informados das mudanças.

## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

Alguns parceiros, conforme listados na tabela abaixo, alteraram seus requisitos de integração com o Audience Manager para incluir suporte com base na estrutura IAB, a fim de seguir os padrões do RGPD.

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
   <td colname="col1"> <p>Yahoo/Oath/datax </p> </td> 
   <td colname="col2"> <p>As sincronizações de ID para usuários na União Europeia são descartadas pelo parceiro </p> </td> 
   <td colname="col3"> <p>Live desde 22 de maio de 12 18 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Escritório comercial </p> </td> 
   <td colname="col2"> <p>As sincronizações de ID para usuários na União Europeia são descartadas pelo parceiro </p> </td> 
   <td colname="col3"> <p>Ainda não live </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>As sincronizações de ID para usuários na União Europeia são descartadas pelo parceiro </p> </td> 
   <td colname="col3"> <p>Ainda não live </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Liveramp </p> </td> 
   <td colname="col2"> <p>As sincronizações de ID para usuários na União Europeia são descartadas pelo parceiro </p> </td> 
   <td colname="col3"> <p>Ainda não live </p> </td> 
  </tr> 
 </tbody> 
</table>

## Audience Manager UI Update - Yahoo/Oath/DataX Integration {#ui-update}

In addition to the updates to the IAB Framework mentioned above, Yahoo/Oath/DataX has added new parameters, **gdpr** and **gdpr_mode**, to their taxonomy and Audience APIs. Seus parâmetros informam Yahoo/Oath/datax que eles têm os direitos de processar um determinado segmento como um Processador de dados ou como um Controlador de dados. Como resultado, os clientes do Audience Manager que enviam segmentos para um destino Yahoo/Oath/datax devem designar o parâmetro apropriado (Processador ou Controlador), com base em seu contrato com Oath.

Entre em contato com seu consultor ou com o Atendimento ao cliente para definir o parâmetro correto. A Adobe não pode fazer essa atualização em nome de um cliente, a menos que receberemos a correspondência por escrito, solicitando esta atualização. Entre em contato com seu representante Yahoo/Oath/datax para compreender a definição completa desses parâmetros.

## Audience Manager Partners With Unsegmentation Capabilities {#aam-partners-with-unsegmentation}

Para ajudar nossos clientes a automatizar solicitações de RGPD, o Audience Manager notifica nossos parceiros de ativação sobre solicitações de exclusão a partir de Itens de dados enviando as informações de dessegmento (ou remover segmentos).

No entanto, alguns de nossos parceiros de ativação:

1. Não é possível suportar solicitações de dessegmentação da Adobe e/ou
1. Não é possível receber atualizações de forma mais frequente do que uma vez em 30 dias.

Nesses casos, não é possível enviar solicitações de exclusão para parceiros de ativação de forma automatizada pelo Audience Manager. Download our [Partner Excel sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx) to see which Audience Manager activation partners support unsegment.
