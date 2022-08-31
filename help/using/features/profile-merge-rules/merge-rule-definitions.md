---
description: As opções de regra de mesclagem permitem controlar o tipo de dados que o Audience Manager de dados usa para segmentação. Uma regra de mesclagem pode incluir perfis de dispositivo mapeados pelo gráfico de dispositivos Link de perfil e/ou outros provedores de gráficos de dispositivos de terceiros que estejam integrados ao Audience Manager. Você pode criar no máximo 4 Regras de mesclagem de perfil.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: Definição das opções da regra de mesclagem de perfis
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 2%

---

# [!UICONTROL Profile Merge Rules] Opções definidas {#profile-merge-rule-options-defined}

O [!UICONTROL profile merge rule] permitem controlar o tipo de dados [!DNL Audience Manager] O usa o para segmentação. A [!UICONTROL profile merge rule] pode incluir perfis de dispositivo mapeados pelo [!UICONTROL Profile Link] gráfico de dispositivos e/ou outros provedores de gráficos de dispositivos de terceiros que estejam integrados com [!DNL Audience Manager]. Você pode criar um máximo de 4 [!UICONTROL Profile Merge Rules]. O quarto [!UICONTROL Profile Merge Rule] está disponível exclusivamente para clientes que compraram a variável [!UICONTROL People-Based Destinations] complemento.

Você cria um [!UICONTROL Profile Merge Rule] fazendo uma seleção das opções descritas abaixo, em [!UICONTROL Profile Merge Rule Setup].

![configuração de regras de mesclagem de perfis](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Visão geral das opções {#overview}

[!UICONTROL Profile Merge Rules] permitir diversas combinações de regras, cada uma delas orientada para casos de uso específicos. Consulte a tabela abaixo para obter detalhes sobre quando usar cada combinação de regras.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilidade | Tipo de avaliação | [!UICONTROL Audience Lab] Suporte | Casos de uso |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Todos os clientes | Tempo real e lote | Sim | [Direcionamento de dispositivo](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | Todos os clientes | Tempo real e lote | Não | [Direcionamento de dispositivo expandido](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Todos os clientes | Somente em tempo real | Não | [Direcionamento de dispositivo compartilhado](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Todos os clientes | Tempo real e lote | Sim | [Direcionamento online/offline](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Todos os clientes | Tempo real e lote | Sim | [Direcionamento entre dispositivos](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | Todos os clientes | Tempo real e lote | Não | [Direcionamento entre dispositivos avançado](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | N/A | Exclusivo para [Destinos com base em pessoas](../destinations/people-based-destinations-overview.md) clientes | Somente em lote | Não | [Direcionamento para destinos com base em pessoas](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Avaliação {#segment-evaluation}

Dependendo do [!UICONTROL Profile Merge Rules] configuração, [!DNL Audience Manager] pode executar o [!UICONTROL segment] avaliação em tempo real, em lote ou ambos.

* Tempo real [!UICONTROL segment] a avaliação exige que [!DNL DCS] para ver os visitantes acessarem suas propriedades digitais em tempo real, para se qualificarem para a variável [!UICONTROL segment].
* Em lote [!UICONTROL segment] a avaliação é realizada em relação a [!UICONTROL traits].
* [!UICONTROL Profile Merge Rules] que suportam em tempo real e em lote [!UICONTROL segment] avaliação combinar a atividade do visitante em tempo real com as qualificações anteriores [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] Latência dos relatórios {#reporting-latency}

Tempo real [!UICONTROL segment] a avaliação reflete imediatamente [!UICONTROL Profile Merge Rules] relatórios.

Em lote [!UICONTROL segment] a avaliação pode levar até 24 horas para ser refletida na variável [Relatórios de Regras de mesclagem de perfis](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

O [!UICONTROL Cross-Device Options] permite selecionar usuários autenticados e não autenticados e aproveitar seu perfil entre dispositivos para segmentação. Essas opções ajudam a identificar e alcançar usuários específicos em um dispositivo compartilhado. Para obter mais informações sobre usuários anônimos e autenticados, consulte [Estados de autenticação de visitante no Audience Manager](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> não usar dados coletados de usuários autenticados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfis Autenticados Atuais</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> para ler e gravar dados no perfil autenticado se um visitante tiver feito logon no site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Últimos perfis autenticados</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> para ler dados do perfil autenticado do usuário que fez logon pela última vez no dispositivo. </p> <p>Quando selecionado, <span class="keyword"> Audience Manager</span> não gravará novos dados de características no perfil autenticado se o usuário for anônimo. Após a autenticação, os novos dados de característica são gravados no perfil autenticado do usuário. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Todos os perfis entre dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Faz com que o Audience Manager leia os dados de todos os perfis entre dispositivos, independentemente do estado de autenticação. Essa opção só está disponível para clientes do Audience Manager que compraram o complemento Destinos com base em pessoas .</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

O [!UICONTROL Cross-Device Profile Options] lista seu [!UICONTROL cross-device data sources]. Essas opções usam os nomes fornecidos quando você criou uma [!UICONTROL cross-device] [!UICONTROL data source] (consulte [Criar uma fonte de dados entre dispositivos](merge-rules-start.md#create-data-source)). É possível selecionar até 3 [!UICONTROL cross-device data sources] para usar com cada regra de perfil. O [!UICONTROL Authenticated Profile Options] estão disponíveis ao escolher **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

O [!UICONTROL Device Options] permite selecionar o tipo de *`device profile`* usada por um [!UICONTROL Profile Merge Rule]. Um perfil de dispositivo é criado a partir de [!UICONTROL traits] coletado da atividade de navegação anônima. No mínimo, uma [!UICONTROL profile merge rule] inclui um [!UICONTROL authenticated option] e [!UICONTROL device option].

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
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> não para usar as características contidas no perfil anônimo para segmentação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfil do dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> para usar o perfil de dispositivo anônimo para segmentação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de dispositivos de link de perfil</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> para ler os perfis do dispositivo atual e até 100 outros dispositivos dos quais o usuário foi autenticado. Esse gráfico de dispositivos é criado com base em seus próprios dados primários em <span class="keyword"> Audience Manager</span>. É ideal para clientes que têm um alto nível de autenticação em suas propriedades digitais. O <span class="wintitle"> Link de perfil</span> O gráfico de dispositivos é atualizado em tempo real. Essa opção está disponível ao selecionar <b><span class="uicontrol"> Perfil atual autenticado</span></b> ou <b><span class="uicontrol"> Último perfil autenticado</span></b>. Ao usar essa opção, você só pode escolher um único perfil autenticado (<span class="keyword"> Audience Manager</span> automaticamente cinza os outros). Consulte também, <a href="profile-link-use-case.md"> Casos de uso do gráfico do dispositivo de link de perfil</a>. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>Opções de gráfico de dispositivo de terceiros</b> (Pessoa e residência) </p> </td>
   <td colname="col2"> <p>Essas opções permitem criar regras de mesclagem com base na tecnologia de gráficos de dispositivos fornecida por um fornecedor terceirizado. Um gráfico de dispositivos de terceiros fornece: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Dados probabilísticos e/ou determinísticos. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Dados ao nível da pessoa ou do agregado familiar. </li> 
     </ul> </p> <p>Para usar essas opções, você deve ser um cliente de um gráfico de dispositivos que já esteja integrado ao <span class="keyword"> Audience Manager</span>. Entre em contato com o gerente da conta para obter mais informações ou começar. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Segmentos de público-alvo que foram criados automaticamente a partir de outros [!DNL Experience Cloud] , com base nas regras de mesclagem definidas fora de [!DNL Audience Manager]são marcadas como usando um [!UICONTROL External Merge Policy]. Por exemplo, consulte [Compartilhamento de público entre o Audience Manager e a Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Perguntas frequentes sobre as regras de mesclagem de perfis](../../faq/faq-profile-merge.md)

