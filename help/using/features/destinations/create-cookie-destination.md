---
description: Um destino de cookie retorna e grava dados em um cookie no navegador do usuário. O cookie contém dados que podem ser lidos por outras plataformas que têm acesso à página. Siga estas instruções para criar um destino de cookie com [!UICONTROL Destination Builder].
seo-description: Um destino de cookie retorna e grava dados em um cookie no navegador do usuário. O cookie contém dados que podem ser lidos por outras plataformas que têm acesso à página. Siga estas instruções para criar um destino de cookie com [!UICONTROL Destination Builder].
seo-title: Configurar um destino de cookie
solution: Audience Manager
title: Configurar um destino de cookie
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 3%

---


# Configurar um destino de cookie {#create-cookie-destination}

Um destino de cookie retorna e grava dados em um cookie no navegador do usuário. O cookie contém dados que podem ser lidos por outras plataformas que têm acesso à página. Siga estas instruções para criar um destino de cookie com [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Para criar um novo destino de cookie, vá até **[!UICONTROL Audience Data > Destinations > Create New Destination]** e preencha as seções conforme descrito abaixo.

## Informações básicas {#basic-information}

Esta seção contém campos e opções que start o processo de criação de destino do cookie. Para concluir esta seção:

1. Clique em **[!UICONTROL Basic Information]** para expor os controles.
2. Nomeie o destino. Evite abreviações e caracteres especiais.
3. *(Opcional)* Descreva o destino. Uma descrição concisa é uma maneira eficaz de definir ou fornecer mais informações sobre um destino.
4. Na lista **[!UICONTROL Category]**, escolha **[!UICONTROL Custom]**.
5. Na lista **[!UICONTROL Environment]**, selecione **[!UICONTROL Browser]**. Não é possível configurar destinos de cookies para ambientes móveis nativos, como aplicativos Android ou iOS.
6. Na lista **[!UICONTROL Type]**, clique em **[!UICONTROL Cookie]**.
7. *(Opcional)* Selecione um  **[!UICONTROL Auto-fill Destination Mapping]**. As opções incluem:
   * **[!UICONTROL Segment ID]**: Adiciona e envia automaticamente a ID do segmento para o destino.
   * **[!UICONTROL Integration Code Value]**: Adiciona e envia automaticamente o código de integração do segmento para o mapeamento de destino. O código de integração é um identificador exclusivo criado e usado pelo cliente. É limitado a 255 caracteres, no máximo.
8. Clique em **[!UICONTROL Next]** para ir para as configurações [!UICONTROL Configuration] ou clique em **[!UICONTROL Data Export Labels]** para aplicar controles de exportação ao destino.

## Rótulos de exportação de dados {#data-export-labels-cookies}

Esta seção contém opções que aplicam [controles de exportação de dados](../../features/data-export-controls.md) a um destino de cookie. Ignore esta etapa se você não usar controles de exportação de dados. Para concluir esta seção:

1. Clique em **[!UICONTROL Data Export Labels]** para expor os controles.
2. Selecione um rótulo que corresponda ao controle de exportação de dados aplicado ao destino (consulte [Adicionar rótulos de exportação a um destino](/help/using/features/destinations/add-data-export-labels.md) para obter detalhes).
3. Clique em **[!UICONTROL Save]**.

## Configuração {#configuration}

Esta seção contém campos e opções que permitem configurar o cookie para seu destino.

>[!NOTE]
>
>[!DNL Audience Manager] codifica dados gravados no cookie de destino. Por exemplo, os espaços são codificados como `%20` e os pontos-e-vírgulas são codificados como `%3B`.

Para concluir esta seção:

1. Clique em **[!UICONTROL Configuration]** para expor os controles
1. Dê um nome ao cookie. Evite abreviações e caracteres especiais.
1. Escolha uma opção de formato de dados. Essas opções permitem escolher os delimitadores e separadores para os pares de valores chave que enviam dados de segmento para um destino. As opções de formato incluem:
   * **Tecla única:** permite definir a chave em um par de valor chave. Você definirá o valor depois de selecionar um segmento na seção [!UICONTROL Segment Mappings] abaixo.
   * **Várias teclas:** Permite definir a chave e o valor de um par de valores chave. Você criará o par de valores chave depois de selecionar um segmento na seção Mapeamentos de segmentos abaixo.
Consulte [Pares padrão e de valores de chave serial](../../features/destinations/key-value-pairs.md) para obter mais informações sobre esses elementos de dados.
1. Clique em **[!UICONTROL Save]**.

Todas as outras configurações são opcionais. Para obter mais informações sobre as configurações **[!UICONTROL Cookie Domain]** e **[!UICONTROL Publish data to]**, consulte [Configurações opcionais para destinos de cookies](/help/using/features/destinations/cookie-destination-options.md).

## Mapeamentos de segmentos {#segments-mapping}

Esta seção permite que você procure e adicione segmentos ao seu destino. Para concluir esta seção:

1. Clique em **[!UICONTROL Segment Mappings]** para expor os controles.
1. Na caixa **[!UICONTROL Search and Add Segments]**, start digitando o nome de um segmento ou clique em **[!UICONTROL Browse All Segments]** para navegar por uma lista de segmentos disponíveis.
1. Clique em **[!UICONTROL Add Selected Segments]** quando encontrar o segmento que deseja usar. Adicionar um segmento abre a janela [!UICONTROL Edit Mapping].
1. Na caixa de diálogo [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mapping]** permite definir um valor para a chave especificada na seção Configuração acima.
   * **[!UICONTROL Publish from]** permite definir a data de start e de término para o destino. Se a data final estiver em branco, o destino nunca expirará.
1. Clique em **[!UICONTROL Save]**.
1. Clique em **[!UICONTROL Done]**.