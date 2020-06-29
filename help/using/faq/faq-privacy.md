---
description: Respostas a perguntas ou problemas comuns relacionados à privacidade ou aos dados.
seo-description: Respostas a perguntas ou problemas comuns relacionados à privacidade ou aos dados.
seo-title: Perguntas frequentes sobre privacidade e retenção de dados
solution: Audience Manager
title: Perguntas frequentes sobre privacidade e retenção de dados
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
feature: Data Governance and Privacy
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 5%

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

Respostas a perguntas ou problemas comuns relacionados à privacidade ou aos dados.

<!-- faq_privacy.xml -->

## Perguntas frequentes sobre privacidade {#privacy-faq}

>[!TIP]
>
>Visite o Centro [de privacidade da](https://www.adobe.com/privacy.html) Adobe para obter mais informações.

**Como o Audience Manager usa cookies e quais cookies ele define?**

See [Audience Manager Cookies](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html).

**Clientes Audience Manager nos públicos alvos dos EUA podem usar propriedades da UE?**

Sim. O Audience Manager trabalha com clientes que têm propriedades e estoque internacionais. A UE tem leis rigorosas sobre privacidade, mas a Audience Manager tem clientes que usam dados primários para segmentação de audiências na Europa. O Audience Manager pode oferecer suporte à definição de metas para audiências da UE, mas é sua responsabilidade cumprir as regulamentações locais de privacidade.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Perguntas frequentes sobre a retenção de dados {#data-retention-faq}

A tabela a seguir lista os tempos de retenção para diferentes tipos de dados e sistemas de armazenamento.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de dados, Fonte ou Armazenamento </th> 
   <th colname="col2" class="entry"> Período da retenção de dados </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Servidores de back-end </p> </td> 
   <td colname="col2"> <p>120 dias. </p> <p> O Audience Manager exclui os dados do usuário de nossos servidores back-end 120 dias após a última visualização de um usuário na plataforma do Audience Manager. Se o <span class="keyword"> Audience Manager</span> registrar a atividade do usuário dentro desse ciclo de 120 dias, manteremos esses dados por mais 120 dias. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores Edge </p> </td> 
   <td colname="col2"> <p> 14 dias. </p> <p>O Audience Manager exclui os dados do usuário de nossos servidores de borda 14 dias após a última visualização de um usuário na plataforma do Audience Manager. Se o <span class="keyword"> Audience Manager</span> registrar a atividade do usuário dentro desse ciclo de 14 dias, manteremos esses dados por mais 14 dias. Se o usuário se tornar ativo novamente após o período de 14 dias, haverá um atraso entre essa primeira visualização de página nova e quando o usuário se tornar acionável. Leva de 6 a 18 horas para que o perfil completo volte ao centro da borda após mais de 14 dias de inatividade. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registros brutos </p> </td> 
   <td colname="col2"> <p>180 dias (removidos após 180 dias sem atividade). </p> <p>Registros brutos são dados recebidos por um servidor de borda por meio de chamadas HTTP ou de arquivos integrados enviados para o <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Logs do servidor de anúncios </p> </td> 
   <td colname="col2"> <p><b>Relatórios</b> </p> <p>Os arquivos de registro são mantidos para fins de relatórios por até 30 dias. Não persistimos registros inigualáveis (ou seja, registros para os quais não há sincronização de ID entre uma ID de servidor de anúncio de visitante <span class="keyword"> e a ID de</span> Audience Manager) em nosso armazenamento de backend, e os registros correspondentes armazenados no <span class="keyword"> Amazon S3</span> são mantidos por até 30 dias. </p> <p><b>Arquivo de registro acionável</b> </p> <p>Both matched and unmatched logs are retained for up to 30 days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>perfis de nível CRM (perfis autenticados) </p> </td> 
   <td colname="col2"> <p>O intervalo TTL (time-to-live) padrão para perfis de nível CRM inativos (IDs do cliente) é de 24 meses. However, you can use the Audience Manager user interface to reduce or extend the TTL interval for inactive CRM-level profiles between one month and 5 years. Isso pode ser feito ao criar ou editar uma fonte de dados entre dispositivos.</p> <p>For more information, see Data Source Settings in <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile Device IDs </p> </td> 
   <td colname="col2"> <p>As condições de retenção para IDs de dispositivos móveis (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) seguem a cadência descrita nas duas primeiras linhas, servidores back-end e servidores de borda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feeds de dados do cliente (CDF) </p> </td> 
   <td colname="col2"> <p>Um arquivo CDF contém os mesmos dados que uma chamada de <span class="keyword"> evento</span> (/evento) envia para nossos servidores. O período de retenção é de 8 dias. Para obter mais detalhes sobre o CDF, consulte as Perguntas frequentes sobre a Introdução <a href="../features/cdf-files.md"> do</a> CDF e sobre o <a href="../faq/faq-cdf.md"> CDF</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mapeamentos entre IDs sincronizadas </p> </td> 
   <td colname="col2"> <p>A duração dos mapeamentos <a href="../features/administration/usage-limits.md#id-mapping-limits"> de</a> ID entre IDs de cookie de Audience Manager (IDs de usuário<a href="../reference/ids-in-aam.md">Audience Manager ou UUIDs</a>de AAM) e IDs de cookie de terceiros é limitada a 120 dias. O tempo de vida do mapeamento de ID é redefinido sempre que o cookie Audience Manager é visualizado na rede Audience Manager. A sincronização de mapeamento de ID mais recente será preservada durante a vida útil da ID de usuário exclusiva do <a href="../reference/ids-in-aam.md">Audience Manager (UUID do AAM)</a>associada.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dados de entrada </p> </td> 
   <td colname="col2"> <p>Esses são dados de entrada enviados para o <span class="keyword"> Audience Manager</span> por FTP ou diretamente para um diretório <span class="keyword"> Amazon S3</span> . Consulte as Perguntas frequentes sobre <a href="../faq/faq-inbound-data-ingestion.md"></a>a assimilação de dados de cliente de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dados de saída </p> </td> 
   <td colname="col2"> <p>Esses são os dados em lote que o Audience Manager <span class="keyword"></span> envia para parceiros de ativação de terceiros. O período de retenção é de 8 dias. Para obter mais detalhes sobre os dados de Saída, consulte Transferências <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"></a>em Lote de Saída. </p> </td> 
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
   <td colname="col2"> <p>A exclusão de uma característica remove os dados de qualificação de característica de todos os perfis de usuário que se qualificaram para a característica anterior. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite de características atingido </p> </td> 
   <td colname="col2"> <p>Nós impomos um limite de 100.000 qualificações de características para cada perfil de usuário. O limite se aplica a perfis autenticados e perfis de dispositivos. Se um perfil de usuário atingir esse limite, excluiremos as qualificações de característica mais antigas, em uma base de primeiro a entrar e primeiro a sair. </p> <p>Para obter mais detalhes, leia nosso Limite <a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit"></a>de qualificação de características. </p> </td> 
  </tr> 
 </tbody> 
</table>

