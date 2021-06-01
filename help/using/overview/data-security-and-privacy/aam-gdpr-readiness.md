---
description: Diretrizes de disponibilidade do GDPR para clientes do Audience Manager
seo-description: Diretrizes de disponibilidade do GDPR para clientes do Audience Manager
seo-title: Diretrizes de disponibilidade do GDPR para clientes do Audience Manager
solution: Audience Manager
title: Diretrizes de disponibilidade do GDPR para clientes do Audience Manager
feature: Governança e privacidade de dados
exl-id: 353b9035-20f3-41ff-819c-71f161e6b1e1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 99%

---

# Diretrizes de disponibilidade do GDPR para clientes do Audience Manager (Controladores de dados) {#gdpr-readiness-guidance}

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
