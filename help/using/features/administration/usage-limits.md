---
description: O Audience Manager define um limite máximo para o número de características, segmentos, destinos e modelos algorítmicos que você pode criar para uma conta. Os limites se aplicam a esses itens, sejam criados na interface do usuário ou por meio de métodos de API de forma programática. Os limites de uso ajudam a proteger a Audience Manager de processos automatizados que podem tentar comprometer nossas APIs ou interface do usuário.
seo-description: O Audience Manager define um limite máximo para o número de características, segmentos, destinos e modelos algorítmicos que você pode criar para uma conta. Os limites se aplicam a esses itens, sejam criados na interface do usuário ou por meio de métodos de API de forma programática. Os limites de uso ajudam a proteger a Audience Manager de processos automatizados que podem tentar comprometer nossas APIs ou interface do usuário.
seo-title: Limites de uso
solution: Audience Manager
title: Limites de uso
keywords: ID mapping, ID mappings, cookie mappings
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
translation-type: tm+mt
source-git-commit: 7d2f4b45ac3e45c9b4fcaffa4b5c5324ff03e683
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 6%

---


# Limites de uso {#usage-limits}

O Audience Manager define um limite máximo para o número de características, segmentos, destinos e modelos algorítmicos que você pode criar para uma conta. Os limites se aplicam a esses itens, sejam criados na interface do usuário ou por meio de [!DNL API] métodos programaticamente. Os limites de uso ajudam a proteger a Audience Manager de processos automatizados que podem tentar comprometer nossa interface [!DNL API]de usuário ou de usuário.

## Limites de mapeamento de ID {#id-mapping-limits}

A tabela abaixo lista os limites de mapeamento [de](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) ID para IDs de dispositivo. Quando uma ID atinge qualquer um dos limites abaixo, a Audience Manager adiciona novos mapeamentos de ID com base em uma lógica [!DNL FIFO] (primeira entrada, primeira saída), removendo o mapeamento de ID armazenado mais antigo e adicionando o novo. Consulte [Índice de IDs](../../reference/ids-in-aam.md) no Audience Manager para obter detalhes sobre as IDs suportadas pelo Audience Manager.

| Mapeamento de ID | Limite máximo |
|-----------|-------------- |
| ID de anúncio do dispositivo ([DAID](../../reference/ids-in-aam.md)) para ID entre dispositivos ([DPUUID](../../reference/ids-in-aam.md)) | 100 Device Advertising ID ([DAID](../../reference/ids-in-aam.md)) para 1 ID entre dispositivos ([DPUUID](../../reference/ids-in-aam.md)) |
| ID entre dispositivos ([DPUUID](../../reference/ids-in-aam.md)) para ID de publicidade do dispositivo ([DAID](../../reference/ids-in-aam.md)) | 10 IDs entre dispositivos ([DPUUID](../../reference/ids-in-aam.md)) para 1 ID de anúncio de dispositivo ([DAID](../../reference/ids-in-aam.md)), por cada [DPID](../../reference/ids-in-aam.md) |
| ID do cookie/navegador para a ID do cookie/navegador | IDs de cookie/navegador 1000 para 1 ID de cookie/navegador |

## Limites de item {#item-limits}

As tabelas listas os limites atuais por tipo de item. Não é possível criar novas características, segmentos, destinos ou [!UICONTROL Algorithmic Models] se você atingir um limite específico para um desses itens. Se você atingir um limite, deverá excluir um item mais antigo antes de criar um novo.

### Limites da característica

| Tipo de característica | Limite máximo |
| -------------------------- | ------------------------------------- |
| Características totais | 100,000 |
| Total de Qualificações de Características | 150,000. Para obter mais informações sobre qualificação de características, consulte Limite de qualificação de características na Referência [de](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit)qualificações de características. |
| Algorítmico | 50 |
| Baseada em regras | 100,000 |
| Onboard | 100,000 |
| Características da pasta | 2,000 |

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
| Ativo [!UICONTROL Look-Alike Models] | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| [!UICONTROL Look-Alike Models] tamanho máximo da audiência | 25,000,000.  Observe que esse limite não pode ser aumentado. Você pode diminuir os tamanhos das audiências selecionando menos fontes de dados para o modelo ou selecionando uma janela de retrospectiva mais curta. |
| Número máximo de características excluídas para um [!UICONTROL Look-Alike Model] | 500. Consulte Exclusão de [características na modelagem](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)algorítmica. |
| Naxima [!UICONTROL Predictive Audiences Models] | 10 |
| Número máximo de personas da linha de base para [!UICONTROL Predictive Audiences Models] | 50 |

### Limites da pasta

| Item | Limite máximo |
| ------------- | ------------------ |
| Pastas de características | 2,000.  Sua estrutura de pastas pode ter no máximo 5 níveis de profundidade. |

### Limites de Sinais Derivados

| Item | Limite máximo |
| --------------- | ------------- |
| Sinais derivados | 50.000. |

### Limite de contas de usuário de Empresa

| Item | Limite máximo |
| ----------- | ------------- |
| Número máximo de contas de usuário para uma empresa | 1.000. |

## Uso do monitor {#monitor-usage}

Você pode ver o uso e os limites de sua conta indo para **[!UICONTROL Administration > Limits]**. O acesso requer permissões de administrador.

![uso limita imagem](assets/usage-limits.png)

## Aumentar limites de item {#increase-item-limits}

Os limites padrão listados aqui devem fornecer capacidade suficiente para suas necessidades comerciais. Se sua organização atingir esses limites de forma consistente, entre em contato com seu representante de conta para discutir um aumento.