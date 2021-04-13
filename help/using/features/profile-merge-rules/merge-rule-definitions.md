---
description: As opções de regra de mesclagem permitem controlar o tipo de dados que o Audience Manager de dados usa para segmentação. Uma regra de mesclagem pode incluir perfis de dispositivos mapeados pelo gráfico de dispositivos Link de perfil, pelo Adobe Experience Cloud Device Co-op e/ou por outros provedores de gráficos de dispositivos de terceiros integrados ao Audience Manager. Você pode criar no máximo 4 Regras de mesclagem de perfil.
seo-description: As opções de regra de mesclagem permitem controlar o tipo de dados que o Audience Manager de dados usa para segmentação. Uma regra de mesclagem pode incluir perfis de dispositivos mapeados pelo gráfico de dispositivos Link de perfil, pelo Adobe Experience Cloud Device Co-op e/ou por outros provedores de gráficos de dispositivos de terceiros integrados ao Audience Manager. Você pode criar no máximo 4 Regras de mesclagem de perfil.
seo-title: Definição das opções da regra de mesclagem de perfis
solution: Audience Manager
title: Definição das opções da regra de mesclagem de perfis
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Mesclar perfis
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 6%

---

# [!UICONTROL Profile Merge Rules] Opções definidas  {#profile-merge-rule-options-defined}

As opções [!UICONTROL profile merge rule] permitem controlar o tipo de dados que [!DNL Audience Manager] usa para segmentação. Um [!UICONTROL profile merge rule] pode incluir perfis de dispositivos mapeados pelo gráfico de dispositivos [!UICONTROL Profile Link], pelo [!UICONTROL Adobe Experience Cloud Device Co-op] e/ou por outros provedores de gráficos de dispositivos de terceiros que estão integrados com [!DNL Audience Manager]. Você pode criar um máximo de 4 [!UICONTROL Profile Merge Rules]. O quarto [!UICONTROL Profile Merge Rule] está disponível exclusivamente para clientes que compraram o complemento [!UICONTROL People-Based Destinations].

Crie um [!UICONTROL Profile Merge Rule] fazendo uma seleção entre as opções descritas abaixo, em [!UICONTROL Profile Merge Rule Setup].

![configuração de regras de mesclagem de perfis](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Visão geral das opções  {#overview}

[!UICONTROL Profile Merge Rules] permitir diversas combinações de regras, cada uma delas orientada para casos de uso específicos. Consulte a tabela abaixo para obter detalhes sobre quando usar cada combinação de regras.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilidade | Tipo de avaliação | [!UICONTROL Audience Lab] Suporte | Casos de uso |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Todos os clientes | Tempo real e lote | Sim | [Direcionamento de dispositivo](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] (inclui  [!UICONTROL Co-op Device Graph]) | Todos os clientes | Tempo real e lote | Não | [Direcionamento de dispositivo expandido](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Todos os clientes | Somente em tempo real | Não | [Direcionamento de dispositivo compartilhado](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Todos os clientes | Tempo real e lote | Sim | [Direcionamento online/offline](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Todos os clientes | Tempo real e lote | Sim | [Direcionamento entre dispositivos](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] (inclui  [!UICONTROL Co-op Device Graph]) | Todos os clientes | Tempo real e lote | Não | [Direcionamento entre dispositivos avançado](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | N/A | Exclusivo para clientes [com base em pessoas](../destinations/people-based-destinations-overview.md) | Somente em lote | Não | [Direcionamento para destinos com base em pessoas](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Avaliação  {#segment-evaluation}

Dependendo da configuração [!UICONTROL Profile Merge Rules], [!DNL Audience Manager] pode executar a avaliação [!UICONTROL segment] em tempo real, em lote ou ambos.

* A avaliação [!UICONTROL segment] em tempo real requer [!DNL DCS] para ver os visitantes acessarem suas propriedades digitais em tempo real, para se qualificarem para o [!UICONTROL segment].
* A avaliação em lote [!UICONTROL segment] é executada em relação a [!UICONTROL traits] qualificado anteriormente.
* [!UICONTROL Profile Merge Rules] que oferecem suporte para a  [!UICONTROL segment] avaliação em tempo real e em lote, combinam a atividade em tempo real do visitante com as qualificações anteriores  [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] Latência dos relatórios  {#reporting-latency}

A avaliação [!UICONTROL segment] em tempo real reflete imediatamente nos relatórios [!UICONTROL Profile Merge Rules].

A avaliação em lote [!UICONTROL segment] pode levar até 24 horas para ser refletida nos [Relatórios de Regras de mesclagem de perfil](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

O [!UICONTROL Cross-Device Options] permite selecionar usuários autenticados e não autenticados e aproveitar seu perfil entre dispositivos para segmentação. Essas opções ajudam a identificar e alcançar usuários específicos em um dispositivo compartilhado. Para obter mais informações sobre usuários anônimos e autenticados, consulte [Estados de autenticação de visitante em Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção entre dispositivos </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Sem perfil entre dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Faz com que <span class="keyword"> Audience Manager</span> não use dados coletados de usuários autenticados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfis Autenticados Atuais</span></b> </p> </td> 
   <td colname="col2"> <p>Informa <span class="keyword"> Audience Manager</span> para ler e gravar dados no perfil autenticado se um visitante tiver feito logon no site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Últimos perfis autenticados</span></b> </p> </td> 
   <td colname="col2"> <p>Informa <span class="keyword"> Audience Manager</span> para ler os dados do perfil autenticado do usuário que fez logon pela última vez no dispositivo. </p> <p>Quando selecionado, <span class="keyword"> Audience Manager</span> não gravará novos dados de característica no perfil autenticado se o usuário for anônimo. Após a autenticação, os novos dados de característica são gravados no perfil autenticado do usuário. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Todos os perfis entre dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Faz com que o Audience Manager leia os dados de todos os perfis entre dispositivos, independentemente do estado de autenticação. Essa opção só está disponível para clientes do Audience Manager que compraram o complemento Destinos com base em pessoas .</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

O [!UICONTROL Cross-Device Profile Options] lista seu [!UICONTROL cross-device data sources]. Essas opções usam os nomes fornecidos ao criar um [!UICONTROL cross-device] [!UICONTROL data source] (consulte [Criar uma fonte de dados entre dispositivos](merge-rules-start.md#create-data-source)). Você pode selecionar até 3 [!UICONTROL cross-device data sources] para usar com cada regra de perfil. Os [!UICONTROL Authenticated Profile Options] estão disponíveis ao escolher **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

O [!UICONTROL Device Options] permite selecionar o tipo de *`device profile`* usado por um [!UICONTROL Profile Merge Rule]. Um perfil de dispositivo é criado a partir de [!UICONTROL traits] coletado de uma atividade de navegação anônima. No mínimo, um [!UICONTROL profile merge rule] inclui um [!UICONTROL authenticated option] e um [!UICONTROL device option].

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção de dispositivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Sem Perfil de Dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Faz com que <span class="keyword"> Audience Manager</span> não use as características contidas no perfil anônimo para segmentação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfil do dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Informa <span class="keyword"> Audience Manager</span> para usar o perfil de dispositivo anônimo para segmentação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de dispositivos de link de perfil</span></b> </p> </td> 
   <td colname="col2"> <p>Informa <span class="keyword"> Audience Manager</span> para ler os perfis do dispositivo atual e até 100 outros dispositivos dos quais o usuário se autenticou. Este gráfico de dispositivos é criado em seus próprios dados primários em <span class="keyword"> Audience Manager</span>. É ideal para clientes que têm um alto nível de autenticação em suas propriedades digitais. O gráfico de dispositivo <span class="wintitle"> Link de perfil</span> é atualizado em tempo real. Essa opção está disponível ao selecionar <b><span class="uicontrol"> Perfil atual autenticado</span></b> ou <b><span class="uicontrol"> Último perfil autenticado</span></b>. Ao usar essa opção, você só pode escolher um único perfil autenticado (<span class="keyword"> Audience Manager</span> automaticamente esmaece os outros). Consulte também, <a href="profile-link-use-case.md"> Casos de uso do gráfico do dispositivo de link de perfil</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de dispositivos cooperativos</span></b> </p> </td> 
   <td colname="col2"> <p>Informa <span class="keyword"> Audience Manager</span> para ler os perfis do dispositivo atual e até 100 outros dispositivos usando os links fornecidos pelo <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co-op</a>. </p> <p>O <span class="keyword"> Device Co-op</span> é uma cooperativa digital em que os participantes compartilham informações de links de dispositivos. O <span class="keyword"> Device Co-op</span> processa esses dados em um <span class="term"> gráfico do dispositivo</span>. Um gráfico de dispositivos vincula os dispositivos aos clusters de dispositivos. Esses links são criados a partir de <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"> dados probabilísticos e determinísticos</a>. Os grupos representam um grupo de dispositivos usados por uma pessoa desconhecida. O <span class="keyword">Device Co-op</span> compartilha esses grupos entre os seus membros, o que os ajuda a entregar experiências valiosas e consistentes entre dispositivos para os seus clientes. </p> <p> Para obter mais informações sobre o <span class="wintitle"> Device Co-op</span>, consulte: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Visão geral do Device Co-op</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> Requisitos de adesão</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> Gráfico de dispositivos: Processos e Saída Internos</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Opções de gráfico de dispositivo de terceiros</b>  (pessoa e residência) </p> </td>
   <td colname="col2"> <p>Essas opções permitem criar regras de mesclagem com base na tecnologia de gráficos de dispositivos fornecida por um fornecedor terceirizado. Um gráfico de dispositivos de terceiros fornece: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Dados probabilísticos e/ou determinísticos. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Dados ao nível da pessoa ou do agregado familiar. </li> 
     </ul> </p> <p>Para usar essas opções, você deve ser um cliente de um gráfico de dispositivos que já esteja integrado com <span class="keyword"> Audience Manager</span>. Entre em contato com o gerente da conta para obter mais informações ou começar. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Segmentos de público-alvo que foram criados automaticamente a partir de outras [!DNL Experience Cloud] soluções, com base nas regras de mesclagem definidas fora de [!DNL Audience Manager], são marcados como usando um [!UICONTROL External Merge Policy]. Por exemplo, consulte [Compartilhamento de público entre o Audience Manager e o Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre as regras de mesclagem de perfis](../../faq/faq-profile-merge.md)

