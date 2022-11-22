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
source-wordcount: '596'
ht-degree: 3%

---

# Importar arquivos de dados do Google Campaign Manager para o Audience Manager {#import-dcm-data-files-into-audience-manager}

Configure um [!DNL Google] grupo para trazer seu [!DNL Google Campaign Manager] arquivos de dados no Audience Manager. O conteúdo desta seção resume o processo de integração e fornece links para [!DNL Google Campaign Manager] recursos para ajudá-lo a começar.

## Resumo da integração

[!DNL Google Campaign Manager]O é o substituto de [!DNL Google] para [!DNL DoubleClick for Advertisers] (DFA). Semelhante ao DFA, [!DNL Google Campaign Manager] os clientes do podem importar, visualizar e trabalhar com seus dados no [!DNL Audience Manager]. Mas [!DNL Audience Manager] não pode acessar diretamente e importar seu [!UICONTROL Data Transfer] e [!UICONTROL Match Table] arquivos. Para importar esses arquivos, o esforço se concentra no cliente.

No entanto, o procedimento de criação está bem documentado no [Ajuda do DoubleClick Campaign Manager](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). Além disso, você pode revisar as etapas listadas abaixo para começar.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] os arquivos de dados contêm dados para todos os anunciantes ou clientes. Se precisar omitir clientes específicos, edite os arquivos antes de disponibilizá-los para [!DNL Audience Manager].

## Frequência e disponibilidade da transferência de dados

[!DNL Audience Manager] O verifica e transfere dados uma vez por dia. Normalmente, os dados estão disponíveis em [!DNL Audience Manager] após 24 horas.

## Etapas

1. [Criar um grupo](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Os grupos controlam o acesso à sua [!DNL Google Campaign Manager] dados. Eventualmente, você convidará e adicionará [!DNL Audience Manager] para este grupo.

1. [Verifique o status do armazenamento na nuvem da Google](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   O Google Cloud Storage contém o bucket de dados que contém seu [!UICONTROL Data Transfer] e [!UICONTROL Match Tables]. Você precisará configurar um bucket ou garantir que seu novo grupo tenha acesso a um bucket de armazenamento de dados existente.

1. [Obter um URL de arquivo de dados](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   Trabalhe com seu [!DNL Google Campaign Manager] Gerente de conta ou consultor de soluções da plataforma. Eles fornecerão um URL para seus arquivos de dados. [!DNL Google] O pode alterar o formato de nomes de arquivo e de bucket em versões futuras. Novamente, trabalhe com seu [!DNL Google Campaign Manager] Gerente de conta para verificar se você está usando os formatos corretos.

1. [Definir permissões de bucket](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   O [!DNL Cloud Storage Manager] permite controlar o compartilhamento de dados e o acesso ao bucket. Forneça ao seu grupo acesso de leitura ao bucket que contém [!UICONTROL Data Transfer] e [!UICONTROL Match Table] arquivos.

1. [Configurar compartilhamento de dados](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Compartilhado [!DNL Google Campaign Manager] as IDs de usuário são criptografadas para proteger a privacidade. A criptografia adiciona 2 colunas ao final do arquivo de Transferência de dados, `PartnerId1` e `PartnerId2`. Essas colunas contêm IDs de usuário codificadas específicas para cada empresa que recebe esses arquivos.

   Como terceiro autorizado, [!DNL Audience Manager] pode receber [!DNL Google Campaign Manager] , mas não pode decodificar as IDs. No entanto, no [!DNL Audience Manager] além disso, sabemos como as IDs codificadas correspondem às IDs. Isso significa que podemos combinar e sincronizar usuários com confiança e precisão.

   >[!NOTE]
   >Não é possível importar [!DNL Google Campaign Manager] arquivos em [!DNL Audience Manager] se você já estiver compartilhando dados com dois outros parceiros de terceiros.

1. Convidar [!DNL Audience Manager] para ingressar no grupo.

   Depois de criar um grupo e conceder a ele acesso a um bucket de dados, convide [!DNL Audience Manager] para ingressar no grupo. Envie um email de convite para dfaaam@adobe.com. Certifique-se de incluir o URL do arquivo de dados da etapa 3. Nossas equipes internas trabalharão com você para verificar o acesso depois de aceitar o convite. 1. Configure duas fontes de dados para [!DNL Google Campaign Manager] na [!DNL Audience Manager] Interface do usuário.

   Nomeie as fontes de dados `Advertiser Analytics: DCM Platform` e `Advertiser Analytics: AAM+DCM Platform`. No [Criar fontes de dados](../../../features/manage-datasources.md#create-data-source) , defina o tipo de ID como `Cookie`. Compartilhe as IDs das duas novas fontes de dados com nossas equipes internas.

1. Você pode criar características facilmente da variável [!DNL Google Campaign Manager] arquivos importados para o [!DNL Audience Manager]. Consulte [Arquivos de registro acionáveis](../../../integration/media-data-integration/actionable-log-files.md) e pergunte ao seu [!DNL Audience Manager] consultor ou do Atendimento ao cliente para habilitar o recurso para você.
