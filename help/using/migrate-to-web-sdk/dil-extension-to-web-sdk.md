---
title: Migração da extensão de tag do Audience Manager para a extensão de tag do SDK da Web
description: Entenda as etapas para atualizar a biblioteca de coleção de dados para o Audience Manager da extensão de tag Audience Manager para a extensão de tag do SDK da Web
source-git-commit: 1cf6a80bd5b7f583ea2511becf415b430ce2889e
workflow-type: tm+mt
source-wordcount: '1309'
ht-degree: 0%

---


# Atualize sua biblioteca de coleção de dados para o Audience Manager da extensão de tag Audience Manager para a extensão de tag do SDK da Web

## Público-alvo

Esta página é destinada aos clientes do Audience Manager que estão usando o [extensão de tag do Audience Manager](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) para trazer dados de coleção da web para o Audience Manager. Para clientes que usam a biblioteca JavaScript do AppMeasurement, leia o guia sobre como atualizar a biblioteca de coleta de dados do Audience Manager [da biblioteca JavaScript do AppMeasurement para a biblioteca JavaScript do SDK da Web](appmeasurement-to-web-sdk.md).

## Vantagens e desvantagens desse caminho de implementação

O uso dessa abordagem de migração tem vantagens e desvantagens. Avalie cuidadosamente cada opção para decidir qual abordagem é a melhor para sua organização.

| Benefícios | Desvantagens |
| --- | --- |
| <ul><li>**Não há alterações de código em seu site**: como sua implementação já tem tags instaladas, todas as atualizações de migração podem ser feitas na interface de tags.</li><li>**Usa sua implementação existente**: essa abordagem não requer uma implementação totalmente nova. Embora isso exija novas ações de regra, é possível reutilizar os elementos de dados existentes e as condições da regra com o mínimo de alterações.</li><li>**Não requer um esquema**: nessa etapa de migração para o SDK da Web, você não precisa de um esquema XDM. Em vez disso, você pode preencher o `data` que envia dados diretamente para o Adobe Audience Manager. Quando a migração para o SDK da Web estiver concluída, você poderá criar um esquema para sua organização e usar o mapeamento de sequência de dados para preencher campos XDM aplicáveis. Se um esquema fosse necessário nesta fase do processo de migração, sua organização seria forçada a usar um esquema XDM da Adobe Audience Manager. O uso desse esquema torna mais difícil para sua organização usar seu próprio esquema no futuro.</li></ul> | <ul><li>**Dívida técnica de implementação**: como essa abordagem usa uma forma modificada da implementação existente, pode ser mais difícil rastrear a lógica de implementação e executar alterações quando necessário. O código personalizado pode ser particularmente difícil de depurar.</li><li>**Requer mapeamento para enviar dados para a Plataforma**: quando sua organização estiver pronta para usar o Real-Time CDP, você deverá enviar dados para um conjunto de dados na Adobe Experience Platform. Essa ação exige que todos os campos na `data` ser uma entrada na ferramenta de mapeamento de sequência de dados que o atribui a um campo de esquema XDM. O mapeamento só precisa ser feito uma vez para esse fluxo de trabalho e não envolve fazer alterações de implementação. No entanto, essa é uma etapa extra que não é necessária ao enviar dados em um objeto XDM.</li></ul> |

A Adobe recomenda seguir esse caminho de implementação quando você tiver uma implementação existente usando a extensão de tag do Adobe Audience Manager.

## Etapas necessárias para migrar para o SDK da Web

As etapas a seguir contêm objetivos concretos a serem atingidos. Selecione cada etapa para obter instruções detalhadas sobre como realizá-la.

+++**1. Criar e configurar um fluxo de dados**

Siga as instruções abaixo para criar um fluxo de dados na Coleção de dados da Adobe Experience Platform. Ao enviar dados para esse fluxo de dados, ele encaminha os dados para o Audience Manager. No futuro, esse mesmo fluxo de dados encaminha dados para o Real-Time CDP.

1. Navegue até [experience.adobe.com](https://experience.adobe.com) e faça logon usando suas credenciais.
1. Use a página inicial ou o seletor de produto no canto superior direito para navegar até **[!UICONTROL Data Collection]**.
1. Na navegação à esquerda, selecione **[!UICONTROL Datastreams]**.
1. Selecionar **[!UICONTROL New Datastream]**.
1. Insira o nome desejado e selecione **[!UICONTROL Save]**.
1. Depois que o fluxo de dados for criado, selecione **[!UICONTROL Add Service]**.
1. No menu suspenso do serviço, selecione **[!UICONTROL Adobe Audience Manager]**.
1. Verifique se **[!UICONTROL Enable XDM Flattened Fields]** está desmarcada.

   ![Adicionar serviço Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

Seu fluxo de dados agora está pronto para receber e transmitir dados para o Audience Manager.

+++

+++**2. Adicionar a extensão SDK da Web à propriedade da tag**

Esta seção prepara a tag para a maior parte do esforço de migração que ocorrerá na próxima etapa.

1. Selecione o ícone de hambúrguer na parte superior esquerda da interface do Adobe Experience Platform e selecione **[!UICONTROL Tags]**.
1. Selecione a propriedade de tag desejada.
1. Na navegação à esquerda da propriedade da tag, selecione **[!UICONTROL Extensions]**.
1. Selecionar **[!UICONTROL Catalog]** próximo à parte superior para ver uma lista de todas as extensões disponíveis.
1. Procure por e selecione o **[!UICONTROL Adobe Experience Platform Web SDK]** e selecione **[!UICONTROL Install]** no lado direito.

   ![Catálogo](assets/catalog.png) {style="border:1px solid lightslategray"}

1. As definições de configuração de extensão são exibidas. Localize o **[!UICONTROL Datastreams]** e selecione a sandbox que você está usando e o fluxo de dados criado na etapa anterior.

   ![Seleção de sequência de dados](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. Selecionar **[!UICONTROL Save]**.

Agora a propriedade da tag tem o SDK da Web instalado.

+++

+++**3. Criar um elemento de dados de objeto de dados**

O elemento de dados do objeto de dados fornece uma estrutura intuitiva para configurar uma carga que o SDK da Web usa para enviar para um fluxo de dados. A maioria das regras que você atualiza na etapa a seguir interage com esse elemento de dados.

1. Na navegação à esquerda da interface de tags, selecione **[!UICONTROL Data Elements]**.
1. Selecionar **[!UICONTROL Add Data Element]**
1. Atribua ao elemento de dados as seguintes configurações:
   * **[!UICONTROL Name]**: qualquer coisa que você desejar, como &quot;Camada de dados&quot; ou &quot;Objeto de dados&quot;
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Data Element Type]**: [!UICONTROL Variable]
   * As caixas de seleção podem permanecer como estão.
1. No lado direito, selecione as seguintes configurações:
   * Botão de opção de propriedade: **[!UICONTROL Data]**
   * **[!UICONTROL Solution]**: [!UICONTROL Adobe Audience Manager]
1. Selecionar **[!UICONTROL Save]**.

   ![Criar elemento de dados](assets/create-data-element.png) {style="border:1px solid lightslategray"}

Agora, a propriedade da tag tem tudo o que é necessário para atualizar cada regra.

+++

+++**4. Atualizar regras para usar a extensão SDK da Web em vez da extensão Audience Manager**

Essa etapa contém a maior parte do esforço necessário para migrar para o SDK da Web e requer conhecimento sobre como a implementação funciona. Um exemplo é fornecido abaixo de como editar uma regra de tag típica. Atualize todas as regras de tag na implementação para substituir todas as referências à extensão Audience Manager pela extensão SDK da Web.

1. Na navegação à esquerda da interface de tags, selecione **[!UICONTROL Rules]**.
1. Selecione uma regra para editar.
1. Selecionar a ação **[!UICONTROL Audience Manager - Set Variables]**
1. Observe todas as variáveis de Audience Manager definidas nessa regra. Inclua as variáveis definidas nos menus suspensos e as variáveis definidas no código personalizado.
1. Altere o [!UICONTROL Action Configuration] para as seguintes configurações:
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: Atualizar variável
1. Verifique se o objeto de dados criado na etapa 3 está selecionado no menu suspenso à direita, na **[!UICONTROL Data element]** campo.
1. Defina os pares de valor-chave Audience Manager com os mesmos valores respectivos que foram configurados na extensão Audience Manager.
1. Depois que toda a lógica da regra for replicada usando a extensão SDK da Web, selecione **[!UICONTROL Keep Changes]**.
1. Repita essas etapas para cada configuração de ação que usa a extensão de tag Audience Manager para definir valores.

As etapas acima se aplicam apenas às regras que definem valores. As etapas a seguir substituem todas as ações que usam o [!UICONTROL Action Configuration] [!UICONTROL Send Event].

1. Selecione uma regra que envia um evento do SDK da Web.
1. Selecionar o tipo de ação **[!UICONTROL Send Event]**.
1. Altere o [!UICONTROL Action Configuration] para as seguintes configurações:
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: [!UICONTROL Send event]
1. À direita, altere as configurações da ação para o seguinte:
   * **[!UICONTROL Type]**: Uso **[!UICONTROL Web Webpagedetails Page Views]**.
   * **[!UICONTROL Data]**: selecione o objeto de dados criado na etapa 3.
1. Selecionar **[!UICONTROL Keep Changes]**.
1. Repita essas etapas para cada configuração de ação que use Audience Manager para enviar um evento.

+++

+++**5. Publicar regras atualizadas**

A publicação de regras atualizadas segue o mesmo fluxo de trabalho de qualquer outra alteração na configuração de tags.

1. Na navegação à esquerda da interface de tags, selecione **[!UICONTROL Publishing Flow]**.
1. Selecionar **[!UICONTROL Add Library]**.
1. Nomeie essa confirmação de tag, como &quot;Atualizar para o SDK da Web&quot;.
1. Selecionar **[!UICONTROL Add All Changed Resources]**.
1. Selecionar **[!UICONTROL Save]**.
1. O fluxo de trabalho de publicação exibe um ponto laranja, indicando que está sendo criado. Quando o ponto ficar verde, as alterações estarão disponíveis no ambiente de desenvolvimento.
1. Teste as alterações no ambiente de desenvolvimento para garantir que todas as regras sejam acionadas corretamente e que o objeto de dados seja preenchido com os valores esperados.
1. Quando estiver pronto, envie a biblioteca para aprovação, crie para preparo e, em seguida, aprove e publique para produção.

   ![Fluxo de publicação](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6. Desativar extensão Audience Manager**

Depois que a implementação de tag for totalmente migrada para o SDK da Web, você poderá desativar a extensão Audience Manager.

1. Na navegação à esquerda da interface de tags, selecione **[!UICONTROL Extensions]**.
1. Localize e selecione o [!UICONTROL Audience Manager] extensão. À direita, selecione **[!UICONTROL Disable]**.
1. Siga o mesmo fluxo de trabalho de publicação acima para publicar a remoção da [!UICONTROL Audience Manager] extensão.
1. Depois que a extensão for desativada na produção, você poderá desinstalá-la totalmente. Selecione a extensão, o menu de três pontos à direita e selecione **[!UICONTROL Uninstall]**.
1. Siga o mesmo fluxo de trabalho de publicação acima para publicar essas alterações na produção.

+++

Neste ponto, a implementação do Audience Manager é totalmente migrada para o SDK da Web e está preparada para mudar para o Real-Time CDP no futuro.
