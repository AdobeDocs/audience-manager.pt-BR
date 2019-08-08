---
description: Um destino de URL faz chamadas de pixel de uma página para o destino. Siga estas instruções para criar um destino de URL com o Construtor de destinos.
seo-description: Um destino de URL faz chamadas de pixel de uma página para o destino. Siga estas instruções para criar um destino de URL com o Construtor de destinos.
seo-title: Configurar um destino de URL
solution: Audience Manager
title: Configurar um destino de URL
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---



# Configurar um destino de URL {#configure-url-destination}

Um [!DNL URL] destino faz chamadas de pixel de uma página para o destino. Siga estas instruções para criar [!DNL URL] um destino.[!UICONTROL Destination Builder]

<!-- create-url-destination.xml -->

Para criar um novo [!DNL URL] destino, vá **[!UICONTROL Audience Data > Destinations > Create New Destination]** para e conclua as seções conforme descrito abaixo.

## Informações básicas {#basic-info}

Esta seção contém campos e opções que iniciam o processo de criação de destino do URL. Para concluir esta seção:

1. Clique **[!UICONTROL Basic Information]** em para expor os controles.
2. Dê um nome ao destino. Evite abreviações e caracteres especiais.
3. *(Opcional)* Descreva o destino. Uma descrição concisa é uma maneira eficaz de definir ou fornecer mais informações sobre um destino.
4. Na **[!UICONTROL Category]** lista, escolha **[!UICONTROL Custom]**.
5. Na **[!UICONTROL Environment]** lista, selecione o ambiente no qual acionar o destino do URL.
6. Na **[!UICONTROL Type]** lista, clique **[!UICONTROL URL]** em.
7. *(Opcional)* Selecione um **[!UICONTROL Auto-fill Destination Mapping]**. As opções incluem:
   * **[!UICONTROL Segment ID]**: Adiciona e envia automaticamente a ID do segmento para o destino.
   * **[!UICONTROL Integration Code Value]**: Adiciona e envia automaticamente o código de integração do segmento para o mapeamento de destino. O código de integração é um identificador exclusivo criado e utilizado pelo cliente. É limitada a 255 caracteres, máximo.
8. Clique **[!UICONTROL Next]** em para acessar as [!UICONTROL Configuration] configurações ou clique **[!UICONTROL Data Export Labels]** para aplicar os controles de exportação ao destino.

## Rótulos de exportação de dados {#data-export-labels-dest}

Esta seção contém opções que aplicam [controles de exportação de dados](../../features/data-export-controls.md) para um [!DNL URL] destino. Pule esta etapa se você não usar controles de exportação de dados. Para concluir esta seção:

1. Clique **[!UICONTROL Data Export Labels]** em para expor os controles.
2. Selecione uma etiqueta que corresponda ao controle de exportação de dados aplicado ao destino (consulte [Adicionar rótulos de exportação a um destino](/help/using/features/destinations/add-data-export-labels.md) para obter detalhes).
3. Clique em **[!UICONTROL Save]**.

## Configuração {#configure-base-data}

Esta seção contém opções que permitem definir uma base [!DNL URL] e delimitadores de dados passados pela sequência de [!DNL URL] caracteres. Esta seção é opcional. Para concluir esta seção:

1. Clique **[!UICONTROL Configuration]** em para expor os controles.
1. *(Opcional)* Marque a caixa **[!UICONTROL Serialize]** de seleção.
Isso permite que você envie segmentos para um destino sequencialmente, em vez de fazer chamadas separadas para cada segmento. A serialização ajuda a tornar as transferências de dados eficientes. Marcar essa caixa de seleção expõe os campos de URL e delimitador. Para obter mais informações, consulte [Pares de valores chave e serial-value](../../features/destinations/key-value-pairs.md).
1. Se você selecionar **[!UICONTROL Serialize]**, também deverá configurar os campos URL e delimitador descritos abaixo.

| Campo | Descrição |
|--- |--- |
| URL básica | A parte básica de um padrão `HTTP`[!DNL URL] que não muda. Além disso, é necessário colocar a macro `%ALIAS%`[do espaço reservado](../../features/destinations/destination-macros.md#destination-macros-defined) no URL base. Exemplo: `https://www.myCompany.com/%alias%...` |
| URL seguro | A parte básica de uma segurança que `HTTPS`[!DNL URL] não muda. Além disso, é necessário colocar a macro `%ALIAS%`[do espaço reservado](../../features/destinations/destination-macros.md#destination-macros-defined) no URL base. Exemplo: `https://www.myCompany.com/%alias%...` |
| Delimitador | O símbolo que separa as variáveis de segmento na [!DNL URL] string. Normalmente, é uma vírgula ou ponto-e-vírgula. Obtenha essas informações do parceiro de destino. |

## Mapeamentos de segmento {#segment-mappings}

Esta seção permite pesquisar e adicionar segmentos ao destino. Para concluir esta seção:

1. Clique **[!UICONTROL Segment Mappings]** em para expor os controles.
1. Na **[!UICONTROL Search and Add Segments]** caixa, comece digitando o nome de um segmento ou clique **[!UICONTROL Browse All Segments]** em uma lista de segmentos disponíveis.
1. Clique **[!UICONTROL Add Selected Segments]** em quando encontrar o segmento que deseja usar. A adição de um segmento abre a [!UICONTROL Edit Mapping] janela.
1. Em [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Forneça os pares de valores chave usados pelo segmento.
   * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: Escolha uma data de início e fim para o destino. Se a data final estiver em branco, o destino nunca expirará.
1. Clique em **[!UICONTROL Done]**.