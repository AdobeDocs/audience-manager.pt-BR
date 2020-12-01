---
description: Um destino de URL faz chamadas de pixel de uma página para seu destino. Siga estas instruções para criar um destino de URL com o Construtor de destinos.
seo-description: Um destino de URL faz chamadas de pixel de uma página para seu destino. Siga estas instruções para criar um destino de URL com o Construtor de destinos.
seo-title: Configurar um destino de URL
solution: Audience Manager
title: Configurar um destino de URL
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 3%

---



# Configurar um [!DNL URL Destination] {#configure-url-destination}

Um [!DNL URL destination] faz chamadas de pixel de uma página para seu [!DNL destination]. Siga estas instruções para criar um [!DNL URL] [!DNL destination] com [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Para criar um novo [!DNL URL] [!DNL destination], vá para **[!UICONTROL Audience Data > Destinations > Create New Destination]** e preencha as seções conforme descrito abaixo.

## Informações básicas {#basic-info}

Esta seção contém campos e opções que start o processo de criação [!DNL URL destination]. Para concluir esta seção:

1. Clique em **[!UICONTROL Basic Information]** para expor os controles.
2. Nomeie o [!DNL destination]. Evite abreviações e caracteres especiais.
3. *(Opcional)* Descreva o  [!DNL destination]. Uma descrição concisa é uma maneira eficaz de definir ou fornecer mais informações sobre um [!DNL destination].
4. Na lista **[!UICONTROL Category]**, escolha **[!UICONTROL Custom]**.
5. Na lista **[!UICONTROL Environment]**, selecione o ambiente no qual disparar [!DNL URL destination].
6. Na lista **[!UICONTROL Type]**, clique em **[!UICONTROL URL]**.
7. *(Opcional)* Selecione um  **[!UICONTROL Auto-fill Destination Mapping]**. As opções incluem:
   * **[!UICONTROL Segment ID]**: Adiciona e envia automaticamente a ID do segmento para o  [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: Adiciona e envia automaticamente o código de integração do segmento para o mapeamento de destino. O código de integração é um identificador exclusivo criado e usado pelo cliente. É limitado a 255 caracteres, no máximo.
8. Clique em **[!UICONTROL Next]** para ir para as configurações [!UICONTROL Configuration] ou clique em **[!UICONTROL Data Export Labels]** para aplicar controles de exportação a [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Esta seção contém opções que aplicam [controles de exportação de dados](../../features/data-export-controls.md) a um destino [!DNL URL]. Ignore esta etapa se você não usar controles de exportação de dados. Para concluir esta seção:

1. Clique em **[!UICONTROL Data Export Labels]** para expor os controles.
2. Selecione um rótulo que corresponda ao controle de exportação de dados aplicado ao destino (consulte [Adicionar rótulos de exportação a um destino](/help/using/features/destinations/add-data-export-labels.md) para obter detalhes).
3. Clique em **[!UICONTROL Save]**.

## Configuração {#configure-base-data}

Esta seção contém opções que permitem definir uma base [!DNL URL] e delimitadores de dados passados pela string [!DNL URL]. Esta seção é opcional. Para concluir esta seção:

1. Clique em **[!UICONTROL Configuration]** para expor os controles.
1. *(Opcional)* Marque a caixa de  **[!UICONTROL Serialize]** seleção.
Isso permite que você envie segmentos para um [!DNL destination] sequencialmente, em vez de fazer chamadas separadas para cada segmento. A serialização ajuda a tornar as transferências de dados eficientes. Marcar essa caixa de seleção expõe os campos URL e delimitador. Para obter mais informações, consulte [Pares padrão e pares de valores de chave serial](../../features/destinations/key-value-pairs.md).
1. Se você selecionar **[!UICONTROL Serialize]**, também deverá configurar os campos de URL e delimitador descritos abaixo.

| Campo | Descrição |
|--- |--- |
| [!UICONTROL Base URL] | A parte base de um padrão `HTTP` [!DNL URL] que não é alterado. Além disso, é necessário colocar a macro `%ALIAS%` [espaço reservado](../../features/destinations/destination-macros.md#destination-macros-defined) no URL base. Exemplo: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | A parte base de um `HTTPS` [!DNL URL] seguro que não é alterado. Além disso, você precisa colocar o `%ALIAS%`   [macro de espaço reservado](../../features/destinations/destination-macros.md#destination-macros-defined) no URL base. Exemplo: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | O símbolo que separa as variáveis de segmento na string [!DNL URL]. Geralmente é uma vírgula ou ponto-e-vírgula. Obtenha essas informações do seu parceiro de destino. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

Esta seção permite que você procure e adicione segmentos a [!UICONTROL destination]. Para concluir esta seção:

1. Clique em **[!UICONTROL Segment Mappings]** para expor os controles.
1. Na caixa **[!UICONTROL Search and Add Segments]**, o start que digita o nome de um segmento ou clica em **[!UICONTROL Browse All Segments]** procura uma lista de segmentos disponíveis.
1. Clique em **[!UICONTROL Add Selected Segments]** quando encontrar o segmento que deseja usar. Adicionar um segmento abre a janela [!UICONTROL Edit Mapping].
1. Em [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Forneça os pares de valor chave usados pelo segmento.
   * **[!UICONTROL Start Date]** e  **[!UICONTROL End Date]**: Escolha um start e uma data de término para o  [!DNL destination]. Se a data final estiver em branco, [!DNL destination] nunca expirará.
1. Clique em **[!UICONTROL Done]**.