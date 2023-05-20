---
description: Perguntas e problemas comuns relacionados ao direcionamento.
seo-description: Common targeting-related questions and issues.
seo-title: Targeting FAQ
solution: Audience Manager
title: Perguntas frequentes sobre direcionamento
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
feature: Match Rates
exl-id: e5f761fd-dfc8-4859-a81e-89abbd7f2914
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 100%

---

# Perguntas frequentes sobre direcionamento{#targeting-faq}

Perguntas e problemas comuns relacionados ao direcionamento.

<br> 

<!-- 

faq_targeting.xml

 -->

**Onde posso encontrar uma lista completa de provedores de dados de terceiros compatíveis com o Audience Manager?**

Consulte o [Adobe Exchange Marketplace](https://exchange.adobe.com/experiencecloud.html) para obter uma lista completa de provedores de dados de terceiros compatíveis com o [!DNL Audience Manager].

<br> 

**Para direcionar usuários que nunca vi em meu site com dados de terceiros, devo usar dados de terceiros no Audience Manager ou em um DSP?**

A resposta depende dos seus objetivos. Por exemplo, se sua campanha foi projetada para encontrar novos clientes com dados de terceiros, trabalhe diretamente com um DSP. Lembre-se, o Audience Manager sincroniza dados com um provedor de dados de terceiros somente quando vemos esse usuário. Se nunca vimos um usuário antes, nosso sistema não terá nenhuma informação para esse visitante do site. Para campanhas que desejam usar apenas dados de terceiros para direcionar usuários que nunca visitaram nenhuma de suas propriedades, crie esses segmentos por meio do DSP.

<br> 

**Posso vender para os indivíduos?**

O Audience Manager permite agregar usuários e vender para eles com base em atributos ou características compartilhadas. No entanto, para cumprir com os regulamentos do setor, os clientes do [!DNL Audience Manager] podem não enviar informações de identificação pessoal (PII) para nossos sistemas. Como resultado, não é possível usar endereços de email, nomes, endereços físicos etc. para direcionar.

<br> 

**Como faço para manter o redirecionamento de dados seguro?**

Recomendamos usar uma conexão servidor a servidor para trocar dados com sua plataforma de redefinição de metas preferida. O Audience Manager troca dados com a maioria dos principais DSPs por meio de conexões servidor a servidor. As transferências de dados de servidor para servidor ajudam a impedir que outras partes interceptem seus dados e revendam essas informações de público-alvo.

<br> 

**A ID de usuário exclusiva (UUID) do Audience Manager está vinculada à ID de usuário exclusiva de um servidor de publicidade por meio da sincronização de ID diretamente na página?**

Não. As sincronizações de ID não são feitas na página para editores ou servidores no site. A UUID do Audience Manager é inserida no campo `u=` dos arquivos de log do servidor de publicidade. Isso acontece quando o segmento é passado para o direcionamento. O módulo de código DIL executa essa função. Esse é o mesmo mecanismo que nos permite mapear a ID de usuário do servidor para um usuário do Audience Manager para o relatórios de desempenho do segmento. No entanto, se um servidor de publicidade estiver presente no site, então sincronizamos IDs diretamente na página.

<br> 

**O Audience Manager conta um usuário que faz logon em dispositivos diferentes como um usuário único ou usuários únicos diferentes?**

[O direcionamento de ID declarada](../features/declared-ids.md#declared-id-targeting) ajuda o Audience Manager a identificar um visitante em vários dispositivos com um único identificador exclusivo. No entanto, de uma perspectiva de direcionamento ou destino, ainda são 2 (ou mais) usuários, pois os DSPs não podem reconciliar essas várias IDs.

<br> 

**O Audience Manager pode identificar um usuário de dispositivos móveis e de exibição.**

Sim. Consulte [Direcionamento de ID declarada](../features/declared-ids.md#declared-id-targeting).

<br> 

**Posso pontuar usuários com dados coletados online e redirecioná-los com base nessa pontuação de modelo?**

Sim. O Audience Manager pode fornecer arquivos de dados para ajudar você a pontuar os usuários, mas você deve trabalhar com outros fornecedores ou softwares para analisar e classificar essas informações. Envie esses dados para o Audience Manager na forma de pares de valores-chave. Podemos pegar essas informações e anexá-las aos perfis de usuário existentes. Entre em contato com seu representante de soluções de parceiros para analisar esse processo.

<br> 

**Quais são as taxas de exclusão de cookies em um determinado período de 1 a 2 meses?**

É difícil medir a exclusão de cookies. A maioria das exclusões de cookies vem de alguns visitantes que excluem cookies frequentemente. No entanto, a maioria dos cookies do navegador é estável por pelo menos 30 dias, mesmo que alguns possam ter uma vida limitada. Alguns estudos sugerem que a definição de metas de funil superior, que é superior a 30 dias, eliminaria com eficiência 7% do público-alvo do navegador em um período de 30 dias. Como você sabe, campanhas de 30 dias para determinada mensagem criativa são padrão no setor. Pelo que vimos, essa queda de 7% é precisa.

A exclusão de cookies tem um efeito adverso no cálculo de alcance e frequência. Como resultado, enfatizamos o valor dos dados comportamentais ao tentar entender a verdadeira natureza das tendências do consumidor para o planejamento da campanha. Nossos clientes podem usar os relatórios de sobreposição de segmentos do Audience Manager, os relatórios de frequência de impressão ideais e as tendências exclusivas do usuário em intervalos de datas específicos para serem mais científicos sobre o planejamento de campanhas e os intervalos de datas ideais para executar campanhas.

<br> 

**Qual é a janela de expiração dos cookies do Audience Manager?**

A interface do usuário permite determinar o intervalo de expiração do cookie. Você pode definir que os cookies expirem após *um número* de dias ou nunca.

<br> 

**A implementação de um anúncio de campanha em uma chamada de evento custa mais?**

Depende. O custo se baseia em usuários únicos. Se uma campanha resultar em novos usuários líquidos, custará mais. Se a campanha chegar a lugares onde já estamos coletando dados, não há custo adicional. Se a campanha for executada em sites relacionados com sobreposição significativa, haverá um custo adicional para os novos usuários únicos que vemos.

<br> 

O **Audience Manager exibe métricas de [!UICONTROL Addressable Audiences] e taxas de correspondência somente para destinos [!UICONTROL Server-to-Server]. Você pode explicar por que não vemos esses números para Cookie e destinos de URL?**

Isso se resume a sincronizações de ID. Para destinos [!UICONTROL Server-to-Server], transferimos dados offline (em tempo real ou em lote) e precisamos enviar a ID que o parceiro de destino entende, para que eles possam mapeá-los de volta ao navegador. O número endereçável do segmento é um subconjunto da população total do segmento.

No caso de Cookie e destinos de URL, o usuário já está no navegador e o que o [!DNL Audience Manager] envia são apenas os segmentos para os quais o usuário se qualificou. O parceiro de destino pode apenas coletar os mapeamentos de segmentos e trabalhar com essas informações. Portanto, considere as taxas de correspondência para Cookie e destinos de URL sempre como 100%.
