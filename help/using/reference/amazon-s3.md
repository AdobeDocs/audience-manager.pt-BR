---
description: Informações sobre o Serviço de Armazenamento Simples da Amazon (Amazon S3).
seo-description: Informações sobre o Serviço de Armazenamento Simples da Amazon (Amazon S3).
seo-title: Amazon S3 Sobre
solution: Audience Manager
title: Amazon S3 Sobre
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Amazon S3: sobre{#amazon-s-about}

Informações sobre o Serviço de Armazenamento Simples da Amazon (Amazon S3).

Como prática recomendada, recomendamos usar o Amazon S3 em vez de FTP como um método para obter arquivos e entregar arquivos para parceiros. O Amazon S3 fornece uma interface de serviços da Web simples que pode ser usada para armazenar e recuperar qualquer quantidade de dados, a qualquer momento, de qualquer lugar da Web.

Os benefícios do uso do Amazon S3 incluem:

* **Escalabilidade:** o Amazon S3 fornece escalabilidade quase ilimitada.
* **Confiabilidade e disponibilidade:** o Amazon S3 oferece alta durabilidade e serviços de armazenamento de alta disponibilidade.
* **Velocidade:** o Amazon S3 permite transferências rápidas de dados.
* **Facilidade de uso:** o Amazon S3 é muito fácil de usar e de implementar. Sua implementação pode estar ativa e em execução em cerca de uma hora. A implementação de um diretório FTP demora muito mais.
* **Uploads de várias partes:** arquivos grandes podem ser carregados de forma rápida e eficiente como uploads de arquivos de várias partes.
* **Segurança:** o Amazon S3 oferece segurança forte.

   * Todos os diretórios podem ser acessados somente para o cliente ou cliente apropriado.
   * Suporte ao protocolo HTTPS para uploads e downloads. Você sempre deve usar HTTPS ao transferir arquivos em [!DNL Audience Manager].
   * O Amazon S3 fornece criptografia em repouso para criptografar [arquivos de dados de saída](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Usamos o método de criptografia [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html), que permite que chaves de criptografia sejam geradas e gerenciadas automaticamente pelo Amazon S3.

* **Suporte para depuração e backup: o** Amazon S3 permite  [!DNL Audience Manager] reter cópias exatas de arquivos para facilitar a depuração ou retransferências.

Para obter mais informações sobre o Amazon S3, consulte os seguintes recursos:

[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/) no site Amazon Web Services .

[Introdução ao Amazon Simple Storage ](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) Service no site da documentação do AWS.
