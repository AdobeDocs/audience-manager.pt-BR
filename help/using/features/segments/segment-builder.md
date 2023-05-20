---
description: Descreve como criar segmentos com o Construtor de segmentos.
seo-description: Describes how to create segments with Segment Builder.
seo-title: Segment Builder
solution: Audience Manager
title: Construtor de segmentos
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 2%

---

# [!UICONTROL Segment Builder] {#segment-builder}

Descreve as etapas obrigatórias e opcionais que criam um segmento no [!UICONTROL Segment Builder].

## Demonstração do vídeo

Comece assistindo ao [Vídeo Criar segmentos no Audience Manager](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). O vídeo o orienta pelo processo de criação de segmentos. Leia as seções abaixo para obter mais informações.

## Criar um [!UICONTROL Segment] {#create-segment}

### Seção do Construtor de segmentos

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] consiste em 3 seções separadas: [!UICONTROL Basic Information], [!UICONTROL Traits], e [!UICONTROL Destinations Mapping]. Para criar um [!UICONTROL segment], preencha os campos obrigatórios na [!UICONTROL Basic Information] e [!UICONTROL Traits] seções. [!UICONTROL Destinations Mapping] são opcionais. Consulte as instruções abaixo para obter ajuda adicional.

1. No [Informações básicas](../../features/segments/segment-builder.md#segment-builder-controls-basics) seção:

   ![create-segment](assets/create-segment.png)

   * Nomeie o [!UICONTROL segment]. O comprimento máximo de um [!UICONTROL segment] O nome do é 255 caracteres.
   * Defina o [!UICONTROL segment] status (ativo é o padrão).
   * Escolha um [!UICONTROL data source]. Use o primeiro menu suspenso para filtrar entre Audience Manager [!UICONTROL data sources], conjuntos de relatórios do Adobe Analytics ou ambos. Em seguida, use o segundo menu suspenso para escolher o [!UICONTROL data source]. Se você não estiver usando conjuntos de relatórios do Adobe Analytics, a variável [!UICONTROL data source] o seletor de tipo está desativado e assume como padrão apenas as fontes de dados de Audience Manager.
   * Selecione um [!UICONTROL profile merge rule] a ser usado para [!UICONTROL segment] qualificação.
   * Atribua a [!UICONTROL segment] para uma pasta de armazenamento.

1. No [Características](../../features/segments/segment-builder.md#segment-builder-controls-traits) seção:
   ![características do construtor de segmentos](assets/segment-builder-traits.png)
   * Procure por [!UICONTROL trait] que deseja adicionar a um segmento e clique em **[!UICONTROL Add Trait]**. Adicionar outro [!UICONTROL trait] para criar um [!UICONTROL trait] grupo.
   * Traga para frente o [!UICONTROL Advanced Search] modal clicando em **[!UICONTROL Browse All Traits]**. Pesquisar por [!UICONTROL traits] por nome, ID, descrição ou [!UICONTROL data source]. Clique em uma pasta enquanto pesquisa para limitar os resultados a essa pasta e suas subpastas. Também é possível filtrar [!UICONTROL traits] por [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded], e [!UICONTROL Algorithmic]) ou tipo de população ([ID do dispositivo](../../reference/ids-in-aam.md) e [ID entre dispositivos](../../reference/ids-in-aam.md)).
      ![segmento-construtor-navegador-características](assets/segment-builder-browse-traits.png)
   * Entrar ao vivo [recomendações de características](trait-recommendations.md) à medida que você cria o [!UICONTROL segment].
   * Clique e arraste [!UICONTROL traits] para criar grupos separados.
   * Passe o mouse entre grupos para definir relações com booleano [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] valores.
   * Passe o mouse sobre o ícone de relógio para adicionar [recenticidade e frequência](../../features/segments/recency-and-frequency.md) regras para a [!UICONTROL trait].
   * Exibir dados de preenchimento do segmento ao adicionar ou remover [!UICONTROL traits]. Clique em **[!UICONTROL Calculate Estimates]** para ver (ou atualizar) os números de população estimados. Leia mais sobre [dados de população do segmento](../../features/segments/segment-builder-data.md#segment-populations) no [!UICONTROL Segment Builder].
   * Clique em **[!UICONTROL Save]** quando terminar.

1. *(Opcional)* Mapear um [!UICONTROL segment] para um [!UICONTROL destination] no [Mapeamento de destinos](../../features/segments/segment-builder.md#segment-builder-controls-destinations) seção:
   * Procure por [!UICONTROL destination] e clique em **[!UICONTROL Add Destination]**. Observe que [!UICONTROL destination] já deve existir antes de ser adicionado a um [!UICONTROL segment].
   * Clique em **[!UICONTROL Save]** quando terminar.

Assista ao vídeo abaixo para obter uma visão detalhada de como as métricas entre dispositivos funcionam.

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder] Controles: [!UICONTROL Basic Information] Seção {#segment-builder-controls-basics}

Entrada [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] As configurações do permitem criar novas características ou editar características existentes. Para criar um novo [!UICONTROL segment], forneça um nome, um [!UICONTROL data source]e selecione uma pasta de armazenamento. Todos os outros campos são opcionais. Vá para a guia [!UICONTROL Traits] quando terminar.

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
| **[!UICONTROL Data Source]** | Associa o segmento a um provedor de dados específico. <br> Use o primeiro menu suspenso para filtrar entre fontes de dados de Audience Manager, conjuntos de relatórios do Adobe Analytics ou ambos. Em seguida, use o segundo menu suspenso para escolher a fonte de dados. <br> Se você não estiver usando conjuntos de relatórios do Adobe Analytics, o seletor de tipo de fonte de dados será desativado e assumirá como padrão apenas as fontes de dados de Audience Manager. |
| **[!UICONTROL Profile Merge Rule]** | Seleciona a Regra de mesclagem de perfis a ser usada para qualificação de segmentos. |
| **[!UICONTROL Status]** | Ativa ou desativa o segmento (ativo por padrão). |
| **Armazenamento de pasta** | Determina a qual pasta de armazenamento o segmento pertence. |

## [!UICONTROL Segment Builder] Controles: [!UICONTROL Traits] Seção {#segment-builder-controls-traits}

Entrada [!UICONTROL Segment Builder], o [!UICONTROL Traits] permite gerenciar [!UICONTROL traits] em um [!UICONTROL segment], criar [!UICONTROL trait] grupos e definir critérios de qualificação. Para adicionar um [!UICONTROL trait] para um [!UICONTROL segment], digite o [!UICONTROL trait] no campo de pesquisa e clique em [!UICONTROL Add Trait]. Salve o [!UICONTROL trait] (se concluído) ou continue para [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Pré-requisitos:** Preencha os campos obrigatórios na [!UICONTROL Basic Information] seção.

| Campo | Descrição |
|--- |--- |
| **[!UICONTROL Basic View]** | Esta seção fornece controles visuais que permitem: <ul><li>Criar novos e gerenciar existentes [!UICONTROL segments].</li><li>Remover [!UICONTROL traits] de a [!UICONTROL segment].</li><li>Adicione até 50 (máximo) [!UICONTROL traits] para um [!UICONTROL segment].</li><li>Arrastar e soltar [!UICONTROL traits] para criar novos grupos.</li><li>Exibir [!UICONTROL traits] e [!UICONTROL trait] grupos em uma [!UICONTROL segment].</li><li>Defina critérios de qualificação com expressões booleanas, operadores de comparação e configurações de recenticidade/frequência.</li></ul> |
| **[!UICONTROL Code View]** | Abre um ambiente de desenvolvimento que permite criar e gerenciar [!UICONTROL traits], grupos e requisitos de qualificação com o código em vez da interface visual. A visualização de código é útil se o [!UICONTROL segments]: <ul><li>Contém mais de 50 [!UICONTROL traits] em um indivíduo [!UICONTROL segment]. Nota: [!UICONTROL Segments] são limitadas a 5000 [!UICONTROL traits] (máximo).</li><li>Contém muitos [!UICONTROL trait] grupos.</li><li>Têm requisitos complexos de qualificação.</li></ul> |
| Pesquisar | Ajuda a encontrar [!UICONTROL traits] para adicionar a um [!UICONTROL segment]. |
| Recomendações   | Obter recomendações em tempo real para semelhantes [!UICONTROL traits], de seu próprio [!UICONTROL traits] e [!UICONTROL Audience Marketplace] feeds de dados nos quais você está inscrito. Adicione essas recomendações à [!UICONTROL segment] regra para expandir seu público-alvo. Leia mais em [Recommendations de características](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Obter recomendações em tempo real para semelhantes [!UICONTROL traits], de [!UICONTROL Audience Marketplace] feeds de dados nos quais você não tem assinatura. Leia mais em [Recommendations de características](trait-recommendations.md). |
| Real e Estimado [!UICONTROL Segment] Tamanho dos dados | Consulte [Dados de população de característica e segmento no Criador de segmentos](segment-builder-data.md). |

## Remover [!UICONTROL Traits] de a [!UICONTROL Segment] {#remove-traits}

Gerenciamento do [!UICONTROL traits] no seu [!UICONTROL segments] é uma parte importante da manutenção [!UICONTROL segments] viáveis. Siga estas etapas se precisar remover [!UICONTROL traits] de a [!UICONTROL segment].

Para remover [!UICONTROL traits] de a [!UICONTROL segment]:

1. Ir para **[!UICONTROL Audience Data > Segments]**. Percorra a lista ou use o recurso de pesquisa para localizar o [!UICONTROL segment] com a qual você deseja trabalhar.
2. Clique em [!UICONTROL segment] nome para abrir o [!UICONTROL segment] tela de detalhes.
3. Clique em **Editar** para abrir [!UICONTROL Segment Builder] e clique em **Características** para abrir o [!UICONTROL traits] painel.
4. Passe o mouse sobre [!UICONTROL trait] exclua e clique no X. Essa ação remove imediatamente a variável [!UICONTROL trait] do seu [!UICONTROL segment].

## [!UICONTROL Segment Builder] Controles: [!UICONTROL Destinations Mappings] Seção {#segment-builder-controls-destinations}

Entrada [!UICONTROL Segment Builder], a opção [!UICONTROL Destinations Mapping] permite enviar [!UICONTROL segment] dados para terceiros [!DNL cookie], [!DNL URL]ou [!UICONTROL server-to-server destination]. Para adicionar um [!UICONTROL destination], pesquise (ou procure) por um [!UICONTROL destination], fornecer [!UICONTROL destination] informações específicas e clique em **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Pré-requisitos

Preencha os campos obrigatórios na [!UICONTROL Basic Information] e [!UICONTROL Traits] seções. Além disso, o destino já deve existir.

### [!UICONTROL Destination Mappings] Ferramentas de pesquisa

A variável **[!UICONTROL Destination Mappings]** contém ferramentas de pesquisa conforme descrito na tabela abaixo.

| Tipo de pesquisa | Descrição |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Permite procurar por um [!UICONTROL destination] por nome. Para pesquisar, comece a digitar. O campo será preenchido automaticamente com base nos termos de pesquisa. Clique em **[!UICONTROL Add Destination]** quando terminar. |
| **[!UICONTROL Browse All Destinations]** | Procurar uma lista de *all* [!UICONTROL destinations] disponíveis para você. Selecionar e adicionar [!UICONTROL destinations] ao seu [!UICONTROL segment] na lista pop-up. |

## Campos na [!UICONTROL Destination Mappings] Janelas pop-up {#fields-in-dest-mappings}

Entrada [!UICONTROL Segment Builder], o [!UICONTROL Add Destination] será exibida após selecionar um [!UICONTROL destination]. Essa janela exibe informações estáticas sobre o [!UICONTROL destination] e campos que variam dependendo da [!UICONTROL destination] tipo. Forneça as informações necessárias nos campos vazios para configurar uma [!UICONTROL destination mapping].

>[!NOTE]
>
>As datas de publicação são opcionais. Quando deixado em branco, o destino se torna ativo e nunca expira.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Campos

No [!UICONTROL Destination Mapping] especifique os pares de valores chave usados para enviar dados para o [!UICONTROL destination]. Insira a chave no primeiro campo e os valores no segundo. Seu [!UICONTROL cookie destination] o pop-up pode ser semelhante a:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Campos

No [!UICONTROL URL] e [!UICONTROL Secure URL] especificar o endereço padrão ou seguro completo usado para enviar dados para o [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Campos

No [!UICONTROL Destination Value] especifique o valor (parte de um par de valores chave) usado para enviar dados para o [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Criar um destino de cookie](../../features/destinations/create-cookie-destination.md)
>* [Criar um destino de URL](../../features/destinations/create-url-destination.md)

