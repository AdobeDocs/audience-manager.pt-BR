---
description: O processo de transferência de dados de saída para clientes que usam o Amazon Simple Storage Service (Amazon S3) exige que solicitemos sua chave de acesso e chave secreta do Amazon S3 para fornecer os arquivos de dados de saída ao seu bucket.
seo-description: O processo de transferência de dados de saída para clientes que usam o Amazon Simple Storage Service (Amazon S3) exige que solicitemos sua chave de acesso e chave secreta do Amazon S3 para fornecer os arquivos de dados de saída ao seu bucket.
seo-title: Potencializar as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída
solution: Audience Manager
title: Potencializar as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Potencializar as permissões de bucket entre contas do Amazon S3 para seus arquivos de saída {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

O [!UICONTROL Outbound Data Transfer] processo para os clientes que usam [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) requer que solicitemos sua chave de [!DNL Amazon S3] acesso e chave secreta, a fim de fornecer os arquivos de dados de saída para seu bucket.

Se preferir não compartilhar sua chave de [!DNL Amazon S3] acesso e chave secreta conosco, entre em contato com seu [!DNL Audience Manager] consultor ou com o Atendimento ao cliente e eles serão configurados [!DNL Cross-Account Bucket Permissions] para você. Você só precisa adicionar a ID da [!DNL Amazon S3] conta ao [!DNL S3] bucket onde deseja receber os arquivos de dados de saída, conforme descrito na documentação [do](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)Amazon S3. Seu [!DNL Audience Manager] consultor ou Atendimento ao cliente fornecerá a nossa ID de [!DNL Amazon S3] conta.