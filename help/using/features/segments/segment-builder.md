---
description: Descreve como criar segmentos com o Construtor de segmentos.
seo-description: Descreve como criar segmentos com o Construtor de segmentos.
seo-title: Construtor de segmentos
solution: Audience Manager
title: Construtor de segmentos
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 2%

---


# [!UICONTROL Segment Builder] {#segment-builder}

Descreve as etapas necessárias e opcionais que criam um segmento em [!UICONTROL Segment Builder].

## Demonstração de vídeo

Start assistindo ao vídeo [Criar segmentos no Audience Manager](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). O vídeo o orienta pelo processo de criação do segmento. Leia as seções abaixo para obter mais informações.

## Criar um [!UICONTROL Segment] {#create-segment}

### Seção do Construtor de segmentos

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] consiste em 3 seções separadas: [!UICONTROL Basic Information], [!UICONTROL Traits]e [!UICONTROL Destinations Mapping]. Para criar um [!UICONTROL segment], preencha os campos obrigatórios nas seções [!UICONTROL Basic Information] e [!UICONTROL Traits] . [!UICONTROL Destinations Mapping] são opcionais. Consulte as instruções abaixo para obter ajuda adicional.

1. Na seção Informações [](../../features/segments/segment-builder.md#segment-builder-controls-basics) básicas:

   ![create-segment](assets/create-segment.png)

   * Dê um nome ao [!UICONTROL segment]. O comprimento máximo de um [!UICONTROL segment] nome é de 255 caracteres.
   * Defina o [!UICONTROL segment] status (ativo é padrão).
   * Escolha um [!UICONTROL data source]. Use o primeiro menu suspenso para filtrar entre Audience Manager [!UICONTROL data sources], conjuntos de relatórios da Adobe Analytics ou ambos. Em seguida, use o segundo menu suspenso para escolher seu [!UICONTROL data source]. Se você não estiver usando os conjuntos de relatórios da Adobe Analytics, o seletor de [!UICONTROL data source] tipos será desativado e o padrão será somente fontes de dados Audience Manager.
   * Selecione um [!UICONTROL profile merge rule] para usar na [!UICONTROL segment] qualificação.
   * Atribua a pasta [!UICONTROL segment] a um armazenamento.

1. Na [seção Características](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   ![características do construtor de segmentos](assets/segment-builder-traits.png)
   * Procure o segmento [!UICONTROL trait] que deseja adicionar e clique em **[!UICONTROL Add Trait]**. Adicione outro [!UICONTROL trait] para criar um [!UICONTROL trait] grupo.
   * Abra o modal [!UICONTROL Advanced Search] clicando em **[!UICONTROL Browse All Traits]**. Procure [!UICONTROL traits] por nome, ID, descrição ou [!UICONTROL data source]. Clique em uma pasta enquanto pesquisa para limitar os resultados a essa pasta e suas subpastas. Você também pode filtrar [!UICONTROL traits] por [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded]e [!UICONTROL Algorithmic]) ou tipo de população (ID[do](../../reference/ids-in-aam.md) dispositivo e ID [de](../../reference/ids-in-aam.md)vários dispositivos).
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Obtenha recomendações [de](trait-recommendations.md) características ao vivo enquanto você cria [!UICONTROL segment].
   * Clique e arraste [!UICONTROL traits] para criar grupos separados.
   * Passe o cursor do mouse sobre os grupos para definir relações com valores Booleanos [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] .
   * Passe o mouse sobre o ícone do relógio para adicionar regras de [recenticidade e frequência](../../features/segments/recency-and-frequency.md) ao [!UICONTROL trait].
   * Visualização dos dados de preenchimento do segmento à medida que você adiciona ou remove [!UICONTROL traits]. Clique **[!UICONTROL Calculate Estimates]** para ver (ou atualizar) os números de população estimados. Leia mais sobre os dados [de população do](../../features/segments/segment-builder-data.md#segment-populations) segmento no [!UICONTROL Segment Builder].
   * Clique **[!UICONTROL Save]** quando concluído.

1. *(Opcional)* Mapeie um [!UICONTROL segment] para um [!UICONTROL destination] na seção Mapeamento [de](../../features/segments/segment-builder.md#segment-builder-controls-destinations) destino:
   * Procure o [!UICONTROL destination] e clique em **[!UICONTROL Add Destination]**. Observe que a variável já [!UICONTROL destination] deve existir antes que você possa adicioná-la a uma [!UICONTROL segment].
   * Clique **[!UICONTROL Save]** quando concluído.

Assista ao vídeo abaixo para ver detalhadamente como as métricas entre dispositivos funcionam.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## [!UICONTROL Segment Builder] Controles: [!UICONTROL Basic Information] Seção {#segment-builder-controls-basics}

Em [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] as configurações permitem criar características novas ou editar características existentes. Para criar um novo [!UICONTROL segment], forneça um nome, um [!UICONTROL data source]e selecione uma pasta de armazenamento. Todos os outros campos são opcionais. Vá para a [!UICONTROL Traits] seção quando terminar.

<!-- r_segment_basic_info_section.xml -->

<!--

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Name</b> </td> 
   <td colname="col2"> <p>Give the segment a short, logical name that describes its function or purpose. Avoid abbreviations and special characters. The maximum length of a segment name is 255 characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> <p>A field for additional descriptive information about the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Integration Code</b> </td> 
   <td colname="col2"> <p>A field for a user-defined ID or other company-specific information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Source</b> </td> 
   <td colname="col2"> <p>Associates the segment with a specific data provider. <p>Use the first drop-down menu to filter between Audience Manager data sources, Adobe Analytics report suites, or both. Then, use the second drop-down menu to choose your data source.</p><p> If you are not using Adobe Analytics report suites, the data source type selector is disabled and defaulted to Audience Manager data sources only.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Profile Merge Rule</b> </td> 
   <td colname="col2"> <p>Selects the Profile Merge Rule to use for segment qualification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Activates or deactivates the segment (active by default). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Folder Storage</b> </td> 
   <td colname="col2"> <p>Determines which storage folder the segment belongs to. </p> </td> 
  </tr> 
 </tbody> 
</table>

-->

| Campo | Descrição |
---------|----------
| **[!UICONTROL Name]** | Dê ao segmento um nome curto e lógico que descreva sua função ou finalidade. Evite abreviações e caracteres especiais. O comprimento máximo de um nome de segmento é de 255 caracteres. |
| **[!UICONTROL Description]** | Um campo para obter informações descritivas adicionais sobre o segmento. |
| **[!UICONTROL Integration Code]** | Um campo para uma ID definida pelo usuário ou outras informações específicas da empresa. |
| **[!UICONTROL Data Source]** | Associa o segmento a um provedor de dados específico. <br> Use o primeiro menu suspenso para filtrar entre fontes de dados Audience Manager, conjuntos de relatórios da Adobe Analytics ou ambos. Em seguida, use o segundo menu suspenso para escolher sua fonte de dados. <br> Se você não estiver usando os conjuntos de relatórios da Adobe Analytics, o seletor de tipo de fonte de dados será desativado e o padrão será somente fontes de dados Audience Manager. |
| **[!UICONTROL Profile Merge Rule]** | Seleciona a Regra de mesclagem de Perfis a ser usada para qualificação de segmentos. |
| **[!UICONTROL Status]** | Ativa ou desativa o segmento (ativo por padrão). |
| **Armazenamento de pasta** | Determina a pasta de armazenamento à qual o segmento pertence. |

## [!UICONTROL Segment Builder] Controles: [!UICONTROL Traits] Seção {#segment-builder-controls-traits}

Em [!UICONTROL Segment Builder], a [!UICONTROL Traits] seção permite que você gerencie [!UICONTROL traits] em um [!UICONTROL segment], crie [!UICONTROL trait] grupos e defina critérios de qualificação. Para adicionar um item [!UICONTROL trait] a um [!UICONTROL segment], digite o [!UICONTROL trait] nome no campo de pesquisa e clique em [!UICONTROL Add Trait]. Salve o [!UICONTROL trait] (se concluído) ou vá para [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Pré-requisitos:** Preencha os campos obrigatórios na [!UICONTROL Basic Information] seção.

| Campo | Descrição |
|--- |--- |
| **[!UICONTROL Basic View]** | Esta seção fornece controles visuais que permitem: <ul><li>Crie novos e gerencie os existentes [!UICONTROL segments].</li><li>Remover [!UICONTROL traits] de um [!UICONTROL segment].</li><li>Adicione até 50 (máximo) [!UICONTROL traits] a um [!UICONTROL segment].</li><li>Arraste e solte [!UICONTROL traits] para criar novos grupos.</li><li>Visualização [!UICONTROL traits] e [!UICONTROL trait] grupos em uma [!UICONTROL segment].</li><li>Defina os critérios de qualificação com expressões booleanas, operadores de comparação e configurações de recenticidade/frequência.</li></ul> |
| **[!UICONTROL Code View]** | Abre um ambiente de desenvolvimento que permite criar e gerenciar [!UICONTROL traits]os requisitos de qualificação, grupos e códigos em vez da interface visual. A visualização de código é útil se você [!UICONTROL segments]: <ul><li>Conter mais de 50 [!UICONTROL traits] em um indivíduo [!UICONTROL segment]. Observação: [!UICONTROL Segments] estão limitados a 5000 [!UICONTROL traits] (máximo).</li><li>Contém muitos [!UICONTROL trait] grupos.</li><li>Ter requisitos de qualificação complexos.</li></ul> |
| Pesquisar | Ajuda você a encontrar [!UICONTROL traits] uma adição a um [!UICONTROL segment]. |
| Recomendações   | Obtenha recomendações ao vivo para semelhantes [!UICONTROL traits], a partir de seus feeds originais [!UICONTROL traits] e [!UICONTROL Audience Marketplace] de dados aos quais você está inscrito. Adicione essas recomendações à [!UICONTROL segment] regra para expandir sua audiência. Leia mais no [Trait Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Obtenha recomendações ao vivo para feeds semelhantes [!UICONTROL traits], de feeds de [!UICONTROL Audience Marketplace] dados aos quais você não está inscrito. Leia mais no [Trait Recommendations](trait-recommendations.md). |
| Dados de [!UICONTROL Segment] tamanho real e estimado | Consulte [Dados de população de característica e segmento no Criador de segmentos](segment-builder-data.md). |

## Remover [!UICONTROL Traits] de uma [!UICONTROL Segment] {#remove-traits}

Gerenciar o [!UICONTROL traits] em seu [!UICONTROL segments] é uma parte importante para manter a [!UICONTROL segments] viabilidade. Siga estas etapas se precisar remover [!UICONTROL traits] de um [!UICONTROL segment].

Para remover [!UICONTROL traits] de um [!UICONTROL segment]:

1. Vá para **[!UICONTROL Audience Data > Segments]**. Percorra a lista ou use o recurso de pesquisa para encontrar o [!UICONTROL segment] que deseja trabalhar.
2. Clique no [!UICONTROL segment] nome para abrir a tela de [!UICONTROL segment] detalhes.
3. Clique em **Editar** para abrir [!UICONTROL Segment Builder] e, em seguida, clique em **Características** para abrir o [!UICONTROL traits] painel.
4. Passe o mouse sobre o item [!UICONTROL trait] que deseja excluir e clique no X. Essa ação remove imediatamente o [!UICONTROL trait] de seu [!UICONTROL segment].

## [!UICONTROL Segment Builder] Controles: [!UICONTROL Destinations Mappings] Seção {#segment-builder-controls-destinations}

Em [!UICONTROL Segment Builder], a seção opcional [!UICONTROL Destinations Mapping] permite enviar [!UICONTROL segment] dados para terceiros [!DNL cookie], [!DNL URL]ou [!UICONTROL server-to-server destination]. Para adicionar um [!UICONTROL destination], pesquise (ou procure) por um [!UICONTROL destination], forneça informações [!UICONTROL destination] específicas e clique em **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Pré-requisitos

Preencha os campos obrigatórios nas seções [!UICONTROL Basic Information] e [!UICONTROL Traits] . Além disso, o destino já deve existir.

### [!UICONTROL Destination Mappings] Ferramentas de pesquisa

O **[!UICONTROL Destination Mappings]** painel contém ferramentas de pesquisa, conforme descrito na tabela abaixo.

| Tipo de pesquisa | Descrição |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Permite que você pesquise por um nome específico [!UICONTROL destination] por. Para pesquisar, digite start. O campo será preenchido automaticamente com base em seus termos de pesquisa. Clique **[!UICONTROL Add Destination]** quando concluído. |
| **[!UICONTROL Browse All Destinations]** | Procure uma lista de *todos* os [!UICONTROL destinations] disponíveis para você. Selecione e adicione [!UICONTROL destinations] a sua lista [!UICONTROL segment] de pop-up. |

## Campos nas janelas pop- [!UICONTROL Destination Mappings] -up {#fields-in-dest-mappings}

Em [!UICONTROL Segment Builder], a caixa de [!UICONTROL Add Destination] diálogo é exibida depois que você seleciona um [!UICONTROL destination]. Essa janela exibe informações estáticas sobre os campos [!UICONTROL destination] e que variam dependendo do [!UICONTROL destination] tipo. Forneça as informações necessárias nos campos vazios para configurar um [!UICONTROL destination mapping].

>[!NOTE]
>
>As datas de publicação são opcionais. Quando em branco, o destino fica ativo e nunca expira.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Campos

Nos [!UICONTROL Destination Mapping] campos, especifique os pares de valores chave usados para enviar dados para o [!UICONTROL destination]. Insira a chave no primeiro campo e os valores no segundo. Seu [!UICONTROL cookie destination] pop pode ser semelhante a este:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Campos

Nos campos [!UICONTROL URL] e [!UICONTROL Secure URL] , especifique o endereço completo padrão ou seguro usado para enviar dados para o [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Campos

No [!UICONTROL Destination Value] campo, especifique o valor (parte de um par de valores chave) usado para enviar dados para o [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Criar um destino de cookie](../../features/destinations/create-cookie-destination.md)
>* [Criar um destino de URL](../../features/destinations/create-url-destination.md)

