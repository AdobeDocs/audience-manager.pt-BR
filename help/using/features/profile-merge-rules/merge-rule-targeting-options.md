---
description: As opções de Regras de mesclagem de perfil permitem expandir ou aumentar o foco do público-alvo em públicos-alvo específicos com base em necessidades ou objetivos de negócios. Esses casos de uso geral exploram como usar opções disponíveis e criar regras de mesclagem para direcionamento individual, doméstico e entre dispositivos. Atualmente, as Regras de mesclagem de perfil funcionam somente com destinos em tempo real.
seo-description: As opções de Regras de mesclagem de perfil permitem expandir ou aumentar o foco do público-alvo em públicos-alvo específicos com base em necessidades ou objetivos de negócios. Esses casos de uso geral exploram como usar opções disponíveis e criar regras de mesclagem para direcionamento individual, doméstico e entre dispositivos. Atualmente, as Regras de mesclagem de perfil funcionam somente com destinos em tempo real.
seo-title: Casos de uso geral para regras de mesclagem de perfil
solution: Audience Manager
title: Casos de uso geral para regras de mesclagem de perfil
uuid: c 9 eb 41 c 8-fe 19-45 f 8-9 ff 1-552 c 11 ef 08 da
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# General Use Cases for Profile Merge Rules {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] permitem expandir ou aumentar o foco do público-alvo em públicos-alvo específicos com base em necessidades ou objetivos de negócios. Esses casos de uso geral exploram como usar opções disponíveis e criar regras de mesclagem para direcionamento individual, doméstico e entre dispositivos. Currently, [!UICONTROL Profile Merge Rules] work with real-time destinations only.

![](assets/merge-rules-options.png)

>[!TIP]
>
>For definitions and descriptions of these [!UICONTROL Merge Rule] settings, see [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md).

## Focused targeting {#focused-targeting}

User authentication to a website should trigger a declared ID call to [!DNL Audience Manager]. After this event, [!DNL Audience Manager] writes trait data to (and reads from) an authenticated profile. The authenticated profile lets [!DNL Audience Manager]:

* Gravar características no perfil autenticado específico a um usuário específico.
* Identifique e diferencie entre vários usuários do dispositivo para segmentação.

### Alcançar usuários autenticados

As opções de perfil autenticado criam regras que permitem a definição de metas para usuários conectados a um site ou aplicativo com base em atributos offline. Por exemplo, uma empresa de serviços financeiros usaria essa opção para direcionar usuários autenticados com ofertas de atualização de cartão de crédito segmentadas ou ofertas especializadas de serviço com base em receita ou atividade offline. Outro exemplo seria uma definição de metas para fliers autenticados com endereços baseados em milênios acumulados.

To create a rule that reaches only authenticated users, select **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL No Device Profile]**. Essa opção avaliará um segmento usando apenas dados de perfil autenticados. Essa regra ignorará os dados no perfil de dispositivo anônimo.

To also include data in the anonymous device profile, use the **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL Current Device Profile]** rule.

### Alcançar usuários com base no estado de autenticação anterior

Essas opções atingem usuários específicos quando estão navegando, mas não conectados. Você pode fazer isso com as opções que dependem da definição de metas no nível do usuário. A definição de metas inferida ajuda você a alcançar pessoas que não são autenticadas explicitamente no site, mas podem estar navegando online. Funciona lendo (mas não gravando) dados do último perfil autenticado. And, to help keep the authenticated profile clean, [!DNL Audience Manager] writes new trait qualifications to the device profile instead of the authenticated profile. Por exemplo, digamos que você seja um comerciante que deseja testar ofertas diferentes com clientes existentes que não estão conectados ao seu site ou aplicativo. Como comerciante, você pode testar essas publicidades com clientes atuais e não autenticados para ver quais ofertas obtêm mais respostas.

Um exemplo de uma regra que chega aos usuários com base na autenticação anterior é:

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**

## Expanded targeting {#expanded-targeting}

Além de regras que ajudam a alcançar clientes específicos, os profissionais de marketing também precisam de regras que aumentem o tamanho dos conjuntos de dados disponíveis para definição de metas. [!UICONTROL Profile Merge Rules] permite fazer isso com a opção de perfil do dispositivo. As opções de dispositivo expandem o conjunto de dados qualificado para segmentação, pois ele é desenhado em características enquanto um usuário estava em um estado anônimo em um ou vários dispositivos. Isso pode ser útil quando você está tentando alcançar um usuário em todos os dispositivos usando um gráfico de dispositivo de pessoa ou todos os dispositivos em um lar usando um gráfico de dispositivo doméstico. Um caso de uso para esta opção pode incluir anúncios de ofertas de férias familiares. Nesse caso, você desejará atingir todos os dispositivos em um lar com a oferta se um usuário em qualquer dispositivo tiver mostrado interesse na oferta.

To create a rule that expands the targeting data set, select the **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Graph]** rule.

<!-- 

<p>Rules that use the device graph option extend your data set even further. With the device graph option, <span class="keyword"> Audience Manager</span> relies on the device profiles aggregated from the last 3 devices that a visitor used for authentication to your site. The device graph rules include: </p> 
<p> 
 <ul id="ul_3008B6AF16EC408F98EC4088111281FB"> 
  <li id="li_FA2087F1ED454CD0B9E09656B79ED23B"> <b><span class="uicontrol"> Current Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
  <li id="li_001A8DB517CB4EE394DBD530F2080FD5"> <b><span class="uicontrol"> Last Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
 </ul> </p> 
<p> 
 <note type="tip">
  Create a simple rule with 
  <b><span class="uicontrol"> No Authenticated Profile</span></b> + 
  <b><span class="uicontrol"> Current Device Profile</span></b> when you're still developing a strategy and are unsure about which options to choose or if your site doesn't use authentication. 
 </note> </p>

 -->

## Device Graph Options {#device-graph-options}

Choosing a [!UICONTROL device graph] option for a [!UICONTROL Profile Merge] rule depends on conditions unique to your digital properties and business goals. Essas diretrizes gerais podem ajudá-lo a entender quando usar um tipo de gráfico vs. Note, you must be a member of the [!DNL Adobe Experience Cloud Device Co-op] or have a contractual relationship with an external device graph to use these options. Consulte a tabela abaixo para obter orientação geral sobre quando escolher uma opção de gráfico de dispositivo. For specific use cases, see [Profile Link Device Graph Use Cases](../../features/profile-merge-rules/profile-link-use-case.md) and [External Device Graph Use Cases](../../features/profile-merge-rules/external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de gráfico de dispositivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Link de perfil</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> As regras de mesclagem</span> de perfil criadas com a <span class="wintitle"> opção Link</span> do perfil são ideais para: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Propriedades digitais com alto nível de autenticação do cliente. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Campanhas com foco e baixa alcance. The <span class="wintitle"> Profile Link</span> device graph is built on deterministic data only. Esse conjunto de perfis de dispositivos será sempre menor em relação ao conjunto de usuários e dispositivos não autenticados. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Casos de uso em que os clientes precisam estar em um estado autenticado para se qualificarem para segmentação. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opções de gráfico de dispositivo externo </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> As regras de mesclagem</span> de perfil criadas com o <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Device Co-op da Experience Cloud</a> ou qualquer gráfico de dispositivo externo integrado com <span class="keyword"> o Audience Manager</span> são ideais para: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Propriedades digitais com um nível baixo de autenticação do cliente. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Campanhas de marca ampla e de alta alcance. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Casos de uso em que os clientes não precisam estar em um estado autenticado para se qualificarem para segmentação. </li> 
     </ul> </p> <p> <p>Tip: The <span class="keyword"> Device Co-op</span> is your best option if you're a <span class="keyword"> Experience Cloud</span> customer with low authentication and no relationship with any device graph provider. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Casos de uso do gráfico de dispositivo de vinculação de perfil](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Casos de uso do gráfico do dispositivo externo](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [Perguntas frequentes sobre regras de mesclagem de perfil](../../faq/faq-profile-merge.md)

