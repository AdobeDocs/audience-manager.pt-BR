---
description: Esta página inclui os principais problemas reportados ao Atendimento ao cliente do Audience Manager.
seo-description: Esta página inclui os principais problemas reportados ao Atendimento ao cliente do Audience Manager.
seo-title: Atendimento ao cliente - Problemas relatados com mais frequência
solution: Audience Manager
title: Atendimento ao cliente - Problemas relatados com mais frequência
translation-type: tm+mt
source-git-commit: f9d57da86b7e8962353b01b693a2359cade7b024

---


# Atendimento ao cliente - Problemas relatados com mais frequência{#most-frequent-issues}

Esta página inclui os principais problemas reportados ao Atendimento ao cliente do Audience Manager em 2019.

## Por que nossos usuários somente leitura podem criar, editar ou excluir características e segmentos?

**Pergunta**

Por que nossos usuários somente leitura podem criar, editar ou excluir características e segmentos?

**Resposta**

Além de criar grupos e permissões na seção de administração, você precisa entrar em contato com o Atendimento ao cliente (amsupport@adobe.com) para que um representante possa habilitar o RBAC (Role Based Access Controls) para sua conta.

<br> 

## Por que minhas populações de traços Onboard caíram para 0 por volta de 15 de outubro? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

Por volta de 14 de outubro de 2019 eu notei que minhas populações de características integradas para o gráfico de ID de dispositivo caíram para 0, onde antes eram muito maiores.

![Imagem do menu suspenso ID do dispositivo](/help/using/support-issues/assets/device_id_populationdrop.png)

**Resposta**

Em 15 de outubro, uma atualização da funcionalidade Regra de mesclagem de perfis do Audience Manager foi alterada para onde os dados integrados removidos de uma ID CRM carregada em uma Fonte de dados entre dispositivos não estão mais sendo realizados em relação às IDs de dispositivos.  Anteriormente, o Audience Manager era detectado em relação à ID de dispositivo cruzado (ou ID de CRM), bem como copiando essas execuções para UUIDs do Audience Manager associadas (IDs de dispositivo).  A alteração foi feita para refletir com mais precisão a natureza dos dados de características e os perfis que estão sendo realizados.

Para exibir as realizações de características, selecione a opção &quot;ID entre dispositivos&quot; na lista suspensa no canto superior direito da exibição Características.

![Exibir Realizações por ID entre dispositivos](/help/using/support-issues/assets/deviceid-crossdevice.png)

<br> 

## Por que minhas características ou segmentos não aparecem na página de Relatórios de sobreposição?

Explicação para as características e os segmentos que podem não aparecer na página de Relatórios de sobreposição.

**Pergunta**

Por que os usuários não veem certas características e segmentos listados na página de relatórios de sobreposição ao tentar executar um relatório de sobreposição?

**Resposta**

Um requisito mínimo de visitante único precisa ser atendido para que uma característica ou segmento seja listado nos relatórios de sobreposição.


* Para características: 28000 durante o período de 14 dias
* Para segmentos: 70000 usuários em tempo real por um período de 14 dias

Mais detalhes sobre isso podem ser encontrados na página Amostragem de [dados e Taxas de erro nos relatórios](/help/using/reporting/report-sampling.md)selecionados do Audience Manager.