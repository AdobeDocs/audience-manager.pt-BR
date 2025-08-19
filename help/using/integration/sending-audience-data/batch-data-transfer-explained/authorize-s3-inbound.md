---
description: Para enviar dados do seu próprio bucket do Amazon S3 para o Audience Manager, primeiro você deve solicitar a configuração de uma função dedicada do Amazon S3.
solution: Audience Manager
title: Aproveite as permissões de bucket entre contas do Amazon S3 para seus arquivos de entrada
feature: Inbound Data Transfers
exl-id: 56ecea5a-0621-4720-9e4c-f9086294c31f
source-git-commit: 65963c462f2a5abb1e2597b3d943628baa9d4730
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Aproveite as permissões de bucket entre contas do Amazon S3 para seus arquivos de entrada {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

Para enviar dados do seu próprio bucket do Amazon S3 para o Audience Manager, primeiro você deve solicitar a configuração de uma função dedicada do Amazon S3.

Para fazer isso, siga as etapas descritas abaixo.

1. Entre em contato com o Atendimento ao cliente e solicite um método alternativo de envio de arquivos para a Audience Manager.
2. Forneça ao Atendimento ao cliente o [!DNL Amazon Resource Name (ARN)] para uma função na sua conta do Amazon S3 que você usará para enviar arquivos. _Esta função deve ser criada antes de você entrar em contato com o Atendimento ao Cliente_. Após a configuração ser concluída, o Atendimento ao cliente fornecerá a você o [!DNL Amazon Resource Name (ARN)] para a função recém-criada.
3. Edite as permissões de sua função existente do Amazon S3 para assumir a função fornecida pelo Atendimento ao cliente.

>[!NOTE]
>
>Ao transferir dados de entrada para o bucket do Audience Manager Amazon S3, use a `bucket-owner-full-control` [lista de controle de acesso](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html) para que o Audience Manager processe os dados corretamente.
>
>Exemplo do comando Amazon Web Services: `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`
