---
description: O Audience Analytics permite enviar segmentos do Audience Manager para o Analytics. Para usar esse recurso, crie um destino do Analytics e mapeie os segmentos a ele no Audience Manager.
seo-description: O Audience Analytics permite enviar segmentos do Audience Manager para o Analytics. Para usar esse recurso, crie um destino do Analytics e mapeie os segmentos a ele no Audience Manager.
seo-title: Configurar um destino do Analytics
solution: Audience Manager
title: Configurar um destino do Analytics
translation-type: tm+mt
source-git-commit: 3179b9007e102f7031cc4cc9e0da64f77cfa3eeb

---


# Configurar um destino do Analytics

## Exigências {#requirements}

See [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## Seu destino padrão do Analytics e novos destinos do Analytics

| Tipo de destino do Analytics | Descrição |
|---|---|
| Padrão | O nome desse destino padrão é &quot;Adobe Analytics&quot;, que pode ser editado. IDs de conjuntos de relatórios mapeados aparecem no armazenamento de pastas para as características e segmentos do Audience Manager. <br>O Audience Manager cria um destino automaticamente se sua conta tiver: <br> <ul><li>Met the requirements described in the [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) documentation.</li><li>A [report suite](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) in Analytics.</li><li>[Um conjunto de relatórios foi mapeado para uma organização](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).</li></ul> |
| Novo | Para criar novos destinos do Analytics, vá para Dados do público-alvo &gt; Destinos &gt; Criar novo destino e siga as etapas para cada seção descrita abaixo. |

## Etapa 1: Fornecer informações básicas

Esta seção contém campos e opções que iniciam o processo de criação de destino do Analytics. Para concluir esta seção:

1. Click **Basic Information** to expose the controls.
2. Dê um nome ao destino. Evite abreviações e caracteres especiais.
3. *(Opcional)* Descreva o destino. Uma descrição concisa é uma maneira eficaz de definir ou fornecer mais informações sobre um destino.
4. *(Opcional)* Na lista **Plataforma** , deixe o padrão definido como **Todos**. Atualmente, essas opções não fazem nada. Eles são projetados para suportar recursos que podem ser adicionados em uma data posterior.
5. In the **Category** list, select **Adobe Experience Cloud**.
6. In the **Type** list, select **Adobe Analytics**.
7. Click **Save** to go to the Configuration settings or click **Data Export Labels** to apply export controls to the destination.

>[!NOTE]
>
>For an Analytics destination, the **Auto-fill Destination Mappping** check box and **Segment ID** option are selected by default. Não é possível alterar essas configurações.

![basicinformation](assets/basicinformation.png)

## Etapa 2: Configurar controles de exportação de dados

This section contains options that apply [Data Export Controls](/help/using/features/data-export-controls.md) to an Analytics destination. Pule esta etapa se você não usar controles de exportação de dados. Para concluir esta seção:

1. Click **Data Export Controls** to expose the controls.
2. Select a label that corresponds to the data export control applied to the destination (see [Add Data Export Labels to a Destination](/help/using/features/destinations/manage-destinations.md#add-data-export-labels) ). Para destinos do Analytics, a caixa de seleção PII é selecionada por padrão.
3. Clique em **Salvar**.

![exportcontrols](assets/exportControls.png)

## Etapa 3: Mapear conjuntos de relatórios

A seção Configuração lista os Conjuntos de relatórios do Analytics que foram ativados para encaminhamento pelo lado do servidor. Se houver vários destinos do Analytics, os conjuntos de relatórios atribuídos a esses destinos serão mutuamente exclusivos e aplicados pelo Audience Manager. Para concluir esta seção:

1. Click **Configuration** to expose the controls.
2. Selecione um ou mais conjuntos de relatórios para os quais você deseja enviar segmentos.
3. Clique em **Salvar**.

![reportsuites](assets/reportSuites.png)

## Etapa 4: Mapeamentos de segmento

Esta seção fornece opções que permitem mapear segmentos automaticamente ou manualmente.

| Opção de mapeamento | Descrição |
|---|---|
| Mapear automaticamente todos os segmentos atuais e futuros | Selecionado por padrão, esse recurso envia todos os segmentos para os quais um visitante é classificado, em uma base por ocorrência, para o Analytics. <br>Se um visitante pertencer a mais de 150 segmentos do Audience Manager em uma única ocorrência, apenas os segments 50 segmentos qualificados mais recentemente serão enviados para o Analytics, enquanto a lista restante será truncada. Um sinalizador adicional é enviado para o Analytics, indicando que a lista de segmentos truncada. Esta ação é exibida como «Limite de público-alvo atingido» na dimensão Nome do público-alvo e «1» na dimensão ID de públicos-alvo. See the [FAQ](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) for details. <br>Além disso, essa opção afeta a disponibilidade de destino no [Construtor](/help/using/features/segments/segment-builder.md)de segmentos. For example, if a segment is mapped automatically to an Analytics destination, that destination is not available for selection in the [destination mappings](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) section of Segment Builder. O destino do Analytics aparece esmaecido e mostra &quot;Analytics&quot; na coluna Tipo do navegador Destino. |
| Mapear segmentos manualmente | Esta opção expõe controles de pesquisa e navegação que permitem escolher os segmentos que você deseja enviar para o Analytics. <br>Para pesquisar um segmento: <br> <ol><li>Digite o nome ou ID do segmento no campo de pesquisa.</li><li>Clique em <b>Adicionar.</b></li><li>Continue to search and add segments or click <b>Done</b>.</li></ol><br>Para procurar um segmento: <ol><li>Click <b>Browse all segments</b>. Isso expõe uma lista de segmentos disponíveis.</li><li>From the list, select the check box of the segment you want to use and click <b>Add selected segments</b>.</li><li>Click <b>Save</b> in the Add Mappings window. Não é possível alterar os mapeamentos, as datas de início ou término durante a versão beta.</li><li>Continue to browse and add segments or click <b>Done</b>.</li></ol> |

![mapeamentos](assets/mapSegments.png)

## Próximas etapas

Depois de criar e salvar um destino, você pode trabalhar com esses dados no Analytics. No entanto, pode levar algumas horas até que os dados estejam disponíveis nos conjuntos de relatórios selecionados. See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).



