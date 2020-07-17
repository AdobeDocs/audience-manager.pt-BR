---
description: As opções de Regras de mesclagem de Perfis permitem que você expanda ou restrinja o foco da audiência em audiências específicas com base nas necessidades ou metas dos negócios. Esses casos de uso geral exploram como usar as opções disponíveis e criar regras de mesclagem para direcionamento individual, doméstico e entre dispositivos.
seo-description: As opções de Regras de mesclagem de Perfis permitem que você expanda ou restrinja o foco da audiência em audiências específicas com base nas necessidades ou metas dos negócios. Esses casos de uso geral exploram como usar as opções disponíveis e criar regras de mesclagem para direcionamento individual, doméstico e entre dispositivos.
seo-title: Casos de uso gerais para regras de mesclagem de perfis
solution: Audience Manager
title: Casos de uso gerais para regras de mesclagem de perfis
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '997'
ht-degree: 4%

---


# Casos de uso gerais para regras de mesclagem de perfis {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] permitem que você expanda ou restrinja o foco da audiência em audiências específicas com base em necessidades ou metas comerciais. Esses casos de uso geral exploram como usar as opções disponíveis e criar regras de mesclagem para direcionamento individual, doméstico e entre dispositivos. [!UICONTROL Profile Merge Rules] trabalhar com destinos em tempo real e em lote.

>[!TIP]
>
>Para obter definições e descrições dessas [!UICONTROL Merge Rule] configurações, consulte Definição [das opções de regra de mesclagem de](merge-rule-definitions.md)Perfis.

## Direcionamento de dispositivo {#device-personalization}

Esse cenário se aplica aos profissionais de marketing que desejam avaliar um único perfil de dispositivo para um segmento de audiência definido no Audience Manager, a fim de fornecer uma experiência consistente ao dispositivo usando plataformas de definição de metas que suportam IDs de dispositivo (DSPs, plataformas de personalização no site e outras plataformas de definição de metas baseadas em dispositivo), sem levar em conta a autenticação do usuário.

Para criar uma regra que público alvo somente perfis de dispositivo, selecione **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![somente dispositivo](assets/device-only.png)

Digamos que John é dono de três smartphones. Dois deles são o iPhone 7s no Data Plan A, e um deles é o Samsung on Data Plan B. Não considerando seu estado autenticado em qualquer um dos três dispositivos, a operadora de celular do John quer oferta uma atualização do plano de dados, mas somente para dispositivos iPhone 7 executados no plano de dados A.

Ao usar a regra **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** , [!DNL Device 1] e [!DNL Device 3] ambos se qualificam para o segmento, enquanto o Dispositivo 2 é ignorado.

![somente dispositivo](assets/device-management.png)

## Direcionamento de dispositivo compartilhado {#target-shared-devices}

Digamos que John e sua esposa, Jane, usem o mesmo laptop para visitar uma loja online e pedir vários itens.

John usa sua própria conta para reservar bilhetes de viagem e negócios especiais, enquanto Jane usa sua própria conta para comprar música e filmes.

A equipe de marketing da loja pode usar a regra **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** para público alvo de John e Jane com negócios específicos, com base apenas em sua atividade autenticada.

![current-no-device](assets/current-no-device.png)

Ao usar essa regra, o Audience Manager ignora completamente o perfil do dispositivo, qualificando a ID do CRM do John para o segmento e não qualificando a ID do CRM da Jane.

![segmentação de dispositivo compartilhado](assets/shared-device-targeting.png)

## Direcionamento online/offline {#device-household-targeting}

Este caso de utilização abrange a gestão da identidade dos agregados familiares. Uma empresa pode unir um único perfil de dispositivo ao último perfil autenticado nesse dispositivo, usando a regra **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]** .

![último perfil de dispositivo](assets/last-device-profile.png)

Vamos considerar um segmento feito de famílias com rendimentos maiores que US$ 100.000/ano, contendo pelo menos um dispositivo [!DNL iPhone 7] ativado [!DNL Data Plan B]. Temos dois perfis domésticos (perfis entre dispositivos), cada um conectado a dois perfis diferentes de dispositivos. As características necessárias para se qualificar para o segmento são distribuídas entre os perfis do dispositivo e entre dispositivos.

Audience Manager une cada dispositivo + par de perfis entre dispositivos para ver se o conjunto unido de características se qualifica para o segmento. Como o Audience Manager avalia cada perfil incluído na mesclagem, tanto um perfil de dispositivo quanto um perfil doméstico podem ser segmentados.

A ligação entre o dispositivo e o perfil doméstico permite que o Audience Manager se qualifique [!DNL Household 2] para o segmento, mas não [!DNL Household 1]. De [!DNL Household 2], só é qualificado para [!DNL Device 3] o segmento. Isso [!UICONTROL Profile Merge Rule] permitiu que o profissional de marketing enviasse uma mensagem de marketing consistente para um dispositivo individual ([!DNL Device 3]) e para uma família mais ampla ([!DNL Household 2]).

![gestão familiar](assets/household-management.png)

## Definição de metas para destinos baseados em pessoas {#all-cross-device}

>[!IMPORTANT]
>
>Este artigo contém a documentação do produto destinada a orientá-lo durante a configuração e o uso deste recurso. Nada aqui contido é aconselhamento jurídico. Consulte o seu próprio advogado para obter orientação jurídica.

Esse cenário de definição de metas está disponível somente para clientes que compraram o [!DNL People-Based Destinations] complemento. Essa regra permite que os comerciantes cheguem aos clientes com base em seus próprios dados autenticados.

Digamos que um varejista online queira alcançar os clientes existentes através de plataformas sociais e mostrar-lhes ofertas personalizadas com base em seus pedidos anteriores. Com [!UICONTROL People-Based Destinations], eles podem assimilar endereços de email com hash [!DNL CRM] para Audience Manager, criar segmentos a partir dos dados offline e enviar esses segmentos para as plataformas sociais nas quais desejam anunciar, usando esse identificador com hash, otimizando seus gastos com publicidade.

Para saber mais sobre essa opção, consulte Destinos [baseados em](../destinations/people-based-destinations-overview.md)pessoas.

![dispositivo completo](assets/all-cross-device.png)

## Opções do Gráfico de dispositivos {#device-graph-options}

A escolha de uma [!UICONTROL device graph] opção para uma [!UICONTROL Profile Merge] regra depende de condições exclusivas de suas propriedades digitais e metas comerciais. Essas orientações gerais podem ajudá-lo a entender quando usar um tipo de gráfico em vez de outro. Observe que você deve ser um membro do Device Co-op [da](https://docs.adobe.com/content/help/pt-BR/device-co-op/using/home.html) Adobe Experience Cloud ou ter uma relação contratual com um gráfico de dispositivo externo para usar essas opções. Consulte a tabela abaixo para obter orientações gerais sobre quando escolher uma opção de gráfico de dispositivo. Para casos de uso específicos, consulte Casos [de uso do gráfico de dispositivo de link de](profile-link-use-case.md) Perfil e Casos [de uso do gráfico de dispositivo](external-graph-use-cases.md)externo.

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de gráfico de dispositivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Gráfico de dispositivos de link de Perfil</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> As regras de mesclagem</span> de Perfis criadas com a opção Link <span class="wintitle"> de</span> Perfil são ideais para: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Propriedades digitais com um alto nível de autenticação de cliente. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">campanhas focadas e de baixo alcance. O gráfico do dispositivo Link <span class="wintitle"> do</span> Perfil é baseado apenas em dados determinísticos. Esse pool de perfis do dispositivo sempre será menor em relação ao pool de usuários e dispositivos não autenticados. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Casos de uso em que os clientes precisam estar em um estado autenticado para se qualificarem para a segmentação. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opções de Gráfico de Dispositivo Externo </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> As regras de mesclagem</span> de Perfil criadas com o <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co-op</a> ou qualquer gráfico de dispositivo externo integrado ao <span class="keyword"> Audience Manager</span> são ideais para: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Propriedades digitais com um nível baixo de autenticação de cliente. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">campanhas de marca amplas e de alto alcance. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Casos de uso em que os clientes não precisam estar em um estado autenticado para se qualificarem para segmentação. </li> 
     </ul> </p> <p> <p>Dica: O <span class="keyword"> Device Co-op</span> é a melhor opção se você for um cliente <span class="keyword"> Experience Cloud</span> com baixa autenticação e sem relacionamento com qualquer provedor de gráficos de dispositivos. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

Assista ao vídeo abaixo para obter uma visão geral de possíveis casos de uso para [!UICONTROL Profile Merge Rules].

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [Casos de uso do gráfico de dispositivo de link de perfis](profile-link-use-case.md)
>* [Casos de uso do gráfico do dispositivo externo](external-graph-use-cases.md)
>* [Perguntas frequentes sobre as regras de mesclagem de Perfis](../../faq/faq-profile-merge.md)

