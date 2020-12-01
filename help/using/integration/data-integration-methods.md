---
description: Uma visão geral de alto nível de como o Audience Manager troca informações com outros provedores e sistemas de dados.
seo-description: Uma visão geral de alto nível de como o Audience Manager troca informações com outros provedores e sistemas de dados.
seo-title: Métodos de integração de dados
solution: Audience Manager
title: Métodos de integração de dados
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1085'
ht-degree: 1%

---


# Métodos de integração de dados {#data-integration-methods}

Uma visão geral de alto nível de como o Audience Manager troca informações com outros provedores e sistemas de dados.

## Métodos de integração de dados suportados: Tempo real e [!DNL Server-to-Server] {#supported-methods}

A escolha do método de integração correto depende de uma combinação de requisitos de negócios e dos recursos técnicos do seu parceiro de dados. A Audience Manager troca informações sobre visitantes com outros provedores de dados por um dos seguintes métodos:

* **Tempo real:** transfere dados imediatamente quando um usuário visita seu site. Esse método também é conhecido como uma integração *`synchronous`*.
* **Lote ([!DNL Server-to-Server]):** Transfere dados entre servidores em uma programação definida depois que um visitante deixa a página. Esse método também é conhecido como uma integração *`out-of-band`* ou *`asynchronous`*.

## Pré-requisitos: Criar uma Taxonomia de características {#prereqs}

Antes de iniciar o processo de integração, lembre-se de [criar características](../features/traits/create-onboarded-rule-based-traits.md) e [estrutura de pastas](../features/traits/trait-storage.md#create-trait-storage-folder) na interface do usuário [!DNL Audience Manager]. A taxonomia conterá todos os seus [!UICONTROL traits] organizados em uma hierarquia lógica.

## Casos de uso da integração {#integration-use-cases}

Um resumo do caso de uso dos métodos de integração de dados Audience Manager, juntamente com as vantagens e desvantagens de cada um.

### Integrações [!DNL Server-to-Server] em tempo real

<!-- c_int_types_use_cases.xml -->

Uma integração de dados [!DNL server-to-server] em tempo real sincroniza rapidamente os dados do usuário entre os servidores de Audience Manager e outro sistema de definição de metas. Na maioria dos casos, a troca de dados ocorre em segundos ou minutos, dependendo da taxa de atualização do sistema de definição de metas. Observe, no entanto, que o sistema de destino determina esse intervalo de atualização, não Audience Manager. Além disso, a taxa de atualização pode variar entre diferentes sistemas. Uma integração [!UICONTROL server-to-server] em tempo real é o tipo de integração preferencial para trocas de dados. A Audience Manager usa esse método sempre que os parceiros de definição de metas puderem suportá-lo.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Benefícios: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Permite qualificar usuários para segmentos sem vê-los novamente na página, em um player de vídeo etc. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Reduz o número de chamadas HTTP da página. Menos chamadas ajudam a preservar a experiência do usuário. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Ajuda com direcionamento que leva em consideração o tempo para que você possa agir rapidamente em um usuário qualificado. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Útil ao mudar para um DSP para direcionamento externo. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Desvantagens:</td>
  <td class="stentry"> Menos útil para o direcionamento no site quando você precisa público alvo o usuário na mesma página, ou na próxima, com base na qualificação de um usuário para esse segmento.</td>
 </tr>
</table>

### [!DNL Server-to-Server] Integrações em lote

Uma integração em lote [!DNL server-to-server] agrupa dados e os envia para outros sistemas em intervalos definidos, em vez de em tempo quase real. Start de intervalos de transferência de dados de 24 horas. Alguns provedores de dados suportam apenas esse tipo de integração. Entretanto, temos visto uma tendência geral de integração de lote para metodologias de integração em tempo real.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Benefícios: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Permite qualificar usuários para segmentos sem vê-los novamente na página, em um player de vídeo etc. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Útil para direcionamento que não diferencia tempo. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Desvantagens:</td>
  <td class="stentry"> O intervalo de sincronização pode atrasar a definição de metas em relação aos dados mais atuais.</td>
 </tr>
</table>

### Chamadas em tempo real

As chamadas em tempo real trocam dados imediatamente com o Audience Manager, à medida que um usuário visita seu site ou age na página. Com esse método, os sistemas de definição de metas obtêm os dados de qualificação de segmento mais atualizados e podem levar essas informações em conta durante uma decisão de conteúdo ou delivery de anúncio. Além disso, esse processo funciona com servidores de anúncios de editores, onde atualizamos segmentos qualificados para um cookie primário que é lido em uma chamada de anúncio como pares de valor chave. Atualmente, o Audience Manager usa chamadas em tempo real para integrar com [!DNL Adobe Target] e outros sistemas de gestão de conteúdo.

<table> 
 <tr>
  <td> <p>Benefícios: </p></td>
  <td> <p> Permite que você público alvo a próxima página, área de conteúdo ou impressão de anúncio com base na qualificação de segmento mais recente. </p></td> 
 </tr> 
 <tr>
  <td> <p>Desvantagens: </p></td>
  <td> <p>Adiciona uma chamada ao Audience Manager da página.</p></td>
 </tr> 
</table>


### Pixels são sincronizados com sistemas de definição de metas

A sincronização de pixels mapeia segmentos para pixels na página. O pixel dispara e transmite dados quando um usuário se qualifica para um segmento específico. A sincronização de pixels é um mecanismo rudimentar e não confiável de transferência de dados. Os provedores de dados de nível superior e os sistemas raramente o usam.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>Benefícios: </p></td>
  <td class="stentry"> <p> Transferências de dados em tempo real. </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>Desvantagens: </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">É possível adicionar várias chamadas do cliente da página. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">Não confiável para transmissão de dados. Perda de 5% a 20% é normal. </li>
   </ul></td>
 </tr> 
</table>

## Como escolher um método de Delivery de dados {#data-delivery-choices}

Descreve motivos técnicos e comerciais para enviar dados por meio de metodologias síncronas (em tempo real) ou assíncronas (servidor para servidor).

<!-- c_int_delivery_choices.xml -->

### Como selecionar um tipo de Delivery de dados

* **Considerações técnicas:O delivery** de dados depende dos recursos técnicos do parceiro de dados. O Audience Manager pode enviar/receber dados em tempo real do navegador ou por atualizações em lote por meio de processos de comunicação offline de servidor para servidor.
* **Considerações comerciais:** os motivos comerciais para selecionar um método de delivery ou outro dependem dos recursos técnicos do parceiro de destino e de como você deseja usar esses dados. Normalmente, as transferências de dados síncronas são úteis quando é necessário executar uma ação nos dados do usuário imediatamente. Transferências de dados assíncronas podem ser úteis quando não é necessária uma ação imediata e quando você tem tempo para criar perfis mais profundos para o usuário para uso posterior.

## Processo de transferência de dados em tempo real {#real-time-data-transfer-process}

Uma visão geral de como o Audience Manager executa uma troca de dados síncrona com um fornecedor terceirizado.

### Transferência de dados em tempo real

<!-- c_int_overview_sync.xml -->

As transferências de dados em tempo real enviam e recebem IDs de segmento quando um usuário visita ou age em seu site. Normalmente, as transferências de dados síncronas são úteis quando você precisa qualificar ou segmentar os usuários imediatamente, à medida que eles navegam pelo seu inventário.

### Etapas da integração de dados em tempo real

O processo de integração de dados em tempo real funciona da seguinte maneira:

1. Um usuário visita o site de um cliente que contém o código de Audience Manager.
1. Audience Manager carrega um Iframe e faz uma chamada para [!UICONTROL Data Collection Server] ([!DNL DCS]).
1. O [!DNL DCS] chama o servidor de terceiros (em tempo real) para verificar se o fornecedor tem alguma informação de segmento sobre o usuário.
1. O terceiro retorna as informações do segmento sobre esse usuário ao Audience Manager.
1. O Audience Manager ingere informações de segmento e as disponibiliza para definição de metas.

![](assets/rt_reduce70.png)

## Processo de transferência de dados em lote {#batch-data-transfer-process}

Uma visão geral de como o Audience Manager troca dados sincronicamente (em tempo real) com um fornecedor terceirizado.

### Integração de dados em lote

<!-- c_int_overview_async.xml -->

O processo de integração de dados em lote ([!DNL server-to-server]) segue a maioria das etapas descritas no processo de transferência de dados em tempo real. No entanto, em vez de retornar IDs de segmento imediatamente, as informações do usuário são salvas em nossos servidores e sincronizadas com um provedor de dados de terceiros em intervalos regulares. O processo de transferência de dados assíncrono é útil quando:

* Não são necessárias transferências de dados imediatas.
* Coleta de dados para criar um grande pool de usuários segmentados.
* Você deseja reduzir as discrepâncias de dados e as chamadas `HTTP` do navegador.

### Etapas de integração de dados em lote

1. Um usuário visita um site de cliente.
1. Audience Manager e o provedor de dados de terceiros atribuem ao visitante uma ID exclusiva (normalmente com um cookie).
1. Audience Manager chama o provedor de dados de terceiros para corresponder às IDs de visitante.
1. Uma solicitação programada, normalmente em um intervalo diário, troca dados de segmento de visitante entre o Audience Manager e o provedor de dados de terceiros.

![](assets/s2s_70.png)

Para obter informações que descrevem os intervalos de tempo quando o Audience Manager processa [!DNL Server-to-Server] ([!UICONTROL S2S]) transferências de arquivos de entrada e saída, consulte [Diretrizes de tempo de transferência de Relatórios e arquivos](../reference/reporting-file-transfer-timeframe.md).
