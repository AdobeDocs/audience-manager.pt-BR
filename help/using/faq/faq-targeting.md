---
description: Perguntas e problemas comuns relacionados à definição de metas.
seo-description: Perguntas e problemas comuns relacionados à definição de metas.
seo-title: Perguntas frequentes sobre definição de metas
solution: Audience Manager
title: Perguntas frequentes sobre definição de metas
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Perguntas frequentes sobre definição de metas{#targeting-faq}

Perguntas e problemas comuns relacionados à definição de metas.

<br> 

<!-- 

faq_targeting.xml

 -->

**Onde posso encontrar uma lista completa de provedores de dados de terceiros suportados pelo Audiência Manager?**

Consulte o [Adobe Exchange Marketplace](https://exchange.adobe.com/experiencecloud.html) para obter uma lista completa de provedores de dados de terceiros [!DNL Audience Manager] compatíveis.

<br> 

**Para usuários do público alvo que nunca vi em meu site com dados de terceiros, devo usar dados de terceiros no Audiência Manager ou em um DSP?**

A resposta depende de seus objetivos. Por exemplo, se sua campanha foi projetada para encontrar novos clientes com dados de terceiros, trabalhe diretamente com um DSP. Lembre-se, o Audiência Manager sincroniza dados com um provedor de dados de terceiros somente quando vemos esse usuário. Se nunca vimos um usuário antes, nosso sistema não terá nenhuma informação para esse visitante do site. Para campanhas que desejam usar apenas dados de terceiros para usuários públicos alvos que nunca visitaram nenhuma de suas propriedades, crie esses segmentos por meio do DSP.

<br> 

**Posso vender para os indivíduos?**

O Gerenciador de Audiências permite que você agregação usuários e comercialize para eles com base em atributos ou características compartilhadas. No entanto, para cumprir com os regulamentos do setor, [!DNL Audience Manager] os clientes podem não enviar informações de identificação pessoal (PII) para nossos sistemas. Como resultado, não é possível usar endereços de email, nomes individuais, endereços físicos etc. para definição de metas.

<br> 

**Como faço para manter o redirecionamento de dados com segurança?**

Recomendamos que você use uma conexão servidor a servidor para trocar dados com sua plataforma de redefinição de metas preferida. O Gerenciador de Audiências troca dados com a maioria dos principais DSPs por meio de conexões servidor a servidor. As transferências de dados de servidor para servidor ajudam a impedir que outros atores interceptem seus dados e revendam essas informações de audiência.

<br> 

**A ID de usuário exclusiva (UUID) do Gerenciador de Audiências está vinculada à ID de usuário exclusiva de um servidor de publicidade por meio da sincronização de ID diretamente na página?**

Não. As sincronizações de ID não são feitas na página para editores ou servidores no site. O UUID do Gerenciador de Audiências é inserido no `u=` campo dos arquivos de log do servidor de publicidade. Isso acontece quando o segmento é passado para definição de metas. O módulo de código DIL executa essa função. Esse é o mesmo mecanismo que nos permite mapear a ID de usuário do servidor para um usuário do Gerenciador de Audiências para o relatórios de desempenho do segmento. No entanto, se um servidor de publicidade estiver presente no site, então sincronizamos IDs diretamente na página.

<br> 

**O Gerenciador de Audiências conta um usuário que faz logon de dispositivos diferentes como um usuário único ou usuários únicos diferentes?**

[A segmentação](../features/declared-ids.md#declared-id-targeting) de ID declarada ajuda o Gerenciador de Audiências a identificar um visitante em vários dispositivos com um único identificador exclusivo. No entanto, de uma perspectiva de direcionamento ou destino, ainda são 2 (ou mais) usuários, pois os DSPs não podem reconciliar essas várias IDs.

<br> 

**O Gerenciador de Audiências pode identificar um usuário de dispositivos móveis e de exibição.**

Sim. Consulte Definição [de meta](../features/declared-ids.md#declared-id-targeting)de ID declarada.

<br> 

**Posso pontuar usuários com dados coletados online e redirecioná-los com base nesta pontuação de modelo?**

Sim. O Gerenciador de Audiências pode fornecer arquivos de dados para ajudá-lo a pontuar os usuários, mas você deve trabalhar com outros fornecedores ou softwares para analisar e classificar essas informações. Envie esses dados para o Gerenciador de Audiências na forma de pares de valores chave. Podemos pegar essas informações e anexá-las aos perfis de usuário existentes. Entre em contato com seu representante de soluções de parceiros para analisar esse processo.

<br> 

**Quais são as taxas de exclusão de cookies em um determinado período de 1 a 2 meses?**

A exclusão de cookies é difícil de medir. A maioria das exclusões de cookies vem de alguns visitantes que excluem cookies frequentemente. No entanto, a maioria dos cookies do navegador é estável por pelo menos 30 dias, mesmo que alguns possam ter uma vida limitada. Alguns estudos sugerem que a definição de metas de funil superior, que é superior a 30 dias, eliminaria com eficácia 7% da audiência de público alvo do navegador em um período de 30 dias. Como você sabe, campanhas de 30 dias para determinada mensagem criativa são padrão no setor. Pelo que vimos, essa queda de 7% é precisa.

A exclusão de cookies tem um efeito adverso no cálculo de alcance e frequência. Como resultado, enfatizamos o valor dos dados comportamentais ao tentar entender a verdadeira natureza das tendências do consumidor para o planejamento da campanha. Nossos clientes podem aproveitar os relatórios de sobreposição de segmentos do Gerenciador de Audiências, os relatórios de frequência de impressão ideais e as tendências exclusivas do usuário em intervalos de datas específicos para serem mais científicos sobre o planejamento de campanhas e os intervalos de datas ideais para executar o campanha.

<br> 

**Qual é a janela de expiração dos cookies do Audiência Manager?**

A interface do usuário permite determinar o intervalo de expiração do cookie. Você pode definir cookies para expirar após *um número* de dias ou nunca.

<br> 

**A implementação de um anúncio de campanha em uma chamada de evento nos custa mais?**

Depende. O custo se baseia em usuários únicos. Se uma campanha resultar em novos usuários líquidos, isso custará mais. Se sua campanha chega a lugares onde já estamos coletando dados, então não há custo adicional. Se sua campanha for executada em sites relacionados com sobreposição significativa, haverá um custo adicional para os novos usuários únicos que vemos.

<br> 

**O Gerenciador de Audiências exibe[!UICONTROL Addressable Audiences]métricas e taxas de correspondência somente para[!UICONTROL Server-to-Server]destinos. Você pode explicar por que não vemos esses números para Cookie e destinos de URL?**

Isso se resume a sincronizações de ID. Para [!UICONTROL Server-to-Server] destinos, transferimos dados offline (em tempo real ou em lote) e precisamos enviar a ID que o parceiro de destino entende, para que possam mapeá-los de volta ao navegador. O número endereçável do segmento é um subconjunto da população total do segmento.

No caso de Cookie e destinos de URL, o usuário já está no navegador e o que [!DNL Audience Manager] envia são apenas os segmentos para os quais o usuário se qualificou. O parceiro de destino pode apenas coletar os mapeamentos de segmentos e trabalhar com essas informações. Portanto, considere as taxas de correspondência para Cookie e destinos de URL sempre 100%.
