---
description: Respostas a perguntas ou problemas comuns relacionados à privacidade ou aos dados.
seo-description: Respostas a perguntas ou problemas comuns relacionados à privacidade ou aos dados.
seo-title: ' Perguntas frequentes sobre privacidade e retenção de dados'
solution: Audience Manager
title: ' Perguntas frequentes sobre privacidade e retenção de dados'
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
translation-type: tm+mt
source-git-commit: 3a4f23bc853a2324a4c91c6e65b14455293a5b1b

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

Respostas a perguntas ou problemas comuns relacionados à privacidade ou aos dados.

<!-- faq_privacy.xml -->

##  Perguntas frequentes sobre privacidade {#privacy-faq}

>[!TIP]
>
>Visite o Centro [de privacidade da](https://www.adobe.com/privacy.html) Adobe para obter mais informações.

**Como o Audience Manager usa cookies e quais cookies ele define?**

See [Audience Manager Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html).

**Clientes do Audience Manager nos EUA podem direcionar usuários para propriedades da UE?**

Sim. O Audience Manager trabalha com clientes que têm propriedades e estoque internacionais. A UE tem leis rigorosas de privacidade, mas o Audience Manager tem clientes que usam dados primários para segmentação de público-alvo na Europa. O Audience Manager pode oferecer suporte à definição de metas para públicos da UE, mas é sua responsabilidade cumprir as regulamentações locais de privacidade.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Perguntas frequentes sobre a retenção de dados {#data-retention-faq}

A tabela a seguir lista os tempos de retenção para diferentes tipos de dados e sistemas de armazenamento.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de dados, origem ou armazenamento </th> 
   <th colname="col2" class="entry"> Período da retenção de dados </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Servidores de back-end </p> </td> 
   <td colname="col2"> <p>120-days. </p> <p> O Audience Manager exclui os dados do usuário de nossos servidores back-end 120 dias após a última visualização de um usuário na plataforma do Audience Manager. Se o <span class="keyword"> Audience Manager</span> registrar a atividade do usuário dentro desse ciclo de 120 dias, nós manteremos esses dados por mais 120 dias. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores Edge </p> </td> 
   <td colname="col2"> <p> 14-days. </p> <p>O Audience Manager exclui os dados do usuário de nossos servidores de borda 14 dias após a última visualização de um usuário na plataforma Audience Manager. Se o <span class="keyword"> Audience Manager</span> registrar a atividade do usuário dentro desse ciclo de 14 dias, nós manteremos esses dados por mais 14 dias. Se o usuário se tornar ativo novamente após o período de 14 dias, haverá um atraso entre essa primeira nova exibição de página e quando o usuário se tornar acionável. It takes 6-18 hours to get the full profile back out to the edge center after more than 14-days of inactivity. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Raw logs </p> </td> 
   <td colname="col2"> <p>180 dias (removidos após 180 dias sem atividade). </p> <p>Raw logs are data received by an edge server via HTTP calls or from onboarded files sent in to  Audience Manager.<span class="keyword"></span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ad Server Logs </p> </td> 
   <td colname="col2"> <p><b>Relatório</b> </p> <p>Log files are retained for reporting purposes for up to 30 days. We do not persist unmatched logs (i.e. logs for which there is no ID sync between a visitor's ad server ID and  Audience Manager ID) in our backend storage, and matched logs stored in  Amazon S3 are retained for up to 30 days.<span class="keyword"></span><span class="keyword"></span> </p> <p><b>Arquivo de registro acionável</b> </p> <p>Both matched and unmatched logs are retained for up to 30 days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM-level profiles (authenticated profiles) </p> </td> 
   <td colname="col2"> <p>The default time-to-live (TTL) interval for inactive CRM-level profiles (Customer IDs) is 24 months. However, you can use the Audience Manager UI to reduce or extend the TTL interval for inactive CRM-level profiles between one month and 5 years. You can accomplish this when creating or editing a Cross-Device data source.</p> <p>For more information, see Data Source Settings in  Create a Cross-Device Data Source .<a href="../features/profile-merge-rules/merge-rules-start.md#settings"></a></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile Device IDs </p> </td> 
   <td colname="col2"> <p>As condições de retenção para IDs de dispositivos móveis (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) seguem a cadência descrita nas duas primeiras linhas, servidores back-end e servidores de borda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Customer Data Feeds (CDF) </p> </td> 
   <td colname="col2"> <p>A CDF file contains the same data that an  Audience Manager event call (/event) sends to our servers. <span class="keyword"></span> O período de retenção é de 8 dias. Para obter mais detalhes sobre o CDF, consulte as Perguntas frequentes sobre a Introdução <a href="../features/cdf-files.md"> do</a> CDF e sobre o <a href="../faq/faq-cdf.md"> CDF</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mapeamentos entre IDs sincronizadas </p> </td> 
   <td colname="col2"> <p>A duração dos mapeamentos <a href="../features/administration/usage-limits.md#id-mapping-limits"> de</a> ID entre IDs de cookie do Audience Manager (IDs de usuário exclusivas do<a href="../reference/ids-in-aam.md">Audience Manager ou UUIDs</a>do AAM) e IDs de cookie de terceiros é limitada a 120 dias. O tempo de vida do mapeamento de ID é redefinido sempre que o cookie do Audience Manager é visualizado na rede do Audience Manager. A sincronização de mapeamento de ID mais recente será preservada durante a vida útil da ID de usuário exclusiva do <a href="../reference/ids-in-aam.md">Audience Manager (UUID do AAM)</a>associada.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dados de entrada </p> </td> 
   <td colname="col2"> <p>Esses são dados de entrada enviados para o <span class="keyword"> Audience Manager</span> por FTP ou diretamente para um diretório <span class="keyword"> Amazon S3</span> . Consulte as Perguntas frequentes sobre <a href="../faq/faq-inbound-data-ingestion.md"></a>a assimilação de dados de cliente de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dados de saída </p> </td> 
   <td colname="col2"> <p>Esses são os dados em lote que <span class="keyword"> o Audience Manager</span> envia para parceiros de ativação de terceiros. O período de retenção é de 8 dias. Para obter mais detalhes sobre os dados de Saída, consulte Transferências <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"></a>em Lote de Saída. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Retenção de dados de qualificação de característica {#trait-qual}

A tabela abaixo lista as opções de retenção para qualificações de características.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operação de características </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Excluir uma característica </p> </td> 
   <td colname="col2"> <p>A exclusão de uma característica remove os dados de qualificação de característica de todos os perfis de usuário qualificados para a característica anterior. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite de características atingido </p> </td> 
   <td colname="col2"> <p>Nós impomos um limite de 100.000 qualificações de características para cada perfil de usuário. O limite se aplica a perfis autenticados e perfis de dispositivo. Se um perfil de usuário atingir esse limite, excluiremos as qualificações de característica mais antigas, em uma base de primeiro a entrar e primeiro a sair. </p> <p>Para obter mais detalhes, leia nosso Limite <a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit"></a>de qualificação de características. </p> </td> 
  </tr> 
 </tbody> 
</table>

