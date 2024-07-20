---
description: Este artigo descreve as convenções de nomenclatura usadas pela variável principal em um par de valores chave.
seo-description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-title: Name Requirements for Key Variables
solution: Audience Manager
title: Requisitos de nome para variáveis-chave
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 0%

---

# Requisitos de nome para variáveis-chave {#name-requirements-for-key-variables}

Este artigo descreve as convenções de nomenclatura usadas pela variável principal em um par de valores chave.

## Requisitos de nomenclatura para chaves

<!-- c_tb_key_name_requirements.xml -->

Em [!UICONTROL Expression Builder], o nome de uma variável de chave em um par de valor-chave pode consistir em qualquer número de dígitos seguido por 1 (ou mais) letras, um traço, um sublinhado e dígitos adicionais.

* Nomes de chave válidos: `price123`, `123price`, `price-123`, `c_price123`.

* Nomes de chave inválidos: `123`, `price!123`.

## Prefixando variáveis-chave com `c_`

O prefixo `c_` é *always* necessário se os parâmetros que enviam dados em uma URL de chamada de evento usarem essa sintaxe.
