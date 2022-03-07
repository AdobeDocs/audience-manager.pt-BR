---
description: Saiba mais sobre os componentes de um segmento e as expressões usadas para definir critérios de qualificação de público-alvo. Encontre também informações sobre como os dados são transmitidos.
landing-page-description: Saiba mais sobre os componentes de um segmento e as expressões usadas para definir critérios de qualificação de público-alvo. Encontre também informações sobre como os dados são transmitidos.
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: Sinais, características e segmentos
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: 865800eb076811db38aec8e98714ad9712804f77
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 2%

---

# [!UICONTROL Signals], [!UICONTROL Traits]e [!UICONTROL Segments] {#signals-traits-and-segments}

Descreve os componentes de um [!DNL Audience Manager] [!UICONTROL segment], as expressões usadas para definir critérios de qualificação de público-alvo e como os dados são transmitidos em uma chamada de evento.

## Composição e finalidade

[!DNL Audience Manager] Os dados do consistem em [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments]e as regras de qualificação relacionadas. Os elementos de dados e as regras são combinados para criar [!UICONTROL segments]. [!UICONTROL Segments] organize visitantes do site em grupos relacionados. A tabela a seguir define os três componentes principais em um [!DNL Audience Manager] [!UICONTROL segment].

| Elemento | Consiste em | Exemplo |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] são as menores unidades de dados em [!DNL Audience Manager] e são expressas como [pares de valor-chave](../reference/key-value-pairs-explained.md).<br><br><ul><li>A chave é uma constante que define um conjunto de dados (por exemplo, gênero, cor, preço).</li><li>O valor é uma variável relacionada à constante (por exemplo, masculino/feminino, verde, 100).</li></ul>Os operadores de comparação se associam ao par de valores chave e definem a relação entre eles. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinações de um ou mais [!UICONTROL signals].<br><br> [!DNL Boolean] expressões e operadores de comparação permitem criar [!UICONTROL trait] regras de qualificação. <br><br>Criar requisitos de qualificação precisos com combinações de [!UICONTROL traits] e [!UICONTROL trait] grupos. | Em [!UICONTROL signals], você pode criar um `High End Camera Browser` regra expressa como: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Usuários que compartilham um conjunto de atributos comuns e se qualificam para [!UICONTROL traits]. [!DNL Boolean] expressões, juntamente com requisitos de recenticidade/frequência, permitem criar [!UICONTROL segment] regras de qualificação.<br><br> Criar requisitos de qualificação precisos com combinações de [!UICONTROL trait] e [!UICONTROL segment] regras. | Em [!UICONTROL traits] e [!UICONTROL signals], você pode criar um [!UICONTROL segment] regra expressa como:`(product=camera AND type=digital SLR) OR (price>1000)` |

Use o diagrama abaixo para manter uma nota mental da relação entre [!UICONTROL signals], [!UICONTROL traits]e [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Criar [!UICONTROL Traits] e [!UICONTROL Segment] Regras com ferramentas visuais e editores de código**

Clientes gerenciam [!UICONTROL traits] e [!UICONTROL segments] com ferramentas visuais e editores de código na [!DNL Audience Manager] interface do usuário. As ferramentas visuais permitem criar regras usando recursos de pesquisa, opções de pop-up, menus suspensos e a funcionalidade de arrastar e soltar. Os editores de código fornecem aos usuários avançados uma maneira de desenvolver programaticamente os critérios de segmentação do público-alvo.

**Chamadas de evento Enviar dados para[!DNL Audience Manager]**

Uma chamada de evento envia dados do site para o [!DNL Audience Manager]. A chamada contém [!UICONTROL signal], [!UICONTROL trait]e [!UICONTROL segment] em um [!DNL HTTP] solicitação. O evento em si é tudo depois do evento `/event` parte de um [!DNL URL] string. Como mostrado no exemplo abaixo, esse processo requer apenas uma chamada de evento para transmitir várias variáveis para [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmentos: finalidade, composição e regras](../features/segments/segments-purpose.md)

