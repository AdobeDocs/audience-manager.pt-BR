---
description: O Audience Manager define um limite máximo para o número de características, segmentos, destinos e modelos algorítmicos que você pode criar para uma conta. Os limites se aplicam a esses itens, sejam criados na interface do usuário ou por meio de métodos de API de forma programática. Os limites de uso ajudam a proteger o Audience Manager de processos automatizados que podem tentar comprometer nossas APIs ou interface de usuário.
seo-description: O Audience Manager define um limite máximo para o número de características, segmentos, destinos e modelos algorítmicos que você pode criar para uma conta. Os limites se aplicam a esses itens, sejam criados na interface do usuário ou por meio de métodos de API de forma programática. Os limites de uso ajudam a proteger o Audience Manager de processos automatizados que podem tentar comprometer nossas APIs ou interface de usuário.
seo-title: Limites de uso
solution: Audience Manager
title: ' Limites de uso'
keywords: Mapeamento de ID, mapeamentos de ID, mapeamentos de cookies
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
translation-type: tm+mt
source-git-commit: d893998e9e59dbce64195a167e267c6f7ed16f90

---


# Limites de uso {#usage-limits}

O Audience Manager define um limite máximo para o número de características, segmentos, destinos e modelos algorítmicos que você pode criar para uma conta. Os limites se aplicam a esses itens, sejam criados na interface do usuário ou por meio de [!DNL API] métodos programaticamente. Os limites de uso ajudam a proteger o Audience Manager de processos automatizados que podem tentar comprometer nossa interface [!DNL API]de usuário ou interface de usuário.

## Limites de mapeamento de ID {#id-mapping-limits}

A tabela abaixo lista os limites de mapeamento [de](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) ID para IDs de dispositivo. Quando uma ID atinge qualquer um dos limites abaixo, o Audience Manager adiciona novos mapeamentos de ID com base em uma lógica [!DNL FIFO] (primeira entrada, primeira saída), removendo o mapeamento de ID armazenado mais antigo e adiciona o novo. Consulte [Índice de IDs](../../reference/ids-in-aam.md) no Audience Manager para obter detalhes sobre as IDs suportadas pelo Audience Manager.

| Mapeamento de ID | Limite máximo |
|-----------|-------------- |
| ID de anúncio de dispositivo (DAID) para ID entre dispositivos (ID CRM) | 100 Device Advertising IDs (DAIDs) para 1 ID entre dispositivos (CRM ID) |
| ID entre dispositivos (ID CRM) para ID de publicidade do dispositivo (DAID) | 10 IDs entre dispositivos (CRM IDs) para 1 ID de anúncio de dispositivo (DAID) |
| ID do cookie/navegador para a ID do cookie/navegador | IDs de cookie/navegador 1000 para 1 ID de cookie/navegador |

## Limites de item {#item-limits}

As tabelas listam os limites atuais por tipo de item. Não é possível criar novas características, segmentos, destinos ou [!UICONTROL Algorithmic Models] se você atingir um limite específico para um desses itens. Se você atingir um limite, deverá excluir um item mais antigo antes de criar um novo.

### Limites da característica

| Tipo de característica | Limite máximo |
| -------------------------- | ------------------------------------- |
| Características totais | 100,000 |
| Total de Qualificações de Características | 150,000. Para obter mais informações sobre qualificação de características, consulte Limite de qualificação de características na Referência [de](/help/using/features/traits/trait-qualification-reference.md#trait-qualification-limit)qualificações de características. |
| Algorítmico | 50 |
| Baseada em regras | 100,000 |
| Onboard | 100,000 |
|  Características da pasta | 2,000 |

### Limites do segmento

| Tipo de segmento | Limite máximo |
| -------------- | ------------- |
| Total de segmentos | 20,000 |

### Limites de Destino

| Tipo de destino | Limite máximo |
| ------------------ | ------------- |
| Total de destinos | 1.000 |
| Cookie | 1.000 |
| URL | 1.000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### Limites do modelo algorítmico

| Item | Limite máximo |
| -------- | ----- |
| Modelos algorítmicos ativos | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| Tamanho máximo do público-alvo dos Modelos algorítmicos | 25,000,000.  Observe que esse limite não pode ser aumentado. Você pode diminuir os tamanhos do público selecionando menos fontes de dados para o modelo ou selecionando uma janela de retrospectiva mais curta. |
| Número máximo de características excluídas para um modelo | 500. Consulte Exclusão de [características na modelagem](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)algorítmica. |

### Limites da pasta

| Item | Limite máximo |
| ------------- | ------------------ |
| Pastas de características | 2,000.  Sua estrutura de pastas pode ter no máximo 5 níveis de profundidade. |

### Limites de Sinais Derivados

| Item | Limite máximo |
| --------------- | ------------- |
| Sinais derivados | 50.000. |

### Limite de contas de usuário da empresa

| Item | Limite máximo |
| ----------- | ------------- |
| Número máximo de contas de usuário para uma empresa | 1.000. |

## Uso do monitor {#monitor-usage}

Você pode ver o uso e os limites de sua conta indo para **[!UICONTROL Administration > Limits]**. O acesso requer permissões de administrador.

![uso limita imagem](assets/usage-limits.png)

## Aumentar limites de item {#increase-item-limits}

Os limites padrão listados aqui devem fornecer capacidade suficiente para suas necessidades comerciais. Se sua organização atingir esses limites de forma consistente, entre em contato com seu representante de conta para discutir um aumento.