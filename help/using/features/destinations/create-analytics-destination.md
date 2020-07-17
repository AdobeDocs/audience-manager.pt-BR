---
description: O Audience Analytics permite enviar segmentos do Audience Manager para o Analytics. Para usar esse recurso, crie um destino do Analytics e mapeie os segmentos a ele no Audience Manager.
seo-description: O Audience Analytics permite enviar segmentos do Audience Manager para o Analytics. Para usar esse recurso, crie um destino do Analytics e mapeie os segmentos a ele no Audience Manager.
seo-title: Configurar um destino do Analytics
solution: Audience Manager
title: Configurar um destino do Analytics
feature: Integration with Analytics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 9%

---


# Configurar um destino do Analytics

## Requisitos {#requirements}

Para configurar um destino Analytics, o usuário Audience Manager deve ter permissões de administrador. Consulte [Criar usuários](/help/using/features/administration/administration-overview.md#create-users) no Guia de administração. Observe que ter a permissão `CREATE_DESTINATIONS` curinga [](/help/using/features/administration/administration-overview.md#wild-card-permissions) não é suficiente para criar destinos do Analytics.
Para obter mais requisitos, consulte Pré-requisitos na [Audiência Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html).

## Seu destino padrão do Analytics e novos destinos do Analytics

| Tipo de Destino do Analytics | Descrição |
|---|---|
| Padrão | O nome desse destino padrão é &quot;Adobe Analytics&quot;, que você pode editar. As IDs de conjunto de relatórios mapeadas aparecem no armazenamento da pasta para seus traços e segmentos de Audience Manager. <br>  Audience Manager cria um destino automaticamente se sua conta tiver: <br>  <ul><li>Satisfaça os requisitos descritos na documentação da [Audiência Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html) .</li><li>Um conjunto [de](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) relatórios no Analytics.</li><li>[Mapeado um conjunto de relatórios para uma organização](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html).</li></ul> |
| Novo | Para criar novos destinos do Analytics, vá até Dados de Audiência > Destinos > Criar novo destino e siga as etapas para cada seção descrita abaixo. |

## Etapa 1: Fornecer informações básicas

Esta seção contém campos e opções que start o processo de criação de destino do Analytics. Para concluir esta seção:

1. Clique em Informações **** básicas para expor os controles.
2. Nomeie o destino. Evite abreviações e caracteres especiais.
3. *(Opcional)* Descreva o destino. Uma descrição concisa é uma maneira eficaz de definir ou fornecer mais informações sobre um destino.
4. *(Opcional)* Na lista **Platform** , deixe o padrão definido como **Todos**. Atualmente, essas opções não fazem nada. Eles foram projetados para suportar recursos que podem ser adicionados posteriormente.
5. Na lista **Categoria** , selecione **Adobe Experience Cloud**.
6. Na lista **Tipo** , selecione **Adobe Analytics**.
7. Clique em **Salvar** para acessar as Configurações ou clique em Rótulos **de exportação de** dados para aplicar controles de exportação ao destino.

>[!NOTE]
>
>Para um destino Analytics, as caixas de seleção Mapeamento **de destino de preenchimento** automático e a opção ID **de** segmento são selecionadas por padrão. Não é possível alterar essas configurações.

![informação básica](assets/basicinformation.png)

## Etapa 2: Configurar controles de exportação de dados

Esta seção contém opções que aplicam Controles [de exportação de](/help/using/features/data-export-controls.md) dados a um destino Analytics. Ignore esta etapa se você não usar controles de exportação de dados. Para concluir esta seção:

1. Clique em Controles **de exportação de** dados para expor os controles.
1. Selecione um rótulo que corresponda ao controle de exportação de dados aplicado ao destino (consulte [Adicionar rótulos de exportação de dados a um destino](/help/using/features/destinations/add-data-export-labels.md) ). Para destinos Analytics, a caixa de seleção PII é selecionada por padrão.
1. Clique em **Salvar**.

![exportcontroles](assets/exportControls.png)

## Etapa 3: Mapear conjuntos de relatórios

A seção Configuração lista seus Conjuntos de relatórios da Analytics que foram habilitados para encaminhamento pelo lado do servidor. Se você tiver vários destinos Analytics, os conjuntos de relatórios atribuídos a esses destinos serão mutuamente exclusivos e aplicados pela Audience Manager. Para concluir esta seção:

1. Clique em **Configuração** para expor os controles.
1. Selecione um (ou mais) conjunto de relatórios para o qual deseja enviar segmentos.
1. Clique em **Salvar**.

![report suites](assets/reportSuites.png)

## Etapa 4: Mapeamentos de segmentos

Esta seção fornece opções que permitem mapear segmentos automaticamente ou manualmente.

| Opção de mapeamento | Descrição |
|---|---|
| Mapear automaticamente todos os segmentos atuais e futuros | Selecionado por padrão, esse recurso envia todos os segmentos para os quais um visitante se qualifica, em uma base por ocorrência, para a Analytics. <br>  Se um visitante pertencer a mais de 150 segmentos de Audience Manager em uma única ocorrência, somente os 150 segmentos qualificados mais recentemente serão enviados à Analytics, enquanto a lista restante será truncada. Um sinalizador adicional é enviado à Analytics, indicando que a lista de segmentos foi truncada. Essa ação é exibida como &quot;Limite de Audiência atingido&quot; na dimensão Nome do Audiência e &quot;1&quot; na dimensão ID do Audiência. Consulte as [Perguntas frequentes](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) para obter detalhes. <br>  Além disso, essa opção afeta a disponibilidade de destino no Construtor [de segmentos](/help/using/features/segments/segment-builder.md). Por exemplo, se um segmento é mapeado automaticamente para um destino Analytics, esse destino não está disponível para seleção na seção de mapeamentos [de](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) destino do Construtor de segmentos. O destino Analytics é exibido acinzentado e mostra &quot;Analytics&quot; na coluna Tipo do navegador de Destino. |
| Mapear segmentos manualmente | Essa opção expõe os controles de pesquisa e navegação que permitem escolher quais segmentos você deseja enviar para a Analytics. <br>  Para procurar um segmento: <br>  <ol><li>Digite o nome ou a ID do segmento no campo de pesquisa.</li><li>Clique em <b>Adicionar.</b></li><li>Continue a pesquisar e adicionar segmentos ou clique em <b>Concluído</b>.</li></ol><br>  Para procurar um segmento: <ol><li>Clique em <b>Procurar todos os segmentos</b>. Isso expõe uma lista de segmentos disponíveis.</li><li>Na lista, marque a caixa de seleção do segmento que deseja usar e clique em <b>Adicionar segmentos</b>selecionados.</li><li>Clique em <b>Salvar</b> na janela Adicionar mapeamentos. Não é possível alterar os mapeamentos, as datas de start ou término durante a versão beta.</li><li>Continue a navegar e adicionar segmentos ou clique em <b>Concluído</b>.</li></ol> ![mapSegmentos](assets/mapSegments.png) |

## Próximas etapas

Depois de criar e salvar um destino, você pode trabalhar com esses dados no Analytics. No entanto, pode levar algumas horas até que os dados estejam disponíveis nos conjuntos de relatórios selecionados. See [Use the Audience Data in Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html).
