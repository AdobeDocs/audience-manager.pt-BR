---
description: As opções de regra de mesclagem permitem controlar o tipo de uso do Audience Manager de dados para segmentação. Uma regra de mesclagem pode incluir perfis de dispositivos mapeados pelo gráfico de dispositivos do Link de Perfil, o Adobe Experience Cloud Device Co-op e/ou outros provedores de gráficos de dispositivos de terceiros que estão integrados ao Audience Manager. É possível criar um máximo de quatro Regras de mesclagem de Perfis.
seo-description: As opções de regra de mesclagem permitem controlar o tipo de uso do Audience Manager de dados para segmentação. Uma regra de mesclagem pode incluir perfis de dispositivos mapeados pelo gráfico de dispositivos do Link de Perfil, o Adobe Experience Cloud Device Co-op e/ou outros provedores de gráficos de dispositivos de terceiros que estão integrados ao Audience Manager. É possível criar um máximo de quatro Regras de mesclagem de Perfis.
seo-title: Definição das opções da regra de mesclagem de perfis
solution: Audience Manager
title: Definição das opções da regra de mesclagem de perfis
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 6%

---


# [!UICONTROL Profile Merge Rules] Opções definidas  {#profile-merge-rule-options-defined}

As opções [!UICONTROL profile merge rule] permitem controlar o tipo de dados que [!DNL Audience Manager] usa para segmentação. Um [!UICONTROL profile merge rule] pode incluir perfis de dispositivo mapeados pelo gráfico de dispositivo [!UICONTROL Profile Link], os [!UICONTROL Adobe Experience Cloud Device Co-op] e/ou outros provedores de gráficos de dispositivos de terceiros que estão integrados com [!DNL Audience Manager]. Você pode criar um máximo de 4 [!UICONTROL Profile Merge Rules]. O quarto [!UICONTROL Profile Merge Rule] está disponível exclusivamente para clientes que compraram o complemento [!UICONTROL People-Based Destinations].

Crie um [!UICONTROL Profile Merge Rule] fazendo uma seleção das opções descritas abaixo, em [!UICONTROL Profile Merge Rule Setup].

![configuração de regra de união de perfis](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Visão geral das opções  {#overview}

[!UICONTROL Profile Merge Rules] permitir várias combinações de regras, cada uma delas orientada para casos de uso específicos. Consulte a tabela abaixo para obter detalhes sobre quando usar cada combinação de regras.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilidade | Tipo de avaliação | [!UICONTROL Audience Lab] Suporte | Casos de uso |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Todos os clientes | Tempo real e lote | Sim | [Direcionamento de dispositivo](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] (inclui  [!UICONTROL Co-op Device Graph]) | Todos os clientes | Tempo real e lote | Não | [Definição de meta de dispositivo expandida](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Todos os clientes | Somente em tempo real | Não | [Direcionamento de dispositivo compartilhado](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Todos os clientes | Tempo real e lote | Sim | [Direcionamento online/offline](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Todos os clientes | Tempo real e lote | Sim | [Definição de metas entre dispositivos](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] (inclui  [!UICONTROL Co-op Device Graph]) | Todos os clientes | Tempo real e lote | Não | [Direcionamento avançado entre dispositivos](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | N/A | Exclusivo para clientes [de Destinos Baseados em Pessoas](../destinations/people-based-destinations-overview.md) | Somente em lote | Não | [Definição de metas para destinos baseados em pessoas](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Avaliação  {#segment-evaluation}

Dependendo da configuração [!UICONTROL Profile Merge Rules], [!DNL Audience Manager] pode executar a avaliação [!UICONTROL segment] em tempo real, em lote ou em ambos.

* A avaliação em tempo real [!UICONTROL segment] requer que [!DNL DCS] veja os visitantes acessarem suas propriedades digitais em tempo real, para se qualificarem para [!UICONTROL segment].
* A avaliação de lote [!UICONTROL segment] é realizada em relação a [!UICONTROL traits] qualificados anteriormente.
* [!UICONTROL Profile Merge Rules] que suportam a  [!UICONTROL segment] avaliação em tempo real e em lote combinam a atividade do visitante em tempo real com as qualificações anteriores  [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] Latência do relatórios  {#reporting-latency}

A avaliação em tempo real [!UICONTROL segment] reflete imediatamente nos relatórios [!UICONTROL Profile Merge Rules].

A avaliação de lote [!UICONTROL segment] pode levar até 24 horas para ser refletida nos [relatórios de Regras de mesclagem de Perfis](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

O [!UICONTROL Cross-Device Options] permite selecionar usuários autenticados e não autenticados e aproveitar seu perfil entre dispositivos para segmentação. Essas opções ajudam a identificar e acessar usuários específicos em um dispositivo compartilhado. Para obter mais informações sobre usuários anônimos e autenticados, consulte [Estados de autenticação de Visitante em Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção entre dispositivos </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Nenhum Perfil entre dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Informa <span class="keyword"> Audience Manager</span> para não usar dados coletados de usuários autenticados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfis Autenticados Atuais</span></b> </p> </td> 
   <td colname="col2"> <p>Informa <span class="keyword"> Audience Manager</span> para ler e gravar dados no perfil autenticado se um visitante tiver feito logon no site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Últimos Perfis autenticados</span></b> </p> </td> 
   <td colname="col2"> <p>Informa <span class="keyword"> Audience Manager</span> para ler dados do perfil autenticado do usuário que fez logon pela última vez no dispositivo. </p> <p>Quando selecionado, <span class="keyword"> Audience Manager</span> não gravará novos dados de características no perfil autenticado se o usuário for anônimo. Após a autenticação, os novos dados de características são gravados no perfil autenticado do usuário. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Todos os Perfis entre dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Informa a Audience Manager para ler dados de todos os perfis entre dispositivos, independentemente do estado de autenticação. Esta opção só está disponível para clientes do Audience Manager que compraram o complemento de Destinos baseados em pessoas.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

O [!UICONTROL Cross-Device Profile Options] lista seu [!UICONTROL cross-device data sources]. Essas opções usam os nomes fornecidos quando você criou um [!UICONTROL cross-device] [!UICONTROL data source] (consulte [Criar uma fonte de dados entre dispositivos](merge-rules-start.md#create-data-source)). Você pode selecionar até 3 [!UICONTROL cross-device data sources] para usar com cada regra de perfil. Os [!UICONTROL Authenticated Profile Options] estão disponíveis quando você escolhe **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

O [!UICONTROL Device Options] permite que você selecione o tipo de *`device profile`* usado por um [!UICONTROL Profile Merge Rule]. Um perfil de dispositivo é criado de [!UICONTROL traits] coletado de uma atividade de navegação anônima. No mínimo, um [!UICONTROL profile merge rule] inclui um [!UICONTROL authenticated option] e um [!UICONTROL device option].

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção de dispositivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Nenhum Perfil de dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Informa <span class="keyword"> Audience Manager</span> para não usar as características contidas no perfil anônimo para segmentação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfil do dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Informa <span class="keyword"> Audience Manager</span> para usar o perfil de dispositivo anônimo para segmentação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de dispositivos de link de perfil</span></b> </p> </td> 
   <td colname="col2"> <p>Informa <span class="keyword"> Audience Manager</span> para ler os perfis do dispositivo atual e até 100 outros dispositivos dos quais o usuário foi autenticado. Este gráfico de dispositivo foi criado em seus próprios dados primários em <span class="keyword"> Audience Manager</span>. É ideal para clientes que têm um alto nível de autenticação em suas propriedades digitais. O gráfico do dispositivo <span class="wintitle"> Link do Perfil</span> é atualizado em tempo real. Esta opção está disponível quando você seleciona <b><span class="uicontrol"> Perfil Autenticado Atual</span></b> ou <b><span class="uicontrol"> Perfil Autenticado pela Última Vez</span></b>. Ao usar essa opção, você só pode escolher um único perfil autenticado (<span class="keyword"> Audience Manager</span> automaticamente desfoca os outros). Consulte também <a href="profile-link-use-case.md"> Casos de uso do gráfico de dispositivo de link de Perfil</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de dispositivos cooperativos</span></b> </p> </td> 
   <td colname="col2"> <p>Informa <span class="keyword"> Audience Manager</span> para ler os perfis do dispositivo atual e até 100 outros dispositivos usando os links fornecidos pelo <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co-op</a>. </p> <p>O <span class="keyword"> Device Co-op</span> é uma cooperativa digital em que os participantes compartilham informações de links de dispositivos. O <span class="keyword"> Device Co-op</span> processa esses dados em um gráfico de dispositivo <span class="term"></span>. Um gráfico de dispositivo vincula dispositivos em conjunto a partir de clusters de dispositivos. Esses links são criados a partir de <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"> dados probabilísticos e determinísticos</a>. Os clusters representam um grupo de dispositivos usados por uma pessoa desconhecida. O <span class="keyword">Device Co-op</span> compartilha esses grupos entre os seus membros, o que os ajuda a entregar experiências valiosas e consistentes entre dispositivos para os seus clientes. </p> <p> Para obter mais informações sobre o <span class="wintitle"> Device Co-op</span>, consulte: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Visão geral do Device Co-op</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> Requisitos de adesão</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> Gráfico de dispositivos: Processos internos e saída</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Opções</b>  de gráfico de dispositivo de terceiros (Pessoa e Família) </p> </td>
   <td colname="col2"> <p>Essas opções permitem criar regras de mesclagem com base na tecnologia de gráficos de dispositivos fornecida por um fornecedor terceirizado. Um gráfico de dispositivo de terceiros fornece: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Dados probabilísticos e/ou determinísticos. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Dados ao nível da pessoa ou do agregado familiar. </li> 
     </ul> </p> <p>Para usar essas opções, você deve ser um cliente de um gráfico de dispositivo que já esteja integrado com <span class="keyword"> Audience Manager</span>. Entre em contato com seu gerente de conta para obter mais informações ou para começar. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Segmentos de audiência que foram criados automaticamente a partir de outras soluções [!DNL Experience Cloud], com base em regras de mesclagem definidas fora de [!DNL Audience Manager], são marcados como usando um [!UICONTROL External Merge Policy]. Por exemplo, consulte [Compartilhamento de Audiência entre Audience Manager e Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre as regras de mesclagem de perfis](../../faq/faq-profile-merge.md)

