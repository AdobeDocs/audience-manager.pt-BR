---
description: O processo de transferência de dados de saída para clientes que usam o Amazon Simple Storage Service (Amazon S3) exige que solicitemos sua chave de acesso e chave secreta do Amazon S3 para entregar os arquivos de dados de saída ao seu bucket.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: Aproveite as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 9c0254e8a29ffeb0353ed6faa898b74bcae7cef1
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Aproveite as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

O processo do [!UICONTROL Outbound Data Transfer] para clientes que usam o [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) exige que solicitemos a chave de acesso e a chave secreta do [!DNL Amazon S3] para entregar os arquivos de dados de saída ao seu bucket.

Se preferir não compartilhar conosco a chave de acesso e a chave secreta do [!DNL Amazon S3], contate o consultor do [!DNL Audience Manager] ou o Atendimento ao Cliente e eles configurarão o [!DNL Cross-Account Bucket Permissions] para você.

Você só precisa adicionar nossa ID de conta [!DNL Amazon S3] a uma lista de permissões para o bucket [!DNL S3] no qual deseja receber os arquivos de dados de saída, conforme descrito na [documentação do Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). O consultor do [!DNL Audience Manager] ou o Atendimento ao cliente fornecerá a você nossa ID da conta do [!DNL Amazon S3].

>[!NOTE]
>
>Devido ao limite de tamanho do objeto do Amazon S3, a Audience Manager oferece suporte a tamanhos divididos de até 1 TB. Se você não especificar um tamanho dividido, o limite de 1 TB será aplicado automaticamente.

