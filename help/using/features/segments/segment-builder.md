---
description: Descreve como criar segmentos com o Construtor de segmentos.
seo-description: Descreve como criar segmentos com o Construtor de segmentos.
seo-title: Construtor de segmentos
solution: Audience Manager
title: Construtor de segmentos
uuid: 5 ca 924 a 5-2 b 29-4802-ab 02-e 292 d 77 a 0 aae
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Construtor de segmentos {#segment-builder}

Descreve as etapas obrigatórias e opcionais que criam um segmento.[!UICONTROL Segment Builder]

## Criar um segmento {#create-segment}

### Seção do Construtor de segmento

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] consiste em 3 seções separadas: [!UICONTROL Basic Information], [!UICONTROL Traits]e [!UICONTROL Destinations Mapping]. Para criar um segmento, preencha os campos obrigatórios nas seções [!UICONTROL Basic Information] e [!UICONTROL Traits] seções. [!UICONTROL Destinations Mapping] são opcionais. Consulte as instruções abaixo para obter ajuda adicional.

1. Na seção [Informações](../../features/segments/segment-builder.md#segment-builder-controls-basics) básicas:
   * Nomeie o segmento. O tamanho máximo de um nome de segmento é de 255 caracteres.
   * Defina o status do segmento (ativo é padrão).
   * Escolha uma fonte de dados.
   * Selecione uma regra de mesclagem de perfil a ser usada para a qualificação de segmentos.
   * Atribua o segmento a uma pasta de armazenamento.
1. Na seção [Características](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   * Pesquise pela característica que deseja adicionar a um segmento e clique **[!UICONTROL Add Trait]** em. Adicione outra característica para criar um grupo de características.
   * Abra o modal Pesquisa avançada clicando **[!UICONTROL Browse All Traits]** em. Pesquise por características por nome, ID, descrição ou fonte de dados. Clique em uma pasta ao pesquisar para limitar os resultados a essa pasta e suas subpastas. Também é possível filtrar características por tipo de característica.
   * Obtenha recomendações [de características ao vivo](trait-recommendations.md) à medida que você cria seu segmento.
   * Clique e arraste características para criar grupos separados.
   * Passe o mouse entre grupos para definir relacionamentos com booleano [!UICONTROL AND], [!UICONTROL OR][!UICONTROL AND NOT] valores.
   * Passe o mouse sobre o ícone de relógio para adicionar [regras de recenticidade e frequência](../../features/segments/recency-and-frequency.md) à característica.
   * Exiba dados de preenchimento de segmentos à medida que você adiciona ou remove características. Clique **[!UICONTROL Calculate Estimates]** para ver (ou atualizar) os números de população estimados. Leia mais sobre [os dados de preenchimento de segmentos](../../features/segments/segment-builder-data.md#segment-populations) no Construtor de segmentos.
   * Click **[!UICONTROL Save]** when done.
1. *(Opcional)* Mapeie um segmento para um destino na [seção Mapeamento](../../features/segments/segment-builder.md#segment-builder-controls-destinations) de destino:
   * Procure pelo destino e clique **[!UICONTROL Add Destination]** em. Observe que o destino já deve existir antes que você possa adicioná-lo a um segmento.
   * Click **[!UICONTROL Save]** when done.

## Controles do Construtor de segmento: Seção de informações básicas {#segment-builder-controls-basics}

Em [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] as configurações permitem criar novos ou editar já existentes. Para criar um novo segmento, forneça um nome, uma fonte de dados e selecione uma pasta de armazenamento. Todos os outros campos são opcionais. Passe para a [!UICONTROL Traits] seção quando terminar.

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

## Controles do Construtor de segmento: Seção de características {#segment-builder-controls-traits}

Em [!UICONTROL Segment Builder], a [!UICONTROL Traits] seção permite gerenciar características em um segmento, criar grupos de características e definir critérios de qualificação. Para adicionar uma característica a um segmento, digite o nome de características no campo de pesquisa e clique [!UICONTROL Add Trait]em. Salve a característica (se concluída) ou prossiga [!UICONTROL Destinations Mapping]para.

<!-- r_segment_traits_section.xml -->

**Pré-requisitos:** Preencha os campos obrigatórios na [!UICONTROL Basic Information] seção.

| Campo | Descrição |
|--- |--- |
| Exibição básica | Esta seção fornece controles visuais que permitem: <ul><li>Crie novos e gerenciar segmentos existentes.</li><li>Remova características de um segmento.</li><li>Adiciona até 50 características (máximo) a um segmento.</li><li>Arraste e solte características para criar novos grupos.</li><li>Exibir características e grupos de características em um segmento.</li><li>Defina critérios de qualificação com expressões Booleanas, operadores de comparação e configurações de recenticidade/frequência.</li></ul> |
| Exibição de código | Abre um ambiente de desenvolvimento que permite criar e gerenciar características, grupos e requisitos de qualificação com código em vez da interface visual. A exibição de código é útil se os segmentos: <ul><li>Contém mais de 50 características em um segmento individual. Observação: Os segmentos são limitados a 5000 características (máximo).</li><li>Contiver muitos grupos de características.</li><li>Tenha requisitos de qualificação complexos.</li></ul> |
| Pesquisar | Ajuda a encontrar características a serem adicionadas a um segmento. |
| Recomendações   | Obtenha recomendações ao vivo para características similares a serem adicionadas à regra de segmento. Leia mais em [Recomendações de características](trait-recommendations.md). |
| Dados de tamanho do segmento real e estimado | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Remover características de um segmento {#remove-traits}

Gerenciar as características em seus segmentos é uma parte importante da manutenção de segmentos viáveis. Siga estas etapas se precisar remover características de um segmento.

Para remover características de um segmento:

1. Acesse Dados **de público-alvo &gt; Segmentos**. Role pela lista ou use o recurso de pesquisa para encontrar o segmento com o qual deseja trabalhar.
2. Clique no nome do segmento para abrir a tela de detalhes do segmento.
3. Clique **em Editar** para abrir o Construtor de segmentos e clique **em Características** para abrir o painel Características.
4. Passe o mouse sobre a característica que deseja excluir e clique no X. Essa ação remove imediatamente a característica do seu segmento.

## Controles do Construtor de segmento: Seção de mapeamentos de destinos {#segment-builder-controls-destinations}

Em [!UICONTROL Segment Builder], a seção opcional [!UICONTROL Destinations Mapping] permite enviar dados de segmento para um destino de terceiros [!DNL cookie], [!DNL URL]ou de servidor para servidor. Para adicionar um destino, pesquise (ou procure) um destino, forneça informações específicas de destino e clique **[!UICONTROL Add Destination]** em.

<!-- r_segment_destinations_map.xml -->

### Pré-requisitos

Preencha os campos obrigatórios nas seções [!UICONTROL Basic Information] e [!UICONTROL Traits] seções. Além disso, o destino já deve existir.

### Ferramentas de pesquisa de mapeamentos de destino

**[!UICONTROL Destination Mappings]** O painel contém ferramentas de pesquisa conforme descrito na tabela abaixo.

| Tipo de pesquisa | Descrição |
|---|---|
| **Pesquisar por nome de destino** | Permite pesquisar por um destino específico por nome. Para pesquisar, comece a digitar. O campo será preenchido automaticamente com base nos seus termos de pesquisa. Click **[!UICONTROL Add Destination]** when done. |
| **Procurar todos os destinos** | Navegue por uma lista de *todos* os destinos disponíveis para você. Selecione e adicione destinos ao seu segmento na lista pop-up. |

## Campos nos pop-up pop-up de Mapeamentos de destino {#fields-in-dest-mappings}

No [!UICONTROL Segment Builder], a [!UICONTROL Add Destination] caixa de diálogo aparece depois de selecionar um destino. Essa janela exibe informações estáticas sobre o destino e os campos que variam dependendo do tipo de destino. Forneça as informações necessárias nos campos vazios para configurar um mapeamento de destino.

>[!NOTE]
>
>As datas de publicação são opcionais. Quando em branco, o destino fica ativo e nunca expira.

<!-- r_add_mappings_pop.xml -->

### Campos de destino do cookie

Nos [!UICONTROL Destination Mapping] campos, especifique os pares de valores chave usados para enviar dados para o destino. Insira a chave no primeiro campo e os valores no segundo. O destino do seu cookie pop-up pode ser semelhante a isto:

![](assets/cookie_modal.PNG)

### Campos de destino de URL

Nos campos [!UICONTROL URL] e [!UICONTROL Secure URL] campos, especifique o endereço padrão ou seguro completo usado para enviar dados para o destino.

![](assets/url_modal.PNG)

### Campos de destino de servidor a servidor

No [!UICONTROL Destination Value] campo, especifique o valor (parte de um par de valor chave) usado para enviar dados para o destino.

![](assets/s2s_modal.PNG)

>[!MORE_ LIKE_ THIS]
>
>* [Criar um destino do cookie](../../features/destinations/create-cookie-destination.md)
>* [Criar um destino de URL](../../features/destinations/create-url-destination.md)

