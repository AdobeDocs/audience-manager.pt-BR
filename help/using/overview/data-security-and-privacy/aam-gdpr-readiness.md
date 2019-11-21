---
description: Diretrizes de disponibilidade do GDPR para clientes do Audience Manager
seo-description: Diretrizes de disponibilidade do GDPR para clientes do Audience Manager
seo-title: Diretrizes de disponibilidade do GDPR para clientes do Audience Manager
solution: Audience Manager
title: Diretrizes de disponibilidade do GDPR para clientes do Audience Manager
translation-type: tm+mt
source-git-commit: caa5207bc2955ee18b40d6a51613340001cbd92f

---


# Diretrizes de disponibilidade do GDPR para clientes do Audience Manager (controladoras de dados) {#gdpr-readiness-guidance}

O Audience Manager recomenda ser pró-ativo nas áreas de controle de dados e disponibilidade organizacional. Isso o ajudará a garantir que seus dados de consumidor sejam organizados para processos relacionados a solicitações de acesso ou exclusão, suas equipes serão habilitadas e capacitadas a gerenciar essas solicitações e seus consumidores (Assuntos de dados) terão uma experiência positiva e diferenciada com sua marca.

Como seu Processador de dados, a Adobe não pode fornecer assistência jurídica sobre os requisitos do RGPD e o processo para obter o consentimento de seus Indivíduos de dados. Consulte o seu consultor jurídico para obter orientação sobre a conformidade com o RGPD da sua organização.

## Controle de dados: Comece a pensar sobre como seus dados de consumidor são gerenciados na sua instância do Audience Manager

* Analise as várias IDs do cliente que suas equipes de marketing usam para identificar usuários no Audience Manager, juntamente com as fontes de dados em que estão armazenados. Isso simplificará o processo de solicitações (como excluir ou acessar), pois determinados tipos de dados serão submetidos a hash pelas equipes antes da ingestão no Audience Manager.
* IDs de dispositivos móveis IDFA/GAID são usadas para vários casos de uso no Audience Manager. Se você estiver usando o SDK do Adobe Mobile, certifique-se de enviar a Experience Cloud ID (MID) juntamente com o IDFA/GAID para garantir que as respostas do RGPD estejam completas.
* Com a definição de dados pessoais se tornando mais abrangente, os endereços IP podem ser considerados dados pessoais em sua região. Interaja proativamente com a Adobe Consulting para ofuscar o último octeto.
* Determine uma política e um processo de validação/autenticação para confirmar a identidade de uma pessoa de dados quando fizer uma solicitação de RGPD.
* Considere usar os Controles [de exportação de](../../features/data-export-controls.md) dados para bloquear a ativação do público-alvo para tecnologias que abrigam dados pessoais. Por exemplo, segmentos com dados de terceiros não devem ser sindicalizados a provedores de serviços de email. Defina uma configuração [!UICONTROL Data Export Control] para garantir que ninguém em sua organização possa ativar acidentalmente esses dados.
* Comece a utilizar os Controles [de acesso baseados em](../../features/administration/administration-overview.md) funções para garantir que as equipes certas tenham acesso aos dados pretendidos.
* Considere os períodos [de](../../faq/faq-privacy.md#data-retention-faq) retenção apropriados para os dados.
* Analisar as políticas de ligação de identidade e as políticas de privacidade e os requisitos legais para verificar quando e onde é adequado associar os conjuntos de identidades; use adequadamente por meio das Regras [de mesclagem de](../../features/profile-merge-rules/merge-rules-overview.md)perfis do Audience Manager.

## Preparação organizacional: Estabelecer um processo de negócios

* Identifique um processo para receber/responder às solicitações da pessoa de dados. Considere a criação de uma ferramenta automática para enviar solicitações ao Audience Manager.
* Nomeie um ponto de contato de privacidade dentro do seu centro de excelência do DMP. Conecte o ponto de privacidade da sua organização ao contato com a equipe de uso do produto do Audience Manager para entender como você pode gerenciar seus requisitos de ID de entrada.
* Realizar uma análise de dados antes de compartilhar com a pessoa em causa. Documente as etapas que você implementou para ajudá-lo a estabelecer a responsabilidade.
