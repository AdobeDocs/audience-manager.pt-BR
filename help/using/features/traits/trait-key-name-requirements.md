---
description: Este artigo descreve as convenções de nomenclatura usadas pela variável-chave em um par de valor chave.
seo-description: Este artigo descreve as convenções de nomenclatura usadas pela variável-chave em um par de valor chave.
seo-title: Requisitos de nome para variáveis principais
solution: Audience Manager
title: Requisitos de nome para variáveis principais
uuid: fa 72 e 732-895 d -4 cf 6-bea 0-66 b 404 c 2 b 059
translation-type: tm+mt
source-git-commit: bdbc2525a13eb04898b0a844ba478cde07e83252

---


# Name Requirements for Key Variables {#name-requirements-for-key-variables}

Este artigo descreve as convenções de nomenclatura usadas pela variável-chave em um par de valor chave.

## Requisitos de nomenclatura para chaves

<!-- c_tb_key_name_requirements.xml -->

In [!UICONTROL Expression Builder], the name of a key variable in a key-value pair can consist of any number of digits followed by 1 (or more) letters, a dash, an underscore, and additional digits.

* Valid key names: `price123`, `123price`, `price-123`, `c_price123`.

* Invalid key names: `123`, `price!123`.

## Prefixing Key Variables with `c_`

The `c_` prefix is *always* required if the parameters that send in data on an event call URL use that syntax.