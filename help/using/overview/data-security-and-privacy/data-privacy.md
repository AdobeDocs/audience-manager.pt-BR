---
description: Descreve a integração do Audience Manager e a conformidade com as práticas recomendadas geralmente aceitas relacionadas à privacidade do consumidor e aos procedimentos de recusa.
seo-description: Descreve a integração do Audience Manager e a conformidade com as práticas recomendadas geralmente aceitas relacionadas à privacidade do consumidor e aos procedimentos de recusa.
seo-title: Visão geral da privacidade de dados
solution: Audience Manager
title: Visão geral da privacidade de dados
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 78%

---


# Visão geral da privacidade de dados {#data-privacy}

## Visão geral

The Data Privacy documentation describes [!DNL Audience Manager] integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.

[!DNL Audience Manager]O reconhece a importância da relação entre os consumidores e as marcas online com as quais eles interagem. Ambas as partes se beneficiam do intercâmbio transparente de elementos de dados pseudônimos:

* Os consumidores recebem conteúdo personalizado, ofertas de produtos com desconto e experiências otimizadas do usuário.
* As marcas recebem fluxos essenciais de receita compatíveis com vários modelos de negócios online.

In our continuing support of this model, [!DNL Audience Manager] remains committed to providing you with the tools to help support your ability to provide  transparency and control to your consumers, while delivering personalized ads subject to the [Online Behavioral Advertising (OBA) Self-Regulatory Principles](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/).

## [!DNL GDPR] {#gdpr}

O [Regulamento Geral sobre a Proteção de Dados (GDPR)](https://eugdpr.org/) introduziu vários novos direitos de privacidade de dados para os membros da União Europeia, incluindo o **Direito de acesso** e o **Direito de ser esquecido**. This means that any [!DNL EU] citizen whose personal data has been collected by your business can request to access or delete their data at any time. O não cumprimento dessas solicitações pode resultar em multas de milhões de dólares para sua organização.

To comply with [!DNL GDPR], [!DNL Audience Manager] supports data access and delete [requests](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

A [California Consumer Privacy Act (CCPA)](https://www.caprivacy.org/about), que entrou em vigor em 1º de janeiro de 2020, fornece aos residentes da Califórnia novos direitos sobre suas informações pessoais e impõe responsabilidades de proteção de dados a determinadas entidades que realizam negócios na Califórnia.

[!DNL CCPA]A fornece novos direitos de privacidade de dados para residentes na Califórnia, incluindo o direito de acessar e excluir seus dados pessoais e saber se seus dados pessoais foram vendidos ou divulgados (e para quem). Para cumprir [!DNL CCPA], [!DNL Audience Manager] suporta [!DNL CCPA] acesso e exclusão de [solicitações](data-privacy-requests.md).

Consulte o [Centro de privacidade da Adobe](https://www.adobe.com/br/privacy/opt-out.html) para obter mais detalhes.

## Conformidade com os regulamentos {#compliance}

[!DNL Audience Manager]O ajuda você a cumprir suas obrigações com determinadas normas de privacidade, por meio de ferramentas de privacidade como o [Adobe Experience Platform Privacy Service](https://docs.adobe.com/content/help/pt-BR/experience-platform/privacy/home.html), para acessar dados e excluir solicitações.

Este serviço fornece uma [!DNL RESTful API] e a interface do usuário para ajudar você a gerenciar solicitações de dados do consumidor. Com o [Privacy Service](https://docs.adobe.com/content/help/pt-BR/experience-platform/privacy/home.html), você pode enviar solicitações para acessar e excluir dados pessoais, com base em uma solicitação individual do consumidor, ajudando a automatizar essa parte das suas obrigações de conformidade.

Enquanto as solicitações de acesso e exclusão de dados são tratadas pelo [Privacy Service](https://docs.adobe.com/content/help/pt-BR/experience-platform/privacy/home.html), [as solicitações de recusa](data-privacy-requests.md#opt-out-requests) são feitas por meio da [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md). Consulte [Solicitações de privacidade de dados](data-privacy-requests.md) para obter detalhes.

## Conceitos relacionados {#related-concepts}

* [Solicitações de privacidade de dados](data-privacy-requests.md)
* [Gerenciamento de consentimento](data-privacy-consent.md)
* [Plug-in do Audience Manager para a TCF do IAB](aam-iab-plugin.md)
* [Identificadores do Audience Manager](data-privacy-ids.md)
* [Glossário da CCPA](aam-ccpa-glossary.md)
* [Glossário do GDPR](aam-gdpr-glossary.md)
* [Considerações sobre o GDPR para destinos](aam-gdpr-partners.md)
* [Diretrizes de disponibilidade do GDPR para clientes do Audience Manager](aam-gdpr-readiness.md)
* [Controle de dados](data-governance.md)
* [Perguntas frequentes sobre privacidade e retenção de dados](../../faq/faq-privacy.md)