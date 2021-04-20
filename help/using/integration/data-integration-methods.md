---
description: Uma visão geral de alto nível de como o Audience Manager troca informações com outros provedores e sistemas de dados.
seo-description: Uma visão geral de alto nível de como o Audience Manager troca informações com outros provedores e sistemas de dados.
seo-title: Métodos de integração de dados
solution: Audience Manager
title: Métodos de integração de dados
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: Third-party Integration
exl-id: 26225461-c35c-4db1-9517-99e82ce163b9
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 1%

---

# Métodos de integração de dados {#data-integration-methods}

Uma visão geral de alto nível de como o Audience Manager troca informações com outros provedores e sistemas de dados.

## Métodos de integração de dados suportados: Tempo real e [!DNL Server-to-Server] {#supported-methods}

A escolha do método de integração correto depende de uma combinação de requisitos comerciais e dos recursos técnicos do seu parceiro de dados. O Audience Manager troca informações do visitante com outros provedores de dados por um dos seguintes métodos:

* **Tempo real:** transfere dados imediatamente quando um usuário visita seu site. Esse método também é conhecido como uma integração *`synchronous`*.
* **Lote ([!DNL Server-to-Server]):** transfere dados entre servidores em um agendamento definido depois que um visitante deixa a página. Esse método também é conhecido como uma integração *`out-of-band`* ou *`asynchronous`*.

## Pré-requisitos: Criar uma taxonomia de características {#prereqs}

Antes de iniciar o processo de integração, lembre-se de [criar características](../features/traits/create-onboarded-rule-based-traits.md) e uma [estrutura de pastas](../features/traits/trait-storage.md#create-trait-storage-folder) na interface do usuário [!DNL Audience Manager]. A taxonomia conterá todos os [!UICONTROL traits] organizados em uma hierarquia lógica.

## Casos de uso da integração {#integration-use-cases}

Um resumo do caso de uso dos métodos de integração de dados do Audience Manager, juntamente com as vantagens e desvantagens de cada um.

### Integrações [!DNL Server-to-Server] em tempo real

<!-- c_int_types_use_cases.xml -->

Uma integração de dados [!DNL server-to-server] em tempo real sincroniza rapidamente os dados do usuário entre os servidores do Audience Manager e outro sistema de direcionamento. Na maioria dos casos, a troca de dados ocorre em segundos ou minutos, dependendo da taxa de atualização do sistema de definição de metas. Observe, no entanto, que o sistema de destino determina esse intervalo de atualização, não o Audience Manager. Além disso, a taxa de atualização pode variar entre diferentes sistemas. Uma integração [!UICONTROL server-to-server] em tempo real é o tipo de integração preferido para trocas de dados. O Audience Manager usa esse método sempre que os parceiros de direcionamento podem suportá-lo.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Benefícios: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Permite qualificar usuários para segmentos sem vê-los novamente na página, em um reprodutor de vídeo etc. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Reduz o número de chamadas HTTP da página. Menos chamadas ajudam a preservar a experiência do usuário. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Ajuda com o direcionamento sensível ao tempo para que você possa realizar ações em um usuário qualificado rapidamente. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Útil ao migrar para uma DSP para direcionamento externo. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Desvantagens:</td>
  <td class="stentry"> Menos útil para direcionamento no site quando é necessário direcionar o usuário na mesma página ou na próxima, com base na qualificação de um usuário para esse segmento.</td>
 </tr>
</table>

### [!DNL Server-to-Server] Integrações em lote

Uma integração em lote [!DNL server-to-server] agrupa dados e os envia para outros sistemas em intervalos definidos, em vez de em tempo quase real. Os intervalos de transferência de dados começam a partir de 24 horas. Alguns provedores de dados oferecem suporte somente para esse tipo de integração. Entretanto, temos visto uma tendência geral de integração em lote para metodologias de integração em tempo real.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Benefícios: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Permite qualificar usuários para segmentos sem vê-los novamente na página, em um reprodutor de vídeo etc. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Útil para direcionamento que não diferencia tempo. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Desvantagens:</td>
  <td class="stentry"> O intervalo de sincronização pode atrasar o direcionamento em relação aos dados mais atuais.</td>
 </tr>
</table>

### Chamadas em tempo real

As chamadas em tempo real trocam dados com o Audience Manager imediatamente, à medida que um usuário visita seu site ou toma medidas na página. Com esse método, os sistemas de definição de metas obtêm os dados de qualificação de segmento mais atualizados e podem levar essas informações em consideração durante uma decisão de entrega de conteúdo ou anúncio. Além disso, esse processo funciona com servidores de anúncios do editor, onde atualizamos segmentos qualificados para um cookie próprio que é lido em uma chamada de anúncio como pares de valor chave. Atualmente, o Audience Manager usa chamadas em tempo real para integrar com [!DNL Adobe Target] e outros sistemas de gerenciamento de conteúdo.

<table> 
 <tr>
  <td> <p>Benefícios: </p></td>
  <td> <p> Permite direcionar a próxima página, área de conteúdo ou impressão de anúncio com base na qualificação de segmento mais recente. </p></td> 
 </tr> 
 <tr>
  <td> <p>Desvantagens: </p></td>
  <td> <p>Adiciona uma chamada ao Audience Manager a partir da página.</p></td>
 </tr> 
</table>


### Sincronizações de pixels para sistemas de direcionamento

A sincronização de pixels mapeia segmentos para pixels na página. O pixel dispara e transmite dados quando um usuário se qualifica para um segmento específico. A sincronização de pixels é um mecanismo rudimentar e não confiável de transferência de dados. Os provedores e sistemas de dados de nível superior raramente o usam.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>Benefícios: </p></td>
  <td class="stentry"> <p> Transferências de dados em tempo real. </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>Desvantagens: </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">Pode adicionar muitas chamadas do lado do cliente na página. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">Não é confiável para transmissão de dados. Perda de 5% a 20% é normal. </li>
   </ul></td>
 </tr> 
</table>

## Como escolher um método de entrega de dados {#data-delivery-choices}

Descreve motivos técnicos e comerciais para enviar dados por metodologias síncronas (em tempo real) ou assíncronas (servidor para servidor).

<!-- c_int_delivery_choices.xml -->

### Seleção de um tipo de delivery de dados

* **Considerações técnicas:** a entrega de dados depende dos recursos técnicos do parceiro de dados. O Audience Manager pode enviar/receber dados em tempo real do navegador ou por atualizações em lote por meio de processos de comunicação offline e de servidor para servidor.
* **Considerações comerciais:** os motivos comerciais para selecionar um método de entrega ou outro dependem dos recursos técnicos do parceiro de destino e de como você deseja usar esses dados. Normalmente, as transferências de dados síncronas são úteis quando é necessário tomar medidas nos dados do usuário imediatamente. As transferências assíncronas de dados podem ser úteis quando uma ação imediata não é necessária e quando você tem tempo para criar perfis de usuário mais profundos para uso posterior.

## Processo de transferência de dados em tempo real {#real-time-data-transfer-process}

Uma visão geral de como o Audience Manager executa uma troca de dados síncrona com um fornecedor terceirizado.

### Transferência de dados em tempo real

<!-- c_int_overview_sync.xml -->

As transferências de dados em tempo real enviam e recebem IDs de segmento conforme um usuário visita ou toma medidas no site. Normalmente, as transferências de dados síncronas são úteis quando é necessário qualificar ou segmentar os usuários imediatamente, conforme eles navegam pelo inventário.

### Etapas da integração de dados em tempo real

O processo de integração de dados em tempo real funciona da seguinte maneira:

1. Um usuário visita o site de um cliente que contém código Audience Manager.
1. O Audience Manager carrega um Iframe e faz uma chamada para o [!UICONTROL Data Collection Server] ([!DNL DCS]).
1. O [!DNL DCS] chama o servidor de terceiros (em tempo real) para verificar se o fornecedor tem alguma informação de segmento sobre o usuário.
1. O terceiro retorna as informações do segmento sobre esse usuário para o Audience Manager.
1. O Audience Manager assimila informações de segmentos e as disponibiliza para direcionamento.

![](assets/rt_reduce70.png)

## Processo de transferência de dados em lote {#batch-data-transfer-process}

Uma visão geral de como o Audience Manager troca dados de forma síncrona (em tempo real) com um fornecedor terceirizado.

### Integração de dados em lote

<!-- c_int_overview_async.xml -->

O processo de integração de dados em lote ([!DNL server-to-server]) segue a maioria das etapas descritas no processo de transferência de dados em tempo real. No entanto, em vez de retornar IDs de segmento imediatamente, as informações do usuário são salvas em nossos servidores e sincronizadas com um provedor de dados de terceiros em intervalos regulares. O processo assíncrono de transferência de dados é útil quando:

* Não são necessárias transferências de dados imediatas.
* Coleta de dados para criar um grande pool de usuários segmentados.
* Você deseja reduzir as discrepâncias de dados e as chamadas `HTTP` do navegador.

### Etapas da integração de dados em lote

1. Um usuário visita um site de cliente.
1. O Audience Manager e o provedor de dados de terceiros atribuem ao visitante uma ID exclusiva (geralmente com um cookie).
1. O Audience Manager chama o provedor de dados de terceiros para corresponder às IDs do visitante.
1. Uma solicitação programada, normalmente em um intervalo diário, troca dados do segmento de visitante entre o Audience Manager e seu provedor de dados de terceiros.

![](assets/s2s_70.png)

Para obter informações descrevendo os intervalos de tempo quando o Audience Manager processa transferências de arquivos [!DNL Server-to-Server] de entrada e saída ([!UICONTROL S2S]), consulte [Diretrizes de tempo de transferência de arquivos e relatórios](../reference/reporting-file-transfer-timeframe.md).
