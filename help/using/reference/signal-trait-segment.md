---
description: Entenda os componentes de um segmento de Audience Manager, as expressões usadas para definir critérios de qualificação de audiência e como os dados são transmitidos em uma chamada de evento.
seo-description: Descreve os componentes de um segmento de Audience Manager, as expressões usadas para definir critérios de qualificação de audiência e como os dados são transmitidos em uma chamada de evento.
seo-title: Sinais, características e segmentos
solution: Audience Manager
title: Sinais, características e segmentos
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: reference
translation-type: tm+mt
source-git-commit: 8027f278aa2b879b6cb277f44caf4b62dc75e2c3
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 4%

---


# [!UICONTROL Signals], [!UICONTROL Traits]e [!UICONTROL Segments] {#signals-traits-and-segments}

Descreve os componentes de uma chamada [!DNL Audience Manager][!UICONTROL segment], as expressões usadas para definir critérios de qualificação de audiência e como os dados são transmitidos em uma chamada de evento.

## Composição e finalidade

[!DNL Audience Manager] os dados consistem em regras de qualificação [!UICONTROL signals], [!UICONTROL traits]e [!UICONTROL segments]relacionadas. Os elementos de dados e as regras se combinam para criar [!UICONTROL segments]. [!UICONTROL Segments] organize visitantes do site em grupos relacionados. A tabela a seguir define os três componentes principais em um [!DNL Audience Manager][!UICONTROL segment].

| Elemento | Consiste em | Exemplo |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] são as menores unidades de dados em [!DNL Audience Manager] e são expressas como pares [de valores](../reference/key-value-pairs-explained.md)chave.<br><br><ul><li>A chave é uma constante que define um conjunto de dados (por exemplo, gênero, cor, preço).</li><li>O valor é uma variável relacionada à constante (por exemplo, macho/fêmea, verde, 100).</li></ul>Os operadores de comparação ingressam no par de valores chave e definem a relação entre eles. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinações de um ou mais [!UICONTROL signals].<br><br> [!DNL Boolean] Os operadores de expressões e comparação permitem que você crie regras [!UICONTROL trait] de qualificação. <br><br>Crie requisitos de qualificação precisos com combinações de [!UICONTROL traits] e [!UICONTROL trait] grupos. | A partir do disponível [!UICONTROL signals], é possível criar uma `High End Camera Browser` regra expressa como: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Usuários que compartilham um conjunto de atributos comuns e se qualificam para os relacionados [!UICONTROL traits]. [!DNL Boolean] As expressões, juntamente com os requisitos de recenticidade/frequência, permitem que você crie regras de [!UICONTROL segment] qualificação.<br><br> Crie requisitos de qualificação precisos com combinações de [!UICONTROL trait] regras e [!UICONTROL segment] regras. | A partir do disponível [!UICONTROL traits] e [!UICONTROL signals], é possível criar uma [!UICONTROL segment] regra expressa como:`(product=camera AND type=digital SLR) OR (price>1000)` |

Use o diagrama abaixo para manter uma nota mental da relação entre [!UICONTROL signals], [!UICONTROL traits]e [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Criar[!UICONTROL Traits]e[!UICONTROL Segment]regras com ferramentas visuais e editores de código**

Os clientes gerenciam [!UICONTROL traits] e [!UICONTROL segments] com ferramentas visuais e editores de código na interface do [!DNL Audience Manager] usuário. As ferramentas visuais permitem criar regras usando recursos de pesquisa, opções de pop-up, menus suspensos e a funcionalidade arrastar e soltar. Os editores de código fornecem aos usuários avançados uma maneira de desenvolver de forma programática os critérios de segmentação de audiência.

**Chamadas de evento para enviar dados para[!DNL Audience Manager]**

Uma chamada de evento envia dados de seu site para [!DNL Audience Manager]. A chamada contém [!UICONTROL signal], [!UICONTROL trait]e [!UICONTROL segment] dados em uma [!DNL HTTP] solicitação. O evento em si é tudo depois da parte `/event` de uma [!DNL URL] string. Como mostrado no exemplo abaixo, esse processo requer apenas uma chamada de evento única para transmitir várias variáveis para [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmentos: finalidade, composição e regras](../features/segments/segments-purpose.md)

