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



# Configure um [!DNL URL Destination] {#configure-url-destination}

Um [!DNL URL destination] faz chamadas de pixel de uma página para o seu [!DNL destination]. Siga estas instruções para criar um [!DNL URL] com [!DNL destination] [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Para criar um novo [!DNL URL] , vá até [!DNL destination]**[!UICONTROL Audience Data > Destinations > Create New Destination]** as seções e preencha-as conforme descrito abaixo.

## Informações básicas {#basic-info}

Esta seção contém campos e opções que start o processo de [!DNL URL destination] criação. Para concluir esta seção:

1. Clique **[!UICONTROL Basic Information]** para expor os controles.
2. Dê um nome ao [!DNL destination]. Evite abreviações e caracteres especiais.
3. *(Opcional)* Descreva o [!DNL destination]. Uma descrição concisa é uma maneira eficaz de definir ou fornecer mais informações sobre uma [!DNL destination].
4. Na **[!UICONTROL Category]** lista, escolha **[!UICONTROL Custom]**.
5. Na **[!UICONTROL Environment]** lista, selecione o ambiente no qual deseja acionar o [!DNL URL destination].
6. Na **[!UICONTROL Type]** lista, clique em **[!UICONTROL URL]**.
7. *(Opcional)* Selecione um **[!UICONTROL Auto-fill Destination Mapping]**. As opções incluem:
   * **[!UICONTROL Segment ID]**: Adiciona e envia automaticamente a ID do segmento para o [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: Adiciona e envia automaticamente o código de integração do segmento para o mapeamento de destino. O código de integração é um identificador exclusivo criado e usado pelo cliente. É limitado a 255 caracteres, no máximo.
8. Clique **[!UICONTROL Next]** para ir para as [!UICONTROL Configuration] configurações ou clique **[!UICONTROL Data Export Labels]** para aplicar os controles de exportação ao [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Esta seção contém opções que aplicam controles [de exportação de](../../features/data-export-controls.md) dados a um [!DNL URL] destino. Ignore esta etapa se você não usar controles de exportação de dados. Para concluir esta seção:

1. Clique **[!UICONTROL Data Export Labels]** para expor os controles.
2. Selecione um rótulo que corresponda ao controle de exportação de dados aplicado ao destino (consulte [Adicionar rótulos de exportação a um destino](/help/using/features/destinations/add-data-export-labels.md) para obter detalhes).
3. Clique em **[!UICONTROL Save]**.

## Configuração {#configure-base-data}

Esta seção contém opções que permitem definir uma base [!DNL URL] e delimitadores de dados passados pela [!DNL URL] string. Esta seção é opcional. Para concluir esta seção:

1. Clique **[!UICONTROL Configuration]** para expor os controles.
1. *(Opcional)* Marque a caixa de **[!UICONTROL Serialize]** seleção.
Isso permite que você envie segmentos para uma [!DNL destination] sequência em vez de realizar chamadas separadas para cada segmento. A serialização ajuda a tornar as transferências de dados eficientes. Marcar essa caixa de seleção expõe os campos URL e delimitador. Para obter mais informações, consulte Pares [](../../features/destinations/key-value-pairs.md)padrão e pares de valores chave serial.
1. Se você selecionar **[!UICONTROL Serialize]**, também deverá configurar os campos de URL e delimitador descritos abaixo.

| Campo | Descrição |
|--- |--- |
| [!UICONTROL Base URL] | A parte base de um padrão `HTTP` [!DNL URL] que não muda. Além disso, é necessário colocar a macro `%ALIAS%` de [](../../features/destinations/destination-macros.md#destination-macros-defined) espaço reservado no URL base. Exemplo: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | A parte base de um seguro `HTTPS` [!DNL URL] que não muda. Além disso, é necessário colocar a macro `%ALIAS%` de [](../../features/destinations/destination-macros.md#destination-macros-defined) espaço reservado no URL base. Exemplo: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | O símbolo que separa as variáveis de segmento na [!DNL URL] string. Geralmente é uma vírgula ou ponto-e-vírgula. Obtenha essas informações do seu parceiro de destino. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

Esta seção permite que você procure e adicione segmentos à sua [!UICONTROL destination]. Para concluir esta seção:

1. Clique **[!UICONTROL Segment Mappings]** para expor os controles.
1. Na **[!UICONTROL Search and Add Segments]** caixa, start que digita o nome de um segmento ou clique em **[!UICONTROL Browse All Segments]** navegar em uma lista de segmentos disponíveis.
1. Clique **[!UICONTROL Add Selected Segments]** quando encontrar o segmento que deseja usar. Adicionar um segmento abre a [!UICONTROL Edit Mapping] janela.
1. Em [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Forneça os pares de valor chave usados pelo segmento.
   * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: Escolha um start e uma data de término para o [!DNL destination]. Se a data de término estiver em branco, a data [!DNL destination] nunca expirará.
1. Clique em **[!UICONTROL Done]**.