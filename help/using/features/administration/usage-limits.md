---
description: O Audience Manager define um limite máximo sobre o número de características, segmentos, destinos e modelos algorítmicos que podem ser criados para uma conta. Os limites se aplicam a esses itens, criados na interface do usuário ou de forma programática por meio de métodos de API. Os limites de uso ajudam a proteger o Audience Manager de processos automatizados que podem tentar comprometer nossas apis ou interface do usuário.
seo-description: O Audience Manager define um limite máximo sobre o número de características, segmentos, destinos e modelos algorítmicos que podem ser criados para uma conta. Os limites se aplicam a esses itens, criados na interface do usuário ou de forma programática por meio de métodos de API. Os limites de uso ajudam a proteger o Audience Manager de processos automatizados que podem tentar comprometer nossas apis ou interface do usuário.
seo-title: Limites de uso
solution: Audience Manager
title: Limites de uso
topic: API DIL
uuid: 50 ca 4647-0 b 5 c -409 c -89 fa -4 fa 1799 b 3222
translation-type: tm+mt
source-git-commit: a9550d71bbc6adf939539df05cd38a9d22ef261b

---


# Usage Limits {#usage-limits}

O Audience Manager define um limite máximo sobre o número de características, segmentos, destinos e modelos algorítmicos que podem ser criados para uma conta. Limits apply to these items whether created in the user interface or programmatically through [!DNL API] methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our [!DNL API]s or user interface.

## Limites de mapeamento de ID {#id-mapping-limits}

The table below lists the [ID mapping](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) limits for device IDs. Once an ID reaches any of the limits below, Audience Manager adds new ID mappings based on a [!DNL FIFO] (first in, first out) logic, by removing the oldest stored ID mapping, and adds the new one. Refer to [Index of IDs](../../reference/ids-in-aam.md) in Audience Manager for details on the IDs supported by Audience Manager.

| Mapeamento de ID | Limite máximo |
|-----------|-------------- |
| ID de publicidade do dispositivo (DAID) na ID entre dispositivos (ID de CRM) | 100 IDs de publicidade de dispositivo (daid) em 1 ID de dispositivo cruzado (ID de CRM) |
| ID de dispositivo cruzado (ID de CRM) para o ID de publicidade do dispositivo (DAID) | 10 IDs de dispositivo cruzado (IDs CRM) para 1 ID de publicidade do dispositivo (DAID) |
| ID de cookie/navegador à ID de cookie/navegador | 1000 cookies/IDs de navegador para 1 cookie/ID do navegador |

## Item Limits {#item-limits}

As tabelas listam os limites atuais por tipo de item. You cannot create new traits, segments, destinations, or [!UICONTROL Algorithmic Models] if you reach a specific limit for one of these items. Se você atingir um limite, deverá excluir um item mais antigo antes de poder criar uma nova.

### Limites de característica

| Tipo de característica | Limite máximo |
| -------------------------- | ------------------------------------- |
| Total de características | 100,000 |
| Qualificações totais de característica | 150,000. For more information on trait qualification, see Trait Qualification Limit in [Trait Qualifications Reference](/help/using/features/traits/trait-qualification-reference.md#trait-qualification-limit). |
| Algorítmica | 50 |
| Baseado em regras | 100,000 |
| Onboarded | 100,000 |
| Características da pasta | 2,000 |

### Limites do segmento

| Tipo de segmento | Limite máximo |
| -------------- | ------------- |
| Total de segmentos | 20,000 |

### Limites de destino

| Tipo de destino | Limite máximo |
| ------------------ | ------------- |
| Total de destinos | 1.000 |
| Cookie | 1.000 |
| URL | 1.000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### Limites de modelo algorítmico

| Item | Limite máximo |
| -------- | ----- |
| Modelos algorítmicos ativos | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| O algoritmo tem o tamanho máximo do público-alvo | 25,000,000.  Observe que esse limite não pode ser aumentado. Você pode reduzir os tamanhos do público-alvo selecionando menos fontes de dados para o modelo ou selecionando uma janela de retrospectiva mais curta. |
| Número máximo de características excluídas para um modelo | 500. See [Trait Exclusion in Algorithmic Modeling](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |

### Limites da pasta

| Item | Limite máximo |
| ------------- | ------------------ |
| Pastas de características | 2,000.  A estrutura de pastas pode ter um nível máximo de 5 níveis. |

### Limites derivados derivados

| Item | Limite máximo |
| --------------- | ------------- |
| Sinais derivados | 50.000. |

### Limite das contas de usuário da empresa

| Item | Limite máximo |
| ----------- | ------------- |
| Número máximo de contas de usuário para uma empresa | 1.000. |

## Monitor Usage {#monitor-usage}

You can see usage and limits for your account by going to **[!UICONTROL Administration > Limits]**. O acesso requer permissões de administrador.

![limites de uso de imagem](assets/usage-limits.png)

## Increase Item Limits {#increase-item-limits}

Os limites padrão listados aqui devem fornecer capacidade suficiente para suas necessidades de negócios. Se a sua organização atingir consistentemente esses limites, entre em contato com seu representante de contas para discutir um aumento.