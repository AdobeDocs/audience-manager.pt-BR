---
description: Configure um grupo do Google para trazer os arquivos de dados do doubleclick Campaign Manager (DCM) para o Audience Manager. O conteúdo nesta seção resume o processo de integração e fornece links para recursos do DCM para ajudá-lo a começar.
seo-description: Configure um grupo do Google para trazer os arquivos de dados do doubleclick Campaign Manager (DCM) para o Audience Manager. O conteúdo nesta seção resume o processo de integração e fornece links para recursos do DCM para ajudá-lo a começar.
seo-title: Importar arquivos de dados DCM para o Audience Manager
solution: Audience Manager
title: Importar arquivos de dados DCM para o Audience Manager
uuid: 3578 cfe 1-6 d 30-4 a 73-ab 75-8 d 272 bebcd 60
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Import DCM Data Files Into Audience Manager {#import-dcm-data-files-into-audience-manager}

Configure um grupo do Google para trazer os arquivos de dados do doubleclick Campaign Manager (DCM) para o Audience Manager. O conteúdo nesta seção resume o processo de integração e fornece links para recursos do DCM para ajudá-lo a começar.

## Resumo da integração

O DCM é o substituto de [!DNL Google] para [!DNL DoubleClick for Advertisers] (DFA). Semelhante ao DFA, os clientes do DCM podem importar, visualizar e trabalhar com os dados no [!DNL Audience Manager]. But [!DNL Audience Manager] cannot directly access and import your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files. Para importar esses arquivos, o esforço se concentra no cliente.

However, the set up procedure is well documented in the [DoubleClick Campaign Manager Help](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456). Além disso, você pode revisar as etapas listadas abaixo para começar.

>[!CAUTION]
>
>Os arquivos de dados do DCM contêm dados para todos os seus anunciantes ou clientes. If you need to omit specific clients, then you must edit the files before making them available to [!DNL Audience Manager].

## Frequência e disponibilidade da transferência de dados

[!DNL Audience Manager] verifica e transfere dados uma vez a cada dia. Data is usually available in [!DNL Audience Manager] after 24-hours.

## Etapas

1. [Criar um grupo](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

   Grupos controlam o acesso aos dados do DCM. Eventually, you&#39;ll invite and add [!DNL Audience Manager] to this group.

1. [Verifique o status de Armazenamento do Google Cloud](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456).

   Google Cloud Storage contains the data bucket that holds your [!UICONTROL Data Transfer] and [!UICONTROL Match Tables]. Você precisará configurar um bucket ou garantir que seu novo grupo tenha acesso a um compartimento de armazenamento de dados existente.

1. [Obtenha um URL de arquivo de dados](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456).

   Trabalhe com seu Gerente de contas do DCM ou Consultor de soluções da plataforma. Elas fornecerão um URL para seus arquivos de dados. [!DNL Google] pode alterar o formato de bucket e nomes de arquivos em versões futuras. Novamente, trabalhe com seu Gerente de contas do DCM para certificar-se de que você está usando os formatos certos.

1. [Defina permissões de bucket](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   The [!DNL Cloud Storage Manager] lets you control data sharing and bucket access. Give your group read access to the bucket that contains your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files.

1. [Configure o compartilhamento de dados](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   As IDs de usuário compartilhadas do DCM são criptografadas para proteger a privacidade. Encryption adds 2 columns to the end of your Data Transfer file, `PartnerId1` and `PartnerId2`. Essas colunas contêm IDs de usuário codificadas específicas para cada empresa que recebe esses arquivos.

   As an authorized third-party, [!DNL Audience Manager] can receive DCM data, but cannot decode the IDs. However, on the [!DNL Audience Manager] side, we know how the encoded IDs match our IDs. Isso significa que podemos combinar e sincronizar os usuários com confiança e precisão.

   >[!NOTE]
   >You cannot import DCM files into [!DNL Audience Manager] if you&#39;re already sharing data with 2 other third-party partners.

1. Invite [!DNL Audience Manager] to join the group.

   After you create a group and give it access to a data bucket, invite [!DNL Audience Manager] to join the group. Envie um email de convite para DFA-AAM@adobe.com. Certifique-se de incluir o URL do arquivo de dados na etapa 3. Nossas equipes internas trabalharão com você para verificar o acesso após aceitar o convite. 1. Set up two data sources for DCM data in the [!DNL Audience Manager] User Interface.

   Name the data sources `Advertiser Analytics: DCM Platform` and `Advertiser Analytics: AAM+DCM Platform`. In the [Create Data Sources](../../../features/manage-datasources.md#create-data-source) workflow, set the ID type to `Cookie`. Compartilhe as IDs das duas novas fontes de dados com nossas equipes internas.

1. You can easily create traits from the DCM files you import into [!DNL Audience Manager]. See [Actionable Log Files](../../../integration/media-data-integration/actionable-log-files.md) and ask your [!DNL Audience Manager] consultant or Customer Care to enable the feature for you.
