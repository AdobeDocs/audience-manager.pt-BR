---
description: Características de pastas permitem que você agregue características que residam na mesma pasta e todas as pastas filho em um segmento direcionável.
keywords: avaliador de tamanho de segmento; sse
seo-description: Características de pastas permitem que você agregue características que residam na mesma pasta e todas as pastas filho em um segmento direcionável.
seo-title: Características da pasta sobre
solution: Audience Manager
title: Características da pasta sobre
uuid: e 561 ce 8 f -6 c 90-44 a 7-b 034-685533 f 29030
translation-type: tm+mt
source-git-commit: 263c55e6bd2c9ad7159306fc889b048d800c59da

---


# Características da pasta: Sobre {#folder-traits-about}

[!UICONTROL Folder traits] permitem que você agregue características automaticamente que residam na mesma pasta e todas as pastas secundárias em um segmento direcionável.

## Benefícios do uso de características de pastas {#benefits}

A [!UICONTROL folder trait] contém todas as características em uma pasta pai e suas pastas filho associadas. Isso permite segmentar e direcionar automaticamente os usuários em diferentes níveis de pasta. Por exemplo, digamos que você tenha uma estrutura de pastas como isto:

`*` Eletrônicos (pai)

`*` Laptops (filho)

`*` Marcas (nehas)

[!UICONTROL Folder traits] qualifica todos os usuários nessas pastas de uma forma automaticamente criada [!DNL Electronics][!UICONTROL Folder Trait] (com base no nome da pasta pai). Além disso, esse processo se repete à medida que você move para baixo a estrutura do arquivo. Nesse caso, as características da pasta capturam todos os usuários nas pastas Laptops e Marcas em Laptops [!UICONTROL Folder Trait]criados automaticamente.

[!UICONTROL Folder traits] são selecionáveis nas expressões de segmento. A seleção de um [!UICONTROL folder trait] equivale a selecionar todas as características dentro dessa pasta e suas subpastas com [!UICONTROL OR] um agrupamento.

![](assets/folder-traits-compare-border.jpg)

## Realização de características da pasta - Recenticidade e frequência {#folder-traits-realization}

A contagem de frequência de uma pasta característica é a soma dos realizações das características na pasta e nas pastas filho. A ilustração abaixo mostra características A, B e C, que moram na pasta Car. Considere que cada uma das características tem os seguintes resultados:

* Característica A: 5
* Característica B: 1
* Característica C: 1

Nesse caso, [!DNL ]o Car [!UICONTROL Folder Trait] tem 7 realizações.

![](assets/folder_traits_rollup_border.png)

## Relatório de características da pasta {#folder-traits-reporting}

[!UICONTROL Folder traits] capturar todos os usuários das características na estrutura de pastas abaixo delas. Se você mover uma característica de uma pasta para outra pasta, a alteração propagará para nossos [servidores](../../reference/system-components/components-data-collection.md) de coleção de dados exatamente como uma alteração de regra de característica. As atualizações de relatórios no próximo relatório são executadas para refletir essa alteração nos intervalos de datas do relatório (1, 7, 14, 30, 60, 90). Os números de relatórios antigos dos dias anteriores não serão alterados.

## Permissões RBAC (Controles de acesso com base em funções) {#role-based-access-controls}

Para empresas que usam [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), os usuários com [!UICONTROL RBAC] as permissões apropriadas podem alterar a fonte de dados associada ao [!UICONTROL folder trait]. Um usuário deve pertencer a um grupo com um dos seguintes:

* `READ` e `WRITE` permissões de grupo para uma fonte de dados característica.
* `VIEW_ALL_TRAITS` e `EDIT_ALL_TRAITS` permissões curingas para fontes de dados de características.

Saiba como atribuir [!UICONTROL RBAC] permissões em nossa [documentação de administração](../../features/administration/administration-overview.md#create-group).

## Limites e outras considerações {#limits}

| Item | Descrição |
|---|---|
| Tipo de característica | [!UICONTROL Onboarded traits] e [!UICONTROL algorithmic traits] contribuir com, no máximo, 1 realização da frequência de uma [!UICONTROL folder trait]. |
| Movimentação de características entre pastas | Mover uma característica de uma pasta para outra desqualificará aquela característica da primeira pasta e qualificará-a para o segundo [!UICONTROL folder trait]. Isso significa que, se você excluir ou mover uma característica da pasta, os usuários na população de características serão dessegmentados dos segmentos usando a característica de pastas como uma expressão de segmento. <br> Ao mapear segmentos do Adobe Analytics ou conjuntos de relatórios para a organização da Experience Cloud, o Audience Manager cria automaticamente novos segmentos correspondentes, correspondentes e somente leitura. Não é possível editar ou alterar o local de armazenamento dessas características do Audience Manager. No entanto, qualquer alteração realizada nos segmentos do Adobe Analytics mapeados ou nos conjuntos de relatórios reflete no Audience Manager. |
| Variáveis do sistema | [!UICONTROL Folder traits] não pode ser observado em chamadas de evento usando o `d_sid` parâmetro. |
| Relatórios | [!UICONTROL Folder traits] são características autosegregadas e não aparecem **[!UICONTROL Overlap Reports]**. |