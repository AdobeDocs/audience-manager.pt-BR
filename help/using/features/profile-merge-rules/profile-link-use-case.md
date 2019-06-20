---
description: Recomendações e casos de uso para redirecionamento de segmentos e qualificação personalizada de segmentos com o gráfico de dispositivo de Link de perfil.
seo-description: Recomendações e casos de uso para redirecionamento de segmentos e qualificação personalizada de segmentos com o gráfico de dispositivo de Link de perfil.
seo-title: Casos de uso do gráfico de dispositivo de vinculação de perfil
solution: Audience Manager
title: Casos de uso do gráfico de dispositivo de vinculação de perfil
uuid: bd 5567 fd-fcd 5-40 ba-b 6 f 1-035 d 2 ddbcd 3 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Link Device Graph Use Cases {#profile-link-device-graph-use-cases}

Recommendations and use cases for segment retargeting and personalized segment qualification with the [!UICONTROL Profile Link] device graph.

## Recomendações {#recommendations}

Consider the [!UICONTROL Profile Link] device graph for campaigns that:

* Tenha um alto nível de autenticação em suas propriedades digitais. Use an [external device graph option](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) if you have a small amount of authenticated users.
* Exigir a definição de metas precisa de públicos-alvo conhecidos. The [!UICONTROL Profile Link device graph] is built using first-party, authenticated data.
* Direcione públicos conhecidos em seus estados autenticados e não autenticados em tempo real.

![](assets/merge-rule-triangle2.png)

## Retargeting Use Case and Profile Merge Rule Configuration {#retargeting-use-cases}

Os públicos-alvo que foram autenticados anteriormente no site e/ou no aplicativo em vários dispositivos. Os segmentos podem ser compostos dos seguintes perfis:

* Último perfil de dispositivo autenticado conhecido.
* Atividade anônima em cada perfil de dispositivo.

>[!NOTE]
>
>As informações de características de um tipo de perfil podem ser usadas para criar o segmento.

### Exemplo de redefinição de metas

Vejamos como isso funciona com uma amostra de empresa de cartão de crédito. Este exemplo usa informações de características coletadas das atividades anônimas, vistas somente em 3 perfis de dispositivo.

<table id="table_8C5ABA47A0634EBA9B1AA1B5C2AABF07"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condições</b> </p> </td> 
   <td colname="col2"> <p>Esse caso de uso pressupõe estas condições: </p> <p> 
     <ul id="ul_72373D0F304044AE84E4CC055E3E8154"> 
      <li id="li_375DA786ED4D4F18A74C8FE42ABF8448">Um usuário tem 3 dispositivos e foi a última pessoa a autenticar no site/aplicativo da empresa de cartão de crédito em todos os dispositivos 3. </li> 
      <li id="li_77FDBFAED21B4DE19AB2B6C112E0C64B">No primeiro dispositivo, um usuário em um estado não autenticado exibe uma oferta de cartão de crédito premium. </li> 
      <li id="li_D3BE1B30BCCA49EA931AA9D97DD5F86D">No segundo dispositivo, um usuário em um estado não autenticado visualiza a página de benefícios do cartão de crédito premium. </li> 
      <li id="li_39D894624FC44806B6DB2C77F459B39E">No terceiro dispositivo, um usuário em um estado não autenticado visualiza as taxas e taxas de cartão de crédito premium. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_1B6174F5C3AF4C32831D4217C5113789"> 
      <li id="li_98FE54696B604C3C8D93CC1C1FBB48D9">Une a atividade anônima e não autenticada coletada de todos os 3 dispositivos usando o último perfil autenticado no dispositivo atual. </li> 
      <li id="li_A73C7DCE36BA42B6BAD26D8A075416C1">Avalia o usuário anônimo para qualificação de segmento com base em: 
       <ul id="ul_EF66EAFD12CA44F5ACCB66319606D937"> 
        <li id="li_541762056ECF4BC1ABF1F5116B5FED6C">Uma combinação de atividades anônimas em todos os dois dispositivos. </li> 
        <li id="li_C386CB62E5234E10AFEDE900ADC0E261">O último perfil autenticado no dispositivo atual. </li> 
       </ul> </li> 
      <li id="li_5C9BDC8FF886494589F005C9658A923C">Envia o segmento para qualquer destino em tempo real para redefinição de metas em todos os dois dispositivos. </li>
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemplo de regra de mesclagem de perfil de redefinição de perfil

To set up retargeting with [!UICONTROL Profile Link], your [!UICONTROL Authenticated Options] and [!UICONTROL Device Options] should look like the rule configuration shown below. [!UICONTROL Authenticated Profile] As opções serão diferentes deste exemplo, pois essas configurações usam os nomes das fontes de dados entre dispositivos.

![Configuração da regra de mesclagem de perfil](assets/merge-rules-internal3.png)

## Personalization Use Case and Profile Merge Rule Configuration {#personalization-use-case}

Personalize a experiência de públicos-alvo autenticados no site e/ou no aplicativo com base na atividade em vários dispositivos. Os segmentos podem ser compostos dos seguintes perfis:

* Perfil de dispositivo autenticado atualmente.
* Perfis de dispositivo anônimos.

>[!NOTE]
>
>Um usuário deve estar em um estado autenticado para se qualificar para um segmento.

### Exemplo de personalização

Vejamos como isso funciona com uma amostra de empresa de cartão de crédito.

<table id="table_D2F4D5D27EB54224BB2CC1D843DDEDA3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condições</b> </p> </td> 
   <td colname="col2"> <p>Nosso caso de uso pressupõe estas condições: </p> <p> 
     <ul id="ul_C4D2108E7B1C4D3C89411A9CCCDA6DAC"> 
      <li id="li_2F10EB17466B4B91A94DF707C3CB6BE5">Um usuário tem 3 dispositivos e foi a última pessoa a autenticar no site/aplicativo da empresa de cartão de crédito em todos os dispositivos 3. </li> 
      <li id="li_1559C4DA51254BCF95291133F32A4057">No primeiro dispositivo, um usuário em um estado não autenticado exibe uma oferta de cartão de crédito premium. </li> 
      <li id="li_734465E5619C474291C42921160CEC6B">No segundo dispositivo, um usuário em um estado não autenticado visualiza a página de benefícios do cartão de crédito premium. </li> 
      <li id="li_B96ABC0205384B59A1901708505B8BF8">No terceiro dispositivo, um usuário em um estado não autenticado visualiza as taxas e taxas de cartão de crédito premium. </li> 
      <li id="li_1A7BDBD546BD4B8EACF4292D885127F2">Em qualquer um desses dispositivos, o cliente autentica (fazendo logon) para verificar o equilíbrio. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_37DBF5FEABC5463D85C74AD9150EA177"> 
      <li id="li_B60FFA5CF3F64FB69997AA05595900D7">Une a atividade anônima e não autenticada coletada de todos os 3 dispositivos usando o perfil autenticado atual. O perfil autenticado fornece um identificador comum em cada dispositivo. </li> 
      <li id="li_AB9FD87DD804474BA33805C364B7B92D">Avalia o usuário autenticado para qualificação de segmento com base em: 
       <ul id="ul_EAF99E72159D4E329052B71344D9C69B"> 
        <li id="li_0B5E52BA6D8B493980291EA7B0AE235A">Uma combinação de atividades anônimas em todos os dois dispositivos. </li> 
        <li id="li_07588DEFBEF64F97850CB12CD62D0213">Seu perfil autenticado atual. </li> 
       </ul> </li> 
      <li id="li_E7CFCEAD7610496189F4486000D7860A">Envia o segmento para qualquer destino em tempo real para criar uma experiência de navegação personalizada para o usuário enquanto ela é autenticada no dispositivo atual. <p>Observação: Isso classifica todos os 3 dispositivos para o segmento, independentemente do estado de autenticação. Esse resultado pode causar preocupações de privacidade se esses forem dispositivos compartilhados. </p> </li>
     </ul> </p> </td>
  </tr>
 </tbody> 
</table>

### Exemplo de regra de mesclagem de perfil de personalização

To set up personalization with [!UICONTROL Profile Link], your [!UICONTROL Authenticated Options] and [!UICONTROL Device Options] should look like the rule configuration shown below. [!UICONTROL Authenticated Profile] As opções serão diferentes deste exemplo, pois essas configurações usam os nomes das fontes de dados entre dispositivos.

![](assets/merge-rules-internal4.png)

For more information about how these device graph processes work, download our PDF, [Audience Manager and External Device Graphs](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_ LIKE_ THIS]
>
>* [Casos de uso do gráfico do dispositivo externo](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [Casos de uso geral para regras de mesclagem de perfil](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [Perguntas frequentes sobre regras de mesclagem de perfil](../../faq/faq-profile-merge.md)

