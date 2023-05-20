---
description: Um destino de URL faz chamadas de pixel de uma página para o seu destino. Siga estas instruções para criar um destino de URL com o Construtor de destinos.
seo-description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-title: Configure a URL Destination
solution: Audience Manager
title: Configurar um destino de URL
feature: Destination Basics
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 3%

---

# Configurar um [!DNL URL Destination] {#configure-url-destination}

A [!DNL URL destination] O faz chamadas de pixel de uma página para a sua [!DNL destination]. Siga estas instruções para criar um [!DNL URL] [!DNL destination] com [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Para criar um novo [!DNL URL] [!DNL destination], vá para **[!UICONTROL Audience Data > Destinations > Create New Destination]** e preencha as seções conforme descrito abaixo.

## Informações básicas {#basic-info}

Esta seção contém campos e opções que iniciam a variável [!DNL URL destination] processo de criação. Para concluir esta seção:

1. Clique em **[!UICONTROL Basic Information]** para expor os controles.
2. Nomeie o [!DNL destination]. Evite abreviações e caracteres especiais.
3. *(Opcional)* Descreva a [!DNL destination]. Uma descrição concisa é uma maneira eficaz de definir ou fornecer mais informações sobre uma [!DNL destination].
4. No **[!UICONTROL Category]** escolha **[!UICONTROL Custom]**.
5. No **[!UICONTROL Environment]** selecione o ambiente no qual acionar a variável [!DNL URL destination].
6. No **[!UICONTROL Type]** clique em **[!UICONTROL URL]**.
7. *(Opcional)* Selecione um **[!UICONTROL Auto-fill Destination Mapping]**. As opções incluem:
   * **[!UICONTROL Segment ID]**: adiciona e envia automaticamente a ID do segmento para a [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: adiciona e envia automaticamente o código de integração de segmento para o mapeamento de destino. O código de integração é um identificador exclusivo criado e usado pelo cliente. É limitado a 255 caracteres, no máximo.
8. Clique em **[!UICONTROL Next]** para acessar o [!UICONTROL Configuration] ou clique em **[!UICONTROL Data Export Labels]** para aplicar controles de exportação à [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Esta seção contém opções que se aplicam [controles de exportação de dados](../../features/data-export-controls.md) para um [!DNL URL] destino. Ignore esta etapa se não usar controles de exportação de dados. Para concluir esta seção:

1. Clique em **[!UICONTROL Data Export Labels]** para expor os controles.
2. Selecione um rótulo que corresponda ao controle de exportação de dados aplicado ao destino (consulte [Adicionar rótulos de exportação a um destino](/help/using/features/destinations/add-data-export-labels.md) para obter detalhes).
3. Clique em **[!UICONTROL Save]**.

## Configuração {#configure-base-data}

Esta seção contém opções que permitem definir uma base [!DNL URL] e delimitadores de dados transmitidos pelo [!DNL URL] string. Esta seção é opcional. Para concluir esta seção:

1. Clique em **[!UICONTROL Configuration]** para expor os controles.
1. *(Opcional)* Selecione o **[!UICONTROL Serialize]** caixa de seleção
Isso permite enviar segmentos para um [!DNL destination] em vez de fazer chamadas separadas para cada segmento. A serialização ajuda a tornar as transferências de dados eficientes. Selecionar essa caixa de seleção expõe os campos URL e delimitador. Para obter mais informações, consulte [Pares padrão e de valor-chave serial](../../features/destinations/key-value-pairs.md).
1. Se você selecionar **[!UICONTROL Serialize]**, você também deve configurar os campos URL e delimitador descritos abaixo.

| Campo | Descrição |
|--- |--- |
| [!UICONTROL Base URL] | A parte base de um padrão `HTTP` [!DNL URL] isso não muda. Além disso, é necessário colocar a variável `%ALIAS%`  [macro de espaço reservado](../../features/destinations/destination-macros.md#destination-macros-defined) no URL base. Exemplo: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | A parte de base de um seguro `HTTPS` [!DNL URL] isso não muda. Além disso, é necessário colocar a variável `%ALIAS%`   [macro de espaço reservado](../../features/destinations/destination-macros.md#destination-macros-defined) no URL base. Exemplo: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | O símbolo que separa as variáveis de segmento na variável [!DNL URL] string. Normalmente, é uma vírgula ou ponto e vírgula. Obtenha essas informações com seu parceiro de destino. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

Esta seção permite procurar e adicionar segmentos ao seu [!UICONTROL destination]. Para concluir esta seção:

1. Clique em **[!UICONTROL Segment Mappings]** para expor os controles.
1. No **[!UICONTROL Search and Add Segments]** digite o nome de um segmento ou clique em **[!UICONTROL Browse All Segments]** procure uma lista de segmentos disponíveis.
1. Clique em **[!UICONTROL Add Selected Segments]** quando você encontra o segmento que deseja usar. A adição de um segmento abre a [!UICONTROL Edit Mapping] janela.
1. Em [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: forneça os pares de valores chave usados pelo segmento.
   * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: escolha uma data de início e término para a variável [!DNL destination]. Se a data final estiver em branco, a variável [!DNL destination] nunca expira.
1. Clique em **[!UICONTROL Done]**.
