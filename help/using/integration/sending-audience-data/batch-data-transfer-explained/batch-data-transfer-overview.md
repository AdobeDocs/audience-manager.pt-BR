---
description: Uma visão geral dos clientes técnicos e não técnicos que desejam trazer dados de outros sistemas (offline) para o Audience Manager.
keywords: entrada, lote, carregamento em lote, dados em lote
seo-description: Uma visão geral dos clientes técnicos e não técnicos que desejam trazer dados de outros sistemas (offline) para o Audience Manager. Para fazer isso, use a opção de upload em lote no Audience Manager.
seo-title: Enviar dados em lote para a visão geral do Audience Manager
solution: Audience Manager
title: Enviar dados em lote para a visão geral do Audience Manager
uuid: 472583 b 1-5057-4 add -8 e 3 c -5 e 50762 c 88 e 0
translation-type: tm+mt
source-git-commit: 2e3adc8f0b2fe6efd9ca57f1d763ee4476d2edee

---


# Enviar dados em lote para a visão geral do Audience Manager{#send-batch-data-to-audience-manager-overview}

Uma visão geral dos clientes técnicos e não técnicos que desejam trazer dados de outros sistemas (offline) para o Audience Manager.

## Benefícios

<!-- c_offline_to_online.xml -->

Você pode disponibilizar dados de outros sistemas no Audience Manager. Nosso sistema pode ajudá-lo a desbloquear o valor e aproveitar os dados do usuário que você coleta anteriormente. Isso inclui informações sobre compras, pesquisas de clientes, dados de registro, [!DNL CRM] bancos de dados etc. Embora cada integração apresente seus próprios desafios, todos compartilham essas etapas comuns. Analise este material para ajudar a reduzir o esforço necessário para colocar seus dados offline online.

## Etapa 1: Sincronizar IDs de usuário

Durante a sincronização, o Audience Manager atribui IDs exclusivas a clientes e seus usuários. Essas IDs são conhecidas como [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) e [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectivamente. O Audience Manager usa [!UICONTROL DPID] o e [!UICONTROL UUID] para identificar usuários e qualificá-los para características, segmentos, grupos de público-alvo e para relatórios. Além disso, nosso código de coleta de dados ([!UICONTROL DIL]) procura por essas IDs para capturar dados de visitantes do site. Quando esta etapa for concluída, o Audience Manager e seu repositório offline deverão conter IDs correspondentes para cada registro do usuário.

Considerações importantes sobre esta etapa:

* **Posicionamento da ID do cliente:** O Audience Manager precisa saber onde a ID do cliente aparece em seu site (por exemplo, é armazenada em um cookie, uma variável do Analytics, no código da página etc.).
* **Excluir[!DNL PII]:** As IDs de usuário não devem conter informações de identificação pessoal ([!DNL PII]).
* **Caso e sensibilidade do conteúdo:** Durante uma sincronização de dados em tempo real, as IDs de usuário capturadas no site pelo Audience Manager devem corresponder às IDs passadas do repositório offline. Por exemplo, se registros offline contêm informações sobre [!DNL User123], mas o site renderiza essa ID como [!DNL USER123], o Audience Manager vê esses visitantes como visitantes diferentes. Como resultado, as informações online para esse visitante não podem ser associadas aos registros correspondentes no banco de dados offline. As IDs devem corresponder exatamente.

See [ID Synchronization for Inbound Data Transfers](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

<!-- 

<p> <b>Step 2: Create a Translation File</b> </p> 
<p>A translation file classifies data according to uniform and logical hierarchy. It is a taxonomy that helps you organize information from general categories (e.g., geography) to more precise classifications (e.g., <i>geography > United States > New York</i>). Also, it labels data with to easy to understand names such as "gender=male" or "color=green" instead of with your internal SKUs, abbreviations, or other names. The file lets Audience Manager display this information in a readable, logical manner. You and your data partners must create and share the translation file with Audience Manager before any real-time or server-to-server data transfers can begin. You can update this file on a schedule relevant to your business needs. </p> 
<p>Important considerations about this step: </p> 
<ul id="ul_6A05AECB0BD649B1BF1B34058E9008E2"> 
 <li id="li_39817ED898F14156A77FCAC066FE0968"> <b>Create a comprehensive list:</b> The translation file must include all the possible values that can be passed in on a particular key. For example, if you have category key called "color" and it accepts the values "red," "green," and "blue," the translation file must contain <i>all</i> those elements. </li> 
 <li id="li_19CAD7683BCF45278E2991C1EDBC9903"> <b>Case and content sensitivity:</b> The key-values in the file must match the values actually passed in to Audience Manager from your website. </li> 
</ul> 
<p>See DATA TRANSLATION FILE. </p>

 -->

## Etapa 2: Formato do arquivo de dados

Os nomes de arquivo e o conteúdo seguem diretrizes estritas. Você *deve* nomear e organizar arquivos de dados de acordo com essas especificações neste guia. Consulte:

* [Requisitos de nome Amazon S3 para arquivos de dados de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Conteúdo do arquivo de dados de entrada: Sintaxe, variáveis e exemplos](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Dados online estão disponíveis para os esforços de marketing offline

Ao trazer dados offline online, você ainda pode usar essas informações para campanhas offline. Para fazer isso, o Audience Manager exporta informações de características e segmentos para um [!DNL FTP] local ou [!DNL Amazon S3] sua escolha. Entre em contato com o gerenciador de Soluções do parceiro para obter mais informações ou assistência.

## Ambientes

O Audience Manager oferece os seguintes ambientes para a rejeição de arquivos:

<table id="table_A61AA64578944B23B5A7355F2A76E882"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ambiente </th> 
   <th colname="col02" class="entry"> Serviço </th> 
   <th colname="col2" class="entry"> Localização </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <b>Produção</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p> <code> ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <b>Ambiente beta</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p><code> sandbox-ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s 2 s-clients-sandbox-us-east -1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Leitura técnica adicional

Engenheiros de sistemas, desenvolvedores ou equipes técnicas/de implementação devem revisar [o Processo de transferência de dados em lote descrito](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) e os outros artigos nesta seção. Esses artigos fornecem detalhes sobre protocolos de transferência, conteúdo de arquivo e requisitos de nome de arquivo.