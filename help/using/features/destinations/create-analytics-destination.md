---
description: O Audience Analytics permite enviar segmentos do Audience Manager para o Analytics. Para usar esse recurso, crie um destino do Analytics e mapeie os segmentos a ele no Audience Manager.
seo-description: Audience Analytics lets you send Audience Manager segments to Analytics. To use this feature, you create an Analytics destination and map segments to it in Audience Manager.
seo-title: Configure an Analytics Destination
solution: Audience Manager
title: Configurar um destino do Analytics
feature: Adobe Analytics Integration
exl-id: f3ead057-04d1-40cd-8e3d-d0934d85cdb4
source-git-commit: ef8cca16c8c9478f8558c26bf6f3ae95cd72e7ac
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 5%

---

# Configurar um destino do Analytics

## Requisitos {#requirements}

Para configurar um destino do Analytics, o usuário do Audience Manager deve ter permissões de administrador. Consulte [Criar usuários](/help/using/features/administration/administration-overview.md#create-users) no Guia de administração. Observe que ter o `CREATE_DESTINATIONS` [permissão curinga](/help/using/features/administration/administration-overview.md#wild-card-permissions) não é suficiente para criar destinos do Analytics.
Para obter mais informações, consulte Pré-requisitos em [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html).

## Seu destino padrão do Analytics e novos destinos do Analytics

| Tipo de destino do Analytics | Descrição |
|---|---|
| Padrão | O nome desse destino padrão é &quot;Adobe Analytics&quot;, que pode ser editado. As IDs do conjunto de relatórios mapeadas aparecem no armazenamento de pastas para suas características e segmentos de Audience Manager. <br>  O Audience Manager cria um destino automaticamente se sua conta tiver: <br>  <ul><li>Atenda aos requisitos descritos na [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html) documentação.</li><li>A [conjunto de relatórios](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html) no Analytics.</li></ul> |
| Novo | Para criar novos destinos do Analytics, acesse Dados de público-alvo > Destinos > Criar novo destino e siga as etapas para cada seção descrita abaixo. |

## qualificações de segmento do Audience Manager no Adobe Analytics {#segment-qualifications}

Ao enviar informações de segmento para um destino do Analytics, o Audience Manager envia somente os segmentos para os quais o visitante se qualificou. Se um visitante deixar de se qualificar para um segmento, essas informações serão _não_ encaminhado para o Adobe Analytics.

Por exemplo, considere as regras de segmento abaixo:

* Segmento A: Característica 1 E Característica 2
* Segmento B: característica 1 E NÃO característica 2

Nos relatórios do Analytics, um perfil pode ser mostrado qualificado para ambos os segmentos, mesmo que ele tenha parado de se qualificar para o Segmento B.

## Etapa 1: Fornecer Informações Básicas

Esta seção contém campos e opções que iniciam o processo de criação de destino do Analytics. Para concluir esta seção:

1. Clique em **Informações básicas** para expor os controles.
2. Nomeie o destino. Evite abreviações e caracteres especiais.
3. *(Opcional)* Descreva o destino. Uma descrição concisa é uma maneira eficaz de definir ou fornecer mais informações sobre um destino.
4. *(Opcional)* No **Platform** deixe o padrão definido como **Todos**. Atualmente, essas opções não fazem nada. Elas foram projetadas para suportar recursos que podem ser adicionados posteriormente.
5. No **Categoria** selecione **Adobe Experience Cloud**.
6. No **Tipo** selecione **Adobe Analytics**.
7. Clique em **Salvar** para acessar as Configurações ou clique em **Rótulos de exportação de dados** para aplicar controles de exportação ao destino.

>[!NOTE]
>
>Para um destino do Analytics, a variável **Preencher automaticamente o mapeamento de destino** caixa de seleção e **ID do segmento** são selecionadas por padrão. Não é possível alterar essas configurações.

![basicinformation](assets/basicinformation.png)

## Etapa 2: Configurar Controles Da Exportação De Dados

Esta seção contém opções que se aplicam [Controles da exportação de dados](/help/using/features/data-export-controls.md) para um destino do Analytics. Ignore esta etapa se não usar controles de exportação de dados. Para concluir esta seção:

1. Clique em **Controles da exportação de dados** para expor os controles.
1. Selecione um rótulo que corresponda ao controle de exportação de dados aplicado ao destino (consulte [Adicionar rótulos de exportação de dados a um destino](/help/using/features/destinations/add-data-export-labels.md) ). Para destinos do Analytics, a caixa de seleção PII é marcada por padrão.
1. Clique em **Salvar**.

![exportcontrols](assets/exportControls.png)

## Etapa 3: Mapear conjuntos de relatórios

A seção Configuração lista os Conjuntos de relatórios do Analytics que foram habilitados para encaminhamento pelo lado do servidor. Se você tiver vários destinos do Analytics, os conjuntos de relatórios atribuídos a esses destinos serão mutuamente exclusivos e aplicados pelo Audience Manager. Para concluir esta seção:

1. Clique em **Configuração** para expor os controles.
1. Selecione um (ou mais) conjunto de relatórios para os quais você deseja enviar segmentos.
1. Clique em **Salvar**.

![conjuntos de relatórios](assets/reportSuites.png)

## Etapa 4: Mapeamentos de Segmento

Esta seção fornece opções que permitem mapear segmentos automática ou manualmente.

| Opção de mapeamento | Descrição |
|---|---|
| Mapear automaticamente todos os segmentos atuais e futuros | Selecionado por padrão, esse recurso envia todos os segmentos para os quais um visitante se qualifica, por ocorrência, para o Analytics. <br>  Se um visitante pertencer a mais de 150 segmentos de Audience Manager em uma única ocorrência, somente os 150 segmentos qualificados mais recentemente serão enviados para o Analytics, enquanto a lista restante será truncada. Um sinalizador adicional é enviado ao Analytics, para avisar que a lista de segmentos está truncada. Essa ação é exibida como &quot;Limite de público-alvo atingido&quot; na dimensão Nome de público-alvo e &quot;1&quot; na dimensão ID de público-alvo. Consulte a [Perguntas frequentes](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) para obter detalhes. <br>  Além disso, essa opção afeta a disponibilidade do destino no [Construtor de segmentos](/help/using/features/segments/segment-builder.md). Por exemplo, se um segmento for mapeado automaticamente para um destino do Analytics, esse destino não estará disponível para seleção na [mapeamentos de destino](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) seção do Construtor de segmentos. O destino do Analytics aparece esmaecido e mostra &quot;Analytics&quot; na coluna Tipo do navegador de destino. |
| Mapear segmentos manualmente | Essa opção expõe os controles de pesquisa e navegação que permitem escolher quais segmentos você deseja enviar para o Analytics. <br>  Para pesquisar um segmento: <br>  <ol><li>Digite o nome ou ID do segmento no campo de pesquisa.</li><li>Clique em <b>Adicionar.</b></li><li>Continue a pesquisar e adicionar segmentos ou clique em <b>Concluído</b>.</li></ol><br>  Para procurar um segmento: <ol><li>Clique em <b>Procurar todos os segmentos</b>. Isso expõe uma lista de segmentos disponíveis.</li><li>Na lista, marque a caixa de seleção do segmento que deseja usar e clique em <b>Adicionar segmentos selecionados</b>.</li><li>Clique em <b>Salvar</b> na janela Adicionar Mapeamentos. Você não pode alterar os mapeamentos, as datas de início ou de término durante a versão beta.</li><li>Continue a procurar e adicionar segmentos ou clique em <b>Concluído</b>.</li></ol> ![mapsegments](assets/mapSegments.png) |

## Próximas etapas

Depois de criar e salvar um destino, você pode trabalhar com esses dados no Analytics. No entanto, pode levar algumas horas até que os dados estejam disponíveis nos conjuntos de relatórios selecionados. Consulte [Usar os dados de público-alvo no Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html).
