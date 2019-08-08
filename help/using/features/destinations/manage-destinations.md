---
description: A página inicial de Destino lista todos os destinos de URL, cookie e servidor para servidor. Ele fornece recursos que permitem criar, editar, pesquisar e gerar relatórios sobre destinos. A página de aterrissagem está localizada em Dados de público-alvo > Destinos.
seo-description: A página inicial de Destino lista todos os destinos de URL, cookie e servidor para servidor. Ele fornece recursos que permitem criar, editar, pesquisar e gerar relatórios sobre destinos. A página de aterrissagem está localizada em Dados de público-alvo > Destinos.
seo-title: Gerenciar destinos
solution: Audience Manager
title: Gerenciar destinos
uuid: 6 b 66 ff 42-0075-49 a 7-a 58 f -7 f 8 ea 2295 fdc
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# Gerenciar destinos {#manage-destinations}

A página [!UICONTROL Destination] de aterrissagem lista todos os destinos [!DNL URL], cookies e destinos de servidor a servidor. Ele fornece recursos que permitem criar, editar, pesquisar e gerar relatórios sobre destinos. A página de aterrissagem **[!UICONTROL Audience Data > Destinations]** está localizada.

## Página de aterrissagem padrão {#default-landing-page}

<!-- destinations-home.xml -->

A página de aterrissagem padrão lista seus destinos, com base no tipo. É possível filtrar os destinos usando as quatro guias disponíveis:

* **Todos**: mostra todos os tipos de destinos.
* **Adobe Experience Cloud**: mostra destinos que enviam dados para outras soluções da Adobe Experience Cloud. Atualmente, a única opção suportada é o Adobe Analytics. See [Configure an Analytics Destination](/help/using/features/destinations/create-analytics-destination.md).
* **Plataformas integradas**: mostra destinos baseados em pessoas e baseados em dispositivos (também nomes de servidor a servidor). Observe que os destinos baseados em pessoas atualmente são um recurso beta apenas disponível para clientes selecionados.
* **Personalizado**: mostra os destinos de cookie e URL.


![](assets/destinations-landing.png)

## Página de aterrissagem de Públicos-alvo endereçáveis {#audiences-landing-page}

Selecione **[!UICONTROL Integrated Platforms > Device-Based]** os dados do público-alvo e as taxas de correspondência do destino do servidor a servidor.

Para obter mais informações sobre as informações exibidas, consulte [Interface de públicos-alvo endereçáveis](/help/using/features/addressable-audiences.md#addressable-audience-interface).

![](/help/using/features/assets/addressable-audiences-landing.png)

## Configurar um destino de URL {#configure-url-destination}

Um [!DNL URL] destino faz chamadas de pixel de uma página para o destino. Siga estas instruções para criar [!DNL URL] um destino.[!UICONTROL Destination Builder]

<!-- create-url-destination.xml -->

Para criar um novo [!DNL URL] destino, vá **[!UICONTROL Audience Data > Destinations > Create New Destination]** para e conclua as seções conforme descrito abaixo.

### Informações básicas {#basic-info}

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

### Rótulos de exportação de dados {#data-export-labels-dest}

Esta seção contém opções que aplicam [controles de exportação de dados](../../features/data-export-controls.md) para um [!DNL URL] destino. Pule esta etapa se você não usar controles de exportação de dados. Para concluir esta seção:

1. Clique **[!UICONTROL Data Export Labels]** em para expor os controles.
2. Selecione uma etiqueta que corresponda ao controle de exportação de dados aplicado ao destino (consulte [Adicionar rótulos de exportação a um destino](../../features/destinations/manage-destinations.md#add-data-export-labels) para obter detalhes).
3. Clique em **[!UICONTROL Save]**.

### Configuração {#configure-base-data}

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

### Mapeamentos de segmento {#segment-mappings}

Esta seção permite pesquisar e adicionar segmentos ao destino. Para concluir esta seção:

1. Clique **[!UICONTROL Segment Mappings]** em para expor os controles.
1. Na **[!UICONTROL Search and Add Segments]** caixa, comece digitando o nome de um segmento ou clique **[!UICONTROL Browse All Segments]** em uma lista de segmentos disponíveis.
1. Clique **[!UICONTROL Add Selected Segments]** em quando encontrar o segmento que deseja usar. A adição de um segmento abre a [!UICONTROL Edit Mapping] janela.
1. Em [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Forneça os pares de valores chave usados pelo segmento.
   * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: Escolha uma data de início e fim para o destino. Se a data final estiver em branco, o destino nunca expirará.
1. Clique em **[!UICONTROL Done]**.

## Adicionar ou editar segmentos para destinos de servidor a servidor {#add-edit-segments}

Você pode adicionar ou editar segmentos para um destino servidor-to-server ([!DNL S2S]). Não é possível criar [!DNL S2S] destinos com [!UICONTROL Destination Builder]. Entre em contato com seu consultor para configurar [!DNL S2S] destinos. Siga estas instruções para adicionar ou editar segmentos para [!DNL S2S] um destino.

<!-- destination-s2s-edit.xml -->

Para adicionar ou editar mapeamentos de segmento para [!DNL S2S] um destino:

1. Ir **[!UICONTROL Audience Data > Destinations]** para. Selecione **Plataformas integradas &gt; Baseado em dispositivo** e localize [!DNL S2S] o destino com o qual deseja trabalhar.
2. Na [!UICONTROL Action] coluna, clique no ícone de lápis para editar o destino.
   * Na **[!UICONTROL Search and Add Segments]** caixa, comece digitando o nome de um segmento ou clique **[!UICONTROL Browse All Segments]** em uma lista de segmentos disponíveis.
   * Clique **[!UICONTROL Add Selected Segments]** em quando encontrar o segmento que deseja usar. A adição de um segmento abre a [!UICONTROL Edit Mapping] janela.
   * Em [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Defina um valor para o par [de valor chave](../../features/destinations/key-value-pairs.md) usado por esse destino.
      * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: Escolha uma data de início e fim para o destino. Se a data final estiver em branco, o destino nunca expirará.
3. Clique **[!UICONTROL Save]** em e **[!UICONTROL Done]** em.

## Adicionar rótulos de exportação de dados a um destino {#add-data-export-labels}

[!DNL Data Export Labels] trabalhar com o [!DNL Export Controls] conjunto definido em uma fonte de dados. [!DNL Data Export Labels] impedir que você adicione traços restritos a um segmento e envie dados de segmento para um destino. É possível definir vários rótulos de exportação para um novo [!DNL cookie][!DNL URL] ou existente ou destino.

>[!NOTE]
>
>Para adicionar um rótulo de exportação, você precisa de permissões *de administrador ou* de privilégios suficientes para criar ou editar um destino.

<!-- t_export_labels.xml -->

Para adicionar rótulos de exportação a um destino:

1. Clique em **[!UICONTROL Audience Data]**:
   * Para novos destinos: Clique **[!UICONTROL Create New Destination]** em. Preencha a [!UICONTROL Basic Information] seção antes de selecionar um rótulo de exportação de dados. Consulte [Criar um destino de cookie](../../features/destinations/manage-destinations.md#create-cookie-destination) ou [Criar um destino de URL](../../features/destinations/manage-destinations.md#configure-url-destination) para obter informações.
   * Para destinos existentes: Use [!DNL Search] a caixa para localizar o destino ou clique na lista e clique no nome de destino para abri-lo.
1. Selecione um [!DNL Data Export Label]. Deixe as caixas de seleção em branco se não quiser definir quaisquer restrições de exportação. Os rótulos de exportação incluem as seguintes opções:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >As restrições de exportação não funcionarão a menos que você defina um [controle de exportação correspondente](../../features/data-export-controls.md) em uma fonte de dados.
1. Clique em **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Criar uma fonte de dados](../../features/manage-datasources.md#create-data-source)

