---
description: Uma visão geral para clientes técnicos e não técnicos que desejam trazer dados de outros sistemas (offline) para o Audience Manager.
keywords: entrada, lote, upload em lote, dados em lote
seo-description: Uma visão geral para clientes técnicos e não técnicos que desejam trazer dados de outros sistemas (offline) para o Audience Manager. Para fazer isso, use a opção de upload em lote no Audience Manager.
seo-title: Visão geral do processo de envio de dados em lote para o Audience Manager
solution: Audience Manager
title: Visão geral do processo de envio de dados em lote para o Audience Manager
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Transferências de dados de entrada
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 6%

---

# Enviar dados em lote para [!DNL Audience Manager] Visão geral {#send-batch-data-to-audience-manager-overview}

Uma visão geral para clientes técnicos e não técnicos que desejam trazer dados de outros sistemas (offline) para [!DNL Audience Manager].

## Benefícios

Você pode disponibilizar dados de outros sistemas em [!DNL Audience Manager]. Nosso sistema pode ajudar você a desbloquear valores e aproveitar os dados do usuário coletados anteriormente. Isso inclui informações sobre compras, pesquisas do cliente, dados de registro, bancos de dados [!DNL CRM] etc. Embora cada integração apresente seus próprios desafios, todos compartilham esses passos comuns. Revise este material para ajudar a reduzir o esforço necessário para colocar seus dados offline online.

## Etapa 1: Sincronizar IDs de usuário

Durante a sincronização, [!DNL Audience Manager] atribui IDs exclusivas aos clientes e seus usuários. Essas IDs são conhecidas como [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) e [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectivamente. [!DNL Audience Manager] O usa o  [!UICONTROL DPID] e  [!UICONTROL UUID] para identificar usuários e qualificá-los para  [!UICONTROL traits],  [!UICONTROL segments], grupos de público-alvo e para relatórios. Além disso, nosso código de coleta de dados ([!UICONTROL DIL]) procura essas IDs para capturar os dados do visitante do seu site. Quando essa etapa for concluída, [!DNL Audience Manager] e seu repositório offline deverá conter as IDs correspondentes para cada registro de usuário.

Considerações importantes sobre esta etapa:

* **Inserção da ID do cliente:** [!DNL Audience Manager] precisa saber onde a ID do cliente aparece em seu site (por exemplo, ela é armazenada em um cookie, em uma variável do Analytics, no código da página etc.).
* **Excluir  [!DNL PII]:** as IDs de usuário não devem conter informações de identificação pessoal ([!DNL PII]).
* **Diferenciação entre maiúsculas e minúsculas e conteúdo:** durante uma sincronização de dados em tempo real, as IDs de usuário capturadas do site pelo  [!DNL Audience Manager] devem corresponder às IDs passadas do repositório offline. Por exemplo, se os registros offline contêm informações sobre [!DNL User123], mas o site renderiza essa ID como [!DNL USER123], [!DNL Audience Manager] os vê como visitantes diferentes. Como resultado, as informações online desse visitante não podem ser associadas aos registros correspondentes no banco de dados offline. As IDs devem corresponder exatamente.

Consulte [Sincronização de ID para transferências de dados de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Etapa 2: Formato do arquivo de dados

Os nomes de arquivos e o conteúdo seguem diretrizes restritas. Você *deve* nomear e organizar arquivos de dados de acordo com essas especificações neste guia. Consulte:

* [Requisitos de nome Amazon S3 para arquivos de dados de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Conteúdo do arquivo de dados de entrada: Sintaxe, variáveis e exemplos](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Os dados online estão disponíveis para os esforços de marketing offline

Quando você adiciona dados offline online, ainda pode usar essas informações para campanhas offline. Para fazer isso, [!DNL Audience Manager] exporta informações de características e segmentos para um local [!DNL FTP] ou [!DNL Amazon S3] de sua escolha. Entre em contato com o gerente de soluções de parceiros para obter mais informações ou assistência.

## Ambientes

[!DNL Audience Manager] O fornece os seguintes ambientes para o menu suspenso de arquivos:

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
   <td colname="col2"> <p> <code> demdex-s2s-clients-sandbox-us-east-1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Leitura técnica adicional

Os engenheiros de sistemas, desenvolvedores ou equipes técnicas/de implementação devem analisar [Processo de transferência de dados em lote Descrito](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) e os outros artigos desta seção. Esses artigos fornecem detalhes sobre protocolos de transferência, conteúdo de arquivo e requisitos de nome de arquivo.
