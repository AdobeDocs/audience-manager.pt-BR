---
description: Diretrizes de disponibilidade do RGPD para clientes Audience Manager
seo-description: Diretrizes de disponibilidade do RGPD para clientes Audience Manager
seo-title: Diretrizes de disponibilidade do RGPD para clientes Audience Manager
solution: Audience Manager
title: Diretrizes de disponibilidade do RGPD para clientes Audience Manager
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---


# Diretrizes de disponibilidade do GDPR para clientes do Audience Manager (controladoras de dados) {#gdpr-readiness-guidance}

A Audience Manager recomenda ser pró-ativa nas áreas de controle de dados e disponibilidade organizacional. Isso o ajudará a garantir que seus dados de consumidor sejam organizados para processos relacionados a solicitações de acesso ou exclusão, suas equipes serão habilitadas e capacitadas a gerenciar essas solicitações e seus consumidores (Assuntos de dados) terão uma experiência positiva e diferenciada com sua marca.

Como seu Processador de dados, a Adobe não pode fornecer assistência jurídica sobre os requisitos do RGPD e o processo para obter o consentimento de seus Indivíduos de dados. Consulte o seu consultor jurídico para obter orientação sobre a conformidade com o RGPD da sua organização.

## Controle de dados: Start pensando sobre como seus dados de consumo são gerenciados em sua instância do Audience Manager

* Revise as várias IDs do cliente que suas equipes de marketing usam para identificar usuários no Audience Manager, juntamente com as fontes de dados em que estão armazenados. Isso simplificará o processo de solicitações (como excluir ou acessar), pois determinados tipos de dados serão submetidos a hash pelas equipes antes da ingestão no Audience Manager.
* As IDs de dispositivo móvel IDFA/GAID são usadas para vários casos de uso no Audience Manager. Se você estiver usando o SDK do Adobe Mobile, certifique-se de enviar a ID do Experience Cloud (MID) junto com o IDFA/GAID para garantir que as respostas do RGPD estejam completas.
* Com a definição de dados pessoais se tornando mais abrangente, os endereços IP podem ser considerados dados pessoais em sua região. Interaja proativamente com a Adobe Consulting para ofuscar o último octeto.
* Determine uma política e um processo de validação/autenticação para confirmar a identidade de uma pessoa de dados quando fizer uma solicitação de RGPD.
* Considere o uso dos Controles [de exportação de](../../features/data-export-controls.md) dados para bloquear a ativação de audiências para tecnologias que abrigam dados pessoais. Por exemplo, segmentos com dados de terceiros não devem ser sindicalizados a provedores de serviço de email. Defina uma configuração [!UICONTROL Data Export Control] para garantir que ninguém em sua organização possa ativar acidentalmente esses dados.
* Comece a utilizar Controles de acesso [baseados em](../../features/administration/administration-overview.md) funções para garantir que as equipes certas tenham acesso aos dados desejados.
* Considere os períodos [de](../../faq/faq-privacy.md#data-retention-faq) retenção apropriados para os dados.
* Analisar as políticas de ligação de identidade e as políticas de privacidade e os requisitos legais para verificar quando e onde é adequado associar os conjuntos de identidades; use adequadamente por meio das Regras [de mesclagem de](../../features/profile-merge-rules/merge-rules-overview.md)Perfis do Audience Manager.

## Preparação organizacional: Estabelecer um processo de negócios

* Identifique um processo para receber/responder às solicitações da pessoa de dados. Considere a criação de uma ferramenta automática para enviar solicitações ao Audience Manager.
* Nomeie um ponto de contato de privacidade dentro do seu centro de excelência do DMP. Conecte o ponto de privacidade da sua organização ao contato com a equipe de uso de produtos do Audience Manager para entender como você pode gerenciar os requisitos de ID de entrada.
* Realizar uma análise de dados antes de compartilhar com a pessoa em causa. Documento as etapas que você implementou para ajudá-lo a estabelecer a responsabilidade.
