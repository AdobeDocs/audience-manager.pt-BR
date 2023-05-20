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
source-wordcount: '522'
ht-degree: 1%

---

# Características da pasta: sobre {#folder-traits-about}

[!UICONTROL Folder traits] As permitem agregar automaticamente características que residem na mesma pasta e todas as pastas secundárias em um segmento direcionável.

## Benefícios do uso de características de pasta {#benefits}

A [!UICONTROL folder trait] contém todas as características em uma pasta pai e suas pastas filho associadas. Isso permite segmentar e direcionar automaticamente os usuários em diferentes níveis de pasta. Por exemplo, digamos que você tenha uma estrutura de pastas como esta:

`*` Eletrônicos (pai)

    `*` Notebooks (secundários)

        `*` Marcas (neto)

[!UICONTROL Folder traits] qualificar todos os usuários nessas pastas em um arquivo criado automaticamente [!DNL Electronics] [!UICONTROL Folder Trait] (com base no nome da pasta principal). E esse processo se repete à medida que você desce pela estrutura do arquivo. Nesse caso, as características da pasta capturam todos os usuários nas pastas de laptops e marcas em um laptop criado automaticamente [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] são selecionáveis em expressões de segmento. Selecionar um [!UICONTROL folder trait] é equivalente a selecionar todas as características nessa pasta e suas subpastas com um [!UICONTROL OR] agrupamento.

![](assets/folder-traits-compare-border.jpg)

## Realização de características da pasta - Recenticidade e frequência {#folder-traits-realization}

A contagem de frequência de uma característica de pasta é a soma das realizações das características em sua pasta e suas pastas secundárias. A ilustração abaixo mostra as características A, B e C, que estão na pasta Automóvel. Considere que cada uma das características tem as seguintes realizações:

* Característica A: 5
* Característica B: 1
* Característica C: 1

Neste caso, o [!DNL Automobile Folder Trait] O tem 7 realizações.

![](assets/folder_traits_rollup_border.png)

## Relatório de características da pasta {#folder-traits-reporting}

[!UICONTROL Folder traits] capture todos os usuários das características na estrutura de pastas abaixo deles. Se você mover uma característica de uma pasta para outra pasta, a alteração se propagará para nossa [servidores de coleção de dados](../../reference/system-components/components-data-collection.md) exatamente como uma alteração de regra de característica. As atualizações de relatório no próximo relatório são executadas para refletir essa alteração nos intervalos de datas de relatório (1, 7, 14, 30, 60, 90). Os números dos relatórios antigos dos dias anteriores não serão alterados.

## Permissões de Controles de Acesso com Base em Função (RBAC) {#role-based-access-controls}

Para empresas que usam [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), seus usuários com as [!UICONTROL RBAC] As permissões do podem alterar a fonte de dados associada à [!UICONTROL folder trait]. Um usuário deve pertencer a um grupo com um dos seguintes:

* `READ` e `WRITE` permissões de grupo para uma fonte de dados de características.
* `VIEW_ALL_TRAITS` e `EDIT_ALL_TRAITS` permissões curinga para fontes de dados de características.

Saiba como atribuir [!UICONTROL RBAC] permissões em nossos [documentação de administração](../../features/administration/administration-overview.md#create-group).

## Limites e outras considerações {#limits}

| Item | Descrição |
|---|---|
| Tipo de característica | [!UICONTROL Onboarded traits] e [!UICONTROL algorithmic traits] contribuir com, no máximo, 1 realização para um [!UICONTROL folder trait]da frequência. |
| Características de movimentação entre pastas | Mover uma característica de uma pasta para outra desqualificará essa característica da primeira característica da pasta e a qualificará para a segunda [!UICONTROL folder trait]. Isso significa que, se você excluir ou mover uma característica da pasta, os usuários na população da característica não serão segmentados dos segmentos que usam a característica da pasta como uma expressão de segmento. <br> Ao mapear segmentos do Adobe Analytics ou conjuntos de relatórios para sua organização Experience Cloud, o Audience Manager cria automaticamente segmentos e características novas, correspondentes e somente leitura. Não é possível editar ou alterar o local de armazenamento dessas características do Audience Manager. No entanto, qualquer alteração executada nos segmentos do Adobe Analytics ou conjuntos de relatórios mapeados é refletida no Audience Manager. |
| Variáveis do sistema | [!UICONTROL Folder traits] não pode ser realizado em chamadas de evento usando o `d_sid` parâmetro. |
| Relatório | [!UICONTROL Folder traits] são características calculadas automaticamente e não aparecem no **[!UICONTROL Overlap Reports]**. |
