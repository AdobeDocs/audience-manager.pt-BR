---
description: Este artigo descreve as convenções de nomenclatura usadas pela variável key em um par de valor chave.
seo-description: Este artigo descreve as convenções de nomenclatura usadas pela variável key em um par de valor chave.
seo-title: Requisitos de nome para variáveis-chave
solution: Audience Manager
title: Requisitos de nome para variáveis-chave
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---


# Requisitos de nome para variáveis-chave {#name-requirements-for-key-variables}

Este artigo descreve as convenções de nomenclatura usadas pela variável key em um par de valor chave.

## Requisitos de nomenclatura para chaves

<!-- c_tb_key_name_requirements.xml -->

Em [!UICONTROL Expression Builder], o nome de uma variável principal em um par de valores chave pode consistir em qualquer número de dígitos seguido por 1 (ou mais) letras, um travessão, um sublinhado e dígitos adicionais.

* Nomes de chave válidos: `price123`, `123price`, `price-123`, `c_price123`.

* Nomes de chave inválidos: `123`, `price!123`.

## Prefixando variáveis principais com `c_`

O `c_` prefixo é *sempre* necessário se os parâmetros que enviam dados em um URL de chamada de evento usarem essa sintaxe.