---
description: Uma visão geral para clientes técnicos e não técnicos que desejam trazer dados de outros sistemas (offline) para o Audience Manager.
keywords: entrada, lote, upload em lote, dados em lote
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: Visão geral do processo de envio de dados em lote para o Audience Manager
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 6%

---

# Enviar dados em lote para o [!DNL Audience Manager] Visão geral {#send-batch-data-to-audience-manager-overview}

Uma visão geral para clientes técnicos e não técnicos que desejam trazer dados de outros sistemas (offline) para [!DNL Audience Manager].

## Benefícios

Você pode disponibilizar dados de outros sistemas em [!DNL Audience Manager]. Nosso sistema pode ajudar você a desbloquear valores e aproveitar os dados do usuário coletados anteriormente. Isso inclui informações sobre compras, pesquisas do cliente, dados de registro, [!DNL CRM] bancos de dados, etc. Embora cada integração apresente seus próprios desafios, todos compartilham esses passos comuns. Revise este material para ajudar a reduzir o esforço necessário para colocar seus dados offline online.

## Etapa 1: Sincronizar IDs de usuário

Durante a sincronização, [!DNL Audience Manager] atribui IDs exclusivas a clientes e usuários. Essas IDs são conhecidas como [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) e [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectivamente. [!DNL Audience Manager] usa a variável [!UICONTROL DPID] e [!UICONTROL UUID] para identificar usuários e qualificá-los para [!UICONTROL traits], [!UICONTROL segments], grupos de público-alvo e para relatórios. Além disso, nosso código de coleta de dados ([!UICONTROL DIL]) procura essas IDs para capturar os dados de visitantes do seu site. Quando esta etapa for concluída, [!DNL Audience Manager] e seu repositório offline deve conter IDs correspondentes para cada registro de usuário.

Considerações importantes sobre esta etapa:

* **Inserção da ID do cliente:** [!DNL Audience Manager] O precisa saber onde a ID do cliente aparece em seu site (por exemplo, ele é armazenado em um cookie, uma variável do Analytics, no código da página etc.).
* **Excluir [!DNL PII]:** As IDs de usuário não devem conter informações de identificação pessoal ([!DNL PII]).
* **Diferenciação entre maiúsculas e minúsculas e conteúdo:** Durante uma sincronização de dados em tempo real, as IDs de usuário capturadas do site por [!DNL Audience Manager] deve corresponder às IDs passadas do repositório offline. Por exemplo, se registros offline contêm informações sobre [!DNL User123], mas seu site renderiza essa ID como [!DNL USER123], [!DNL Audience Manager] O os vê como visitantes diferentes. Como resultado, as informações online desse visitante não podem ser associadas aos registros correspondentes no banco de dados offline. As IDs devem corresponder exatamente.

Consulte [Sincronização de ID para transferências de dados de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Etapa 2: Formato do arquivo de dados

Os nomes de arquivos e o conteúdo seguem diretrizes restritas. Você *must* nomeie e organize arquivos de dados de acordo com essas especificações neste guia. Consulte:

* [Requisitos de nome Amazon S3 para arquivos de dados de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Conteúdo do arquivo de dados de entrada: Sintaxe, variáveis e exemplos](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Os dados online estão disponíveis para os esforços de marketing offline

Quando você adiciona dados offline online, ainda pode usar essas informações para campanhas offline. Para fazer isso, [!DNL Audience Manager] exporta informações de características e segmentos para um [!DNL FTP] ou [!DNL Amazon S3] local de sua escolha. Entre em contato com o gerente de soluções de parceiros para obter mais informações ou assistência.

## Ambientes

[!DNL Audience Manager] O fornece os seguintes ambientes para o menu suspenso de arquivos:

| Ambiente | Serviço | Localização |
|---------|----------|---------|
| Produção | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients</li><li>ftp-in.demdex.com</li></ul> |
| Ambiente beta | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients-sandbox-us-East-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Leitura técnica adicional

Os engenheiros de sistemas, desenvolvedores ou equipes técnicas/de implementação devem analisar [Descrição do processo de transferência de dados em lote](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) e os outros artigos desta seção. Esses artigos fornecem detalhes sobre protocolos de transferência, conteúdo de arquivo e requisitos de nome de arquivo.
