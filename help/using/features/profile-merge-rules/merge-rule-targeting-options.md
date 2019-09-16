---
description: As opções de Regras de mesclagem de perfil permitem que você expanda ou restrinja o foco do público-alvo em públicos-alvo específicos com base nas necessidades ou metas dos negócios. Esses casos de uso geral exploram como usar as opções disponíveis e criar regras de mesclagem para direcionamento individual, doméstico e entre dispositivos. Atualmente, as Regras de mesclagem de perfil funcionam somente com destinos em tempo real.
seo-description: As opções de Regras de mesclagem de perfil permitem que você expanda ou restrinja o foco do público-alvo em públicos-alvo específicos com base nas necessidades ou metas dos negócios. Esses casos de uso geral exploram como usar as opções disponíveis e criar regras de mesclagem para direcionamento individual, doméstico e entre dispositivos. Atualmente, as Regras de mesclagem de perfil funcionam somente com destinos em tempo real.
seo-title: Casos de uso gerais para regras de mesclagem de perfil
solution: Audience Manager
title: Casos de uso gerais para regras de mesclagem de perfil
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Casos de uso gerais para regras de mesclagem de perfil {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] permitem que você expanda ou restrinja o foco do público-alvo em públicos-alvo específicos com base em necessidades ou metas comerciais. Esses casos de uso geral exploram como usar as opções disponíveis e criar regras de mesclagem para direcionamento individual, doméstico e entre dispositivos. Atualmente, [!UICONTROL Profile Merge Rules] trabalha somente com destinos em tempo real.

![](assets/merge-rules-options.png)

>[!TIP]
>
>Para obter definições e descrições dessas [!UICONTROL Merge Rule] configurações, consulte Definição [das opções de regra de mesclagem de](../../features/profile-merge-rules/merge-rule-definitions.md)perfis.

## Direcionamento focado {#focused-targeting}

A autenticação do usuário para um site deve acionar uma chamada de ID declarada para [!DNL Audience Manager]. Depois desse evento, [!DNL Audience Manager] grava dados de características em (e lê de) um perfil autenticado. O perfil autenticado permite [!DNL Audience Manager]:

* Grave características no perfil autenticado específico de um usuário específico.
* Identifique e diferencie usuários de vários dispositivos para segmentação.

### Alcance usuários autenticados

As opções de perfil autenticadas criam regras que permitem direcionar os usuários conectados a um site ou aplicativo com base em atributos offline. Por exemplo, uma empresa de serviços financeiros usaria essa opção para direcionar usuários autenticados com ofertas direcionadas de atualização de cartão de crédito ou ofertas de serviço especializadas com base em renda ou atividade offline. Outro exemplo seria uma companhia aérea direcionada a passageiros frequentes autenticados com transações baseadas em quilometragem acumulada.

Para criar uma regra que alcance somente usuários autenticados, selecione **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL No Device Profile]**. Essa opção avaliará um segmento usando apenas dados de perfil autenticados. Essa regra ignorará os dados no perfil de dispositivo anônimo.

Para incluir dados no perfil de dispositivo anônimo, use a regra **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL Current Device Profile]** .

### Alcance usuários com base no estado de autenticação anterior

Essas opções chegam a usuários específicos quando eles navegam, mas não estão conectados. Você pode fazer isso com opções que dependem da definição de metas inferida no nível do usuário. A definição de metas reduzida ajuda a alcançar pessoas que não são autenticadas explicitamente em seu site, mas que podem estar navegando online. Funciona lendo (mas não gravando) dados do último perfil autenticado. E, para ajudar a manter o perfil autenticado limpo, [!DNL Audience Manager] grava novas qualificações de característica no perfil do dispositivo em vez do perfil autenticado. Por exemplo, considere que você é um comerciante que deseja testar ofertas diferentes com clientes existentes que não estão conectados ao seu site ou aplicativo. Como comerciante, você pode testar esses anúncios com clientes atuais e não autenticados para ver quais ofertas obtêm mais resposta.

Um exemplo de uma regra que chega aos usuários com base na autenticação anterior é:

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**

## Direcionamento expandido {#expanded-targeting}

Junto com regras que ajudam a atingir clientes específicos, os comerciantes também precisam de regras que aumentem o tamanho dos conjuntos de dados disponíveis para definição de metas. [!UICONTROL Profile Merge Rules] permite fazer isso com a opção de perfil do dispositivo. As opções do dispositivo expandem o conjunto de dados elegível para segmentação, pois ele se baseia em características realizadas enquanto um usuário estava em um estado anônimo em um ou vários dispositivos. Isso pode ser útil quando você está tentando alcançar um usuário através de todos os seus dispositivos usando um gráfico de dispositivo pessoal ou todos os dispositivos em uma casa usando um gráfico de dispositivo doméstico. Um caso de uso para essa opção pode incluir a publicidade de uma oferta de férias da família. Nesse caso, você desejará alcançar todos os dispositivos em uma residência com a oferta se um usuário em qualquer dispositivo tiver mostrado interesse na oferta.

Para criar uma regra que expanda o conjunto de dados de definição de metas, selecione a regra **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Graph]** .

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

## Opções do Gráfico de dispositivos {#device-graph-options}

A escolha de uma [!UICONTROL device graph] opção para uma [!UICONTROL Profile Merge] regra depende de condições exclusivas de suas propriedades digitais e metas comerciais. Essas orientações gerais podem ajudá-lo a entender quando usar um tipo de gráfico em vez de outro. Observe que você deve ser um membro do [!DNL Adobe Experience Cloud Device Co-op] ou ter uma relação contratual com um gráfico de dispositivos externo para usar essas opções. Consulte a tabela abaixo para obter orientações gerais sobre quando escolher uma opção de gráfico de dispositivo. Para casos de uso específicos, consulte Casos [de uso do gráfico de dispositivo de link de](../../features/profile-merge-rules/profile-link-use-case.md) perfil e Casos [de uso do gráfico de dispositivo](../../features/profile-merge-rules/external-graph-use-cases.md)externo.

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
   <td colname="col2"> <p><span class="wintitle"> As regras de mesclagem</span> de perfil criadas com a opção Link <span class="wintitle"></span> de perfil são ideais para: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Propriedades digitais com um alto nível de autenticação de cliente. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Campanhas focadas e de baixo alcance. O gráfico de dispositivo de Link <span class="wintitle"></span> de perfil é baseado apenas em dados determinísticos. Esse pool de perfis de dispositivos sempre será menor em relação ao pool de usuários e dispositivos não autenticados. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Casos de uso em que os clientes precisam estar em um estado autenticado para se qualificarem para a segmentação. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opções de gráfico de dispositivo externo </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> As regras de mesclagem</span> de perfil criadas com o Device Co-op <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> da</a> Experience Cloud ou qualquer gráfico de dispositivo externo integrado ao <span class="keyword"> Audience Manager</span> são ideais para: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Propriedades digitais com um nível baixo de autenticação de cliente. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Amplas campanhas de marcas de alto alcance. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Casos de uso em que os clientes não precisam estar em um estado autenticado para se qualificarem para segmentação. </li> 
     </ul> </p> <p> <p>Dica: O <span class="keyword"> Device Co-op</span> é a melhor opção se você for um cliente da <span class="keyword"> Experience Cloud</span> com baixa autenticação e sem relacionamento com nenhum provedor de gráficos de dispositivos. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Casos de uso do gráfico de dispositivo de link de perfil](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Casos de uso do gráfico do dispositivo externo](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [Perguntas frequentes sobre as regras de mesclagem de perfil](../../faq/faq-profile-merge.md)

