---
description: Configure um grupo do Google para trazer seus arquivos de dados do Google Campaign Manager para o Audience Manager. O conteúdo desta seção resume o processo de integração e fornece links para recursos do Google Campaign Manager para ajudá-lo a começar.
seo-description: Configure um grupo do Google para trazer seus arquivos de dados do Google Campaign Manager para o Audience Manager. O conteúdo desta seção resume o processo de integração e fornece links para recursos do Google Campaign Manager para ajudá-lo a começar.
seo-title: Importar arquivos de dados do Google Campaign Manager para o Audience Manager
solution: Audience Manager
title: Importar arquivos de dados do Google Campaign Manager para o Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 97129b435ab8e13def14bc85dcaab8254b2c4bda
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 3%

---


# Importar arquivos de dados do Google Campaign Manager para o Audience Manager {#import-dcm-data-files-into-audience-manager}

Configure um [!DNL Google] grupo para trazer seus arquivos [!DNL Google Campaign Manager] de dados para o Audience Manager. O conteúdo desta seção resume o processo de integração e fornece links para [!DNL Google Campaign Manager] recursos para ajudá-lo a começar.

## Resumo da integração

[!DNL Google Campaign Manager]O é o substituto de [!DNL Google] para [!DNL DoubleClick for Advertisers] (DFA). Similar to DFA, [!DNL Google Campaign Manager] customers can import, view, and work with their data in [!DNL Audience Manager]. Mas [!DNL Audience Manager] não é possível acessar e importar diretamente seus arquivos [!UICONTROL Data Transfer] e [!UICONTROL Match Table] arquivos. Para importar esses arquivos, o esforço se concentra no cliente.

No entanto, o procedimento de configuração está bem documentado na Ajuda [do Gerenciador de Campanhas](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456)DoubleClick. Além disso, você pode revisar as etapas listadas abaixo para começar.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] os arquivos de dados contêm dados para todos os anunciantes ou clientes. Se for necessário omitir clientes específicos, edite os arquivos antes de disponibilizá-los para [!DNL Audience Manager].

## Frequência e disponibilidade da transferência de dados

[!DNL Audience Manager] verifica e transfere dados uma vez por dia. Os dados geralmente estão disponíveis em [!DNL Audience Manager] após 24 horas.

## Etapas

1. [Criar um grupo](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Os grupos controlam o acesso aos seus [!DNL Google Campaign Manager] dados. Eventualmente, você convidará e adicionará [!DNL Audience Manager] a este grupo.

1. [Verifique o status](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456)do Armazenamento do Google Cloud.

   O Armazenamento do Google Cloud contém o grupo de dados que contém seu [!UICONTROL Data Transfer] e [!UICONTROL Match Tables]. Você precisará configurar um grupo ou verificar se o novo grupo tem acesso a um grupo de armazenamentos de dados existente.

1. [Obter um URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456)de arquivo de dados.

   Entre em contato com seu Gerente de [!DNL Google Campaign Manager] conta ou Consultor de soluções da Platform. Eles fornecerão um URL para seus arquivos de dados. [!DNL Google] pode alterar o formato para nomes de arquivo e de grupo em versões futuras. Novamente, entre em contato com seu Gerente de [!DNL Google Campaign Manager] conta para verificar se você está usando os formatos corretos.

1. [Defina permissões](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)de grupo.

   O [!DNL Cloud Storage Manager] permite controlar o compartilhamento de dados e o acesso por bucket. Dê ao seu grupo acesso de leitura ao grupo que contém seus arquivos [!UICONTROL Data Transfer] e [!UICONTROL Match Table] arquivos.

1. [Configure o compartilhamento](https://support.google.com/dcm/partner/answer/6206106?hl=en)de dados.

   As IDs de [!DNL Google Campaign Manager] usuário compartilhadas são criptografadas para proteger a privacidade. A criptografia adiciona 2 colunas ao final do arquivo de Transferência de dados `PartnerId1` e `PartnerId2`. Essas colunas contêm IDs de usuário codificadas específicas para cada empresa que recebe esses arquivos.

   Como um terceiro autorizado, [!DNL Audience Manager] pode receber [!DNL Google Campaign Manager] dados, mas não pode decodificá-los. Entretanto, do [!DNL Audience Manager] lado, sabemos como as IDs codificadas correspondem às nossas IDs. Isso significa que podemos combinar e sincronizar usuários com confiança e precisão.

   >[!NOTE]
   >Não é possível importar [!DNL Google Campaign Manager] arquivos para [!DNL Audience Manager] se você já estiver compartilhando dados com outros dois parceiros.

1. Convidar [!DNL Audience Manager] para participar do grupo.

   Depois de criar um grupo e conceder acesso a um grupo de dados, convide [!DNL Audience Manager] para entrar no grupo. Envie um email de convite para DFA-AAM@adobe.com. Certifique-se de incluir o URL do arquivo de dados da etapa 3. Nossas equipes internas trabalharão com você para verificar o acesso depois de aceitar o convite. 1. Configure duas fontes de dados para [!DNL Google Campaign Manager] os dados na interface [!DNL Audience Manager] do usuário.

   Nomeie as fontes de dados `Advertiser Analytics: DCM Platform` e `Advertiser Analytics: AAM+DCM Platform`. No fluxo de trabalho [Criar fontes](../../../features/manage-datasources.md#create-data-source) de dados, defina o tipo de ID como `Cookie`. Compartilhe as IDs das duas novas fontes de dados com nossas equipes internas.

1. Você pode criar facilmente características a partir dos [!DNL Google Campaign Manager] arquivos para os quais importa [!DNL Audience Manager]. Consulte Arquivos [de registro](../../../integration/media-data-integration/actionable-log-files.md) acionáveis e peça a seu [!DNL Audience Manager] consultor ou ao Atendimento ao cliente para ativar o recurso para você.
