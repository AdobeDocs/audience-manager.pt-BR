---
description: Esta página descreve as informações fornecidas diretamente pelos nossos parceiros, conforme elas ficam disponíveis, juntamente com quaisquer implicações relacionadas à sua prática do Audience Manager. As principais implicações para os parceiros que efetuaram estas atualizações são o resultado do RGPD (Regulamento geral de proteção de dados), que entrou em vigor em 25 de maio de 2018 e do novo Quadro IAB de Transparência e Consentimento do RGPD (Quadro IAB).
seo-description: Esta página descreve as informações fornecidas diretamente pelos nossos parceiros, conforme elas ficam disponíveis, juntamente com quaisquer implicações relacionadas à sua prática do Audience Manager. As principais implicações para os parceiros que efetuaram estas atualizações são o resultado do RGPD (Regulamento geral de proteção de dados), que entrou em vigor em 25 de maio de 2018 e do novo Quadro IAB de Transparência e Consentimento do RGPD (Quadro IAB).
seo-title: Considerações sobre RGPD para Destinos
solution: Audience Manager
title: Considerações sobre RGPD para Destinos
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: 69be038d0f2d31b6b5eda20041082c1890abc38f

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

Além das atualizações à Estrutura IAB mencionadas acima, o Yahoo/Oath/DataX adicionou novos parâmetros, **gdpr** e **gdpr_mode**, às APIs de taxonomia e de público-alvo. Seus parâmetros informam ao Yahoo/Oath/DataX que eles têm os direitos de processar um determinado segmento como um Processador de dados ou como um Controlador de dados. Como resultado, os clientes do Audience Manager que enviam segmentos para um destino Yahoo/Oath/DataX devem designar o parâmetro apropriado (Processador ou Controlador), com base em seu acordo com Oath.

Entre em contato com seu Consultor ou com o Client Care para definir o parâmetro correto. A Adobe não pode fazer esta atualização em nome de um cliente, a menos que recebamos correspondência por escrito, solicitando esta atualização. Entre em contato com seu representante do Yahoo/Oath/DataX para entender a definição completa desses parâmetros.

## Parceiros Do Audience Manager Com Recursos De Dessegmentação {#aam-partners-with-unsegmentation}

Para ajudar nossos clientes a automatizar as solicitações do RGPD, o Audience Manager notifica nossos parceiros de ativação sobre as solicitações de exclusão de Indivíduos de dados enviando-os para dessegmentar (ou remover segmentos) as informações.

Entretanto, alguns de nossos parceiros de ativação:

1. Não é possível suportar solicitações de cancelamento de segmento da Adobe e/ou
1. Não podem receber atualizações de nós com mais frequência do que uma vez em 30 dias.

Nesses casos, não é possível enviar solicitações de exclusão para parceiros de ativação de forma automatizada pelo Audience Manager. Baixe nossa planilha [do Excel do](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx) Parceiro para ver quais parceiros de ativação do Audience Manager suportam a anulação de segmentos.
