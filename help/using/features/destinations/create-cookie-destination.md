---
description: Um destino de cookie retorna e grava dados em um cookie no navegador do usuário. O cookie contém dados que podem ser lidos por outras plataformas com acesso à página. Siga estas instruções para criar um destino de cookie com [!UICONTROL Destination Builder].
seo-description: A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].
seo-title: Configure a Cookie Destination
solution: Audience Manager
title: Configurar um destino de cookie
feature: Destination Basics
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 1%

---

# Configurar um destino de cookie {#create-cookie-destination}

Um destino de cookie retorna e grava dados em um cookie no navegador do usuário. O cookie contém dados que podem ser lidos por outras plataformas com acesso à página. Siga estas instruções para criar um destino de cookie com [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Para criar um novo destino de cookie, vá para **[!UICONTROL Audience Data > Destinations > Create New Destination]** e conclua as seções conforme descrito abaixo.

## Informações básicas {#basic-information}

Esta seção contém campos e opções que iniciam o processo de criação do destino de cookie. Para concluir esta seção:

1. Clique em **[!UICONTROL Basic Information]** para expor os controles.
2. Nomeie o destino. Evite abreviações e caracteres especiais.
3. *(Opcional)* Descreva o destino. Uma descrição concisa é uma maneira eficaz de definir ou fornecer mais informações sobre um destino.
4. Na lista **[!UICONTROL Category]**, escolha **[!UICONTROL Custom]**.
5. Na lista **[!UICONTROL Environment]**, selecione **[!UICONTROL Browser]**. Não é possível configurar destinos de cookies para ambientes móveis nativos, como aplicativos Android ou iOS.
6. Na lista **[!UICONTROL Type]**, clique em **[!UICONTROL Cookie]**.
7. *(Opcional)* Selecione um **[!UICONTROL Auto-fill Destination Mapping]**. As opções incluem:
   * **[!UICONTROL Segment ID]**: adiciona e envia automaticamente a ID do segmento para o destino.
   * **[!UICONTROL Integration Code Value]**: adiciona e envia automaticamente o código de integração do segmento para o mapeamento de destino. O código de integração é um identificador exclusivo criado e usado pelo cliente. É limitado a 255 caracteres, no máximo.
8. Clique em **[!UICONTROL Next]** para ir para as configurações de [!UICONTROL Configuration] ou clique em **[!UICONTROL Data Export Labels]** para aplicar controles de exportação ao destino.

## Rótulos de exportação de dados {#data-export-labels-cookies}

Esta seção contém opções que aplicam [controles de exportação de dados](../../features/data-export-controls.md) a um destino de cookie. Ignore esta etapa se não usar controles de exportação de dados. Para concluir esta seção:

1. Clique em **[!UICONTROL Data Export Labels]** para expor os controles.
2. Selecione um rótulo que corresponda ao controle de exportação de dados aplicado ao destino (consulte [Adicionar rótulos de exportação a um destino](/help/using/features/destinations/add-data-export-labels.md) para obter detalhes).
3. Clique em **[!UICONTROL Save]**.

## Configuração {#configuration}

Esta seção contém campos e opções que permitem configurar o cookie para o seu destino.

>[!NOTE]
>
>[!DNL Audience Manager] codifica dados gravados no cookie de destino. Por exemplo, os espaços são codificados como `%20` e os pontos-e-vírgulas são codificados como `%3B`.

Para concluir esta seção:

1. Clique em **[!UICONTROL Configuration]** para expor os controles
1. Nomeie o cookie. Evite abreviações e caracteres especiais.
1. Escolha uma opção de formato de dados. Essas opções permitem escolher os delimitadores e separadores para os pares de valores chave que enviam dados de segmento para um destino. As opções de formato incluem:
   * **Chave única:** Permite que você defina a chave em um par de valor-chave. Você definirá o valor depois de selecionar um segmento na seção [!UICONTROL Segment Mappings] abaixo.
   * **Chave múltipla:** Permite definir a chave e o valor de um par de valor-chave. Você criará o par de valor-chave depois de selecionar um segmento na seção Mapeamentos de segmento abaixo.
Consulte [Pares padrão e de valor-chave serial](../../features/destinations/key-value-pairs.md) para obter mais informações sobre esses elementos de dados.
1. Clique em **[!UICONTROL Save]**.

Todas as outras configurações são opcionais. Para obter mais informações sobre as configurações de **[!UICONTROL Cookie Domain]** e **[!UICONTROL Publish data to]**, consulte [Configurações Opcionais para Destinos de Cookies](/help/using/features/destinations/cookie-destination-options.md).

## Mapeamentos de segmentos {#segments-mapping}

Esta seção permite procurar e adicionar segmentos ao seu destino. Para concluir esta seção:

1. Clique em **[!UICONTROL Segment Mappings]** para expor os controles.
1. Na caixa **[!UICONTROL Search and Add Segments]**, comece digitando o nome de um segmento ou clique em **[!UICONTROL Browse All Segments]** para procurar uma lista de segmentos disponíveis.
1. Clique em **[!UICONTROL Add Selected Segments]** quando encontrar o segmento que deseja usar. Adicionar um segmento abre a janela [!UICONTROL Edit Mapping].
1. No diálogo [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mapping]** permite que você defina um valor para a chave especificada na seção Configuração acima.
   * **[!UICONTROL Publish from]** permite que você defina as datas de início e término para o destino. Se a data final estiver em branco, o destino nunca expirará.
1. Clique em **[!UICONTROL Save]**.
1. Clique em **[!UICONTROL Done]**.
