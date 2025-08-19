---
description: As opções de Regras de mesclagem de perfis permitem expandir ou estreitar o foco do público-alvo em públicos-alvo específicos com base em necessidades ou metas comerciais. Esses casos de uso gerais exploram como usar as opções disponíveis e criar regras de mesclagem para direcionamento individual, doméstico e entre dispositivos.
seo-description: Profile Merge Rules options let you expand or tighten audience focus on specific audiences based on business needs or goals. These general use cases explore how to use available options and create merge rules for individual, household, and cross-device targeting.
seo-title: General Use Cases for Profile Merge Rules
solution: Audience Manager
title: Casos de uso gerais para regras de mesclagem de perfis
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Profile Merge
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 1%

---

# Casos de uso gerais para regras de mesclagem de perfis {#general-use-cases-for-profile-merge-rules}

As opções do [!UICONTROL Profile Merge Rules] permitem expandir ou estreitar o foco do público-alvo para públicos-alvo específicos com base nas necessidades ou metas comerciais. Esses casos de uso gerais exploram como usar as opções disponíveis e criar regras de mesclagem para direcionamento individual, doméstico e entre dispositivos. [!UICONTROL Profile Merge Rules] trabalhar com destinos em lote e em tempo real.

>[!TIP]
>
>Para obter definições e descrições dessas configurações do [!UICONTROL Merge Rule], consulte [Opções de Regra de Mesclagem de Perfis Definidas](merge-rule-definitions.md).

## Direcionamento de dispositivo {#device-personalization}

Esse cenário se aplica aos profissionais de marketing que desejam avaliar um único perfil de dispositivo para um segmento de público-alvo definido no Audience Manager, a fim de fornecer uma experiência consistente para o dispositivo usando plataformas de direcionamento que oferecem suporte a IDs de dispositivo (DSPs, plataformas de personalização no site e outras plataformas de direcionamento baseadas em dispositivo), sem considerar a autenticação do usuário.

Para criar uma regra que segmente apenas perfis de dispositivo, selecione **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![somente dispositivo](assets/device-only.png)

Digamos que John seja dono de três smartphones. Dois deles são iPhone 7s no Plano de Dados A, e um deles é a Samsung no Plano de Dados B. Sem considerar seu estado autenticado em nenhum dos três dispositivos, a operadora de celular de John deseja oferecer a ele uma atualização do plano de dados, mas somente para dispositivos iPhone 7 executados no Plano de dados A.

Ao usar a regra **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**, [!DNL Device 1] e [!DNL Device 3] se qualificam para o segmento, enquanto o Dispositivo 2 é ignorado.

![somente dispositivo](assets/device-management.png)

## Direcionamento de dispositivo compartilhado {#target-shared-devices}

Digamos que John e sua esposa, Jane, usem o mesmo laptop para visitar uma loja on-line e fazer pedidos de vários itens.

John usa sua própria conta para reservar passagens de viagem e ofertas especiais, enquanto Jane usa sua própria conta para comprar música e filmes.

A equipe de marketing da loja pode usar a regra **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** para direcionar John e Jane com ofertas específicas, com base exclusivamente em sua atividade autenticada.

![atual-sem-dispositivo](assets/current-no-device.png)

Ao usar essa regra, o Audience Manager ignora completamente o perfil do dispositivo, qualificando a ID de CRM de John para o segmento e não qualificando a ID de CRM de Jane.

![direcionamento-compartilhado-dispositivo](assets/shared-device-targeting.png)

## Direcionamento online/offline {#device-household-targeting}

Este caso de uso abrange o gerenciamento de identidade do agregado. Uma empresa pode mesclar um único perfil de dispositivo com o último perfil autenticado nesse dispositivo, usando a regra **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]**.

![último-perfil-de-dispositivo](assets/last-device-profile.png)

Vamos considerar um segmento feito de famílias com renda superior a US$ 100.000/ano, que contenha pelo menos um dispositivo que seja um [!DNL iPhone 7] em [!DNL Data Plan B]. Temos dois perfis domésticos (perfis entre dispositivos), cada um conectado a dois perfis de dispositivos diferentes. As características necessárias para se qualificar para o segmento são distribuídas pelos perfis do dispositivo e entre dispositivos.

O Audience Manager mescla cada par de dispositivos + perfis entre dispositivos para ver se o conjunto mesclado de características se qualifica para o segmento. Como o Audience Manager avalia cada perfil que foi incluído na mesclagem, um perfil de dispositivo e um perfil doméstico podem ser segmentados.

O vínculo entre o dispositivo e o perfil doméstico permite que o Audience Manager qualifique [!DNL Household 2] para o segmento, mas não [!DNL Household 1]. De [!DNL Household 2], somente [!DNL Device 3] se qualifica para o segmento. Este [!UICONTROL Profile Merge Rule] habilitou o profissional de marketing a fornecer uma mensagem de marketing consistente para um dispositivo individual ([!DNL Device 3]) e para a família maior ([!DNL Household 2]).

![gerenciamento doméstico](assets/household-management.png)

## Direcionamento para destinos com base em pessoas {#all-cross-device}

>[!IMPORTANT]
>
>Este artigo contém a documentação do produto destinada a orientá-lo pela configuração e pelo uso desse recurso. Nada contido aqui é aconselhamento jurídico. Consulte seu próprio serviço jurídico para obter orientação jurídica.

Este cenário de direcionamento está disponível somente para clientes que compraram o complemento [!DNL People-Based Destinations]. Essa regra permite que os profissionais de marketing acessem os clientes com base em seus próprios dados autenticados.

Digamos que um retailer online queira alcançar os clientes existentes por meio de plataformas sociais e mostrar ofertas personalizadas com base em seus pedidos anteriores. Com o [!UICONTROL People-Based Destinations], eles podem assimilar endereços de email com hash de seu próprio [!DNL CRM] na Audience Manager, criar segmentos a partir de dados offline e enviar esses segmentos para as plataformas sociais nas quais desejam anunciar, usando esse identificador com hash e otimizando seus gastos com publicidade.

Para saber mais sobre esta opção, consulte [Destinos com base em pessoas](../destinations/people-based-destinations-overview.md).

![todos entre dispositivos](assets/all-cross-device.png)

## Opções do gráfico de dispositivos {#device-graph-options}

Escolher uma opção [!UICONTROL device graph] para uma regra [!UICONTROL Profile Merge] depende de condições exclusivas de suas propriedades digitais e metas comerciais. Essas diretrizes gerais podem ajudá-lo a entender quando usar um tipo de gráfico em vez de outro. Observe que você deve ter uma relação contratual com um gráfico de dispositivos externo para usar essas opções. Consulte a tabela abaixo para obter orientações gerais sobre quando escolher uma opção de gráfico de dispositivos. Para casos de uso específicos, consulte [Casos de uso do gráfico de dispositivo de link de perfil](profile-link-use-case.md) e [Casos de uso do gráfico de dispositivo externo](external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de gráfico do dispositivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Gráfico do dispositivo de vinculação de perfis</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Regras de Mesclagem de Perfis</span> criadas com a opção <span class="wintitle"> Link de Perfis</span> são ideais para: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Propriedades digitais que têm um alto nível de autenticação do cliente. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Campanhas focadas de baixo alcance. O gráfico de dispositivos <span class="wintitle"> Link de Perfil</span> foi criado somente com dados determinísticos. Esse pool de perfis de dispositivo sempre será menor em relação ao pool de usuários e dispositivos não autenticados. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Casos de uso em que os clientes precisam estar em um estado autenticado para se qualificarem para segmentação. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opções do gráfico do dispositivo externo </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> As regras de Mesclagem de Perfis</span> criadas com qualquer gráfico de dispositivos externo integrado ao <span class="keyword"> Audience Manager</span> são ideais para: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Propriedades digitais que têm um baixo nível de autenticação do cliente. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Campanhas de marca amplas e de alto alcance. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Casos de uso em que os clientes não precisam estar em um estado autenticado para se qualificarem para segmentação. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Assista ao vídeo abaixo para obter uma visão geral dos possíveis casos de uso do [!UICONTROL Profile Merge Rules].

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [Casos de uso do gráfico de dispositivo de link de perfis](profile-link-use-case.md)
>* [Casos de uso do gráfico do dispositivo externo](external-graph-use-cases.md)
>* [Perguntas frequentes sobre Regras de Mesclagem de Perfis](../../faq/faq-profile-merge.md)
