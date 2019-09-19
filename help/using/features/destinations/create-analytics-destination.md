---
description: O Audience Analytics permite enviar segmentos do Audience Manager para o Analytics. Para usar esse recurso, crie um destino do Analytics e mapeie os segmentos a ele no Audience Manager.
seo-description: O Audience Analytics permite enviar segmentos do Audience Manager para o Analytics. Para usar esse recurso, crie um destino do Analytics e mapeie os segmentos a ele no Audience Manager.
seo-title: Configurar um destino do Analytics
solution: Audience Manager
title: Configurar um destino do Analytics
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


#  Configurar um destino do Analytics

## Exigências {#requirements}

Consulte [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## Destino padrão do Analytics e novos destinos do Analytics

| Tipo de destino do Analytics | Descrição |
|---|---|
| Padrão | O nome desse destino padrão é "Adobe Analytics", que você pode editar. As IDs de conjunto de relatórios mapeadas aparecem no armazenamento de pastas para suas características e segmentos do Audience Manager. <br>  O Audience Manager cria um destino automaticamente se sua conta tiver: <br>  <ul><li>Atenda aos requisitos descritos na documentação do [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) .</li><li>Um conjunto [de](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) relatórios no Analytics.</li><li>[Mapeado um conjunto de relatórios para uma organização](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).</li></ul> |
| Novo | Para criar novos destinos do Analytics, vá até Dados de público-alvo &gt; Destinos &gt; Criar novo destino e siga as etapas para cada seção descrita abaixo. |

## Etapa 1: Fornecer informações básicas

Esta seção contém campos e opções que iniciam o processo de criação de destino do Analytics. Para concluir esta seção:

1. Clique em Informações **** básicas para expor os controles.
1. Nomeie o destino. Evite abreviações e caracteres especiais.
1. *(Opcional)* Descreva o destino. Uma descrição concisa é uma maneira eficaz de definir ou fornecer mais informações sobre um destino.
1. *(Opcional)* Na lista **Plataforma** , deixe o padrão definido como **Todos**. Atualmente, essas opções não fazem nada. Eles foram projetados para suportar recursos que podem ser adicionados posteriormente.
1. Na lista **Categoria** , selecione **Adobe Experience Cloud**.
1. Na lista **Tipo** , selecione **Adobe Analytics**.
1. Clique em **Salvar** para acessar as Configurações ou clique em Rótulos **de exportação de** dados para aplicar controles de exportação ao destino.

>[!NOTE]
>
>Para um destino do Analytics, a caixa de seleção Preencher **automaticamente o mapeamento** de destino e a opção ID **de** segmento são selecionadas por padrão. Não é possível alterar essas configurações.

![informação básica](assets/basicinformation.png)

## Etapa 2: Configurar controles de exportação de dados

Esta seção contém opções que aplicam Controles [de exportação de](/help/using/features/data-export-controls.md) dados a um destino do Analytics. Ignore esta etapa se não usar controles de exportação de dados. Para concluir esta seção:

1. Clique em Controles **de exportação de** dados para expor os controles.
1. Selecione um rótulo que corresponda ao controle de exportação de dados aplicado ao destino (consulte [Adicionar rótulos de exportação de dados a um destino](/help/using/features/destinations/add-data-export-labels.md) ). Para destinos do Analytics, a caixa de seleção PII é selecionada por padrão.
1. Clique em **Salvar**.

![exportcontroles](assets/exportControls.png)

## Etapa 3: Mapear conjuntos de relatórios

A seção Configuração lista seus Report Suites do Analytics que foram habilitados para encaminhamento pelo lado do servidor. Se você tiver vários destinos do Analytics, os conjuntos de relatórios atribuídos a esses destinos serão mutuamente exclusivos e aplicados pelo Audience Manager. Para concluir esta seção:

1. Clique em **Configuração** para expor os controles.
1. Selecione um (ou mais) conjunto de relatórios para o qual deseja enviar segmentos.
1. Clique em **Salvar**.

![report suites](assets/reportSuites.png)

## Etapa 4: Mapeamentos de segmentos

Esta seção fornece opções que permitem mapear segmentos automaticamente ou manualmente.

| Opção de mapeamento | Descrição |
|---|---|
| Mapear automaticamente todos os segmentos atuais e futuros | Selecionado por padrão, esse recurso envia todos os segmentos para os quais um visitante se qualifica, por ocorrência, para o Analytics. <br>  Se um visitante pertencer a mais de 150 segmentos do Audience Manager em uma única ocorrência, somente os 150 segmentos qualificados mais recentemente serão enviados ao Analytics, enquanto a lista restante será truncada. Um sinalizador adicional é enviado ao Analytics, o que significa que a lista de segmentos foi truncada. Essa ação é exibida como "Limite de público-alvo atingido" na dimensão Nome de públicos-alvo e "1" na dimensão ID de públicos-alvo. Consulte as [Perguntas frequentes](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) para obter detalhes. <br>  Além disso, essa opção afeta a disponibilidade de destino no Construtor [de segmentos](/help/using/features/segments/segment-builder.md). Por exemplo, se um segmento é mapeado automaticamente para um destino do Analytics, esse destino não está disponível para seleção na seção de mapeamentos [de](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) destino do Construtor de segmentos. O destino do Analytics aparece esmaecido e mostra "Analytics" na coluna Tipo do navegador de Destino. |
| Mapear segmentos manualmente | Essa opção expõe os controles de pesquisa e navegação que permitem escolher quais segmentos você deseja enviar ao Analytics. <br>  Para procurar um segmento: <br>  <ol><li>Digite o nome ou a ID do segmento no campo de pesquisa.</li><li>Clique em <b>Adicionar.</b></li><li>Continue a pesquisar e adicionar segmentos ou clique em <b>Concluído</b>.</li></ol><br>  Para procurar um segmento: <ol><li>Clique em <b>Procurar todos os segmentos</b>. Isso expõe uma lista de segmentos disponíveis.</li><li>Na lista, marque a caixa de seleção do segmento que deseja usar e clique em <b>Adicionar segmentos</b>selecionados.</li><li>Clique em <b>Salvar</b> na janela Adicionar mapeamentos. Não é possível alterar as datas de mapeamento, início ou término durante a versão beta.</li><li>Continue a navegar e adicionar segmentos ou clique em <b>Concluído</b>.</li></ol> ![mapSegmentos](assets/mapSegments.png) |

## Próximas etapas

Depois de criar e salvar um destino, você pode trabalhar com esses dados no Analytics. No entanto, pode levar algumas horas até que os dados estejam disponíveis nos conjuntos de relatórios selecionados. See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).
