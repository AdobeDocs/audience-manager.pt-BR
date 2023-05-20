---
description: Respostas a perguntas ou problemas comuns relacionados à privacidade ou aos dados.
seo-description: Answers to common privacy- and data-related questions or issues.
seo-title: Privacy and Data Retention FAQ
solution: Audience Manager
title: Perguntas frequentes sobre privacidade e retenção de dados
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
feature: Data Governance & Privacy
exl-id: bccf49d7-1a3b-4286-86fb-59e472af4501
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 83%

---

# Perguntas frequentes sobre privacidade e retenção de dados{#privacy-and-data-retention-faq}

Respostas a perguntas ou problemas comuns relacionados à privacidade ou aos dados.

<!-- faq_privacy.xml -->

## Perguntas frequentes sobre privacidade {#privacy-faq}

>[!TIP]
>
>Visite o [Centro de privacidade da Adobe](https://www.adobe.com/br/privacy.html) para obter mais informações.

**Como o Audience Manager usa cookies e quais cookies ele define?**

Consulte [Cookies do Audience Manager](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html).

**Os clientes do Audience Manager nos EUA podem direcionar usuários em propriedades da UE?**

Sim. O Audience Manager trabalha com clientes que têm propriedades e inventário internacionais. A UE tem leis rigorosas de privacidade, mas o Audience Manager tem clientes que usam dados primários para direcionar públicos na Europa. O Audience Manager pode direcionar públicos da UE, mas é sua responsabilidade cumprir as regulamentações locais de privacidade.

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
   <td colname="col1"> <p>Servidores de back-end </p> </td> 
   <td colname="col2"> <p>120 dias </p> <p> O Audience Manager exclui os dados do usuário de nossos servidores de back-end 120 dias após a última visualização de um usuário na plataforma do Audience Manager. Se <span class="keyword"> Audience Manager</span> registra a atividade do usuário dentro desse ciclo de 120 dias. Manteremos esses dados por mais 120 dias. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores de borda </p> </td> 
   <td colname="col2"> <p> 14 dias </p> <p>O Audience Manager exclui os dados do usuário de nossos servidores de borda 14 dias após a última visualização de um usuário na plataforma do Audience Manager. Se <span class="keyword"> Audience Manager</span> O registra a atividade do usuário nesse ciclo de 14 dias. Manteremos esses dados por mais 14 dias. Se o usuário se tornar ativo novamente após o ciclo de 14 dias, haverá um atraso entre essa primeira visualização de página nova e quando o usuário se tornar acionável. Leva de 6 a 18 horas para que o perfil completo volte ao centro da borda após mais de 14 dias de inatividade. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registros brutos </p> </td> 
   <td colname="col2"> <p>60 dias (removidos após 60 dias sem atividade) </p> <p>Registros brutos são dados recebidos por um servidor de borda por meio de chamadas HTTP ou de arquivos integrados enviados para o <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Logs do servidor de anúncios </p> </td> 
   <td colname="col2"> <p><b>Relatório</b> </p> <p>Os arquivos de registro são mantidos para fins de relatórios por até 30 dias. Não conservamos registros sem correspondência (ou seja, registros para os quais não há sincronização de ID entre uma ID de servidor de visitante e a ID do <span class="keyword"> Audience Manager</span> ID) em nosso armazenamento de back-end e os logs correspondentes armazenados no <span class="keyword"> Amazon S3</span> são retidos por até 30 dias. </p> <p><b>Arquivo de registro acionável</b> </p> <p>Os registros correspondentes e não correspondentes são retidos por até 30 dias. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Perfis em nível de CRM (perfis autenticados) </p> </td> 
   <td colname="col2"> <p>O intervalo TTL (tempo de vida útil) padrão para perfis em nível de CRM inativos (IDs do cliente) é de 24 meses. No entanto, você pode usar a interface do usuário do Audience Manager para reduzir ou estender o intervalo TTL para perfis inativos em nível de CRM entre um mês e cinco anos. Isso pode ser feito ao criar ou editar uma fonte de dados entre dispositivos.</p> <p>Para obter mais informações, consulte Configurações da fonte de dados em <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Criar uma fonte de dados entre dispositivos </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IDs de dispositivo móvel </p> </td> 
   <td colname="col2"> <p>As condições de retenção para IDs de dispositivos móveis (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) seguem o ritmo descrito nas duas primeiras linhas, para servidores back-end e servidores de borda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feeds de dados do cliente (CDF) </p> </td> 
   <td colname="col2"> <p>Um arquivo CDF contém os mesmos dados que uma chamada de evento (/event) do <span class="keyword"> Audience Manager</span> envia para nossos servidores. O período de retenção é de 8 dias. Para obter mais detalhes sobre CDF, consulte <a href="../features/cdf-files.md"> Introdução ao CDF</a> e <a href="../faq/faq-cdf.md"> Perguntas frequentes sobre CDF</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mapeamentos entre IDs sincronizadas </p> </td> 
   <td colname="col2"> <p>A duração dos <a href="../features/administration/usage-limits.md#id-mapping-limits"> mapeamentos de ID</a> entre as IDs de cookie do Audience Manager (<a href="../reference/ids-in-aam.md">IDs de usuário exclusivas do Audience Manager ou UUIDs do AAM</a>) e IDs de cookie de terceiros é limitada a 120 dias. O tempo de vida do mapeamento de ID é redefinido sempre que o cookie do Audience Manager é visualizado na rede do Audience Manager. A sincronização de mapeamento de ID mais recente será preservada durante a vida útil da <a href="../reference/ids-in-aam.md">ID de usuário exclusiva do Audience Manager (UUID do AAM)</a>associada.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dados de entrada </p> </td> 
   <td colname="col2"> <p>São dados de entrada que você envia para o <span class="keyword">Audience Manager</span> por FTP ou diretamente para um diretório <span class="keyword">Amazon S3</span>. Consulte as <a href="../faq/faq-inbound-data-ingestion.md">Perguntas frequentes sobre assimilação de dados de entrada do cliente</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dados de saída </p> </td> 
   <td colname="col2"> <p>São os dados em lote que o <span class="keyword">Audience Manager</span> envia para parceiros de ativação de terceiros. O período de retenção é de 8 dias. Para obter mais detalhes sobre dados de saída, consulte <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md">Transferências em lote de saída</a>. </p> </td> 
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
   <td colname="col2"> <p>Nós impomos um limite de 100.000 qualificações de características para cada perfil de usuário. O limite se aplica a perfis autenticados e perfis de dispositivos. Se um perfil de usuário atingir esse limite, excluiremos as qualificações de característica mais antigas, em uma base de primeiro a entrar e primeiro a sair. </p> <p>Para obter mais detalhes, leia o <a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit">Limite de qualificação de características</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
