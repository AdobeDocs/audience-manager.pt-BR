---
description: Uma visão geral para clientes técnicos e não técnicos que desejam trazer dados de outros sistemas (offline) para o Audience Manager.
keywords: entrada, lote, upload em lote, dados em lote
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: Visão geral do envio de dados em lote para o Audience Manager
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 4%

---

# Visão geral do processo de envio de dados em lote para o [!DNL Audience Manager] {#send-batch-data-to-audience-manager-overview}

Uma visão geral para clientes técnicos e não técnicos que desejam trazer dados de outros sistemas (offline) para o [!DNL Audience Manager].

## Benefícios

Você pode disponibilizar dados de outros sistemas no [!DNL Audience Manager]. Nosso sistema pode ajudá-lo a desbloquear valor e aproveitar os dados do usuário coletados anteriormente. Isso inclui informações sobre compras, pesquisas com clientes, dados de registro, [!DNL CRM] bancos de dados, etc. Embora cada integração apresente seus próprios desafios, todas elas compartilham essas etapas comuns. Consulte este material para ajudar a reduzir o esforço necessário para colocar seus dados offline online.

## Etapa 1: sincronizar IDs de usuário

Durante a sincronização, o [!DNL Audience Manager] atribui IDs exclusivas aos clientes e seus usuários. Essas IDs são conhecidas como [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) e [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectivamente. [!DNL Audience Manager] usa [!UICONTROL DPID] e [!UICONTROL UUID] para identificar usuários e qualificá-los para [!UICONTROL traits], [!UICONTROL segments], grupos de público-alvo e relatórios. Além disso, nosso código de coleta de dados ([!UICONTROL DIL]) procura essas IDs para capturar dados de visitantes de seu site. Quando esta etapa for concluída, [!DNL Audience Manager] e seu repositório offline deverão conter IDs correspondentes para cada registro de usuário.

Considerações importantes sobre esta etapa:

* **Posicionamento da ID do cliente:** O [!DNL Audience Manager] precisa saber onde a ID do cliente aparece no seu site (por exemplo, se ela está armazenada em um cookie, uma variável do Analytics, no código da página etc.).
* **Excluir [!DNL PII]:** as IDs de usuário não devem conter informações pessoalmente identificáveis ([!DNL PII]).
* **Diferenciação de maiúsculas e minúsculas e conteúdo:** Durante uma sincronização de dados em tempo real, as IDs de usuário capturadas do seu site pelo [!DNL Audience Manager] devem corresponder às IDs passadas do seu repositório offline. Por exemplo, se os registros offline contiverem informações sobre [!DNL User123], mas o site renderizar essa ID como [!DNL USER123], [!DNL Audience Manager] os verá como visitantes diferentes. Como resultado, as informações online desse visitante não podem ser associadas aos registros correspondentes no banco de dados offline. As IDs devem corresponder exatamente.

Consulte [Sincronização de ID para Transferências de Dados de Entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Etapa 2: Formato de Arquivo de Dados

Os nomes e o conteúdo dos arquivos seguem diretrizes rigorosas. Você *deve* nomear e organizar arquivos de dados de acordo com essas especificações neste guia. Consulte:

* [Requisitos de nome Amazon S3 para arquivos de dados de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Conteúdo do arquivo de dados de entrada: sintaxe, variáveis e exemplos](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Os dados online estão disponíveis para os esforços de marketing offline

Quando você coloca os dados offline online, ainda pode usar essas informações para campanhas offline. Para fazer isso, o [!DNL Audience Manager] exporta informações de características e segmentos para um local [!DNL FTP] ou [!DNL Amazon S3] de sua escolha. Entre em contato com o gerente de soluções de parceiros para obter mais informações ou assistência.

## Ambientes

[!DNL Audience Manager] fornece os seguintes ambientes para entrega de arquivos:

| Ambiente | Serviço | Localização |
|---------|----------|---------|
| Produção | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients</li><li>ftp-in.demdex.com</li></ul> |
| Ambiente do Beta | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients-sandbox-us-east-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style="table-layout:auto"}

## Leitura técnica adicional

Engenheiros de sistemas, desenvolvedores ou equipes técnicas/de implementação devem revisar o [Processo de transferência de dados em lote descrito](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) e os outros artigos desta seção. Estes artigos fornecem detalhes sobre protocolos de transferência, conteúdo de arquivos e requisitos de nome de arquivo.
