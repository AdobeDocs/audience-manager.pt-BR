---
description: A qualificação de características, ou realização de características, é tratada de forma diferente no Audience Manager, dependendo do tipo de característica. Consulte a tabela abaixo para obter informações detalhadas sobre qualificação de características.
keywords: qualificação de característica;realização de característica;Realizações de características únicas;UTR;População de características totais;TTP
seo-description: A qualificação de características, ou realização de características, é tratada de forma diferente no Audience Manager, dependendo do tipo de característica. Consulte a tabela abaixo para obter informações detalhadas sobre qualificação de características.
seo-title: Referência de qualificação de característica
solution: Audience Manager
title: Referência de qualificação de característica
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# Referência de qualificação de característica {#trait-qualification-reference}

A qualificação de características, ou realização de características, é tratada de forma diferente no Audience Manager, dependendo do tipo de característica. Consulte a tabela abaixo para obter informações detalhadas sobre qualificação de características.

## Qualificação de característica por tipo de característica {#trait-type}

<table id="table_14CD705F376B44EEA9A6C011984356F0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de característica </th> 
   <th colname="col2" class="entry"> Critérios de qualificação </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Características baseadas em regras </p> </td> 
   <td colname="col2"> <p>A qualificação de características acontece em tempo real, já que os usuários se qualificam para uma característica em seu navegador. Seus usuários começarão a se qualificar para uma característica baseada em regras aproximadamente 4 horas depois que você <a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits"> criar a característica</a> na interface do usuário. </p> <p>Características baseadas em regras permitem usar controles de recenticidade e frequência <a href="../../features/segments/recency-and-frequency.md"></a> para o limite de frequência de anúncio e outros casos de uso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Características integradas </p> </td> 
   <td colname="col2"> <p>A qualificação de características ocorre depois que um arquivo de entrada é processado, isto é, o arquivo de entrada é <a href="../../faq/faq-inbound-data-ingestion.md"> importado para o Audience Manager</a> e é quando a qualificação de características acontece. </p> <p> Para características integradas, o número máximo de qualificações para um perfil de usuário é 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Características algorítmicas </p> </td> 
   <td colname="col2"> <p>Para características algorítmicas, o número máximo de qualificações para um perfil de usuário é 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Características da pasta </p> </td> 
   <td colname="col2"> <p>Uma característica de pasta resume as qualificações de característica das características que ela contém. </p> <p>Ler <a href="../../features/traits/about-folder-traits.md"> características da pasta: Sobre</a> para obter mais informações. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>Características do público-alvo ativo e características sincronizadas da fonte de dados </p> </td> 
   <td colname="col2"> <p>Uma característica de Público-alvo <span class="wintitle"> ativo contém todos os dispositivos sob gerenciamento na sua conta do</span> Audience Manager <span class="wintitle"></span> . </p> <p><span class="wintitle"> As Características</span> sincronizadas da fonte de dados rastreiam todos os usuários associados a uma fonte de dados. </p> <p>Leia mais sobre Características <a href="../../features/traits/client-activity-synced-audience-traits.md"> do público-alvo ativo e Características</a>sincronizadas da fonte de dados. </p> </td>
  </tr>
 </tbody>
</table>

## Realizações de características únicas e população de características totais {#unique-trait-realizations}

![](assets/utr-ttp1.png)

A **[!UICONTROL Unique Trait Realizations]** contagem do número de visitantes que adicionaram a característica ao perfil, dentro de intervalos de tempo diferentes.

O **[!UICONTROL Total Trait Population]** representa o número de visitantes que têm essa característica no perfil.

Pense nos números desta forma. Na imagem acima, na exibição Detalhes [da](../../features/traits/trait-details-page.md) característica, 181 representa o número de dispositivos ativos que visitaram suas propriedades ontem. A [!UICONTROL Total Trait Population] de 1.595 representa a quantidade de usuários atualmente qualificados para essa característica. A [!UICONTROL Total Trait Population] figura deve mostrar a quantidade total de usuários que podem ser usados para segmentação/definição de metas. Normalmente, os usuários permanecerão parte de uma característica por 120 dias.

Porque nós executamos dois trabalhos computacionais diferentes para calcular as duas populações, as [!UICONTROL Total Trait Population] sempre ficam para trás [!UICONTROL Unique Trait Realizations] por 24 horas. No gráfico acima, você pode ver 175 [!UICONTROL Unique Trait Realizations] e um [!UICONTROL Total Trait Population] de 6 para 11 de fevereiro. Os 175 perfis são adicionados ao [!UICONTROL Total Trait Population] no dia seguinte.

Para direcionar ainda mais o ponto para casa, se você experimentasse um pico de 10.000 visitantes no momento, eles apareceriam no dia [!UICONTROL Unique Trait Realizations]de amanhã, mas só apareceriam 24 horas depois no [!UICONTROL Total Trait Population].

## Limite de qualificação de características {#trait-qualification-limit}

Nós aplicamos um limite de 150.000 qualificações de características para cada perfil de usuário, seja um perfil autenticado ( [DPUUID](../../reference/ids-in-aam.md)) ou uma ID de dispositivo ( [UUID](../../reference/ids-in-aam.md)). Observe que, embora os DPUUIDs sejam exclusivos de uma instância específica do [!DNL Audience Manager], os UUIDs são compartilhados na [!DNL Audience Manager] plataforma. Para [!UICONTROL UUID]nós, impomos uma política de equidade ao armazenarmos qualificações profissionais. Um algoritmo garante que um compartilhamento igual do [!UICONTROL UUID] perfil seja disponibilizado para cada instância do [!DNL Audience Manager].
