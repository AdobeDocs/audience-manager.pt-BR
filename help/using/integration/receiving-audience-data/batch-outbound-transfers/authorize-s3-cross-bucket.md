---
description: O processo de transferência de dados de saída para clientes que usam o Amazon Simple Storage Service (Amazon S3) exige que solicitemos sua chave de acesso e chave secreta do Amazon S3 para entregar os arquivos de dados de saída ao seu bucket.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: Potencializar as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 12%

---

# Potencializar as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

A variável [!UICONTROL Outbound Data Transfer] processo para clientes que usam [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) exige que solicitemos sua [!DNL Amazon S3] acesse a chave e a chave secreta para entregar os arquivos de dados de saída ao seu bucket.

Se preferir não compartilhar seu [!DNL Amazon S3] chave de acesso e chave secreta conosco, entre em contato com seu [!DNL Audience Manager] ou Atendimento ao cliente e configurarão [!DNL Cross-Account Bucket Permissions] para você. Você só precisa adicionar nosso [!DNL Amazon S3] ID da conta para uma lista de permissões para a [!DNL S3] bucket onde você deseja receber os arquivos de dados de saída, conforme descrito no [Documentação do Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Seu [!DNL Audience Manager] ou o Atendimento ao cliente fornecerá a você nossas [!DNL Amazon S3] ID da conta.
