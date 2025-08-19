---
description: As Características de pasta permitem que você agregue características automaticamente que residem na mesma pasta e todas as pastas secundárias em um segmento direcionável.
keywords: avaliador de tamanho de segmento;sse
seo-description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
seo-title: Folder Traits  About
solution: Audience Manager
title: Características de pasta sobre
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 0%

---

# Características da pasta: sobre {#folder-traits-about}

O [!UICONTROL Folder traits] permite que você agregue características automaticamente que residem na mesma pasta e todas as pastas derivadas em um segmento direcionável.

## Benefícios do uso de características de pasta {#benefits}

Um [!UICONTROL folder trait] contém todas as características em uma pasta pai e suas pastas filho associadas. Isso permite segmentar e direcionar automaticamente os usuários em diferentes níveis de pasta. Por exemplo, digamos que você tenha uma estrutura de pastas como esta:

`*` Eletrônicos (pai)

    `*` Laptops (filhos)

        `*` Marcas (neto)

[!UICONTROL Folder traits] qualifique todos os usuários nessas pastas em um [!DNL Electronics] do [!UICONTROL Folder Trait] criado automaticamente (com base no nome da pasta pai). E esse processo se repete à medida que você desce pela estrutura do arquivo. Nesse caso, as características da pasta capturam todos os usuários nas pastas de Notebooks e Marcas em um [!UICONTROL Folder Trait] de Notebooks criado automaticamente.

[!UICONTROL Folder traits] são selecionáveis em expressões de segmento. Selecionar um [!UICONTROL folder trait] é equivalente a selecionar todas as características dentro dessa pasta e suas subpastas com um agrupamento [!UICONTROL OR].

![](assets/folder-traits-compare-border.jpg)

## Realização de características da pasta - Recenticidade e frequência {#folder-traits-realization}

A contagem de frequência de uma característica de pasta é a soma das realizações das características em sua pasta e suas pastas secundárias. A ilustração abaixo mostra as características A, B e C, que estão na pasta Automóvel. Considere que cada uma das características tem as seguintes realizações:

* Característica A: 5
* Característica B: 1
* Característica C: 1

Nesse caso, o [!DNL Automobile Folder Trait] tem 7 realizações.

![](assets/folder_traits_rollup_border.png)

## Relatório de características da pasta {#folder-traits-reporting}

[!UICONTROL Folder traits] capture todos os usuários das características na estrutura de pastas abaixo deles. Se você mover uma característica de uma pasta para outra pasta, a alteração se propagará para nossos [servidores de coleta de dados](../../reference/system-components/components-data-collection.md) da mesma forma que uma alteração de regra de característica. As atualizações de relatório no próximo relatório são executadas para refletir essa alteração nos intervalos de datas de relatório (1, 7, 14, 30, 60, 90). Os números dos relatórios antigos dos dias anteriores não serão alterados.

## Permissões de Controles de Acesso com Base em Função (RBAC) {#role-based-access-controls}

Para empresas que usam o [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), seus usuários com as permissões [!UICONTROL RBAC] apropriadas podem alterar a fonte de dados associada ao [!UICONTROL folder trait]. Um usuário deve pertencer a um grupo com um dos seguintes:

* Permissões de grupo `READ` e `WRITE` para uma fonte de dados de característica.
* Permissões curinga `VIEW_ALL_TRAITS` e `EDIT_ALL_TRAITS` para fontes de dados de características.

Saiba como atribuir permissões de [!UICONTROL RBAC] em nossa [documentação de administração](../../features/administration/administration-overview.md#create-group).

## Limites e outras considerações {#limits}

| Item | Descrição |
|---|---|
| Tipo de característica | [!UICONTROL Onboarded traits] e [!UICONTROL algorithmic traits] contribuem com no máximo 1 realização para a frequência de [!UICONTROL folder trait]. |
| Características de movimentação entre pastas | Mover uma característica de uma pasta para outra desqualificará essa característica da primeira característica da pasta e a qualificará para a segunda [!UICONTROL folder trait]. Isso significa que, se você excluir ou mover uma característica da pasta, os usuários na população da característica não serão segmentados dos segmentos que usam a característica da pasta como uma expressão de segmento. <br> Ao mapear segmentos ou conjuntos de relatórios do Adobe Analytics para sua organização da Experience Cloud, o Audience Manager cria automaticamente segmentos e características novas, correspondentes e somente leitura. Não é possível editar ou alterar o local de armazenamento dessas características do Audience Manager. No entanto, qualquer alteração executada nos segmentos mapeados do Adobe Analytics ou nos conjuntos de relatórios é refletida no Audience Manager. |
| Variáveis do sistema | Não é possível realizar [!UICONTROL Folder traits] em chamadas de evento usando o parâmetro `d_sid`. |
| Relatórios | [!UICONTROL Folder traits] são características calculadas automaticamente e não aparecem em **[!UICONTROL Overlap Reports]**. |
