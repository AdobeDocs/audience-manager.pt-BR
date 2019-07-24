---
description: Perguntas e problemas comuns relacionados a definição de metas.
seo-description: Perguntas e problemas comuns relacionados a definição de metas.
seo-title: Perguntas frequentes sobre segmentação
solution: Audience Manager
title: Perguntas frequentes sobre segmentação
uuid: ee 96 ef 71-b 903-4953-afc 4-8 ec 8 e 48 bd 49 e
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Targeting FAQ{#targeting-faq}

Perguntas e problemas comuns relacionados a definição de metas.

<br> 

<!-- 

faq_targeting.xml

 -->

**Onde posso encontrar uma lista completa de provedores de dados de terceiros compatíveis com o Audience Manager?**

See the [Adobe Exchange Marketplace](https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) (https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) for a complete list of third-party data providers that [!DNL Audience Manager] supports.

<br> 

**Para direcionar os usuários que nunca vi no meu site com dados de terceiros, devo usar dados de terceiros no Audience Manager ou em um DSP?**

A resposta depende de suas metas. Por exemplo, se sua campanha foi projetada para localizar novos clientes com dados de terceiros e, em seguida, trabalhar diretamente com um DSP. Lembre-se, o Audience Manager sincroniza dados com um provedor de dados de terceiros somente quando visualizamos esse usuário. Se nunca visualizarmos um usuário, nosso sistema não terá informações para esse visitante do site. Para campanhas que só desejam usar dados de terceiros para direcionar os usuários que nunca visitaram nenhuma de suas propriedades, então crie esses segmentos por meio do DSP.

<br> 

**Posso comercializar para indivíduos?**

O Audience Manager permite que você agregue usuários e mercado a eles com base em atributos ou características compartilhadas. However, to comply with industry regulations, [!DNL Audience Manager] customers may not send personally identifiable information (PII) to our systems. Como resultado, não é possível usar endereços de email, nomes de indivíduos, endereços físicos etc. para direcionamento.

<br> 

**Como manter os dados de redefinição de metas com segurança?**

Recomendamos que você use uma conexão de servidor para servidor para trocar dados com sua plataforma de redefinição de metas preferida. O Audience Manager troca dados com a maioria dos principais dsps por meio de conexões de servidor para servidor. As transferências de dados de servidor a servidor ajudam a impedir que outros atores interceptem seus dados e enviem novamente essas informações do público-alvo.

<br> 

**A ID de usuário exclusiva do Audience Manager está vinculada à ID de usuário exclusiva do servidor de publicidade por meio da sincronização de ID diretamente na página?**

Não. As sincronizações de ID não são feitas na página para editores ou servidores locais. The Audience Manager UUID is inserted into the `u=` field of the ad server log files. Isso ocorre quando o segmento é passado para definição de metas. O módulo de código DIL executa essa função. Este é o mesmo mecanismo que nos permite mapear a ID de usuário do servidor para um usuário do Audience Manager para relatório de desempenho de segmento. No entanto, se um servidor de publicidade estiver presente no site, então sincronizamos IDs diretamente na página.

<br> 

**O Audience Manager conta um usuário que faz logon de diferentes dispositivos como um usuário único ou usuários únicos diferentes?**

[A Definição de metas](../features/declared-ids.md#declared-id-targeting) ID declarada ajuda o Audience Manager a identificar um visitante em vários dispositivos com um único identificador exclusivo. No entanto, de uma perspectiva de definição de metas ou destino, isso ainda é 2 (ou mais) usuários, pois dsps não pode reconciliar essas várias IDs.

<br> 

**Pode o Audience Manager identificar um usuário de dispositivos móveis e exibidos.**

Sim. See [Declared ID Targeting](../features/declared-ids.md#declared-id-targeting).

<br> 

**É possível pontuar os usuários com dados coletados online e retorná-los com base nesta pontuação do modelo?**

Sim. O Audience Manager pode fornecer arquivos de dados para ajudar a pontuar os usuários, mas você deve trabalhar com outros fornecedores ou softwares para analisar e classificar essas informações. Envie esses dados para o Audience Manager na forma de pares de valor chave. Podemos realizar essas informações e anexá-las a perfis de usuário existentes. Entre em contato com o representante de soluções do parceiro para analisar esse processo.

<br> 

**Quais são as taxas de exclusão de cookie por um determinado período de 1 a 2 meses?**

A exclusão do cookie é difícil de medir. A exclusão do cookie é proveniente de alguns visitantes que excluem cookies com frequência. No entanto, a maioria dos cookies do navegador é estável por pelo menos 30 dias, embora alguns possam ter uma vida limitada. Alguns estudos sugerem a definição de metas de funil superior que é superior a 30 dias, eliminando efetivamente 7% do público-alvo do navegador ao longo de um período de 30 dias. Como você sabe, as campanhas de 30 dias para uma determinada mensagem criativa são padrão no setor. A partir do que vimos, o menu suspenso de 7% é preciso.

A exclusão do cookie tem um efeito negativo nos cálculos de alcance e frequência. Como resultado, sublinhamos o valor dos dados comportamentais ao tentar entender a verdadeira natureza das tendências do consumidor para o planejamento da campanha de exibição. Nossos clientes podem aproveitar os relatórios de sobreposição de segmento do Audience Manager, relatórios de frequência de impressão ideais e tendências únicas do usuário em intervalos de datas específicos para serem mais científicos sobre o planejamento da campanha e os intervalos de datas ideais para a execução de campanhas.

<br> 

**Qual é a janela de expiração dos cookies do Audience Manager?**

A interface do usuário permite determinar o intervalo de expiração do cookie. You can set cookies to expire after *n* number of days or never.

<br> 

**A implementação de uma campanha criativa em uma chamada de evento nos custa mais?**

Depende de. O custo é baseado em usuários únicos. Se uma campanha resultar em novos usuários líquidos, sim, isso custará mais custo. Se a sua campanha chega a locais onde já coletamos dados, não há custo adicional. Se a sua campanha for executada em sites relacionados, onde houver uma sobreposição significativa, haverá um custo adicional para os novos usuários únicos que vemos.

<br> 

**O Audience Manager exibe[!UICONTROL Addressable Audiences]métricas e taxas de correspondência somente para[!UICONTROL Server-to-Server]destinos. Can you explain why we don't see these figures for Cookie and URL destinations?**

Ele se resume às sincronizações de ID. For [!UICONTROL Server-to-Server] destinations, we transfer data offline (either real-time or batch) and we need to send the ID that the destination partner understands, so they can map it back to the browser. O número endereçável do segmento é um subconjunto da população do segmento total.

In the case of Cookie and URL destinations, the user is already on the browser, and what [!DNL Audience Manager] sends is just the segments that the user qualified for. O parceiro de destino pode apenas coletar os mapeamentos de segmentos e trabalhar com essas informações. Portanto, considere as taxas de correspondência para os destinos de Cookie e URL sempre 100%.
