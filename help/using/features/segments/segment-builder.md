---
description: Descreve como criar segmentos com o Construtor de segmentos.
seo-description: Descreve como criar segmentos com o Construtor de segmentos.
seo-title: Construtor de segmentos
solution: Audience Manager
title: Construtor de segmentos
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
translation-type: tm+mt
source-git-commit: 9215942bd33af0eabf5143e52edcb249d4ca2cac

---


# Construtor de segmentos {#segment-builder}

Descreve as etapas necessárias e opcionais que criam um segmento em [!UICONTROL Segment Builder].

## Demonstração de vídeo

Comece assistindo ao vídeo [](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)Criar segmentos no Audience Manager. O vídeo o orienta pelo processo de criação do segmento. Leia as seções abaixo para obter mais informações.

## Criar um segmento {#create-segment}

### Seção do Construtor de segmentos

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] consiste em 3 seções separadas: [!UICONTROL Basic Information], [!UICONTROL Traits]e [!UICONTROL Destinations Mapping]. Para criar um segmento, preencha os campos obrigatórios nas seções [!UICONTROL Basic Information] e [!UICONTROL Traits] . [!UICONTROL Destinations Mapping] são opcionais. Consulte as instruções abaixo para obter ajuda adicional.

![create-segment](assets/create-segment.png)

1. Na seção Informações [](../../features/segments/segment-builder.md#segment-builder-controls-basics) básicas:
   * Nomeie o segmento. O comprimento máximo de um nome de segmento é de 255 caracteres.
   * Defina o status do segmento (ativo é padrão).
   * Escolha uma fonte de dados. Use o primeiro menu suspenso para filtrar entre as fontes de dados do Audience Manager, os conjuntos de relatórios do Adobe Analytics ou ambos. Em seguida, use o segundo menu suspenso para escolher sua fonte de dados. Se você não estiver usando os conjuntos de relatórios do Adobe Analytics, o seletor de tipo de fonte de dados será desativado e o padrão será usado somente nas fontes de dados do Audience Manager.
   * Selecione uma regra de mesclagem de perfil a ser usada para qualificação de segmento.
   * Atribua o segmento a uma pasta de armazenamento.
2. Na [seção Características](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   * Procure a característica que deseja adicionar a um segmento e clique em **[!UICONTROL Add Trait]**. Adicione outra característica para criar um grupo de características.
   * Abra o modal Pesquisa avançada clicando em **[!UICONTROL Browse All Traits]**. Procure características por nome, ID, descrição ou fonte de dados. Clique em uma pasta enquanto pesquisa para limitar os resultados a essa pasta e suas subpastas. Você também pode filtrar características por tipo de característica.
   * Obtenha recomendações [de](trait-recommendations.md) características ao vivo enquanto cria seu segmento.
   * Clique e arraste características para criar grupos separados.
   * Passe o cursor do mouse sobre os grupos para definir relações com valores Booleanos [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] .
   * Passe o mouse sobre o ícone do relógio para adicionar regras de [recenticidade e frequência](../../features/segments/recency-and-frequency.md) à característica.
   * Exibir dados de preenchimento do segmento à medida que você adiciona ou remove características. Clique **[!UICONTROL Calculate Estimates]** para ver (ou atualizar) os números de população estimados. Leia mais sobre os dados [de preenchimento do](../../features/segments/segment-builder-data.md#segment-populations) segmento no Construtor de segmentos.
   * Click **[!UICONTROL Save]** when done.
3. *(Opcional)* Mapeie um segmento para um destino na seção Mapeamento [de](../../features/segments/segment-builder.md#segment-builder-controls-destinations) destino:
   * Procure o destino e clique em **[!UICONTROL Add Destination]**. Observe que o destino já deve existir antes que você possa adicioná-lo a um segmento.
   * Click **[!UICONTROL Save]** when done.

## Controles do Construtor de segmentos: Seção Informações básicas {#segment-builder-controls-basics}

Em [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] as configurações permitem criar características novas ou editar características existentes. Para criar um novo segmento, forneça um nome, uma fonte de dados e selecione uma pasta de armazenamento. Todos os outros campos são opcionais. Vá para a [!UICONTROL Traits] seção quando terminar.

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
   <td colname="col2"> <p>Dê ao segmento um nome curto e lógico que descreva sua função ou finalidade. Evite abreviações e caracteres especiais. O comprimento máximo de um nome de segmento é de 255 caracteres. </p> </td> 
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
   <td colname="col2"> <p>Associa o segmento a um provedor de dados específico. <p>Use o primeiro menu suspenso para filtrar entre as fontes de dados do Audience Manager, os conjuntos de relatórios do Adobe Analytics ou ambos. Em seguida, use o segundo menu suspenso para escolher sua fonte de dados.</p><p> Se você não estiver usando os conjuntos de relatórios do Adobe Analytics, o seletor de tipo de fonte de dados será desativado e o padrão será usado somente nas fontes de dados do Audience Manager.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Regra de mesclagem de perfil</b> </td> 
   <td colname="col2"> <p>Seleciona a Regra de mesclagem de perfil a ser usada para qualificação de segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Ativa ou desativa o segmento (ativo por padrão). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Armazenamento de pasta</b> </td> 
   <td colname="col2"> <p>Determina a pasta de armazenamento à qual o segmento pertence. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Controles do Construtor de segmentos: Seção Características {#segment-builder-controls-traits}

Em [!UICONTROL Segment Builder], a [!UICONTROL Traits] seção permite gerenciar características em um segmento, criar grupos de características e definir critérios de qualificação. Para adicionar uma característica a um segmento, digite o nome da característica no campo de pesquisa e clique em [!UICONTROL Add Trait]. Salve a característica (se concluída) ou vá para [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml -->

**** Pré-requisitos: Preencha os campos obrigatórios na [!UICONTROL Basic Information] seção.

| Campo | Descrição |
|--- |--- |
| Exibição básica | Esta seção fornece controles visuais que permitem: <ul><li>Crie novos segmentos e gerencie os existentes.</li><li>Remova características de um segmento.</li><li>Adicione até 50 (máximo) características a um segmento.</li><li>Arraste e solte características para criar novos grupos.</li><li>Exibir características e grupos de características em um segmento.</li><li>Defina os critérios de qualificação com expressões booleanas, operadores de comparação e configurações de recenticidade/frequência.</li></ul> |
| Exibição de código | Abre um ambiente de desenvolvimento que permite criar e gerenciar características, grupos e requisitos de qualificação com código em vez da interface visual. A visualização de código é útil se seus segmentos: <ul><li>Contêm mais de 50 características em um segmento individual. Observação: Os segmentos são limitados a 5000 características (máximo).</li><li>Contém muitos grupos de características.</li><li>Ter requisitos de qualificação complexos.</li></ul> |
| Pesquisar | Ajuda a encontrar características a serem adicionadas a um segmento. |
| Recomendações   | Obtenha recomendações ao vivo para características semelhantes a serem adicionadas à regra de segmento. Leia mais no [Trait Recommendations](trait-recommendations.md). |
| Dados reais e estimados do tamanho do segmento | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Remover características de um segmento {#remove-traits}

O gerenciamento das características em seus segmentos é uma parte importante para manter os segmentos viáveis. Siga estas etapas se precisar remover características de um segmento.

Para remover características de um segmento:

1. Vá para Dados de **público-alvo &gt; Segmentos**. Role pela lista ou use o recurso de pesquisa para encontrar o segmento com o qual você deseja trabalhar.
2. Clique no nome do segmento para abrir a tela de detalhes do segmento.
3. Clique em **Editar** para abrir o Construtor de segmentos e clique em **Características** para abrir o painel Características.
4. Passe o mouse sobre a característica que deseja excluir e clique no X. Essa ação remove imediatamente a característica do seu segmento.

## Controles do Construtor de segmentos: Seção Mapeamentos de Destinos {#segment-builder-controls-destinations}

Em [!UICONTROL Segment Builder], a [!UICONTROL Destinations Mapping] seção opcional permite enviar dados de segmento para um destino de terceiros [!DNL cookie], [!DNL URL]ou servidor para servidor. Para adicionar um destino, pesquise (ou navegue) por um destino, forneça informações específicas do destino e clique em **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Pré-requisitos

Preencha os campos obrigatórios nas seções [!UICONTROL Basic Information] e [!UICONTROL Traits] . Além disso, o destino já deve existir.

### Mapeamentos de Destino Ferramentas de Pesquisa

O **[!UICONTROL Destination Mappings]** painel contém ferramentas de pesquisa, conforme descrito na tabela abaixo.

| Tipo de pesquisa | Descrição |
|---|---|
| **Pesquisar por nome de destino** | Permite que você procure um destino específico por nome. Para pesquisar, comece a digitar. O campo será preenchido automaticamente com base em seus termos de pesquisa. Click **[!UICONTROL Add Destination]** when done. |
| **Procurar todos os destinos** | Procure uma lista de *todos* os destinos disponíveis para você. Selecione e adicione destinos ao seu segmento na lista suspensa. |

## Campos nas janelas pop-up Mapeamentos de destino {#fields-in-dest-mappings}

Em [!UICONTROL Segment Builder], a caixa de [!UICONTROL Add Destination] diálogo é exibida depois que você seleciona um destino. Essa janela exibe informações estáticas sobre o destino e os campos que variam dependendo do tipo de destino. Forneça as informações necessárias nos campos vazios para configurar um mapeamento de destino.

>[!NOTE]
>
>As datas de publicação são opcionais. Quando em branco, o destino fica ativo e nunca expira.

<!-- r_add_mappings_pop.xml -->

### Campos de destino de cookie

Nos [!UICONTROL Destination Mapping] campos, especifique os pares de valores chave usados para enviar dados para o destino. Insira a chave no primeiro campo e os valores no segundo. O pop-up de destino do cookie pode ser semelhante a este:

![](assets/cookie_modal.PNG)

### Campos de destino do URL

Nos campos [!UICONTROL URL] e [!UICONTROL Secure URL] , especifique o endereço completo padrão ou seguro usado para enviar dados para o destino.

![](assets/url_modal.PNG)

### Campos de destino de servidor para servidor

No [!UICONTROL Destination Value] campo, especifique o valor (parte de um par de valores chave) usado para enviar dados para o destino.

![](assets/s2s_modal.PNG)

>[!MORE_LIKE_THIS]
>
>* [Criar um destino de cookie](../../features/destinations/create-cookie-destination.md)
>* [Criar um destino de URL](../../features/destinations/create-url-destination.md)

