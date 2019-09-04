---
description: O Audience Analytics permite enviar segmentos do Audience Manager para o Analytics. Para usar esse recurso, crie um destino do Analytics e mapeie os segmentos a ele no Audience Manager.
seo-description: O Audience Analytics permite enviar segmentos do Audience Manager para o Analytics. Para usar esse recurso, crie um destino do Analytics e mapeie os segmentos a ele no Audience Manager.
seo-title: Configurar um destino do Analytics
solution: Audience Manager
title: Configurar um destino do Analytics
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Configurar um destino do Analytics

## Exigências {#requirements}

Consulte [Análise de público-alvo](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## Seu destino padrão do Analytics e novos destinos do Analytics

| Tipo de destino do Analytics | Descrição |
|---|---|
| Padrão | O nome desse destino padrão é "Adobe Analytics", que pode ser editado. IDs de conjuntos de relatórios mapeados aparecem no armazenamento de pastas para as características e segmentos do Audience Manager. <br>O Audience Manager cria um destino automaticamente se sua conta tiver: <br> <ul><li>Atende aos requisitos descritos na documentação [do Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) .</li><li>Um [conjunto de relatórios](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) no Analytics.</li><li>[Um conjunto de relatórios foi mapeado para uma organização](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).</li></ul> |
| Novo | Para criar novos destinos do Analytics, vá para Dados do público-alvo &gt; Destinos &gt; Criar novo destino e siga as etapas para cada seção descrita abaixo. |

## Etapa 1: Fornecer informações básicas

Esta seção contém campos e opções que iniciam o processo de criação de destino do Analytics. Para concluir esta seção:

1. Clique **em Informações básicas** para expor os controles.
1. Dê um nome ao destino. Evite abreviações e caracteres especiais.
1. *(Opcional)* Descreva o destino. Uma descrição concisa é uma maneira eficaz de definir ou fornecer mais informações sobre um destino.
1. *(Opcional)* Na lista **Plataforma** , deixe o padrão definido como **Todos**. Atualmente, essas opções não fazem nada. Eles são projetados para suportar recursos que podem ser adicionados em uma data posterior.
1. Na lista **Categoria** , selecione **Adobe Experience Cloud**.
1. Na lista **Tipo** , selecione **Adobe Analytics**.
1. Clique **em Salvar** para ir para as configurações de Configuração ou clique **em Rótulos de exportação de dados** para aplicar controles de exportação ao destino.

>[!NOTE]
>
>Para um destino do Analytics, a caixa **de seleção Preencher automaticamente mapeamento** de destino e **a** opção ID do segmento são selecionadas por padrão. Não é possível alterar essas configurações.

![basicinformation](assets/basicinformation.png)

## Etapa 2: Configurar controles de exportação de dados

Esta seção contém opções que aplicam [Controles de exportação de dados](/help/using/features/data-export-controls.md) a um destino do Analytics. Pule esta etapa se você não usar controles de exportação de dados. Para concluir esta seção:

1. Clique **em Controles de exportação de dados** para expor os controles.
1. Selecione uma etiqueta que corresponda ao controle de exportação de dados aplicado ao destino (consulte [Adicionar rótulos de exportação de dados a um destino](/help/using/features/destinations/add-data-export-labels.md) ). Para destinos do Analytics, a caixa de seleção PII é selecionada por padrão.
1. Clique em **Salvar**.

![exportcontrols](assets/exportControls.png)

## Etapa 3: Mapear conjuntos de relatórios

A seção Configuração lista os Conjuntos de relatórios do Analytics que foram ativados para encaminhamento pelo lado do servidor. Se houver vários destinos do Analytics, os conjuntos de relatórios atribuídos a esses destinos serão mutuamente exclusivos e aplicados pelo Audience Manager. Para concluir esta seção:

1. Clique **em Configuração** para expor os controles.
1. Selecione um ou mais conjuntos de relatórios para os quais você deseja enviar segmentos.
1. Clique em **Salvar**.

![reportsuites](assets/reportSuites.png)

## Etapa 4: Mapeamentos de segmento

Esta seção fornece opções que permitem mapear segmentos automaticamente ou manualmente.

| Opção de mapeamento | Descrição |
|---|---|
| Mapear automaticamente todos os segmentos atuais e futuros | Selecionado por padrão, esse recurso envia todos os segmentos para os quais um visitante é classificado, em uma base por ocorrência, para o Analytics. <br>Se um visitante pertencer a mais de 150 segmentos do Audience Manager em uma única ocorrência, apenas os segments 50 segmentos qualificados mais recentemente serão enviados para o Analytics, enquanto a lista restante será truncada. Um sinalizador adicional é enviado para o Analytics, indicando que a lista de segmentos truncada. Esta ação é exibida como «Limite de público-alvo atingido» na dimensão Nome do público-alvo e «1» na dimensão ID de públicos-alvo. Consulte [as Perguntas frequentes](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) para obter detalhes. <br>Além disso, essa opção afeta a disponibilidade de destino no [Construtor](/help/using/features/segments/segment-builder.md)de segmentos. Por exemplo, se um segmento é mapeado automaticamente para um destino do Analytics, esse destino não está disponível para seleção na seção [de mapeamentos](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) de destino do Construtor de segmentos. O destino do Analytics aparece esmaecido e mostra "Analytics" na coluna Tipo do navegador Destino. |
| Mapear segmentos manualmente | Esta opção expõe controles de pesquisa e navegação que permitem escolher os segmentos que você deseja enviar para o Analytics. <br>Para pesquisar um segmento: <br> <ol><li>Digite o nome ou ID do segmento no campo de pesquisa.</li><li>Clique em <b>Adicionar.</b></li><li>Continue a pesquisar e adicionar segmentos ou clique <b>em Concluído</b>.</li></ol><br>Para procurar um segmento: <ol><li>Clique em <b>Procurar todos os segmentos</b>. Isso expõe uma lista de segmentos disponíveis.</li><li>Na lista, marque a caixa de seleção do segmento que deseja usar e clique <b>em Adicionar segmentos selecionados</b>.</li><li>Clique <b>em Salvar</b> na janela Adicionar mapeamentos. Não é possível alterar os mapeamentos, as datas de início ou término durante a versão beta.</li><li>Continue a navegar e adicionar segmentos ou clique <b>em Concluído</b>.</li></ol> ![mapeamentos](assets/mapSegments.png) |

## Próximas etapas

Depois de criar e salvar um destino, você pode trabalhar com esses dados no Analytics. No entanto, pode levar algumas horas até que os dados estejam disponíveis nos conjuntos de relatórios selecionados. See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).
