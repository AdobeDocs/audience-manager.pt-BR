---
description: Respostas a perguntas ou problemas comuns relacionados à privacidade ou aos dados.
seo-description: Respostas a perguntas ou problemas comuns relacionados à privacidade ou aos dados.
seo-title: Perguntas frequentes sobre privacidade e retenção de dados
solution: Audience Manager
title: Perguntas frequentes sobre privacidade e retenção de dados
uuid: ef 558 fca -35 ff -44 f 1-8527-f 8 bee 9 f 2 c 7 e 9
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

Respostas a perguntas ou problemas comuns relacionados à privacidade ou aos dados.

<!-- faq_privacy.xml -->

## Privacy FAQ {#privacy-faq}

>[!TIP]
>
>Visit the [Adobe Privacy Center](https://www.adobe.com/privacy.html) for more information.

**Como o Audience Manager usa cookies e quais cookies ele define?**

See [Audience Manager Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html).

**Os clientes do Audience Manager podem usar os clientes do Audience Manager em propriedades EU?**

Sim. O Audience Manager trabalha com clientes que possuem propriedades internacionais e inventário. A UE possui leis de privacidade estritas, mas o Audience Manager tem clientes que usam dados primários para direcionamento de público-alvo na Europa. O Audience Manager pode suportar a definição de metas para públicos-alvo da UE, mas é sua responsabilidade cumprir com as regulamentações de privacidade locais.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Perguntas frequentes sobre a retenção de dados {#data-retention-faq}

A tabela a seguir lista os tempos de retenção para diferentes tipos de dados e sistemas de armazenamento.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de dados, fonte ou armazenamento </th> 
   <th colname="col2" class="entry"> Período da retenção de dados </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Servidores back-end </p> </td> 
   <td colname="col2"> <p>120 dias. </p> <p> O Audience Manager exclui dados do usuário de nossos servidores back-end 120 dias depois de ver um usuário na plataforma do Audience Manager. If <span class="keyword"> Audience Manager</span> records user activity within this 120-day cycle, we will keep this data for another 120-days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores Edge </p> </td> 
   <td colname="col2"> <p> 14 dias. </p> <p>O Audience Manager exclui dados do usuário de nossos servidores de borda 14 dias após a última visualização de um usuário na plataforma do Audience Manager. If <span class="keyword"> Audience Manager</span> records user activity in within this 14-day cycle, we will keep this data for another 14-days. Se o usuário ficar ativo novamente após o período de 14 dias, haverá um atraso entre essa primeira exibição de página e quando o usuário se tornar acionável. Leva 6-18 horas para retornar o perfil completo ao centro de borda após mais de 14 dias de inatividade. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Logs brutos </p> </td> 
   <td colname="col2"> <p>180 dias (removidos após 180 dias sem atividade). </p> <p>Raw logs are data received by an edge server via HTTP calls or from onboarded files sent in to <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Logs do servidor de publicidade </p> </td> 
   <td colname="col2"> <p><b>Relatório</b> </p> <p>Os arquivos de registro são retidos para fins de relatório por até 30 dias. We do not persist unmatched logs (i.e. logs for which there is no ID sync between a visitor's ad server ID and <span class="keyword"> Audience Manager</span> ID) in our backend storage, and matched logs stored in <span class="keyword"> Amazon S3</span> are retained for up to 30 days. </p> <p><b>Arquivo de registro acionável</b> </p> <p>Os logs correspondentes e não correspondentes são retidos por até 30 dias. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Perfis no nível do CRM (perfis autenticados) </p> </td> 
   <td colname="col2"> <p>O intervalo padrão de tempo padrão (TTL) para perfis inativos de nível CRM (IDs do cliente) é de 24 meses. No entanto, você pode usar a interface do usuário do Audience Manager para reduzir ou estender o intervalo TTL para perfis de nível CRM inativos entre um mês e 5 anos. Você pode fazer isso ao criar ou editar uma fonte de dados entre dispositivos.</p> <p>For more information, see Data Source Settings in <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IDs de dispositivo móvel </p> </td> 
   <td colname="col2"> <p>The retention conditions for mobile device IDs (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) follow the cadence described in the first two rows, back-end servers and edge servers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feeds de dados do cliente (CDF) </p> </td> 
   <td colname="col2"> <p>A CDF file contains the same data that an <span class="keyword"> Audience Manager</span> event call (/event) sends to our servers. O período de retenção é de 8 dias. For more details about CDF, please refer to <a href="../features/cdf-files.md"> CDF Intro</a> and <a href="../faq/faq-cdf.md"> CDF FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mapeamentos entre IDs sincronizadas </p> </td> 
   <td colname="col2"> <p>Mappings between synchronized IDs may be kept for the life of the associated <a href="../reference/ids-in-aam.md"> Audience Manager Unique User ID (AAM UUID)</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dados de entrada </p> </td> 
   <td colname="col2"> <p>This is inbound data you send to <span class="keyword"> Audience Manager</span> by FTP or directly to an <span class="keyword"> Amazon S3</span> directory. See the <a href="../faq/faq-inbound-data-ingestion.md"> Inbound Customer Data Ingestion FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dados de saída </p> </td> 
   <td colname="col2"> <p>This is the batch data that <span class="keyword"> Audience Manager</span> sends to third party activation partners. O período de retenção é de 8 dias. For more details about Outbound data, please refer to <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> Outbound Batch Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait Qualification Data Retention {#trait-qual}

A tabela abaixo lista as opções de retenção para as qualificações de características.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operação de característica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Excluir uma característica </p> </td> 
   <td colname="col2"> <p>Excluir uma característica remove os dados da qualificação de característica de todos os perfis de usuário qualificados para a característica no passado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite de características atingido </p> </td> 
   <td colname="col2"> <p>Nós impuímos um limite de qualifications 00,000 qualificações de característica para cada perfil do usuário. O limite se aplica a perfis autenticados e perfis de dispositivo. Se um perfil de usuário atingir esse limite, excluiremos as qualificações de característica mais antigas, de uma base inicial e primeira. </p> <p>For more details, read our <a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit"> Trait Qualification Limit</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

