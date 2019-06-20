---
description: Uma visão geral de alto nível sobre como o Audience Manager troca informações com outros fornecedores de dados e sistemas.
seo-description: Uma visão geral de alto nível sobre como o Audience Manager troca informações com outros fornecedores de dados e sistemas.
seo-title: Métodos de integração de dados
solution: Audience Manager
title: Métodos de integração de dados
uuid: 17 a 4179 a-e 99 b -49 eb -8 f 45-f 2946 afbd 27 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Métodos de integração de dados {#data-integration-methods}

Uma visão geral de alto nível sobre como o Audience Manager troca informações com outros fornecedores de dados e sistemas.

## Supported Data Integration Methods: Real-Time and Server-to-Server {#supported-methods}

Escolher o método de integração certo depende de uma combinação de requisitos de negócios e dos recursos técnicos do seu parceiro de dados. O Audience Manager troca informações do visitante com outros provedores de dados por um dos seguintes métodos:

* **Tempo real:** Transfere dados imediatamente quando um usuário visita seu site. This method is also known as a *`synchronous`* integration.
* **Lote (servidor para servidor):** Transfere dados entre servidores em um agendamento definido depois que um visitante saiu da página. This method is also known as an *`out-of-band`* or *`asynchronous`* integration.

## Prerequisites: Create a Trait Taxonomy {#prereqs}

Before the integration process begins, remember to [create traits](../features/traits/create-onboarded-rule-based-traits.md) and a [folder structure](../features/traits/trait-storage.md#create-trait-storage-folder) in the [!DNL Audience Manager] UI. A taxonomia conterá todas as suas características organizadas em uma hierarquia lógica.

## Integration Use Cases {#integration-use-cases}

Um resumo de casos de integração de dados do Audience Manager, juntamente com as vantagens e desvantagens de cada um.

### Integrações de servidor em tempo real para servidor

<!-- c_int_types_use_cases.xml -->

Uma integração de dados de servidor a servidor em tempo real sincroniza rapidamente os dados do usuário entre os servidores do Audience Manager e outro sistema de direcionamento. Na maioria dos casos, o intercâmbio de dados ocorre em segundos ou minutos, dependendo da taxa de atualização do sistema de definição de metas. No entanto, o sistema segmentado determina este intervalo de atualização, não o Audience Manager. Além disso, a taxa de atualização pode variar entre sistemas diferentes. Uma integração de servidor em tempo real é o tipo de integração preferencial para trocas de dados. O Audience Manager usa este método sempre que os parceiros de definição de metas podem suportar.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Benefícios: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Permite que você qualifique usuários para segmentos sem visualizá-los novamente na página, em um player de vídeo etc. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Reduz o número de chamadas HTTP da página. Menos chamadas ajudam a preservar a experiência do usuário. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Ajuda com o direcionamento com sensibilidade a tempo para que você possa agir rapidamente em um usuário qualificado. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Útil ao mover-se para um DSP para direcionamento externo. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Desvantagens:</td>
  <td class="stentry"> Menos útil para a definição de metas no site quando você precisa direcionar o usuário na mesma página ou na página seguinte, com base na qualificação de um usuário para esse segmento.</td>
 </tr>
</table>

### Integrações em lote do servidor para servidor

Uma integração em lote de servidor para servidor agrupa dados e a envia para outros sistemas em intervalos definidos, em vez de em tempo quase real. Os intervalos de transferência de dados começam de 24 horas. Alguns provedores de dados suportam apenas esse tipo de integração. Entretanto, observamos uma tendência geral das integrações em lote para as metodologias de integração em tempo real.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Benefícios: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Permite que você qualifique usuários para segmentos sem visualizá-los novamente na página, em um player de vídeo etc. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Útil para direcionamento que não diferencia tempo. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Desvantagens:</td>
  <td class="stentry"> O intervalo de sincronização pode atrasar a definição de metas em relação aos dados mais atuais.</td>
 </tr>
</table>

### Chamadas em tempo real

As chamadas em tempo real trocam dados com o Audience Manager imediatamente, quando um usuário visita seu site ou executa ações na página. Com esse método, os sistemas de definição de metas obtêm os dados de qualificação de segmento mais atualizados e podem levar essas informações em consideração durante uma decisão de conteúdo ou entrega de anúncios. Além disso, esse processo funciona com servidores de publicidade do editor nos quais atualizamos segmentos qualificados para um cookie primário que é lido em uma chamada de anúncio como pares de valores chave. Currently, Audience Manager uses real-time calls to integrate with [!DNL Target] and other content management systems.

<table> 
 <tr>
  <td> <p>Benefícios: </p></td>
  <td> <p> Permite direcionar a próxima página, área de conteúdo ou impressão de anúncios com base na qualificação de segmento mais recente. </p></td> 
 </tr> 
 <tr>
  <td> <p>Desvantagens: </p></td>
  <td> <p>Adiciona uma chamada ao Audience Manager na página.</p></td>
 </tr> 
</table>


### Sincronizações de pixels para sistemas de definição de metas

A sincronização de pixels mapeia segmentos para pixels na página. O pixel dispara e transmite dados quando um usuário é qualificado para um segmento específico. A sincronização de pixels é um mecanismo rudimentar e não confiável de transferência de dados. Os fornecedores de dados de nível superior e sistemas raramente usam-os.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>Benefícios: </p></td>
  <td class="stentry"> <p> Transferências de dados em tempo real. </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>Desvantagens: </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">Pode adicionar muitas chamadas do cliente a partir da página. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">Não confiável para transmissão de dados. A perda de 5% a 20% é normal. </li>
   </ul></td>
 </tr> 
</table>

## How to Choose a Data Delivery Method {#data-delivery-choices}

Descreve motivos técnicos e comerciais para enviar dados por meio de metodologias síncronas (em tempo real) ou assíncronas (servidor a servidor).

<!-- c_int_delivery_choices.xml -->

### Selecionar um tipo de entrega de dados

* **Considerações técnicas:** A entrega de dados depende dos recursos técnicos do parceiro de dados. O Audience Manager pode enviar/receber dados em tempo real do navegador ou por atualizações em lote por meio de processos de comunicação offline, de servidor para servidor.
* **Considerações comerciais:** Os motivos empresariais para selecionar um método de entrega ou outro dependem dos recursos técnicos do seu parceiro de destino e da forma como você deseja usar esses dados. Normalmente, transferências de dados síncronos são úteis quando você precisa executar ações nos dados do usuário imediatamente. Transferências assíncronas de dados podem ser úteis quando uma ação imediata não é necessária e quando você tem tempo para criar perfis de usuário mais profundos para uso posterior.

## Real-Time Data Transfer Process {#real-time-data-transfer-process}

Uma visão geral geral de como o Audience Manager realiza uma troca de dados síncrona com um fornecedor terceirizado.

### Transferência de dados em tempo real

<!-- c_int_overview_sync.xml -->

As transferências de dados em tempo real enviam e recebem IDs de segmento enquanto um usuário visita ou executa ações em seu site. Normalmente, transferências de dados síncronos são úteis quando você precisa qualificar ou segmentar os usuários imediatamente, à medida que navegam pelo inventário.

### Etapas de integração de dados em tempo real

O processo de integração de dados em tempo real funciona da seguinte maneira:

1. Um usuário visita o site de um cliente que contém o código do Audience Manager.
1. Audience Manager loads an Iframe and makes a call to the [!UICONTROL Data Collection Server] ([!UICONTROL DCS]).
1. [!UICONTROL DCS] A chamada do servidor de terceiros (em tempo real) para verificar se o fornecedor tem informações de segmento sobre o usuário.
1. O terceiro retorna informações de segmento sobre esse usuário para o Audience Manager.
1. O Audience Manager assimila informações do segmento e o torna disponível para definição de metas.

![](assets/rt_reduce70.png)

## Batch Data Transfer Process {#batch-data-transfer-process}

Uma visão geral geral de como o Audience Manager envia dados sincronicamente (em tempo real) com um fornecedor terceirizado.

### Integração de dados em lote

<!-- c_int_overview_async.xml -->

O processo de integração de dados em lote (servidor a servidor) segue a maioria das etapas descritas no processo de transferência de dados em tempo real. No entanto, em vez de retornar IDs de segmento imediatamente, as informações do usuário são salvas nos nossos servidores e sincronizadas com um provedor de dados de terceiros em intervalos regulares. O processo assíncrono de transferência de dados é útil quando:

* Transferências de dados imediatas não são necessárias.
* Coleta de dados para criar um grande conjunto de usuários segmentados.
* You want to reduce data discrepancies and `HTTP` calls from the browser.

### Etapas de integração de dados em lote

1. Um usuário visita um site do cliente.
1. O Audience Manager e o provedor de dados de terceiros atribuem o visitante uma ID exclusiva (geralmente com um cookie).
1. O Audience Manager chama o provedor de dados de terceiros para corresponder às IDs do visitante.
1. Uma solicitação programada, normalmente em um intervalo diário, envia os dados de segmento do visitante entre o Audience Manager e seu provedor de dados de terceiros.

![](assets/s2s_70.png)

For information describing the time frames when Audience Manager processes inbound and outbound Server-to-Server ([!UICONTROL S2S]) file transfers, see [Reporting and File Transfer Time-Frame Guidelines](../reference/reporting-file-transfer-timeframe.md).
