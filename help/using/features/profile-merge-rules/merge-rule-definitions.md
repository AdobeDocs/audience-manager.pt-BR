---
description: As opções de regra de mesclagem permitem controlar o tipo de dados que o Audience Manager usa para segmentação. Uma regra de mesclagem pode incluir perfis de dispositivo mapeados pelo gráfico de dispositivo do Link de perfil, pelo Adobe Experience Cloud Device Co-op e/ou outros provedores de gráficos de dispositivo de terceiros integrados ao Audience Manager. É possível criar um máximo de 3 Regras de mesclagem de perfil.
seo-description: As opções de regra de mesclagem permitem controlar o tipo de dados que o Audience Manager usa para segmentação. Uma regra de mesclagem pode incluir perfis de dispositivo mapeados pelo gráfico de dispositivo do Link de perfil, pelo Adobe Experience Cloud Device Co-op e/ou outros provedores de gráficos de dispositivo de terceiros integrados ao Audience Manager. É possível criar um máximo de 3 Regras de mesclagem de perfil.
seo-title: Definição das opções de regra de mesclagem de perfil
solution: Audience Manager
title: Definição das opções de regra de mesclagem de perfil
uuid: 225eaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rule Options Defined {#profile-merge-rule-options-defined}

As opções de regra de mesclagem permitem controlar o tipo de dados que o Audience Manager usa para segmentação. Uma regra de mesclagem pode incluir perfis de dispositivo mapeados pelo gráfico de [!UICONTROL Profile Link] dispositivo, pelos provedores de gráficos de dispositivo de terceiros [!UICONTROL Adobe Experience Cloud Device Co-op]e/ou outros que estejam integrados ao Audience Manager. Você pode criar um máximo de 3 [!UICONTROL Profile Merge Rules].

Você cria uma [!UICONTROL Profile Merge Rule] seleção com estas opções:

<ul class="simplelist"> 
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#auth-options"> Opções autenticadas</a> </li>
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#profile-options"> Opções de perfil autenticadas</a> </li>
 <li><a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> Opções do dispositivo</a> </li>
</ul>

## Opções autenticadas {#auth-options}

O [!UICONTROL Authenticated Options] permite selecionar usuários não autenticados e autenticados e aproveitar seu perfil entre dispositivos para segmentação. Essas opções ajudam a identificar e acessar usuários específicos em um dispositivo compartilhado. Para obter mais informações sobre usuários anônimos e autenticados, consulte Estados de autenticação do [visitante no Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção autenticada </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Nenhum perfil autenticado</span></b> </p> </td> 
   <td colname="col2"> <p>Informa <span class="keyword"> o Audience Manager</span> para não usar os dados coletados de usuários autenticados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfil atual autenticado</span></b> </p> </td> 
   <td colname="col2"> <p>Instrui o <span class="keyword"> Audience Manager</span> a ler e gravar dados no perfil autenticado se um visitante tiver feito logon em seu site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Último perfil autenticado</span></b> </p> </td> 
   <td colname="col2"> <p>Informa <span class="keyword"> o Audience Manager</span> para ler dados do perfil autenticado do usuário que fez logon pela última vez no dispositivo. </p> <p>Quando selecionada, <span class="keyword"> o Audience Manager</span> não gravará novos dados de características no perfil autenticado se o usuário for anônimo. Após a autenticação, os novos dados de características são gravados no perfil autenticado do usuário. </p> </td>
  </tr> 
 </tbody>
</table>

## Opções de perfil autenticadas {#profile-options}

A [!UICONTROL Authenticated Profile Options] lista as fontes de dados entre dispositivos. Essas opções usam os nomes fornecidos quando você criou uma fonte de dados entre dispositivos (consulte [Criar uma fonte](../../features/profile-merge-rules/merge-rules-start.md#create-data-source)de dados entre dispositivos). Você pode selecionar até 3 fontes de dados entre dispositivos para usar com cada regra de perfil. Os [!UICONTROL Authenticated Profile Options] estão disponíveis quando você escolher **[!UICONTROL Current Authenticated Profile]** ou **[!UICONTROL Last Authenticated Profile]**.

## Opções do dispositivo {#device-options}

O [!UICONTROL Device Options] permite selecionar o tipo de *`device profile`* usado por um [!UICONTROL Profile Merge Rule]. Um perfil de dispositivo é composto de características coletadas pelos usuários que navegam anonimamente na Web. No mínimo, uma regra de mesclagem de perfil inclui uma opção autenticada e uma opção de dispositivo.

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção de dispositivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Sem perfil de dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Diz ao <span class="keyword"> Audience Manager</span> para não usar as características contidas no perfil anônimo para segmentação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfil do dispositivo atual</span></b> </p> </td> 
   <td colname="col2"> <p>Informa <span class="keyword"> o Audience Manager</span> para usar o perfil de dispositivo anônimo para segmentação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de dispositivos de link de perfil</span></b> </p> </td> 
   <td colname="col2"> <p>Instrui o <span class="keyword"> Audience Manager</span> a ler os perfis do dispositivo atual e dos últimos 3 dispositivos dos quais o usuário foi autenticado. Este gráfico de dispositivo é criado com base em seus próprios dados primários no <span class="keyword"> Audience Manager</span>. É ideal para clientes que têm um alto nível de autenticação em suas propriedades digitais. O gráfico do dispositivo Link <span class="wintitle"> do</span> perfil é atualizado em tempo real. Esta opção está disponível quando você seleciona <b><span class="uicontrol"> Perfil</span></b> Autenticado Atual ou Perfil <b><span class="uicontrol"></span></b>Último Autenticado. Ao usar essa opção, você só pode escolher um único perfil autenticado (<span class="keyword"> o Audience Manager</span> automaticamente fica cinza nos outros). Consulte também, <a href="../../features/profile-merge-rules/profile-link-use-case.md"> Casos</a>de uso do gráfico de dispositivo de link de perfil. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de dispositivos cooperativos</span></b> </p> </td> 
   <td colname="col2"> <p>Informa o <span class="keyword"> Audience Manager</span> para unir perfis de dispositivo usando os links fornecidos pelo Device Co-op <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> da</a>Experience Cloud. </p> <p>O <span class="keyword"> Device Co-op</span> é uma cooperativa digital em que os participantes compartilham informações de links de dispositivos. O <span class="keyword"> Device Co-op</span> processa esses dados em um gráfico <span class="term"> de</span>dispositivos. Um gráfico de dispositivo vincula dispositivos em conjunto a partir de clusters de dispositivos. Esses links são criados a partir de dados <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"></a>probabilísticos e determinísticos. Os clusters representam um grupo de dispositivos usados por uma pessoa desconhecida. O <span class="keyword">Device Co-op</span> compartilha esses grupos entre os seus membros, o que os ajuda a entregar experiências valiosas e consistentes entre dispositivos para os seus clientes. </p> <p> Para obter mais informações sobre o <span class="wintitle"> Device Co-op</span>, consulte: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html" format="https" scope="external"> Visão geral do Device Co-op</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-requirements.html" format="https" scope="external"> Requisitos de adesão</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html" format="https" scope="external"> Gráfico de dispositivos: Processos internos e saída</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Audience Manager e Gráficos</a> de dispositivos externos (download de PDF). </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Opções</b> de gráfico de dispositivo de terceiros (Pessoa e Família) </p> </td>
   <td colname="col2"> <p>Essas opções permitem criar regras de mesclagem com base na tecnologia de gráficos de dispositivos fornecida por um fornecedor terceirizado. Um gráfico de dispositivo de terceiros fornece: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Dados probabilísticos e/ou determinísticos. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Dados ao nível da pessoa ou do agregado familiar. </li> 
     </ul> </p> <p>Para usar essas opções, você deve ser um cliente de um gráfico de dispositivo que já esteja integrado ao <span class="keyword"> Audience Manager</span>. Entre em contato com seu gerente de conta para obter mais informações ou para começar. </p> <p>Consulte também &lt;a href="../../features/profile-merge-rules/external-graph-use-cases.md). </p> </td>
  </tr>
 </tbody>
</table>

>[!MORE_LIKE_THIS]
>
>* [Perguntas frequentes sobre as regras de mesclagem de perfil](../../faq/faq-profile-merge.md)

