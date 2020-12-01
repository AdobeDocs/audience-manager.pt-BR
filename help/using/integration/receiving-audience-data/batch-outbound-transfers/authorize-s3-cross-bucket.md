---
description: O processo de Transferência de dados de saída para clientes que usam o Amazon Simple Armazenamento Service (Amazon S3) exige que solicitemos sua chave de acesso e chave secreta do Amazon S3 para fornecer os arquivos de dados de saída ao seu bucket.
seo-description: O processo de Transferência de dados de saída para clientes que usam o Amazon Simple Armazenamento Service (Amazon S3) exige que solicitemos sua chave de acesso e chave secreta do Amazon S3 para fornecer os arquivos de dados de saída ao seu bucket.
seo-title: Potencializar as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída
solution: Audience Manager
title: Potencializar as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 14%

---


# Potencializar as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

O processo [!UICONTROL Outbound Data Transfer] para clientes que usam [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) exige que solicitemos sua chave de acesso e chave secreta [!DNL Amazon S3], a fim de fornecer os arquivos de dados de saída para seu bucket.

Se você preferir não compartilhar sua [!DNL Amazon S3] chave de acesso e chave secreta conosco, entre em contato com seu [!DNL Audience Manager] consultor ou com o Atendimento ao cliente e eles configurarão [!DNL Cross-Account Bucket Permissions] para você. Você só precisa adicionar nossa ID de conta [!DNL Amazon S3] a uma lista de permissões para o bucket [!DNL S3] onde deseja receber os arquivos de dados de saída, conforme descrito na [documentação do Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Seu consultor [!DNL Audience Manager] ou Atendimento ao cliente fornecerá a você nossa ID de conta [!DNL Amazon S3].