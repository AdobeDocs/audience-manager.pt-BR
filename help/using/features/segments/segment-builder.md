---
description: Descreve como criar segmentos com o Construtor de segmentos.
seo-description: Descreve como criar segmentos com o Construtor de segmentos.
seo-title: Construtor de segmentos
solution: Audience Manager
title: Construtor de segmentos
uuid: 5 ca 924 a 5-2 b 29-4802-ab 02-e 292 d 77 a 0 aae
translation-type: tm+mt
source-git-commit: b346dbe500f1e662c7b121a18c6cc0704ef3cfac

---


# Construtor de segmentos {#segment-builder}

Describes the required and optional steps that create a segment in [!UICONTROL Segment Builder].

## Criar um segmento {#create-segment}

### Seção do Construtor de segmento

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] consiste em 3 seções separadas: [!UICONTROL Basic Information], [!UICONTROL Traits]e [!UICONTROL Destinations Mapping]. To create a segment, complete the required fields in the [!UICONTROL Basic Information] and [!UICONTROL Traits] sections. [!UICONTROL Destinations Mapping] são opcionais. Consulte as instruções abaixo para obter ajuda adicional.

1. In the [Basic Information](../../features/segments/segment-builder.md#segment-builder-controls-basics) section:
   * Nomeie o segmento. O tamanho máximo de um nome de segmento é de 255 caracteres.
   * Defina o status do segmento (ativo é padrão).
   * Escolha uma fonte de dados.
   * Selecione uma regra de mesclagem de perfil a ser usada para a qualificação de segmentos.
   * Atribua o segmento a uma pasta de armazenamento.
1. In the [Traits](../../features/segments/segment-builder.md#segment-builder-controls-traits) section:
   * Search for the trait you want to add to a segment and click **[!UICONTROL Add Trait]**. Adicione outra característica para criar um grupo de características.
   * Bring up the Advanced Search modal by clicking **[!UICONTROL Browse All Traits]**. Pesquise por características por nome, ID, descrição ou fonte de dados. Clique em uma pasta ao pesquisar para limitar os resultados a essa pasta e suas subpastas. Também é possível filtrar características por tipo de característica.
   * Get live [trait recommendations](trait-recommendations.md) as you build your segment.
   * Clique e arraste características para criar grupos separados.
   * Hover between groups to set relationships with Boolean [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] values.
   * Hover over the clock icon to add [recency and frequency](../../features/segments/recency-and-frequency.md) rules to the trait.
   * Exiba dados de preenchimento de segmentos à medida que você adiciona ou remove características. Click **[!UICONTROL Calculate Estimates]** to see (or refresh) the estimated population numbers. Read more about [segment population data](../../features/segments/segment-builder-data.md#segment-populations) in the Segment Builder.
   * Click **[!UICONTROL Save]** when done.
1. *(Opcional)* Mapeie um segmento para um destino na [seção Mapeamento](../../features/segments/segment-builder.md#segment-builder-controls-destinations) de destino:
   * Search for the destination and click **[!UICONTROL Add Destination]**. Observe que o destino já deve existir antes que você possa adicioná-lo a um segmento.
   * Click **[!UICONTROL Save]** when done.

## Segment Builder Controls: Basic Information Section {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] settings let you create new, or edit existing traits. Para criar um novo segmento, forneça um nome, uma fonte de dados e selecione uma pasta de armazenamento. Todos os outros campos são opcionais. Move on to the [!UICONTROL Traits] section when done.

<!-- r_segment_basic_info_section.xml -->

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Nome</b> </td> 
   <td colname="col2"> <p>Dê ao segmento um nome curto e lógico que descreva sua função ou finalidade. Evite abreviações e caracteres especiais. O tamanho máximo de um nome de segmento é de 255 caracteres. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Descrição</b> </td> 
   <td colname="col2"> <p>Um campo para obter informações descritivas adicionais sobre o segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Código de integração</b> </td> 
   <td colname="col2"> <p>Um campo para uma ID definida pelo usuário ou outras informações específicas da empresa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fonte de dados</b> </td> 
   <td colname="col2"> <p>Associa o segmento a um provedor de dados específico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Regra de mesclagem de perfil</b> </td> 
   <td colname="col2"> <p>Seleciona a Regra de mesclagem de perfil a ser usada para a qualificação de segmentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Ativa ou desativa o segmento (ativo por padrão). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Armazenamento da pasta</b> </td> 
   <td colname="col2"> <p>Determina a pasta de armazenamento à qual o segmento pertence. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segment Builder Controls: Traits Section {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder], the [!UICONTROL Traits] section lets you manage traits in a segment, create trait groups, and set qualification criteria. To add a trait to a segment, type the trait name in the search field and click [!UICONTROL Add Trait]. Save the trait (if finished) or move on to [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml -->

**Pré-requisitos:** Preencha os campos obrigatórios na [!UICONTROL Basic Information] seção.

| Campo | Descrição |
|--- |--- |
| Exibição básica | Esta seção fornece controles visuais que permitem: <ul><li>Crie novos e gerenciar segmentos existentes.</li><li>Remova características de um segmento.</li><li>Adiciona até 50 características (máximo) a um segmento.</li><li>Arraste e solte características para criar novos grupos.</li><li>Exibir características e grupos de características em um segmento.</li><li>Defina critérios de qualificação com expressões Booleanas, operadores de comparação e configurações de recenticidade/frequência.</li></ul> |
| Exibição de código | Abre um ambiente de desenvolvimento que permite criar e gerenciar características, grupos e requisitos de qualificação com código em vez da interface visual. A exibição de código é útil se os segmentos: <ul><li>Contém mais de 50 características em um segmento individual. Observação: Os segmentos são limitados a 5000 características (máximo).</li><li>Contiver muitos grupos de características.</li><li>Tenha requisitos de qualificação complexos.</li></ul> |
| Pesquisar | Ajuda a encontrar características a serem adicionadas a um segmento. |
| Recomendações   | Obtenha recomendações ao vivo para características similares a serem adicionadas à regra de segmento. Read more in [Trait Recommendations](trait-recommendations.md). |
| Dados de tamanho do segmento real e estimado | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Remove Traits from a Segment {#remove-traits}

Gerenciar as características em seus segmentos é uma parte importante da manutenção de segmentos viáveis. Siga estas etapas se precisar remover características de um segmento.

Para remover características de um segmento:

1. Go to **Audience Data &gt; Segments**. Role pela lista ou use o recurso de pesquisa para encontrar o segmento com o qual deseja trabalhar.
2. Clique no nome do segmento para abrir a tela de detalhes do segmento.
3. Click **Edit** to open Segment Builder and then click **Traits** to open the traits panel.
4. Passe o mouse sobre a característica que deseja excluir e clique no X. Essa ação remove imediatamente a característica do seu segmento.

## Segment Builder Controls: Destinations Mappings Section {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder], the optional [!UICONTROL Destinations Mapping] section lets you send segment data to a third-party [!DNL cookie], [!DNL URL], or server-to-server destination. To add a destination, search (or browse) for a destination, provide destination specific information, and click **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Pré-requisitos

Complete the required fields in the [!UICONTROL Basic Information] and [!UICONTROL Traits] sections. Além disso, o destino já deve existir.

### Ferramentas de pesquisa de mapeamentos de destino

**[!UICONTROL Destination Mappings]** O painel contém ferramentas de pesquisa conforme descrito na tabela abaixo.

| Tipo de pesquisa | Descrição |
|---|---|
| **Pesquisar por nome de destino** | Permite pesquisar por um destino específico por nome. Para pesquisar, comece a digitar. O campo será preenchido automaticamente com base nos seus termos de pesquisa. Click **[!UICONTROL Add Destination]** when done. |
| **Procurar todos os destinos** | Browse a list of *all* destinations available to you. Selecione e adicione destinos ao seu segmento na lista pop-up. |

## Fields in the Destination Mappings Pop-up Windows {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder], the [!UICONTROL Add Destination] dialog appears after you select a destination. Essa janela exibe informações estáticas sobre o destino e os campos que variam dependendo do tipo de destino. Forneça as informações necessárias nos campos vazios para configurar um mapeamento de destino.

>[!NOTE]
>
>As datas de publicação são opcionais. Quando em branco, o destino fica ativo e nunca expira.

<!-- r_add_mappings_pop.xml -->

### Campos de destino do cookie

In the [!UICONTROL Destination Mapping] fields, specify the key-value pairs used to send data to the destination. Insira a chave no primeiro campo e os valores no segundo. O destino do seu cookie pop-up pode ser semelhante a isto:

![](assets/cookie_modal.PNG)

### Campos de destino de URL

In the [!UICONTROL URL] and [!UICONTROL Secure URL] fields, specify the complete standard or secure address used to send data to the destination.

![](assets/url_modal.PNG)

### Campos de destino de servidor a servidor

In the [!UICONTROL Destination Value] field specify the value (part of a key-value pair) used to send data to the destination.

![](assets/s2s_modal.PNG)

>[!MORE_ LIKE_ THIS]
>
>* [Criar um destino do cookie](../../features/destinations/manage-destinations.md#create-cookie-destination)
>* [Criar um destino de URL](../../features/destinations/manage-destinations.md#configure-url-destination)

