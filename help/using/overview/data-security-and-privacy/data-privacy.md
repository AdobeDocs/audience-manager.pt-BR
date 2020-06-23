---
description: Descreve a integração do Audience Manager e a conformidade com as práticas recomendadas geralmente aceitas relacionadas à privacidade do consumidor e aos procedimentos de opção de não participação.
seo-description: Descreve a integração do Audience Manager e a conformidade com as práticas recomendadas geralmente aceitas relacionadas à privacidade do consumidor e aos procedimentos de opção de não participação.
seo-title: Visão geral da privacidade de dados
solution: Audience Manager
title: Visão geral da privacidade de dados
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 1%

---


# Visão geral da privacidade de dados {#data-privacy}

## Visão geral

A documentação de Privacidade de dados descreve a integração e a conformidade com as práticas recomendadas geralmente aceitas relacionadas à privacidade do consumidor e aos procedimentos de recusa. [!DNL Audience Manager]

[!DNL Audience Manager] reconhece a importância da relação entre os consumidores e as marcas online com as quais interagem. Ambas as partes beneficiam do intercâmbio transparente de elementos de dados pseudônimos:

* Os consumidores recebem conteúdo personalizado, ofertas de produtos com desconto e experiências otimizadas do usuário.
* As marcas recebem fluxos vitais de receita suportando vários modelos de negócios online.

Em nosso apoio contínuo a este modelo, [!DNL Audience Manager] continua comprometido em fornecer as ferramentas para ajudá-lo a oferecer transparência e controle aos seus consumidores, além de fornecer anúncios personalizados sujeitos aos Princípios [autorregulatórios da OBA (](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/)Online Behavioral Advertising).

## [!DNL GDPR] {#gdpr}

O Regulamento [Geral sobre a Proteção de Dados (RGPD)](https://eugdpr.org/) introduziu vários novos direitos de privacidade de dados para os membros da União Europeia, incluindo o **direito de acesso** e o **direito de ser esquecido**. Isso significa que qualquer [!DNL EU] cidadão cujos dados pessoais foram coletados por sua empresa pode solicitar acesso ou excluir seus dados a qualquer momento. O não cumprimento dessas solicitações pode resultar em multas de vários milhões de dólares para sua organização.

Para cumprir [!DNL GDPR], [!DNL Audience Manager] é compatível com o acesso aos dados e a exclusão de [solicitações](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

A [California Consumer Privacy Act (CCPA)](https://www.caprivacy.org/about), que entrou em vigor em 1º de janeiro de 2020, fornece aos residentes da Califórnia novos direitos sobre suas informações pessoais e impõe responsabilidades de proteção de dados a determinadas entidades que realizam negócios na Califórnia.

[!DNL CCPA] fornece novos direitos de privacidade de dados aos residentes da Califórnia, incluindo o direito de acessar e excluir seus dados pessoais e saber se seus dados pessoais foram vendidos ou divulgados (e a quem). Para cumprir [!DNL CCPA], [!DNL Audience Manager] suporta [!DNL CCPA] acesso e exclusão de [solicitações](data-privacy-requests.md).

Consulte o Centro [de privacidade da](https://www.adobe.com/privacy/opt-out.html) Adobe para obter mais detalhes.

## Conformidade com os regulamentos {#compliance}

[!DNL Audience Manager] ajuda você a cumprir suas obrigações de acordo com determinadas normas de privacidade, por meio de ferramentas de privacidade, como a [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) para acesso a dados e solicitações de exclusão.

Este serviço fornece uma interface [!DNL RESTful API] e de usuário para ajudá-lo a gerenciar solicitações de dados do consumidor. Usando o [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), você pode enviar solicitações para acessar e excluir dados pessoais, com base em uma solicitação individual do consumidor, ajudando a automatizar essa parte das suas obrigações de conformidade.

Embora as solicitações de acesso e exclusão de dados sejam tratadas por meio do [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), as solicitações [de](data-privacy-requests.md#opt-out-requests) não participação são atualmente suportadas por meio da API [](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)DCS. Consulte Solicitações [de privacidade de](data-privacy-requests.md) dados para obter detalhes.

## Conceitos relacionados {#related-concepts}

* [Solicitações de privacidade de dados](data-privacy-requests.md)
* [Gerenciamento de consentimento](data-privacy-consent.md)
* [Plug-in do Audience Manager para a Estrutura de consentimento do IAB](aam-iab-plugin.md)
* [Identificadores de Audience Manager](data-privacy-ids.md)
* [Glossário CCPA](aam-ccpa-glossary.md)
* [Glossário do RGPD](aam-gdpr-glossary.md)
* [Considerações sobre RGPD para Destinos](aam-gdpr-partners.md)
* [Diretrizes de disponibilidade do RGPD para clientes Audience Manager](aam-gdpr-readiness.md)
* [Controle de dados](data-governance.md)
* [Perguntas frequentes sobre privacidade e retenção de dados](../../faq/faq-privacy.md)