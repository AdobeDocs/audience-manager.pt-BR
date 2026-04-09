---
description: Diretrizes de disponibilidade do GDPR para clientes do Audience Manager
seo-description: GDPR Readiness Guidance for Audience Manager Customers
seo-title: GDPR Readiness Guidance for Audience Manager Customers
solution: Audience Manager
title: Diretrizes de disponibilidade do GDPR para clientes do Audience Manager
feature: Data Governance & Privacy
exl-id: 353b9035-20f3-41ff-819c-71f161e6b1e1
TQID: https://experienceleague.adobe.com/K72pQ8Q6yILWexkG38Hc5W1roYObFvhLE5A0GSCyhYE
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: c814092e-2730-45e8-a12d-e084529f52cbid: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 461
ht-degree: 98%

---

# Diretrizes de disponibilidade do GDPR para clientes da Audience Manager (Controladores de dados) {#gdpr-readiness-guidance}

O Audience Manager recomenda ser proativo nas áreas de controle de dados e disponibilidade organizacional. Dessa forma, os dados do seu consumidor são organizados para processos relacionados a solicitações de acesso ou exclusão, suas equipes são habilitadas e capacitadas a gerenciar essas solicitações e os consumidores (Titular dos dados) têm uma experiência positiva e diferenciada com sua marca.

Como Processador de dados, a Adobe não pode fornecer assistência jurídica sobre os requisitos do GDPR e o processo para obter o consentimento dos Titulares dos dados. Entre em contato com um consultor jurídico para obter orientação sobre a conformidade com o GDPR da sua organização.

## Governança de dados: comece a pensar em como os dados do seu consumidor são gerenciados na instância do Audience Manager

* Revise as várias IDs de clientes que suas equipes de marketing usam para identificar usuários no Audience Manager, junto com as fontes de dados nas quais eles estão armazenados. O processo de solicitações (como exclusão ou acesso) será simplificado, pois determinados tipos de dados serão agrupados por suas equipes antes da assimilação no Audience Manager.
* As IDs de dispositivo móvel IDFA/GAID são usadas para vários casos de uso no Audience Manager. Se você estiver usando o SDK do Adobe Mobile, envie a Experience Cloud ID (MID) juntamente com o IDFA/GAID para garantir que as respostas do GDPR estejam completas.
* Com a definição de dados pessoais cada vez mais abrangente, os endereços IP podem ser considerados dados pessoais na sua região. Interaja proativamente com a Adobe Consulting para ofuscar o último octeto.
* Determine uma política e um processo de validação/autenticação para confirmar a identidade de uma titular de dados quando fizer uma solicitação de GDPR.
* Considere o uso de [Controles de exportação de dados](../../features/data-export-controls.md) para bloquear a ativação de públicos-alvo para tecnologias que abrigam dados pessoais. Por exemplo, segmentos com dados de terceiros não devem ser sindicalizados a provedores de serviço de email. Defina um [!UICONTROL Data Export Control] para garantir que ninguém em sua organização possa ativar acidentalmente esses dados.
* Comece a utilizar [Controles de acesso com base em funções](../../features/administration/administration-overview.md) para garantir que as equipes certas tenham acesso aos dados desejados.
* Considere os [períodos de retenção](../../faq/faq-privacy.md#data-retention-faq) apropriados para os dados.
* Analise as políticas de vinculação de identidade e privacidade e requisitos legais para ver quando e onde é apropriado vincular conjuntos de identidades; use corretamente por meio das [Regras de mesclagem de perfis](../../features/profile-merge-rules/merge-rules-overview.md) do Audience Manager.

## Disponibilidade organizacional: estabelecer um processo de negócios

* Identifique um processo para receber/responder às solicitações do titular dos dados. Considere a criação de uma ferramenta automática para enviar solicitações ao Audience Manager.
* Nomeie um ponto de contato de privacidade dentro do seu centro de excelência DMP. Conecte o ponto de privacidade da sua organização ao contato da equipe de uso do produto do Audience Manager para entender como você pode gerenciar os requisitos de ID de entrada.
* Faça uma análise de dados antes de compartilhar com o titular dos dados. Documente as etapas que você implementou para ajudar a estabelecer a responsabilidade.
