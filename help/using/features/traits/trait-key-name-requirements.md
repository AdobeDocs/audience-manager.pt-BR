---
description: Este artigo descreve as convenções de nomenclatura usadas pela variável de chave em um par de valor chave.
seo-description: Este artigo descreve as convenções de nomenclatura usadas pela variável de chave em um par de valor chave.
seo-title: Requisitos de nome para variáveis-chave
solution: Audience Manager
title: Requisitos de nome para variáveis-chave
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: 'Características '
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 12%

---

# Requisitos de nome para variáveis-chave {#name-requirements-for-key-variables}

Este artigo descreve as convenções de nomenclatura usadas pela variável de chave em um par de valor chave.

## Requisitos de nomenclatura para chaves

<!-- c_tb_key_name_requirements.xml -->

Em [!UICONTROL Expression Builder], o nome de uma variável de chave em um par de valor-chave pode consistir em qualquer número de dígitos seguido por 1 (ou mais) letras, um traço, um sublinhado e dígitos adicionais.

* Nomes de chave válidos: `price123`, `123price`, `price-123`, `c_price123`.

* Nomes de chave inválidos: `123`, `price!123`.

## Prefixando variáveis-chave com `c_`

O prefixo `c_` é *sempre* necessário se os parâmetros que enviam dados em um URL de chamada de evento usarem essa sintaxe.
