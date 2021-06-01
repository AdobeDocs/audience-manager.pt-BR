---
description: Configure um grupo do Google para trazer seus arquivos de dados do Google Campaign Manager para o Audience Manager. O conteúdo desta seção resume o processo de integração e fornece links para os recursos do Google Campaign Manager para ajudar você a começar.
seo-description: Configure um grupo do Google para trazer seus arquivos de dados do Google Campaign Manager para o Audience Manager. O conteúdo desta seção resume o processo de integração e fornece links para os recursos do Google Campaign Manager para ajudar você a começar.
seo-title: Importar arquivos de dados do Google Campaign Manager para o Audience Manager
solution: Audience Manager
title: Importar arquivos de dados do Google Campaign Manager para o Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Relatórios de otimização de público-alvo
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 3%

---

# Importar arquivos de dados do Google Campaign Manager para o Audience Manager {#import-dcm-data-files-into-audience-manager}

Configure um grupo [!DNL Google] para trazer seus arquivos de dados [!DNL Google Campaign Manager] para o Audience Manager. O conteúdo desta seção resume o processo de integração e fornece links para recursos [!DNL Google Campaign Manager] que ajudam a começar.

## Resumo da integração

[!DNL Google Campaign Manager]O é o substituto de [!DNL Google] para [!DNL DoubleClick for Advertisers] (DFA). Semelhante ao DFA, [!DNL Google Campaign Manager] os clientes podem importar, visualizar e trabalhar com seus dados em [!DNL Audience Manager]. Mas [!DNL Audience Manager] não pode acessar diretamente e importar seus arquivos [!UICONTROL Data Transfer] e [!UICONTROL Match Table]. Para importar esses arquivos, o esforço se concentra no cliente.

No entanto, o procedimento de configuração está bem documentado na [Ajuda do DoubleClick Campaign Manager](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). Além disso, você pode revisar as etapas listadas abaixo para começar.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] os arquivos de dados contêm dados para todos os anunciantes ou clientes. Se precisar omitir clientes específicos, edite os arquivos antes de disponibilizá-los para [!DNL Audience Manager].

## Frequência e disponibilidade da transferência de dados

[!DNL Audience Manager] O verifica e transfere dados uma vez por dia. Normalmente, os dados estão disponíveis em [!DNL Audience Manager] após 24 horas.

## Etapas

1. [Criar um grupo](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Os grupos controlam o acesso aos seus dados [!DNL Google Campaign Manager]. Eventualmente, você convidará e adicionará [!DNL Audience Manager] a este grupo.

1. [Verifique o status](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456) do armazenamento na nuvem do Google.

   O Armazenamento do Google Cloud contém o bucket de dados que contém seus [!UICONTROL Data Transfer] e [!UICONTROL Match Tables]. Você precisará configurar um bucket ou garantir que seu novo grupo tenha acesso a um bucket de armazenamento de dados existente.

1. [Obtenha um URL de arquivo de dados](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   Trabalhe com seu [!DNL Google Campaign Manager] Gerente de conta ou Consultor de soluções da plataforma. Eles fornecerão um URL para seus arquivos de dados. [!DNL Google] O pode alterar o formato de nomes de arquivo e de bucket em versões futuras. Novamente, trabalhe com seu [!DNL Google Campaign Manager] Gerente de conta para verificar se você está usando os formatos corretos.

1. [Defina permissões](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission) de bucket.

   O [!DNL Cloud Storage Manager] permite controlar o compartilhamento de dados e o acesso do bucket. Forneça ao seu grupo acesso de leitura ao bucket que contém seus arquivos [!UICONTROL Data Transfer] e [!UICONTROL Match Table].

1. [Configure o compartilhamento de dados](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   As IDs de usuário compartilhadas [!DNL Google Campaign Manager] são criptografadas para proteger a privacidade. A criptografia adiciona 2 colunas ao final do arquivo de Transferência de dados, `PartnerId1` e `PartnerId2`. Essas colunas contêm IDs de usuário codificadas específicas para cada empresa que recebe esses arquivos.

   Como um terceiro autorizado, [!DNL Audience Manager] pode receber dados [!DNL Google Campaign Manager], mas não pode decodificar as IDs. No entanto, no lado [!DNL Audience Manager], sabemos como as IDs codificadas correspondem às nossas IDs. Isso significa que podemos combinar e sincronizar usuários com confiança e precisão.

   >[!NOTE]
   >Não é possível importar arquivos [!DNL Google Campaign Manager] para [!DNL Audience Manager] se você já estiver compartilhando dados com dois outros parceiros de terceiros.

1. Convide [!DNL Audience Manager] para ingressar no grupo.

   Depois de criar um grupo e conceder a ele acesso a um bucket de dados, convide [!DNL Audience Manager] para ingressar no grupo. Envie um email de convite para DFA-AAM@adobe.com. Certifique-se de incluir o URL do arquivo de dados da etapa 3. Nossas equipes internas trabalharão com você para verificar o acesso depois de aceitar o convite. 1. Configure duas fontes de dados para [!DNL Google Campaign Manager] dados na [!DNL Audience Manager] Interface do Usuário.

   Nomeie as fontes de dados `Advertiser Analytics: DCM Platform` e `Advertiser Analytics: AAM+DCM Platform`. No workflow [Criar fontes de dados](../../../features/manage-datasources.md#create-data-source), defina o tipo de ID como `Cookie`. Compartilhe as IDs das duas novas fontes de dados com nossas equipes internas.

1. Você pode criar facilmente características dos arquivos [!DNL Google Campaign Manager] que você importa para [!DNL Audience Manager]. Consulte [Arquivos de registro acionáveis](../../../integration/media-data-integration/actionable-log-files.md) e solicite ao consultor [!DNL Audience Manager] ou ao Atendimento ao cliente que ative o recurso para você.
