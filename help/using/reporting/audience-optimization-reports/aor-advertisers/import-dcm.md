---
description: Configure um grupo do Google para trazer seus arquivos de dados do Google Campaign Manager para o Audience Manager. O conteúdo desta seção resume o processo de integração e fornece links para os recursos do Google Campaign Manager para ajudar você a começar.
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: Importar arquivos de dados do Google Campaign Manager para o Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 2%

---

# Importar arquivos de dados do Google Campaign Manager para o Audience Manager {#import-dcm-data-files-into-audience-manager}

Configure um grupo [!DNL Google] para trazer seus arquivos de dados [!DNL Google Campaign Manager] para o Audience Manager. O conteúdo desta seção resume o processo de integração e fornece links para os recursos do [!DNL Google Campaign Manager] para ajudar você a começar.

## Resumo da integração

[!DNL Google Campaign Manager] é o substituto de [!DNL Google] para [!DNL DoubleClick for Advertisers] (DFA). Semelhante ao DFA, os clientes do [!DNL Google Campaign Manager] podem importar, visualizar e trabalhar com seus dados no [!DNL Audience Manager]. Mas o [!DNL Audience Manager] não pode acessar diretamente e importar seus arquivos [!UICONTROL Data Transfer] e [!UICONTROL Match Table]. Para importar esses arquivos, o esforço se concentra no cliente.

No entanto, o procedimento de configuração está bem documentado na [Ajuda do DoubleClick Campaign Manager](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). Além disso, você pode revisar as etapas listadas abaixo para começar.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] arquivos de dados contêm dados para todos os anunciantes ou clientes. Se você precisar omitir clientes específicos, edite os arquivos antes de disponibilizá-los para [!DNL Audience Manager].

## Frequência e disponibilidade da transferência de dados

[!DNL Audience Manager] verifica e transfere dados uma vez por dia. Normalmente, os dados estão disponíveis em [!DNL Audience Manager] após 24 horas.

## Etapas

1. [Criar um grupo](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Os grupos controlam o acesso aos seus dados do [!DNL Google Campaign Manager]. Eventualmente, você convidará e adicionará [!DNL Audience Manager] a este grupo.

1. [Verifique seu status do Google Cloud Storage](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   O Google Cloud Storage contém o compartimento de dados que contém o [!UICONTROL Data Transfer] e o [!UICONTROL Match Tables]. Você precisará configurar um bucket ou garantir que o novo grupo tenha acesso a um bucket de armazenamento de dados existente.

1. [Obter uma URL de arquivo de dados](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   Trabalhe com seu Gerente de Conta do [!DNL Google Campaign Manager] ou Consultor de Soluções de Plataforma. Eles fornecerão um URL para seus arquivos de dados. O [!DNL Google] poderá alterar o formato de nomes de arquivo e compartimento em versões futuras. Novamente, trabalhe com seu Gerente de conta do [!DNL Google Campaign Manager] para verificar se você está usando os formatos certos.

1. [Definir permissões de bucket](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   O [!DNL Cloud Storage Manager] permite controlar o compartilhamento de dados e o acesso ao bucket. Conceda ao seu grupo acesso de leitura ao compartimento que contém os arquivos [!UICONTROL Data Transfer] e [!UICONTROL Match Table].

1. [Configurar compartilhamento de dados](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   As IDs de usuário [!DNL Google Campaign Manager] compartilhadas são criptografadas para proteger a privacidade. A criptografia adiciona duas colunas ao final do arquivo de Transferência de Dados, `PartnerId1` e `PartnerId2`. Essas colunas contêm IDs de usuário codificadas específicas para cada empresa que recebe esses arquivos.

   Como um terceiro autorizado, [!DNL Audience Manager] pode receber dados de [!DNL Google Campaign Manager], mas não pode decodificar as IDs. No entanto, no lado do [!DNL Audience Manager], sabemos como as IDs codificadas correspondem às nossas IDs. Isso significa que podemos corresponder e sincronizar usuários com confiança e precisão.

   >[!NOTE]
   >Você não pode importar [!DNL Google Campaign Manager] arquivos para [!DNL Audience Manager] se já estiver compartilhando dados com outros dois parceiros de terceiros.

1. Convide [!DNL Audience Manager] para ingressar no grupo.

   Depois de criar um grupo e conceder a ele acesso a um bucket de dados, convide [!DNL Audience Manager] para ingressar no grupo. Envie um email de convite para dfaaam@adobe.com. Certifique-se de incluir o URL do arquivo de dados da etapa 3. Nossas equipes internas trabalharão com você para verificar o acesso após aceitar o convite. 1. Configure duas fontes de dados para [!DNL Google Campaign Manager] dados na Interface do Usuário [!DNL Audience Manager].

   Nomeie as fontes de dados `Advertiser Analytics: DCM Platform` e `Advertiser Analytics: AAM+DCM Platform`. No fluxo de trabalho [Criar Fontes de Dados](../../../features/manage-datasources.md#create-data-source), defina o tipo de ID como `Cookie`. Compartilhe as IDs das duas novas fontes de dados com nossas equipes internas.

1. Você pode criar características com facilidade a partir dos [!DNL Google Campaign Manager] arquivos importados para o [!DNL Audience Manager]. Consulte [Arquivos de Log Acionáveis](../../../integration/media-data-integration/actionable-log-files.md) e peça ao consultor do [!DNL Audience Manager] ou ao Atendimento ao Cliente para habilitar o recurso para você.
