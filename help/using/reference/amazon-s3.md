---
description: Informações sobre o Amazon Simple Storage Service (Amazon S 3).
seo-description: Informações sobre o Amazon Simple Storage Service (Amazon S 3).
seo-title: Amazon S 3 sobre
solution: Audience Manager
title: Amazon S 3 sobre
uuid: 8197 ecdf-df 8 f -488 d-bbc 0-d 8 d 4205 b 42 b 4
translation-type: tm+mt
source-git-commit: 212ec8641068a9ed4c620987bb18586ee8c7d519

---


# Amazon S3: About{#amazon-s-about}

Informações sobre o Amazon Simple Storage Service (Amazon S 3).

Como prática recomendada, recomendamos usar o Amazon S 3 em vez de FTP como um método para obter arquivos e entregar arquivos para parceiros. O Amazon S 3 fornece uma interface simples de serviços da Web que pode ser usada para armazenar e recuperar qualquer quantidade de dados, a qualquer momento, de qualquer lugar na Web.

Os benefícios do uso do Amazon S 3 incluem:

* **Escalabilidade:** O Amazon S 3 oferece escalabilidade quase ilimitada.
* **Confiabilidade e disponibilidade:** O Amazon S 3 fornece serviços de armazenamento de alta duração e alta disponibilidade.
* **Velocidade:** O Amazon S 3 permite transferências de dados rápidas.
* **Facilidade de uso:** O Amazon S 3 é muito fácil de usar e implementar. Sua implementação pode estar ativa em cerca de uma hora. Implementar um diretório FTP leva muito mais tempo.
* **Uploads de várias partes:** Arquivos grandes podem ser carregados de forma rápida e eficiente como carregamentos de arquivos de várias partes.
* **Segurança:** O Amazon S 3 oferece segurança forte.

   * Todos os diretórios podem ser acessados apenas para o cliente ou cliente apropriado.
   * Suporte de protocolo HTTPS para uploads e downloads. You should always use HTTPS when transferring files in [!DNL Audience Manager].
   * Amazon S3 provides encryption-at-rest for encrypting [outbound data files](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). We use the [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) encryption method, which allows encryption keys to be automatically generated and managed by Amazon S3.

* **Suporte de depuração e backup:** O Amazon S 3 permite [!DNL Audience Manager] manter cópias exatas de arquivos para facilitar a depuração ou retransferências.

Para obter mais informações sobre o Amazon S 3, consulte os seguintes recursos:

[Amazon Simple Storage Service (Amazon S 3)](https://aws.amazon.com/s3/) no site da Amazon Web Services.

[Comece com o Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) no site da Documentação AWS.
