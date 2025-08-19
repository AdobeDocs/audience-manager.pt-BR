---
title: Atualize sua biblioteca de coleta de dados do Audience Manager da biblioteca JavaScript do AppMeasurement para a biblioteca JavaScript do Web SDK.
description: Entenda as etapas para atualizar sua biblioteca de coleta de dados para o Audience Manager da biblioteca JavaScript do AppMeasurement para a biblioteca JavaScript do Web SDK.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: f180e423d4bdf5535d8dcc000e1d0f908bc54d7b
workflow-type: tm+mt
source-wordcount: '3385'
ht-degree: 0%

---


# Atualizar a biblioteca de coleta de dados para Audience Manager do AppMeasurement para o Web SDK

## Público-alvo {#intended-audience}

Esta página destina-se aos clientes do Audience Manager e do Adobe Analytics que usam a biblioteca JavaScript do [!DNL AppMeasurement] para enviar dados da Web para o Audience Manager.

Consulte a tabela abaixo para obter orientação sobre as etapas de migração para o Web SDK, dependendo do seu método de coleta de dados atual.

| Seu método de coleta de dados existente | Instruções de migração do Web SDK |
|---------|----------|
| Biblioteca JavaScript [!DNL AppMeasurement] com módulo AudienceManagement | Siga as instruções neste guia. |
| [!DNL Audience Manager] [extensão de tag](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) | Siga as instruções em [atualizando sua biblioteca de coleção de dados da extensão de marca da Audience Manager para a extensão de marca da Web SDK](dil-extension-to-web-sdk.md). |
| [!DNL AppMeasurement] biblioteca JavaScript + [!DNL Audience Manager] [biblioteca DIL](../dil/dil-overview.md) autônoma | Siga as instruções em [atualizando sua biblioteca de coleção de dados da extensão de marca da Audience Manager para a extensão de marca da Web SDK](dil-extension-to-web-sdk.md). |

## Visão geral da migração {#overview}

A migração do [!DNL AppMeasurement] para o [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) é basicamente uma migração do Adobe Analytics. Para clientes do Audience Manager, essa migração também inclui o Audience Manager. As duas devem ser migradas juntas. Se você trabalhar principalmente com o Audience Manager, certifique-se de envolver a equipe do Analytics nessa migração.

Se você usa o [!DNL AppMeasurement] para coleta de dados do Audience Manager, está usando atualmente a abordagem [!DNL Server-side Forwarding (SSF)] para enviar dados do Analytics para o Audience Manager. Nesta configuração, a solicitação de coleta de dados do Analytics é encaminhada ao Audience Manager, que também lida com a resposta do Audience Manager à página.

Essa tem sido a abordagem padrão por muitos anos e provavelmente é a sua configuração atual. Se a biblioteca [!DNL AppMeasurement] contiver o módulo `AudienceManagement` e suas chamadas de coleta de dados incluírem o caminho `/10/` na solicitação (`/b/ss/examplereportsuite/10/`), este guia será para você.

## Encaminhamento pelo lado do servidor (SSF) versus Fluxos de dados do Web SDK {#data-flows}

Entender as diferenças de fluxo de dados entre o Analytics e o Audience Manager ao migrar para o Web SDK (e o Edge Network) é fundamental para as instruções abaixo.

Com o encaminhamento pelo lado do servidor, o nó de coleção de dados regionais do Analytics coleta os dados, transforma-os em um sinal aceito pelo Audience Manager, envia-os para o Audience Manager e retorna a resposta do Audience Manager à página. O módulo [!DNL AudienceManagement] na biblioteca [!DNL AppMeasurement] manipula a resposta (por exemplo, descartando cookies, enviando destinos de URL). Esse processo é chamado de encaminhamento pelo lado do servidor porque o Analytics encaminha os dados para o Audience Manager usando servidores da Adobe.

Com o Web SDK, o Edge Network envia dados para o Analytics e o Audience Manager em ações separadas. O Web SDK é uma única biblioteca que envia dados para todas as soluções, e a Edge Network transforma pontos de dados independentes de solução em formatos específicos de solução.

Neste novo fluxo de dados, todos os dados são enviados para uma [sequência de dados](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview) do Edge Network, que você pode [configurar](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) para enviar dados para soluções da Adobe, conforme necessário. Para o Audience Manager, habilitar o serviço Audience Manager na sequência de dados transforma os dados do [!DNL XDM] e do Analytics em sinais aceitos pelo Audience Manager. O Edge Network também retorna a resposta do Audience Manager para a página, onde o Web SDK lida com a resposta, de modo semelhante ao que o [!DNL AppMeasurement] e o módulo [!DNL AudienceManagement] fizeram.

## Migração de tags versus não tags {#tags-vs-non-tags}

Se você estiver usando Tags com a extensão [!DNL AppMeasurement], a biblioteca [!DNL AppMeasurement] em outro sistema de gerenciamento de tags ou colocando [!DNL AppMeasurement] diretamente na página, as etapas de migração do Audience Manager para a Web SDK serão as mesmas. Como a migração do Audience Manager depende da migração do Analytics, as etapas para migrar do [!DNL AppMeasurement] para o Web SDK são determinadas durante a migração do Analytics.

Essas informações são abordadas na documentação do Analytics para implementações baseadas em [Tags](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) ou [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk).

## XDM e os nós `data.__adobe.` {#xdm-data-nodes}

Uma das principais funções do [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) é enviar dados para o [Real-Time Customer Data Platform (RTCDP)](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/home). Para fazer isso e ainda coletar dados para outras soluções da Experience Cloud sem uma reimplementação completa, os dados específicos da solução são compartimentalizados na chamada do servidor de coleta de dados. Esta chamada usa um esquema JSON padronizado chamado de [Experience Data Model (XDM)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home)

Elementos independentes de solução, como informações sobre o navegador e o dispositivo, são enviados para a Edge Network em uma estrutura XDM predeterminada. O Edge Network transforma esses dados em formatos específicos da solução. No entanto, os dados específicos do Target, Analytics e Audience Manager são armazenados em um nó `data.__adobe` dedicado na carga XDM.

Por exemplo:

* A variável do Analytics `s.eVar1` é representada na carga XDM como `data.__adobe.analytics.evar1`.
* Um parâmetro do Target relacionado ao status de fidelidade do cliente está armazenado como `data.__adobe.target.loyaltyStatus`.

Os dados no nó `__adobe` são enviados para as respectivas soluções (como Analytics e Audience Manager) sem serem enviados para a Experience Platform, mesmo que o serviço Experience Platform esteja habilitado na sequência de dados. Isso significa que você pode manter suas configurações atuais do Analytics e do Audience Manager, além de ter a flexibilidade de mapear os elementos de dados necessários para elementos de esquema XDM, para casos de uso em tempo real no Experience Platform usando o [Preparo de dados para a coleção de dados](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep).

Por exemplo, a sequência de caracteres `s.products` do Analytics, usada para relatar o conteúdo do carrinho durante o check-out, ainda pode ser enviada para o Analytics e o Audience Manager no formato original. Ao mesmo tempo, você pode usar os elementos dessa string para criar esquemas de carrinho XDM mais intuitivos para casos de uso do Experience Platform.

Como a maioria das implementações do Audience Manager depende dos dados do Analytics encaminhados para o Audience Manager, muitas de suas expressões de características do Audience Manager provavelmente se baseiam em variáveis do Analytics (`c_evar#`, `c_prop#` e `c_events`). Para evitar a recriação de expressões de características usando formatos XDM durante a migração, o Edge Network é configurado por padrão para transformar qualquer variável do Analytics encontrada no nó `data.__adobe.analytics` em sinais do Audience Manager. Um processo de transformação semelhante ocorre no fluxo de trabalho de encaminhamento do lado do servidor.

O Edge Network pode executar essa transformação porque uma única chamada de coleta de dados da página é enviada para um único fluxo de dados que alimenta várias soluções da Adobe. Portanto, a maioria das migrações do [!DNL AppMeasurement] para o Web SDK do Analytics e do Audience Manager usará principalmente o nó `data.__adobe.analytics`.

O Edge Network transforma os dados do dispositivo e do navegador da carga XDM e dos cabeçalhos de pacote em sinais Audience Manager. Isso permite que você continue usando as chaves de plataforma `h_` e `d_` em expressões de características do Audience Manager.

## O nó `data.__adobe.audiencemanager` {#data-note}

O nó `data.__adobe.audiencemanager` é usado para implementações do Audience Manager que não dependem do Analytics. Ele armazena pares de chave/valor personalizados do Audience Manager que foram enviados anteriormente pela biblioteca [DIL](../dil/dil-overview.md), conforme descrito no [guia de migração de extensão de tag](dil-extension-to-web-sdk.md).

Embora o nó `data.__adobe.audiencemanager` não seja necessário para a migração descrita neste guia, o novo fluxo de dados explicado aqui permite que os dados sejam enviados para a Audience Manager sem serem registrados no Analytics.

Se você precisar enviar um par personalizado de chave/valor para a Audience Manager sem incluí-lo no Analytics, poderá usar o nó `data.__adobe.audiencemanager`. Qualquer conjunto de dados nesse nó será anexado aos dados do Analytics transformados pela Audience Manager na chamada do servidor de coleta de dados.

## Vantagens e desvantagens desse caminho de implementação

O uso dessa abordagem de migração tem vantagens e desvantagens. Avalie cuidadosamente cada opção para decidir qual abordagem é a melhor para sua organização.

| Benefícios | Desvantagens |
| --- | --- |
| <ul><li>**Usa sua implementação existente**: embora esta abordagem exija algumas alterações de implementação, ela não requer uma implementação completamente nova do zero. Você pode usar sua camada de dados e código existentes com o mínimo de alterações na lógica de implementação.</li><li>**Não requer um esquema**: nesta fase de migração para o Web SDK, você não precisa de um esquema XDM. Em vez disso, você pode preencher o objeto `data`, que envia dados diretamente para o Audience Manager. Quando a migração para o Web SDK estiver concluída, você poderá criar um esquema para sua organização e usar o mapeamento de fluxo de dados para preencher campos XDM aplicáveis. Se um esquema fosse necessário nesta fase do processo de migração, sua organização seria forçada a usar um esquema XDM da Audience Manager. O uso desse esquema torna mais difícil para sua organização usar seu próprio esquema no futuro.</li></ul> | <ul><li>**Dívida técnica da implementação**: como esta abordagem usa uma forma modificada da sua implementação existente, pode ser mais difícil rastrear a lógica da implementação e realizar alterações no futuro, quando necessário.</li><li>**Requer mapeamento para enviar dados para a Platform**: quando sua organização estiver pronta para usar o Real-Time CDP, você deverá enviar dados para um conjunto de dados na Adobe Experience Platform. Esta ação requer que cada campo no objeto `data` seja uma entrada na ferramenta de mapeamento de sequência de dados que o atribui a um campo de esquema XDM. O mapeamento só precisa ser feito uma vez para esse fluxo de trabalho e não envolve fazer alterações de implementação. No entanto, essa é uma etapa extra que não é necessária ao enviar dados em um objeto XDM.</li></ul> |

A Adobe recomenda seguir esse caminho de implementação nos seguintes cenários:

* Você tem uma implementação existente usando a biblioteca JavaScript do Adobe Analytics AppMeasurement. Se você tiver uma implementação usando a extensão de tag da Audience Manager, siga [Migrar da extensão de tag da Audience Manager para a extensão de tag da Web SDK](dil-extension-to-web-sdk.md).
* Você pretende usar o Real-Time CDP no futuro, mas não deseja substituir sua implementação do Audience Manager por uma implementação do Web SDK do zero. A alternativa de substituir sua implementação do zero pelo Web SDK requer mais esforço, pois é necessário reconstruir todas as características do Audience Manager para procurar dados formatados em XDM. No entanto, também é a arquitetura de implementação de longo prazo mais viável. Se a sua organização estiver disposta a realizar o esforço de uma implementação limpa do Web SDK, consulte a [documentação do Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) em vez de usar este guia, para obter mais detalhes.

## Etapas necessárias para migrar para o Web SDK

Siga as etapas abaixo para migrar a integração da coleção de dados para o Web SDK.

+++**1. Planeje a migração do Analytics**.

Trabalhe com sua equipe do Analytics para seguir as etapas de migração do Analytics nas implementações baseadas em [Marcas](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) ou [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk). Depois de planejar a migração do Analytics, volte para este guia e continue com as etapas do Audience Manager para determinar o que você precisa fazer pelo Audience Manager para implantar a migração do Analytics e do Audience Manager juntas.

+++

+++**2. Adicionar o serviço Audience Manager à sequência de dados**

Adicione o serviço Audience Manager à sequência de dados que você está usando na migração do Analytics mencionada na etapa 1.

1. Navegue até [experience.adobe.com](https://experience.adobe.com) e faça logon usando suas credenciais.
1. Use a página inicial ou o seletor de produto na parte superior direita para navegar até **[!UICONTROL Data Collection]**.
1. Na navegação à esquerda, selecione **[!UICONTROL Datastreams]**.
1. Selecione o fluxo de dados criado como parte da migração do Analytics na etapa 1.
1. Selecione **[!UICONTROL Add Service]**.
1. No menu suspenso de serviço, selecione **[!UICONTROL Audience Manager]**.
1. Verifique as opções **[!UICONTROL Cookie Destinations Enabled]** e **[!UICONTROL URL Destinations Enabled]**. Essas opções permitem que o Edge Network retorne esses tipos de destino do Audience Manager à página.
1. Verifique se o **[!UICONTROL Enable XDM Flattened Fields]** está desativado. Essa opção desativa a transformação automática das variáveis do Analytics em sinais do Audience Manager. Essa opção foi projetada para manter a compatibilidade com versões anteriores para usuários que migraram para o Web SDK antes que o Edge Network transformasse automaticamente os dados do Analytics em sinais do Audience Manager.

   >[!NOTE]
   >
   >A migração para o Web SDK com a opção **[!UICONTROL Enabled XDM Flattened Fields]** habilitada requer que todos os dados necessários no Audience Manager formatados como XDM e todas as características do Audience Manager usando props, eVars ou eventos sejam atualizados para procurar dados formatados como XDM. A Adobe recomenda deixar essa opção desativada.


   ![Adicionar serviço Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

1. Selecione **[!UICONTROL Save]** para salvar a configuração da sequência de dados.

Seu fluxo de dados agora está pronto para receber e transmitir dados para a Audience Manager. Observe a ID do fluxo de dados, pois essa ID é necessária ao configurar o Web SDK no código.

+++

+++**3. Habilitar Sincronizações de ID de Terceiros e definir a ID de Contêiner do Audience Manager**

1. Navegue até [experience.adobe.com](https://experience.adobe.com) e faça logon usando suas credenciais.
1. Use a página inicial ou o seletor de produto na parte superior direita para navegar até **[!UICONTROL Data Collection]**.
1. Na navegação à esquerda, selecione **[!UICONTROL Datastreams]**.
1. Selecione o fluxo de dados criado como parte da migração do Analytics na etapa 1.
1. Selecione **[!UICONTROL Edit]** no canto superior direito da página de configuração da sequência de dados.
1. Expanda o menu suspenso **[!UICONTROL Advanced Options]** e habilite a funcionalidade **[!UICONTROL Third Party ID Sync]** se ela ainda não estiver habilitada. Essa opção instrui o Edge Network a retornar as sincronizações de ID do parceiro para parceiros de dados da Audience Manager e da Experience Platform.

   ![Habilitar sincronização de ID de terceiros.](assets/third-party-id-sync.png) {style="border:1px solid lightslategray"}

1. Na maioria dos casos, você pode deixar o campo **[!UICONTROL Third Party ID Sync Container ID]** em branco. O padrão será `0`. No entanto, se você preferir garantir que a ID de contêiner correta seja usada, siga as próximas etapas:
   * Abra uma janela do navegador no modo incógnito ou privado e navegue até uma página que faça parte da migração.
   * Use as ferramentas de desenvolvedor do navegador para filtrar a chamada de rede para `dpm.demdex.net/id`. Essa chamada só será acionada na primeira página de uma primeira visita, por isso é necessário um navegador incógnito ou privado.
   * Visualize a carga da solicitação. Se o parâmetro `d_nsid` for diferente de zero, copie-o para o campo **[!UICONTROL Third Party ID Sync Container ID]**.

1. Selecione **[!UICONTROL Save]**.

Agora, a sequência de dados está pronta para enviar dados ao Audience Manager e enviar as respostas do Audience Manager para o Web SDK.

+++

+++**4. Adicionar IDs do cliente ao mapa de identidade**

A maioria das implementações do Audience Manager usa [Regras de mesclagem de perfil](../features/profile-merge-rules/merge-rules-overview.md) em cenários de personalização entre dispositivos e para ajudar a controlar para quais segmentos os visitantes podem se qualificar, dependendo de seu estado de autenticação (logon ou logout). As Regras de mesclagem de perfis exigem que um identificador de propriedade do cliente (ID de CRM, número de conta etc.) seja enviado à Audience Manager em cada chamada de coleta de dados após a autenticação. Anteriormente, a função `setCustomerIDs` do Serviço de ID de visitante ([!DNL visitor.js]) era usada para anexar IDs de cliente a cada chamada de coleta de dados do Analytics, que era então encaminhada para a Audience Manager.

Com o Web SDK, essas identidades agora precisam ser enviadas para o Edge Network usando uma construção XDM especial chamada [IdentityMap](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/identitymap).

Passar as identidades corretamente em um mapa de identidade requer a compreensão de [namespaces de identidade](https://experienceleague.adobe.com/pt-br/docs/experience-platform/identity/features/namespaces) e a consideração cuidadosa de quais identidades devem ser passadas, especialmente ao enviar dados para uma sandbox da Experience Platform. [Este artigo](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-21305) descreve essas considerações e instruções.

Depois de determinar quais identidades devem ser passadas e quando, siga os guias para usar o [!UICONTROL Identity map] **[!UICONTROL Identity map]** [elemento de dados](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/data-element-types#identity-map) nas Tags ou defina-o manualmente conforme descrito na [visão geral dos dados de identidade](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/identity/overview) para alinhar-se à sua estratégia de implantação do Web SDK.

+++

+++**5. (Opcional) Defina o `aam_uuid` cookie próprio**

Uma prática padrão por muitos anos era colocar a UUID do Audience Manager (o valor no cookie demdex de terceiros) em um cookie próprio geralmente chamado de `aam_uuid`.

Para definir o cookie, você deve inserir um nome de cookie no campo **[!UICONTROL Name]** da seção **[!UICONTROL Unique User ID Cookie]** da extensão de tag do Analytics ou no campo `uuidCookie` ao configurar o `audienceManagementModule`. Embora normalmente configurado no código, o cookie raramente era usado porque o valor da UUID do Audience Manager é um identificador de domínio cruzado específico do dispositivo usado pelas plataformas de publicidade e fornece pouco valor como um identificador próprio.

Se você descobrir que a implementação requer que esse cookie `aam_uuid` continue a ser definido após a migração para o Web SDK, poderá recuperar a UUID do Audience Manager de duas maneiras.

1. Cada resposta do [ponto de extremidade de interação do Edge Network](https://developer.adobe.com/data-collection-apis/docs/endpoints/interact/) contém uma carga com nós `id`. O nó `id` da carga do namespace `CORE` contém a UUID do Audience Manager.

2. Use o comando [getIdentity](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/getidentity) do Web SDK para recuperá-lo. Use o namespace `CORE` conforme descrito na documentação e recupere o valor do campo `identity.CORE` na resposta.

Independentemente do método usado para recuperar a UUID do Audience Manager, cabe à sua equipe de desenvolvimento analisar a resposta, recuperar a UUID e definir o cookie. Não há uma maneira automática de definir esse cookie por meio do Web SDK.

+++

## Configurar o encaminhamento pelo lado do servidor e o Audience Analytics na interface do usuário do Gerenciador de conjunto de relatórios do Analytics {#configure-ssf-analytics}

Se você conhece o recurso [encaminhamento pelo lado do servidor](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf) do Analytics, talvez se pergunte: &quot;*Devo desabilitar a configuração de encaminhamento pelo lado do servidor na interface do usuário do Gerenciador de Conjunto de Relatórios do Analytics para evitar o envio de dados do Analytics para o Audience Manager duas vezes?*&quot;.

A resposta é não. Você não deve desativar essa configuração pelos seguintes motivos:

1. Quando o serviço Audience Manager é habilitado em uma sequência de dados, o Edge Network anexa a variável `cm.ssf` a todas as solicitações de coleta de dados enviadas ao Analytics. Isso impede que os dados do Analytics também sejam enviados para a Audience Manager. Quaisquer logs do Assurance usados para validar a migração do Analytics mostrarão a variável `cm.ssf=1` quando o serviço do Audience Manager estiver habilitado na sequência de dados. Consulte a [página de conformidade do Analytics e do GDPR focada no encaminhamento pelo lado do servidor](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf-gdpr) para obter mais detalhes.

1. Esta configuração também habilita o fluxo de dados para a integração do [!DNL Audience Analytics]. Conforme descrito na [visão geral do Audience Analytics](https://experienceleague.adobe.com/en/docs/analytics/integration/audience-analytics/mc-audiences-aam), o encaminhamento pelo lado do servidor é necessário para essa integração porque a resposta do Audience Manager ao servidor de coleta de dados do Analytics é adicionada à ocorrência do Analytics antes do processamento. Um processo semelhante ocorre no Edge Network. Quando o encaminhamento pelo lado do servidor está ativado, o Edge Network adiciona os segmentos necessários da resposta do Audience Manager aos dados enviados para o Analytics.

Em resumo, é importante que essa configuração permaneça ativada para que o Audience Analytics continue a funcionar com uma implementação do Web SDK e nenhum dado seja contado duas vezes no Audience Manager.

## Validar a migração {#validation}

Como todas as soluções da Adobe agora são atendidas por uma única chamada do Web SDK, as etapas de validação podem mudar, dependendo das soluções fornecidas pelo Web SDK.

Se o Adobe Target ou o Adobe Journey Optimizer (incluindo [!DNL Decisioning]) fizerem parte da pilha de soluções que está sendo atendida pela implementação, você terá várias chamadas de rede para o Edge Network na página. Alguns deles se destinam à recuperação de personalizações e ofertas, enquanto outros se destinam à coleta de dados e relatórios.

Independentemente da implementação, os princípios gerais abaixo se aplicam para validar se os dados estão fluindo corretamente de e para a Audience Manager por meio da Web SDK.

1. A primeira chamada de rede para um visitante de primeira página será para o domínio `adobedc.demdex.net` e o ponto de extremidade `/interact`. Você pode ver as chamadas de rede feitas pelo Web SDK abrindo a guia do desenvolvedor no navegador da Web, clicando na guia Rede e filtrando por `/interact`.
Há outros tipos de chamadas do Web SDK, mas apenas `interact` chamadas enviam dados para o e obtêm uma carga de resposta do Edge Network.

   ![Imagem de uma guia de rede do navegador mostrando as chamadas interativas.](assets/network.png)

1. A resposta para a primeira chamada de rede tem várias cargas. Um desses nós de carga inclui vários subnós do tipo `url`. Esses `url` nós são as sincronizações de ID de terceiros que foram historicamente acionadas pelo serviço [!DNL Visitor ID]. Deve haver um nó `url` para cada sincronização de ID de terceiros configurada no contêiner (consulte a etapa 3 acima).

   ![Imagem de uma guia de rede do navegador mostrando as cargas.](assets/payload.png)

   Além disso, você pode filtrar por `demdex` e descobrir que cada uma das URLs referenciadas na carga acionou sua própria solicitação de rede para sincronização de ID da mesma forma que o serviço [!DNL Visitor ID]. Essas sincronizações de ID só devem ser acionadas na primeira página de um visitante pela primeira vez e somente uma vez a cada 14 dias depois disso.

1. Quaisquer solicitações `/interact` subsequentes usadas para a coleta de dados do Analytics e do Audience Manager devem conter os nós `data.__adobe.analytics` na carga.

   ![Imagem de uma guia de rede do navegador mostrando o nó de análise na carga.](assets/analytics-node.png)

   As características do Audience Manager que dependem dessas variáveis do Analytics, bem como as características que usam as chaves de plataforma `h_` ou `d_` devem continuar sendo preenchidas.

   >[!TIP]
   >
   >Você pode criar uma característica de teste com uma expressão de regra que só pode ser expressa se os dados do Web SDK estiverem sendo coletados. Como não há nenhum ambiente de desenvolvimento do Audience Manager e vários sites podem estar enviando dados para a mesma instância do Audience Manager, observar a contagem geral de população pode não fornecer a validação necessária.

1. Na mesma chamada `/interact` pela qual as variáveis do Analytics são passadas, qualquer cookie ou destino de URL pode ser encontrado nos nós de carga da resposta. Os destinos da URL estarão em cargas do tipo `url` (como em sincronizações de ID de terceiros) e os destinos de cookies estarão em cargas do tipo `cookie`.

   ![Imagem de uma guia de rede do navegador mostrando os dados da carga.](assets/destinations.png)

   Você também deve se certificar de que os cookies foram colocados no armazenamento de cookies do navegador.

   >[!TIP]
   >
   >Semelhante à etapa de validação anterior, qualificar para um segmento que deve retornar um destino de cookie é uma determinada maneira de garantir que os dados fluam de e para o Audience Manager.

1. Se precisar passar outras IDs do cliente pelo Mapa de identidade, autentique no site e verifique se as identidades e seus parâmetros associados são passados no nó Mapa de identidade da carga da solicitação.

   ![Imagem de uma guia de rede do navegador mostrando os dados de identityMap.](assets/pass-customer-ids.png)

   >[!TIP]
   >
   >Se o Adobe Target for uma das soluções de recebimento e houver atividades do Target que dependam de segmentos do Audience Manager que exigem a identidade correta a ser transmitida, verifique se o Mapa de identidade é transmitido nas chamadas `/interact` usadas para recuperar personalizações e não apenas em chamadas de coleta de dados. O Adobe Target usará essas identidades na chamada do lado do servidor para o Audience Manager ao recuperar informações do segmento.

