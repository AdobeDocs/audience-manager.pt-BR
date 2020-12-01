---
description: As características da pasta permitem que você agregação automaticamente as características que residem na mesma pasta e todas as pastas filhas em um segmento direcionável.
keywords: segment size estimator;sse
seo-description: As características da pasta permitem que você agregação automaticamente as características que residem na mesma pasta e todas as pastas filhas em um segmento direcionável.
seo-title: Características da pasta sobre
solution: Audience Manager
title: Características da pasta sobre
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 1%

---


# Características da pasta: sobre {#folder-traits-about}

[!UICONTROL Folder traits] permite que você agregação automaticamente as características que residem na mesma pasta e todas as pastas filhas em um segmento direcionável.

## Benefícios do uso das características da pasta {#benefits}

Um [!UICONTROL folder trait] contém todas as características em uma pasta pai e suas pastas filhas associadas. Isso permite que você segmente e público alvo automaticamente seus usuários em diferentes níveis de pasta. Por exemplo, digamos que você tenha uma estrutura de pastas como esta:

`*` Eletrônicos (pai)

    `*` Notebooks (filho)

        `*` Marcas (netos)

[!UICONTROL Folder traits] qualificar todos os usuários dessas pastas em uma pasta criada automaticamente  [!DNL Electronics] [!UICONTROL Folder Trait] (com base no nome da pasta pai). E esse processo se repete enquanto você move para baixo a estrutura de arquivos. Nesse caso, as características das pastas capturam todos os usuários nas pastas Notebooks e Marcas em um laptop criado automaticamente [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] são selecionáveis em expressões de segmentos. Selecionar um [!UICONTROL folder trait] equivale a selecionar todas as características dentro dessa pasta e suas subpastas com um agrupamento [!UICONTROL OR].

![](assets/folder-traits-compare-border.jpg)

## Realização das características da pasta - Idade e frequência {#folder-traits-realization}

A contagem de frequência de uma característica de pasta é a soma das realizações das características em sua pasta e em suas pastas filhas. A ilustração abaixo mostra as características A, B e C, que vivem na pasta Automóvel. Considere que cada uma das características tem as seguintes realizar:

* Caractere A: 5
* Característica B: 1
* Característica C: 1

Nesse caso, o [!DNL Automobile Folder Trait] tem 7 realizações.

![](assets/folder_traits_rollup_border.png)

## Relatórios de característica da pasta {#folder-traits-reporting}

[!UICONTROL Folder traits] capture todos os usuários das características na estrutura de pastas abaixo deles. Se você mover uma característica de uma pasta para outra pasta, a alteração será propagada para nossos [servidores de coleta de dados](../../reference/system-components/components-data-collection.md) da mesma forma que uma alteração de regra de característica. As atualizações do relatórios na próxima execução do relatórios refletem essa alteração nos intervalos de datas do relatórios (1, 7, 14, 30, 60, 90). Os números de relatórios antigos dos dias anteriores não serão alterados.

## Permissões RBAC (Controles de acesso Baseados em Função) {#role-based-access-controls}

Para empresa usando [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), seus usuários com as permissões [!UICONTROL RBAC] apropriadas podem alterar a fonte de dados associada ao [!UICONTROL folder trait]. Um usuário deve pertencer a um grupo com uma das seguintes opções:

* `READ` e permissões de  `WRITE` grupo para uma fonte de dados de característica.
* `VIEW_ALL_TRAITS` e permissões  `EDIT_ALL_TRAITS` curingas para fontes de dados de características.

Saiba como atribuir [!UICONTROL RBAC] permissões na [documentação administrativa](../../features/administration/administration-overview.md#create-group).

## Limites e outras considerações {#limits}

| Item | Descrição |
|---|---|
| Tipo de característica | [!UICONTROL Onboarded traits] e  [!UICONTROL algorithmic traits] contribuir, no máximo, para a realização da frequência  [!UICONTROL folder trait]de um evento. |
| Mover características entre pastas | Mover uma característica de uma pasta para outra desqualificará essa característica da primeira pasta e a qualificará para a segunda [!UICONTROL folder trait]. Isso significa que, se você excluir ou mover uma característica da pasta, os usuários na população da característica não serão segmentados dos segmentos usando a característica da pasta como uma expressão de segmento. <br> Ao mapear segmentos do Adobe Analytics ou conjuntos de relatórios para a organização do Experience Cloud, o Audience Manager cria automaticamente segmentos e características novos, correspondentes e somente leitura. Não é possível editar ou alterar o local do armazenamento para o Audience Manager. No entanto, qualquer alteração que você efetuar em seus segmentos Adobe Analytics ou conjuntos de relatórios mapeados será refletida no Audience Manager. |
| Variáveis de sistema | [!UICONTROL Folder traits] não pode ser realizado em chamadas de evento usando o  `d_sid` parâmetro. |
| Relatório | [!UICONTROL Folder traits] são características calculadas automaticamente e não aparecem em  **[!UICONTROL Overlap Reports]**. |