---
description: As opções de regra de mesclagem permitem controlar o tipo de uso do Audience Manager de dados para segmentação. Uma regra de mesclagem pode incluir perfis de dispositivo mapeados pelo gráfico de dispositivo do Link de Perfil, o Adobe Experience Cloud Device Co-op e/ou outros provedores de gráficos de dispositivo de terceiros que estão integrados ao Audience Manager. É possível criar um máximo de quatro Regras de mesclagem de Perfis.
seo-description: As opções de regra de mesclagem permitem controlar o tipo de uso do Audience Manager de dados para segmentação. Uma regra de mesclagem pode incluir perfis de dispositivo mapeados pelo gráfico de dispositivo do Link de Perfil, o Adobe Experience Cloud Device Co-op e/ou outros provedores de gráficos de dispositivo de terceiros que estão integrados ao Audience Manager. É possível criar um máximo de quatro Regras de mesclagem de Perfis.
seo-title: Definição das opções de regra de mesclagem de Perfis
solution: Audience Manager
title: Definição das opções de regra de mesclagem de Perfis
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 4%

---


# Profile Merge Rules Options Defined {#profile-merge-rule-options-defined}

The merge rule options let you control the type of data [!DNL Audience Manager] uses for segmentation. Uma regra de mesclagem pode incluir perfis de dispositivo mapeados pelo gráfico de [!UICONTROL Profile Link] dispositivo, os provedores de gráficos de dispositivo de terceiros [!UICONTROL Adobe Experience Cloud Device Co-op]e/ou outros com os quais eles estão integrados [!DNL Audience Manager]. Você pode criar um máximo de 4 [!UICONTROL Profile Merge Rules]. O quarto [!UICONTROL Profile Merge Rule] está disponível exclusivamente para clientes que compraram o complemento [!UICONTROL People-Based Destinations] .

Crie um formulário [!UICONTROL Profile Merge Rule] fazendo uma seleção das opções descritas abaixo, em [!UICONTROL Profile Merge Rule Setup].

![configuração de regra de união de perfis](assets/profile-merge-rule-setup.png)

## Profile Merge Rule Options Overview {#overview}

[!UICONTROL Profile Merge Rules] permitir várias combinações de regras, cada uma delas orientada para casos de uso específicos. Consulte a tabela abaixo para obter detalhes sobre quando usar cada combinação de regras.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilidade | Tipo de avaliação | [!UICONTROL Audience Lab] Suporte | Casos de uso |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Todos os clientes | Tempo real e lote | Sim | [Direcionamento de dispositivo](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] (inclui [!UICONTROL Co-op Device Graph]) | Todos os clientes | Tempo real e lote | Não | [Definição de meta de dispositivo expandida](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Todos os clientes | Somente em tempo real | Não | [Direcionamento de dispositivo compartilhado](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Todos os clientes | Tempo real e lote | Sim | [Direcionamento online/offline](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Todos os clientes | Tempo real e lote | Sim | [Definição de metas entre dispositivos](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] (inclui [!UICONTROL Co-op Device Graph]) | Todos os clientes | Tempo real e lote | Não | [Direcionamento avançado entre dispositivos](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | N/A | Exclusivo para clientes de Destinos [Baseados em](../destinations/people-based-destinations-overview.md) Pessoas | Somente em lote | Não | [Definição de metas para destinos baseados em pessoas](merge-rule-targeting-options.md#all-cross-device) |

## Avaliação do segmento da regra de mesclagem de Perfis {#segment-evaluation}

Dependendo da sua [!UICONTROL Profile Merge Rules] configuração, [!DNL Audience Manager] é possível executar a avaliação de segmentos em tempo real, em lote ou em ambos.

* A avaliação de segmentos em tempo real exige que os visitantes acessem suas propriedades digitais em tempo real para se qualificarem para o segmento. [!DNL DCS]
* A avaliação do segmento de lote é realizada em relação a características qualificadas anteriormente.
* [!UICONTROL Profile Merge Rules] que suportam a avaliação de segmentos em tempo real e em lote combinam a atividade de visitante em tempo real com características qualificadas anteriormente.

## Latência do Relatórios das Regras de Mesclagem de Perfis {#reporting-latency}

A avaliação de segmentos em tempo real reflete imediatamente nos [!UICONTROL Profile Merge Rules] relatórios.

A avaliação do segmento de lote pode levar até 24 horas para ser refletida nos relatórios [de Regras de mesclagem de](profile-link-metrics.md)Perfis.

## Opções entre dispositivos {#auth-options}

O [!UICONTROL Cross-Device Options] permite selecionar usuários autenticados e não autenticados e aproveitar seu perfil entre dispositivos para segmentação. Essas opções ajudam a identificar e acessar usuários específicos em um dispositivo compartilhado. Para obter mais informações sobre usuários anônimos e autenticados, consulte Estados de autenticação de [Visitante](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p>Informa ao <span class="keyword"> Audience Manager</span> para não usar os dados coletados de usuários autenticados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfis Autenticados Atuais</span></b> </p> </td> 
   <td colname="col2"> <p>Informa o <span class="keyword"> Audience Manager</span> a ler e gravar dados no perfil autenticado se um visitante tiver feito logon no site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Últimos Perfis autenticados</span></b> </p> </td> 
   <td colname="col2"> <p>Informa ao <span class="keyword"> Audience Manager</span> para ler os dados do perfil autenticado do usuário que fez logon pela última vez no dispositivo. </p> <p>Quando selecionado, o <span class="keyword"> Audience Manager</span> não gravará novos dados de características no perfil autenticado se o usuário for anônimo. Após a autenticação, os novos dados de características são gravados no perfil autenticado do usuário. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Todos os Perfis entre dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Informa a Audience Manager para ler dados de todos os perfis entre dispositivos, independentemente do estado de autenticação. Esta opção só está disponível para clientes do Audience Manager que compraram o complemento de Destinos baseados em pessoas.</p> </td>
  </tr>
 </tbody>
</table>

## Opções de Perfil entre dispositivos {#profile-options}

A [!UICONTROL Cross-Device Profile Options] lista suas fontes de dados entre dispositivos. Essas opções usam os nomes fornecidos quando você criou uma fonte de dados entre dispositivos (consulte [Criar uma fonte](merge-rules-start.md#create-data-source)de dados entre dispositivos). Você pode selecionar até 3 fontes de dados entre dispositivos para usar com cada regra de perfil. Os [!UICONTROL Authenticated Profile Options] estão disponíveis quando você escolher **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**.

## Opções do dispositivo {#device-options}

O [!UICONTROL Device Options] permite selecionar o tipo de *`device profile`* usado por um [!UICONTROL Profile Merge Rule]. Um perfil de dispositivo é criado a partir de características coletadas de atividades de navegação anônimas. No mínimo, uma regra de união de perfis inclui uma opção autenticada e uma opção de dispositivo.

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
   <td colname="col2"> <p>Informa ao <span class="keyword"> Audience Manager</span> para não usar as características contidas no perfil anônimo para segmentação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfil do dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Informa ao <span class="keyword"> Audience Manager</span> para usar o perfil de dispositivo anônimo para segmentação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de dispositivos de link de Perfil</span></b> </p> </td> 
   <td colname="col2"> <p>Informa a <span class="keyword"> Audience Manager</span> para ler os perfis do dispositivo atual e até 100 outros dispositivos dos quais o usuário foi autenticado. Este gráfico de dispositivos foi criado com base em seus próprios dados primários no <span class="keyword"> Audience Manager</span>. É ideal para clientes que têm um alto nível de autenticação em suas propriedades digitais. O gráfico do dispositivo Link <span class="wintitle"> do</span> Perfil é atualizado em tempo real. Essa opção está disponível quando você seleciona <b><span class="uicontrol"> Perfil</span></b> Autenticado atual ou <b><span class="uicontrol"> Último Perfil</span></b>autenticado. Ao usar essa opção, você só pode escolher um único perfil autenticado (o<span class="keyword"> Audience Manager</span> fica automaticamente cinza os outros). Consulte também, Casos <a href="profile-link-use-case.md"> de uso do gráfico de dispositivo de link de</a>Perfil. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de dispositivos cooperativos</span></b> </p> </td> 
   <td colname="col2"> <p>Informa o <span class="keyword"> Audience Manager</span> a ler os perfis do dispositivo atual e até 100 outros dispositivos usando os links fornecidos pelo <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co-op</a>. </p> <p>O <span class="keyword"> Device Co-op</span> é uma cooperativa digital em que os participantes compartilham informações de links de dispositivos. O <span class="keyword"> Device Co-op</span> processa esses dados em um gráfico <span class="term"> de</span>dispositivos. Um gráfico de dispositivo vincula dispositivos em conjunto a partir de clusters de dispositivos. Esses links são criados a partir de dados <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"></a>probabilísticos e determinísticos. Os clusters representam um grupo de dispositivos usados por uma pessoa desconhecida. O <span class="keyword">Device Co-op</span> compartilha esses grupos entre os seus membros, o que os ajuda a entregar experiências valiosas e consistentes entre dispositivos para os seus clientes. </p> <p> Para obter mais informações sobre o <span class="wintitle"> Device Co-op</span>, consulte: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Visão geral do Device Co-op</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> Requisitos de adesão</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> Gráfico de dispositivos: Processos internos e saída</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Opções</b> de gráfico de dispositivo de terceiros (Pessoa e Família) </p> </td>
   <td colname="col2"> <p>Essas opções permitem criar regras de mesclagem com base na tecnologia de gráficos de dispositivos fornecida por um fornecedor terceirizado. Um gráfico de dispositivo de terceiros fornece: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Dados probabilísticos e/ou determinísticos. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Dados ao nível da pessoa ou do agregado familiar. </li> 
     </ul> </p> <p>Para usar essas opções, você deve ser um cliente de um gráfico de dispositivo que já esteja integrado ao <span class="keyword"> Audience Manager</span>. Entre em contato com seu gerente de conta para obter mais informações ou para começar. </p> </td>
  </tr>
 </tbody>
</table>

## Políticas de mesclagem externas {#external-merge-policies}

Os segmentos de Audiência que foram criados automaticamente a partir de outras soluções de Experience Cloud, com base nas regras de mesclagem definidas fora do [!DNL Audience Manager], são marcados como usando um [!UICONTROL External Merge Policy]. Por exemplo, consulte Compartilhamento de [Audiência entre Audience Manager e Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre as regras de mesclagem de Perfis](../../faq/faq-profile-merge.md)

