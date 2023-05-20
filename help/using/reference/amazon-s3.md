---
description: Informações sobre o Amazon Simple Storage Service (Amazon S3).
seo-description: Information about Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3  About
solution: Audience Manager
title: Sobre o Amazon S3
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 1%

---

# Amazon S3: sobre{#amazon-s-about}

Informações sobre o Amazon Simple Storage Service (Amazon S3).

Como prática recomendada, recomendamos usar o Amazon S3 em vez do FTP como um método para obter arquivos do e entregá-los aos parceiros. O Amazon S3 fornece uma interface simples de serviços da Web que pode ser usada para armazenar e recuperar qualquer quantidade de dados, a qualquer momento, de qualquer lugar na Web.

Os benefícios de usar o Amazon S3 incluem:

* **Escalabilidade:** O Amazon S3 fornece escalabilidade quase ilimitada.
* **Confiabilidade e disponibilidade:** O Amazon S3 fornece serviços de armazenamento de alta durabilidade e disponibilidade.
* **Velocidade:** O Amazon S3 permite transferências rápidas de dados.
* **Facilidade de uso:** O Amazon S3 é muito fácil de usar e implementar. Sua implementação pode começar a ser executada em cerca de uma hora. A implementação de um diretório FTP demora muito mais.
* **Carregamentos de várias partes:** É possível fazer upload de arquivos grandes de maneira rápida e eficiente como uploads de arquivos de várias partes.
* **Segurança:** O Amazon S3 oferece alta segurança.

   * Todos os diretórios podem ser acessados somente pelo cliente ou cliente apropriado.
   * Suporte ao protocolo HTTPS para uploads e downloads. Você sempre deve usar HTTPS ao transferir arquivos no [!DNL Audience Manager].
   * O Amazon S3 fornece criptografia inativa para criptografia [arquivos de dados de saída](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Usamos o [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) método de criptografia, que permite que as chaves de criptografia sejam geradas e gerenciadas automaticamente pelo Amazon S3.

* **Suporte a depuração e backup:** O Amazon S3 permite [!DNL Audience Manager] para reter cópias exatas de arquivos para facilitar a depuração ou as retransferências.

Para obter mais informações sobre o Amazon S3, consulte os seguintes recursos:

[Serviço de armazenamento simples da Amazon (Amazon S3)](https://aws.amazon.com/s3/) no site da Amazon Web Services.

[Introdução ao Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) no site Documentação do AWS.
