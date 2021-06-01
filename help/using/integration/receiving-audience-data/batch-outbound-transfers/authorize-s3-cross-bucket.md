---
description: O processo de transferência de dados de saída para clientes que usam o Amazon Simple Storage Service (Amazon S3) exige que solicitemos sua chave de acesso e chave secreta do Amazon S3 para fornecer os arquivos de dados de saída ao seu bucket.
seo-description: O processo de transferência de dados de saída para clientes que usam o Amazon Simple Storage Service (Amazon S3) exige que solicitemos sua chave de acesso e chave secreta do Amazon S3 para fornecer os arquivos de dados de saída ao seu bucket.
seo-title: Potencializar as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída
solution: Audience Manager
title: Potencializar as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Transferências de dados de saída
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 14%

---

# Potencializar as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

O processo [!UICONTROL Outbound Data Transfer] para clientes que usam [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) requer que solicitemos sua chave de acesso [!DNL Amazon S3] e a chave secreta, para fornecer os arquivos de dados de saída ao seu bucket.

Se preferir não compartilhar a chave de acesso e a chave secreta [!DNL Amazon S3] conosco, entre em contato com seu consultor [!DNL Audience Manager] ou com o Atendimento ao cliente e eles configurarão [!DNL Cross-Account Bucket Permissions] para você. Você só precisa adicionar a ID da conta [!DNL Amazon S3] a uma lista de permissões para o bucket [!DNL S3], onde deseja receber os arquivos de dados de saída, conforme descrito na [documentação do Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Seu consultor [!DNL Audience Manager] ou o Atendimento ao cliente fornecerá a você a ID da conta [!DNL Amazon S3].
