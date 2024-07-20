---
description: Saiba mais sobre os componentes de um segmento e as expressões usadas para definir critérios de qualificação de público-alvo. Encontre também informações sobre como os dados são transmitidos.
landing-page-description: Saiba mais sobre os componentes de um segmento e as expressões usadas para definir critérios de qualificação de público-alvo. Encontre também informações sobre como os dados são transmitidos.
short-description: Saiba mais sobre os componentes de um segmento e as expressões usadas para definir critérios de qualificação de público-alvo. Encontre também informações sobre como os dados são transmitidos.
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: Sinais, características e segmentos
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 21%

---

# [!UICONTROL Signals], [!UICONTROL Traits] e [!UICONTROL Segments] {#signals-traits-and-segments}

Descreve os componentes de um [!DNL Audience Manager] [!UICONTROL segment], as expressões usadas para definir critérios de qualificação de público e como os dados são transmitidos em uma chamada de evento.

## Composição e finalidade

Os dados de [!DNL Audience Manager] consistem em [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments] e regras de qualificação relacionadas. Os elementos de dados e as regras se combinam para criar [!UICONTROL segments]. [!UICONTROL Segments] organize os visitantes do site em grupos relacionados. A tabela a seguir define os três componentes principais em um [!DNL Audience Manager] [!UICONTROL segment].

| Elemento | Consiste em | Exemplo |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] são as menores unidades de dados em [!DNL Audience Manager] e são expressas como [pares de valores-chave](../reference/key-value-pairs-explained.md).<br><br><ul><li>A chave é uma constante que define um conjunto de dados (por exemplo, gênero, cor, preço).</li><li>O valor é uma variável relacionada à constante (por exemplo, macho/fêmea, verde, 100).</li></ul>Os operadores de comparação se unem ao par de valores chave e definem a relação entre eles. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinações de um ou mais [!UICONTROL signals].<br><br> [!DNL Boolean] expressões e operadores de comparação permitem criar [!UICONTROL trait] regras de qualificação. <br><br>Crie requisitos de qualificação precisos com combinações de grupos [!UICONTROL traits] e [!UICONTROL trait]. | A partir do [!UICONTROL signals] disponível, você pode criar uma regra de `High End Camera Browser` expressa como: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Usuários que compartilham um conjunto de atributos comuns e se qualificam para o [!UICONTROL traits] relacionado. [!DNL Boolean] expressões, juntamente com os requisitos de recenticidade/frequência, permitem criar [!UICONTROL segment] regras de qualificação.<br><br> Crie requisitos de qualificação precisos com combinações de regras [!UICONTROL trait] e [!UICONTROL segment]. | A partir dos [!UICONTROL traits] e [!UICONTROL signals] disponíveis, você pode criar uma regra de [!UICONTROL segment] expressa como:`(product=camera AND type=digital SLR) OR (price>1000)` |

Use o diagrama abaixo para manter uma anotação mental da relação entre [!UICONTROL signals], [!UICONTROL traits] e [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Regras da Compilação [!UICONTROL Traits] e [!UICONTROL Segment] com Ferramentas Visuais e Editores de Código**

Os clientes gerenciam o [!UICONTROL traits] e o [!UICONTROL segments] com ferramentas visuais e editores de código na interface do usuário do [!DNL Audience Manager]. As ferramentas visuais permitem criar regras usando recursos de pesquisa, opções pop-up, menus suspensos e a funcionalidade arrastar e soltar. Os editores de código fornecem aos usuários avançados uma maneira de desenvolver programaticamente critérios de segmentação de público-alvo.

**Chamadas de Evento Enviam Dados para[!DNL Audience Manager]**

Uma chamada de evento envia dados do seu site para [!DNL Audience Manager]. A chamada contém dados [!UICONTROL signal], [!UICONTROL trait] e [!UICONTROL segment] em uma solicitação [!DNL HTTP]. O evento em si é tudo depois da parte `/event` de uma cadeia de caracteres [!DNL URL]. Como mostrado no exemplo abaixo, esse processo requer apenas uma única chamada de evento para transmitir em múltiplas variáveis para [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmentos: finalidade, composição e regras](../features/segments/segments-purpose.md)
