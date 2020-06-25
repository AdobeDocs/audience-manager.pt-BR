---
description: Informações sobre o Amazon Simple Armazenamento Service (Amazon S3).
seo-description: Informações sobre o Amazon Simple Armazenamento Service (Amazon S3).
seo-title: Amazon S3 Sobre
solution: Audience Manager
title: Amazon S3 Sobre
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---


# Amazon S3: About{#amazon-s-about}

Informações sobre o Amazon Simple Armazenamento Service (Amazon S3).

Como prática recomendada, recomendamos usar o Amazon S3 em vez de FTP como método para obter arquivos e fornecer arquivos aos parceiros. O Amazon S3 fornece uma interface simples de serviços da Web que pode ser usada para armazenar e recuperar qualquer quantidade de dados, a qualquer momento, de qualquer lugar na Web.

Os benefícios do uso do Amazon S3 incluem:

* **Escalabilidade:** O Amazon S3 oferece escalabilidade quase ilimitada.
* **Confiabilidade e disponibilidade:** O Amazon S3 oferece alta durabilidade e serviços de armazenamento de alta disponibilidade.
* **Velocidade:** O Amazon S3 permite transferências rápidas de dados.
* **Facilidade de uso:** O Amazon S3 é muito fácil de usar e implementar. Sua implementação pode estar funcionando em cerca de uma hora. A implementação de um diretório FTP leva muito mais tempo.
* **Carregamentos de várias peças:** Arquivos grandes podem ser carregados de forma rápida e eficiente como uploads de arquivos de várias partes.
* **Segurança:** O Amazon S3 oferece segurança forte.

   * Todos os diretórios estão acessíveis somente ao cliente ou cliente apropriado.
   * Suporte ao protocolo HTTPS para uploads e downloads. Você sempre deve usar HTTPS ao transferir arquivos para [!DNL Audience Manager].
   * O Amazon S3 fornece criptografia em repouso para criptografar arquivos [de dados de](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)saída. Usamos o método de criptografia [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) , que permite que chaves de criptografia sejam geradas e gerenciadas automaticamente pelo Amazon S3.

* **Suporte para Depuração e Backup:** O Amazon S3 permite [!DNL Audience Manager] reter cópias exatas de arquivos para facilitar a depuração ou a retransferência.

Para obter mais informações sobre o Amazon S3, consulte os seguintes recursos:

[Amazon Simple Armazenamento Service (Amazon S3)](https://aws.amazon.com/s3/) no site Amazon Web Services.

[Introdução ao serviço](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) de Armazenamento simples da Amazon no site de documentação do AWS.
