---
description: O processo de Transferência de dados de saída para clientes que usam o Amazon Simple Storage Service (Amazon S 3) exige a solicitação da chave de acesso do Amazon S 3 e da chave secreta, a fim de entregar os arquivos de dados de saída ao seu bucket.
seo-description: O processo de Transferência de dados de saída para clientes que usam o Amazon Simple Storage Service (Amazon S 3) exige a solicitação da chave de acesso do Amazon S 3 e da chave secreta, a fim de entregar os arquivos de dados de saída ao seu bucket.
seo-title: Potencializar as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída
solution: Audience Manager
title: Potencializar as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída
uuid: 400 a 8 d 67-ebf 3-48 be-aa 3 f -498 a 5441 f 498
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Potencializar as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

The [!UICONTROL Outbound Data Transfer] process for customers using [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) requires us to ask for your [!DNL Amazon S3] access key and secret key, in order to deliver the outbound data files to your bucket.

If you&#39;d rather not share your [!DNL Amazon S3] access key and secret key with us, contact your [!DNL Audience Manager] consultant or Customer Care and they will set up [!DNL Cross-Account Bucket Permissions] for you. You only need to whitelist our [!DNL Amazon S3] account ID for the [!DNL S3] bucket where you wish to receive the outbound data files, as described in the [Amazon S3 documentation](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Your [!DNL Audience Manager] consultant or Customer Care will provide you with our [!DNL Amazon S3] account ID.