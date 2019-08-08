---
description: Um destino de cookie retorna e grava dados em um cookie no navegador do usuário. O cookie contém dados que podem ser lidos por outras plataformas que têm acesso à página. Siga estas instruções para criar um destino de cookie com [! Construtor de destino UICONTROL].
seo-description: Um destino de cookie retorna e grava dados em um cookie no navegador do usuário. O cookie contém dados que podem ser lidos por outras plataformas que têm acesso à página. Siga estas instruções para criar um destino de cookie com [! Construtor de destino UICONTROL].
seo-title: Configurar um destino do cookie
solution: Audience Manager
title: Configurar um destino do cookie
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# Configurar um destino do cookie {#create-cookie-destination}

Um destino de cookie retorna e grava dados em um cookie no navegador do usuário. O cookie contém dados que podem ser lidos por outras plataformas que têm acesso à página. Siga estas instruções para criar um destino de cookie com [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Para criar um novo destino de cookie, vá **[!UICONTROL Audience Data > Destinations > Create New Destination]** para e conclua as seções conforme descrito abaixo.

## Informações básicas {#basic-information}

Esta seção contém campos e opções que iniciam o processo de criação de destino do cookie. Para concluir esta seção:

1. Clique **[!UICONTROL Basic Information]** em para expor os controles.
2. Dê um nome ao destino. Evite abreviações e caracteres especiais.
3. *(Opcional)* Descreva o destino. Uma descrição concisa é uma maneira eficaz de definir ou fornecer mais informações sobre um destino.
4. Na **[!UICONTROL Category]** lista, escolha **[!UICONTROL Custom]**.
5. Na **[!UICONTROL Environment]** lista, selecione **[!UICONTROL Browser]**. Não é possível configurar destinos de cookies para ambientes móveis nativos, como aplicativos Android ou iOS.
6. Na **[!UICONTROL Type]** lista, clique **[!UICONTROL Cookie]** em.
7. *(Opcional)* Selecione um **[!UICONTROL Auto-fill Destination Mapping]**. As opções incluem:
   * **[!UICONTROL Segment ID]**: Adiciona e envia automaticamente a ID do segmento para o destino.
   * **[!UICONTROL Integration Code Value]**: Adiciona e envia automaticamente o código de integração do segmento para o mapeamento de destino. O código de integração é um identificador exclusivo criado e utilizado pelo cliente. É limitada a 255 caracteres, máximo.
8. Clique **[!UICONTROL Next]** em para acessar as [!UICONTROL Configuration] configurações ou clique **[!UICONTROL Data Export Labels]** para aplicar os controles de exportação ao destino.

## Rótulos de exportação de dados {#data-export-labels-cookies}

Esta seção contém opções que aplicam [controles de exportação de dados](../../features/data-export-controls.md) para um destino de cookie. Pule esta etapa se você não usar controles de exportação de dados. Para concluir esta seção:

1. Clique **[!UICONTROL Data Export Labels]** em para expor os controles.
2. Selecione um rótulo que corresponda ao controle de exportação de dados aplicado ao destino (consulte [Adicionar rótulos de exportação a um destino](/help/using/features/destinations/add-data-export-labels.md) para obter detalhes).
3. Clique em **[!UICONTROL Save]**.

## Configuração {#configuration}

Esta seção contém campos e opções que permitem configurar o cookie para o destino.

>[!NOTE]
>
>[!DNL Audience Manager] codifica dados gravados no cookie de destino. Por exemplo, os espaços são codificados como `%20` e pontos-e-vírgulas são codificados como `%3B`.

Para concluir esta seção:

1. Clique **[!UICONTROL Configuration]** para expor os controles
1. Nomeie o cookie. Evite abreviações e caracteres especiais.
1. Escolha uma opção de formato de dados. Essas opções permitem escolher os delimitadores e separadores para os pares de valores chave que enviam dados de segmento para um destino. As opções de formato incluem:
   * **Chave única:** Permite definir a chave em um par de valor chave. Você definirá o valor depois de selecionar um segmento na [!UICONTROL Segment Mappings] seção abaixo.
   * **Várias chaves:** Permite definir a chave e o valor para um par de valor chave. Você criará o par de valor chave depois de selecionar um segmento na seção Mapeamentos de segmento abaixo.
Consulte [Pares de valores chave e serial-value](../../features/destinations/key-value-pairs.md) para obter mais informações sobre esses elementos de dados.
1. Clique em **[!UICONTROL Save]**.

Todas as outras configurações são opcionais. Para obter mais informações sobre as **[!UICONTROL Cookie Domain]** configurações e **[!UICONTROL Publish data to]** as configurações, consulte [Configurações opcionais para destinos](/help/using/features/destinations/cookie-destination-options.md)de cookies.

## Mapeamentos de segmento {#segments-mapping}

Esta seção permite pesquisar e adicionar segmentos ao destino. Para concluir esta seção:

1. Clique **[!UICONTROL Segment Mappings]** em para expor os controles.
1. Na **[!UICONTROL Search and Add Segments]** caixa, comece digitando o nome de um segmento ou clique **[!UICONTROL Browse All Segments]** para procurar uma lista de segmentos disponíveis.
1. Clique **[!UICONTROL Add Selected Segments]** em quando encontrar o segmento que deseja usar. A adição de um segmento abre a [!UICONTROL Edit Mapping] janela.
1. Na caixa de [!UICONTROL Edit Mapping] diálogo:
   * **[!UICONTROL Mapping]** permite definir um valor para a chave especificada na seção Configuração acima.
   * **[!UICONTROL Publish from]** permite definir a data de início e fim do destino. Se a data final estiver em branco, o destino nunca expirará.
1. Clique em **[!UICONTROL Save]**.
1. Clique em **[!UICONTROL Done]**.