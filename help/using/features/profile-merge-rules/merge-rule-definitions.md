---
description: As opções de regra de mesclagem permitem controlar o tipo de dados que o Audience Manager usa para segmentação. Uma regra de mesclagem pode incluir perfis de dispositivo mapeados pelo gráfico de dispositivos Link de perfil e/ou outros provedores de gráficos de dispositivo de terceiros que estejam integrados ao Audience Manager. É possível criar no máximo 4 Regras de mesclagem de perfis.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: Definição das Opções de Regra de Mesclagem de Perfis
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 1%

---

# [!UICONTROL Profile Merge Rules] Opções definidas {#profile-merge-rule-options-defined}

As opções [!UICONTROL profile merge rule] permitem controlar o tipo de dados que [!DNL Audience Manager] usa para segmentação. Um [!UICONTROL profile merge rule] pode incluir perfis de dispositivo mapeados pelo gráfico de dispositivos [!UICONTROL Profile Link] e/ou outros provedores de gráficos de dispositivo de terceiros que estejam integrados ao [!DNL Audience Manager]. Você pode criar um máximo de 4 [!UICONTROL Profile Merge Rules]. O quarto [!UICONTROL Profile Merge Rule] está disponível exclusivamente para clientes que compraram o complemento [!UICONTROL People-Based Destinations].

Você compila um [!UICONTROL Profile Merge Rule] fazendo uma seleção das opções descritas abaixo, em [!UICONTROL Profile Merge Rule Setup].

![configuração-regra-de-mesclagem-de-perfis](assets/profile-merge-rule-setup.png)

## Visão geral das opções de [!UICONTROL Profile Merge Rule] {#overview}

O [!UICONTROL Profile Merge Rules] permite várias combinações de regras, cada uma direcionada a casos de uso específicos. Consulte a tabela abaixo para obter detalhes sobre quando usar cada combinação de regras.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilidade | Tipo de avaliação | Suporte do [!UICONTROL Audience Lab] | Casos de uso |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Todos os clientes | Tempo real e lote | Sim | [Direcionamento de dispositivo](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | Todos os clientes | Tempo real e lote | Não | [Direcionamento Expandido de Dispositivo](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Todos os clientes | Somente em tempo real | Não | [Direcionamento de dispositivo compartilhado](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Todos os clientes | Tempo real e lote | Sim | [Direcionamento Online/Offline](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Todos os clientes | Tempo real e lote | Sim | [Direcionamento entre dispositivos](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | Todos os clientes | Tempo real e lote | Não | [Direcionamento avançado entre dispositivos](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | N/A | Exclusivo para [Destinos com base em pessoas](../destinations/people-based-destinations-overview.md) clientes | Somente lote | Não | [Direcionamento para destinos com base em pessoas](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Avaliação {#segment-evaluation}

Dependendo da configuração do [!UICONTROL Profile Merge Rules], o [!DNL Audience Manager] pode executar a avaliação do [!UICONTROL segment] em tempo real, em lote ou em ambos.

* A avaliação do [!UICONTROL segment] em tempo real exige que o [!DNL DCS] veja os visitantes acessarem suas propriedades digitais em tempo real, para se qualificar para o [!UICONTROL segment].
* A avaliação do lote [!UICONTROL segment] é executada em relação ao [!UICONTROL traits] qualificado anteriormente.
* [!UICONTROL Profile Merge Rules] que oferecem suporte à avaliação em tempo real e em lote [!UICONTROL segment] combinam a atividade de visitante em tempo real com a [!UICONTROL traits] qualificada anteriormente.

## [!UICONTROL Profile Merge Rules] Relatando latência {#reporting-latency}

A avaliação de [!UICONTROL segment] em tempo real reflete imediatamente nos relatórios [!UICONTROL Profile Merge Rules].

A avaliação do lote [!UICONTROL segment] pode levar até 24 horas para ser refletida nos [relatórios de Regras de mesclagem de perfil](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

O [!UICONTROL Cross-Device Options] permite selecionar usuários autenticados e não autenticados e aproveitar seu perfil entre dispositivos para segmentação. Essas opções ajudam você a identificar e alcançar usuários específicos em um dispositivo compartilhado. Para obter mais informações sobre usuários anônimos e autenticados, consulte [Estados de autenticação de visitante no Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção entre dispositivos </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Nenhum Perfil Entre Dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Instrui <span class="keyword"> Audience Manager</span> a não usar os dados coletados de usuários autenticados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfis Autenticados Atuais</span></b> </p> </td> 
   <td colname="col2"> <p>Instrui o <span class="keyword"> Audience Manager</span> a ler e gravar dados no perfil autenticado se um visitante estiver conectado ao site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Últimos perfis autenticados</span></b> </p> </td> 
   <td colname="col2"> <p>Instrui <span class="keyword"> Audience Manager</span> a ler dados do perfil autenticado do usuário que fez logon pela última vez no dispositivo. </p> <p>Quando selecionado, o Audience Manager <span class="keyword"> </span> não gravará novos dados de características no perfil autenticado se o usuário for anônimo. Após a autenticação, os novos dados de características são gravados no perfil autenticado do usuário. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Todos os perfis entre dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Instrui o Audience Manager a ler dados de todos os perfis entre dispositivos, independentemente do estado de autenticação. Essa opção só está disponível para clientes do Audience Manager que compraram o complemento Destinos com base em pessoas.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

O [!UICONTROL Cross-Device Profile Options] lista seu [!UICONTROL cross-device data sources]. Essas opções usam os nomes que você forneceu quando criou um [!UICONTROL cross-device] [!UICONTROL data source] (consulte [Criar uma Source de Dados entre Dispositivos](merge-rules-start.md#create-data-source)). Você pode selecionar até 3 [!UICONTROL cross-device data sources] para usar com cada regra de perfil. Os [!UICONTROL Authenticated Profile Options] estão disponíveis quando você escolhe **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

O [!UICONTROL Device Options] permite selecionar o tipo de *`device profile`* usado por um [!UICONTROL Profile Merge Rule]. Um perfil de dispositivo foi criado a partir de [!UICONTROL traits] coletado da atividade de navegação anônima. No mínimo, um [!UICONTROL profile merge rule] inclui um [!UICONTROL authenticated option] e um [!UICONTROL device option].

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção do dispositivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Nenhum Perfil de Dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Instrui <span class="keyword"> Audience Manager</span> a não usar as características contidas no perfil anônimo para segmentação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfil de dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Instrui <span class="keyword"> Audience Manager</span> a usar o perfil de dispositivo anônimo para segmentação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico do dispositivo de vinculação de perfis</span></b> </p> </td> 
   <td colname="col2"> <p>Instrui o Audience Manager <span class="keyword"> </span> a ler os perfis do dispositivo atual e de até 100 outros dispositivos nos quais o usuário autenticou. Este gráfico de dispositivos foi criado com base nos seus próprios dados primários em <span class="keyword"> Audience Manager</span>. É ideal para clientes que têm um alto nível de autenticação em suas propriedades digitais. O gráfico de dispositivos <span class="wintitle"> Link de Perfil</span> é atualizado em tempo real. Esta opção está disponível quando você seleciona <b><span class="uicontrol"> Perfil Autenticado Atual</span></b> ou <b><span class="uicontrol"> Último Perfil Autenticado</span></b>. Ao usar essa opção, você só pode escolher um único perfil autenticado (<span class="keyword"> Audience Manager</span> acinzenta automaticamente os outros). Consulte também <a href="profile-link-use-case.md"> Casos de uso do gráfico de dispositivo de link de perfil</a>. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>Opções de Gráfico de Dispositivos de Terceiros</b> (Pessoa e Residência) </p> </td>
   <td colname="col2"> <p>Essas opções permitem criar regras de mesclagem com base na tecnologia de gráficos de dispositivos fornecida por um fornecedor terceirizado. Um gráfico de dispositivos de terceiros fornece: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Dados probabilísticos e/ou determinísticos. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Dados a nível da pessoa ou do agregado familiar. </li> 
     </ul> </p> <p>Para usar essas opções, você deve ser um cliente de um gráfico de dispositivos que já esteja integrado ao Audience Manager <span class="keyword"> </span>. Entre em contato com o gerente da conta para obter mais informações ou para começar. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Os segmentos de público-alvo que foram criados automaticamente a partir de outras soluções do [!DNL Experience Cloud], com base nas regras de mesclagem definidas fora do [!DNL Audience Manager], são marcados como usando um [!UICONTROL External Merge Policy]. Por exemplo, consulte [Compartilhamento de público-alvo entre Audience Manager e Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre Regras de Mesclagem de Perfis](../../faq/faq-profile-merge.md)
