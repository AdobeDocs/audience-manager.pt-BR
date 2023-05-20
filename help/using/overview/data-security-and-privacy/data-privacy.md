---
description: Descreve a integração do Audience Manager e a conformidade com as práticas recomendadas geralmente aceitas relacionadas à privacidade do consumidor e aos procedimentos de recusa.
seo-description: Describes Audience Manager integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.
seo-title: Data Privacy Overview
solution: Audience Manager
title: Visão geral da privacidade de dados
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
feature: Data Governance & Privacy
exl-id: 051de369-e762-49fb-b65f-6faf94db48a4
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 68%

---

# Visão geral da privacidade de dados {#data-privacy}

## Visão geral

A documentação de Privacidade de dados descreve [!DNL Audience Manager] integração e conformidade com as práticas recomendadas geralmente aceites relacionadas com a privacidade do consumidor e os procedimentos de recusa.

[!DNL Audience Manager]O reconhece a importância da relação entre os consumidores e as marcas online com as quais eles interagem. Ambas as partes se beneficiam do intercâmbio transparente de elementos de dados pseudônimos:

* Os consumidores recebem conteúdo personalizado, ofertas de produtos com desconto e experiências otimizadas do usuário.
* As marcas recebem fluxos essenciais de receita compatíveis com vários modelos de negócios online.

Em nosso contínuo apoio a este modelo, [!DNL Audience Manager] O continua comprometido a fornecer as ferramentas que ajudarão você a oferecer transparência e controle aos seus consumidores, além de fornecer anúncios personalizados sujeitos às [Princípios autorregulatórios da OBA (Online Behavioral Advertising)](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/).

## [!DNL GDPR] {#gdpr}

O [Regulamento Geral sobre a Proteção de Dados (GDPR)](https://gdpr.eu/data-privacy/) introduziu vários novos direitos de privacidade de dados para os membros da União Europeia, incluindo o **Direito de acesso** e o **Direito de ser esquecido**. Isto significa que qualquer [!DNL EU] os cidadãos cujos dados pessoais tenham sido coletados pela sua empresa podem solicitar acesso ou excluir os dados a qualquer momento. O não cumprimento dessas solicitações pode resultar em multas de milhões de dólares para sua organização.

Para cumprir com [!DNL GDPR], [!DNL Audience Manager] suporta acesso e exclusão de dados [solicitações](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

A [California Consumer Privacy Act (CCPA)](https://www.caprivacy.org/about), que entrou em vigor em 1º de janeiro de 2020, fornece aos residentes da Califórnia novos direitos sobre suas informações pessoais e impõe responsabilidades de proteção de dados a determinadas entidades que realizam negócios na Califórnia.

[!DNL CCPA]A fornece novos direitos de privacidade de dados para residentes na Califórnia, incluindo o direito de acessar e excluir seus dados pessoais e saber se seus dados pessoais foram vendidos ou divulgados (e para quem). Para cumprir com [!DNL CCPA], [!DNL Audience Manager] suporta [!DNL CCPA] acessar e excluir [solicitações](data-privacy-requests.md).

Consulte o [Centro de privacidade da Adobe](https://www.adobe.com/br/privacy/opt-out.html) para obter mais detalhes.

## Conformidade com os regulamentos {#compliance}

[!DNL Audience Manager]O ajuda você a cumprir suas obrigações com determinadas normas de privacidade, por meio de ferramentas de privacidade como o [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en), para acessar dados e excluir solicitações.

Este serviço fornece uma [!DNL RESTful API] e a interface do usuário para ajudar você a gerenciar solicitações de dados do consumidor. Com o [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en), você pode enviar solicitações para acessar e excluir dados pessoais, com base em uma solicitação individual do consumidor, ajudando a automatizar essa parte das suas obrigações de conformidade.

Enquanto as solicitações de acesso e exclusão de dados são tratadas pelo Privacy Service, [solicitações de recusa](data-privacy-requests.md#opt-out-requests) são atualmente compatíveis com o [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md). Consulte [Solicitações de privacidade de dados](data-privacy-requests.md) para obter detalhes.

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
