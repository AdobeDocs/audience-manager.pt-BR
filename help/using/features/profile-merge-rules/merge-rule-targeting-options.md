---
description: As opções de Regras de mesclagem de perfil permitem expandir ou restringir o foco do público-alvo em públicos-alvo específicos com base em necessidades ou objetivos de negócios. Esses casos de uso gerais exploram como usar as opções disponíveis e criar regras de mesclagem para direcionamento individual, doméstico e entre dispositivos.
seo-description: As opções de Regras de mesclagem de perfil permitem expandir ou restringir o foco do público-alvo em públicos-alvo específicos com base em necessidades ou objetivos de negócios. Esses casos de uso gerais exploram como usar as opções disponíveis e criar regras de mesclagem para direcionamento individual, doméstico e entre dispositivos.
seo-title: Casos de uso gerais para regras de mesclagem de perfis
solution: Audience Manager
title: Casos de uso gerais para regras de mesclagem de perfis
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Mesclar perfis
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 4%

---

# Casos de uso gerais para regras de mesclagem de perfis {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] As opções permitem expandir ou restringir o foco do público-alvo em públicos-alvo específicos com base em necessidades ou objetivos comerciais. Esses casos de uso gerais exploram como usar as opções disponíveis e criar regras de mesclagem para direcionamento individual, doméstico e entre dispositivos. [!UICONTROL Profile Merge Rules] trabalhe com destinos em tempo real e em lote.

>[!TIP]
>
>Para obter as definições e descrições dessas configurações [!UICONTROL Merge Rule], consulte [Opções de Regra de Mesclagem de Perfil Definidas](merge-rule-definitions.md).

## Direcionamento de dispositivo {#device-personalization}

Esse cenário se aplica aos profissionais de marketing que desejam avaliar um único perfil de dispositivo para um segmento de público-alvo definido no Audience Manager, a fim de fornecer uma experiência consistente ao dispositivo usando plataformas de direcionamento que oferecem suporte a IDs de dispositivo (DSP, plataformas de personalização no site e outras plataformas de direcionamento baseadas em dispositivos), não considerando a autenticação do usuário.

Para criar uma regra que segmente somente perfis de dispositivo, selecione **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![somente dispositivo](assets/device-only.png)

Digamos que John é dono de três smartphones. Dois deles são o iPhone 7s no Plano de Dados A, e um deles é o Samsung on Data Plan B. Sem considerar seu estado autenticado em qualquer um dos três dispositivos, a operadora de celular do John quer oferecer a ele uma atualização do plano de dados, mas somente para dispositivos iPhone 7 que são executados no Plano de Dados A.

Ao usar a regra **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**, [!DNL Device 1] e [!DNL Device 3] se qualificam para o segmento, enquanto o Dispositivo 2 é ignorado.

![somente dispositivo](assets/device-management.png)

## Direcionamento de dispositivo compartilhado {#target-shared-devices}

Digamos que John e sua esposa, Jane, usem o mesmo laptop para visitar uma loja online e pedir vários itens.

John usa sua própria conta para reservar ingressos de viagem e negócios especiais, enquanto Jane usa sua própria conta para comprar música e filmes.

A equipe de marketing da loja pode usar a regra **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** para direcionar John e Jane a ofertas específicas, com base apenas em sua atividade autenticada.

![current-no-device](assets/current-no-device.png)

Ao usar essa regra, o Audience Manager ignora completamente o perfil do dispositivo, qualificando a ID do CRM de John para o segmento e não qualificando a ID do CRM de Jane.

![segmentação de dispositivo compartilhado](assets/shared-device-targeting.png)

## Direcionamento online/offline {#device-household-targeting}

Este caso de uso abrange a gestão da identidade doméstica. Uma empresa pode mesclar um único perfil de dispositivo com o último perfil que foi autenticado nesse dispositivo, usando a regra **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]**.

![perfil do último dispositivo](assets/last-device-profile.png)

Considere um segmento feito de famílias com rendimentos maiores que US$ 100.000/ano, contendo pelo menos um dispositivo que seja [!DNL iPhone 7] em [!DNL Data Plan B]. Temos dois perfis familiares (perfis entre dispositivos), cada um conectado a dois perfis de dispositivo diferentes. As características necessárias para se qualificar para o segmento são distribuídas entre os perfis de dispositivo e entre dispositivos.

O Audience Manager mescla todos os pares de perfis de dispositivo + entre dispositivos para ver se o conjunto unido de características se qualifica para o segmento. Como o Audience Manager avalia cada perfil incluído na mesclagem, um perfil de dispositivo e um perfil da família podem ser segmentados.

O link entre o dispositivo e o perfil residencial permite que o Audience Manager se qualifique [!DNL Household 2] para o segmento, mas não [!DNL Household 1]. A partir de [!DNL Household 2], somente [!DNL Device 3] se qualifica para o segmento. Esse [!UICONTROL Profile Merge Rule] permitiu que o profissional de marketing fornecesse uma mensagem de marketing consistente a um dispositivo individual ([!DNL Device 3]) e a família em geral ([!DNL Household 2]).

![gestão doméstica](assets/household-management.png)

## Direcionamento para destinos com base em pessoas {#all-cross-device}

>[!IMPORTANT]
>
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e uso deste recurso. Nada neste documento é de aconselhamento jurídico. Consulte o seu advogado para obter orientação jurídica.

Esse cenário de direcionamento está disponível somente para clientes que compraram o complemento [!DNL People-Based Destinations]. Essa regra permite que os profissionais de marketing atinjam os clientes com base em seus próprios dados autenticados.

Digamos que um varejista online queira alcançar os clientes existentes por meio de plataformas sociais e mostrar a eles ofertas personalizadas com base em seus pedidos anteriores. Com [!UICONTROL People-Based Destinations], eles podem assimilar endereços de email com hash de seu próprio [!DNL CRM] no Audience Manager, criar segmentos a partir dos dados offline e enviar esses segmentos para as plataformas sociais nas quais desejam fazer publicidade, usando esse identificador com hash, otimizando seus gastos com publicidade.

Para saber mais sobre essa opção, consulte [Destinos com base em pessoas](../destinations/people-based-destinations-overview.md).

![todos os dispositivos](assets/all-cross-device.png)

## Opções de gráfico de dispositivo {#device-graph-options}

Escolher uma opção [!UICONTROL device graph] para uma regra [!UICONTROL Profile Merge] depende de condições exclusivas de suas propriedades digitais e objetivos de negócios. Essas diretrizes gerais podem ajudá-lo a entender quando usar um tipo de gráfico em vez de outro. Observe que você deve ser membro do [Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/pt-BR/device-co-op/using/home.html) ou ter uma relação contratual com um gráfico de dispositivos externo para usar essas opções. Consulte a tabela abaixo para obter orientações gerais sobre quando escolher uma opção de gráfico de dispositivos. Para casos de uso específicos, consulte [Casos de uso do gráfico do dispositivo de link de perfil](profile-link-use-case.md) e [Casos de uso do gráfico do dispositivo externo](external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de gráfico do dispositivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Gráfico de dispositivos de link de perfil</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> As </span> métricas de perfil criadas com a opção  <span class="wintitle"> de </span> vinculação de perfil são ideais para: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Propriedades digitais com alto nível de autenticação de cliente. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Campanhas focadas e de baixo alcance. O gráfico de dispositivo <span class="wintitle"> Link de perfil</span> é criado somente em dados determinísticos. Esse pool de perfis de dispositivo sempre será menor em relação ao pool de usuários e dispositivos não autenticados. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Casos de uso em que os clientes precisam estar em um estado autenticado para se qualificarem para segmentação. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opções de gráfico do dispositivo externo </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> As </span> métricas de perfil criadas com o  <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co-</a> opor qualquer gráfico de dispositivos externo integrado ao  <span class="keyword"> Audience </span> Manager são ideais para: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Propriedades digitais que têm um baixo nível de autenticação de cliente. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Campanhas de marca amplas e de alto alcance. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Casos de uso em que os clientes não precisam estar em um estado autenticado para se qualificarem para segmentação. </li> 
     </ul> </p> <p> <p>Dica: O <span class="keyword"> Device Co-op</span> é a melhor opção se você for um cliente do <span class="keyword"> Experience Cloud</span> com baixa autenticação e sem relacionamento com qualquer provedor de gráfico de dispositivo. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

Assista ao vídeo abaixo para obter uma visão geral de possíveis casos de uso para [!UICONTROL Profile Merge Rules].

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [Casos de uso do gráfico de dispositivo de link de perfis](profile-link-use-case.md)
* [Casos de uso do gráfico do dispositivo externo](external-graph-use-cases.md)
* [Perguntas frequentes sobre as regras de mesclagem de perfis](../../faq/faq-profile-merge.md)

