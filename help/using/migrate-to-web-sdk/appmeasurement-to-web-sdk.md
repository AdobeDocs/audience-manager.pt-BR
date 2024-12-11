---
title: Atualize sua biblioteca de coleção de dados para o Audience Manager da biblioteca JavaScript do AppMeasurement para a biblioteca JavaScript do SDK da Web.
description: Entenda as etapas para atualizar sua biblioteca de coleção de dados para o Audience Manager da biblioteca JavaScript do AppMeasurement para a biblioteca JavaScript do SDK da Web.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: 3ba980e97763866d82bdf94109068f1f1f8f63d2
workflow-type: tm+mt
source-wordcount: '2398'
ht-degree: 0%

---


# Atualize sua biblioteca de coleção de dados para o Audience Manager da biblioteca JavaScript do AppMeasurement para a biblioteca JavaScript do SDK da Web

## Público-alvo {#intended-audience}

Esta página destina-se aos clientes do Audience Manager e do Adobe Analytics que usam a biblioteca JavaScript do [!DNL AppMeasurement] para enviar dados da Web para o Audience Manager.

Consulte a tabela abaixo para obter orientação sobre as etapas de migração para o SDK da Web, dependendo do seu método de coleta de dados atual.

| Seu método de coleta de dados existente | Instruções de migração do SDK da Web |
|---------|----------|
| Biblioteca JavaScript [!DNL AppMeasurement] | Siga as instruções neste guia. |
| [!DNL Audience Manager] [extensão de tag](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) | Siga as instruções em [atualizando sua biblioteca de coleção de dados da extensão de tag Audience Manager para a extensão de tag do SDK da Web](dil-extension-to-web-sdk.md). |
| [!DNL AppMeasurement] biblioteca JavaScript + [!DNL Audience Manager] [biblioteca DIL](../dil/dil-overview.md) | Siga as instruções em [atualizando sua biblioteca de coleção de dados da extensão de tag Audience Manager para a extensão de tag do SDK da Web](dil-extension-to-web-sdk.md). |

## Visão geral da migração {#overview}

A migração do [!DNL AppMeasurement] para o [SDK da Web](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) é basicamente uma migração do Adobe Analytics. Para clientes do Audience Manager, essa migração também inclui o Audience Manager. As duas devem ser migradas juntas. Se você trabalhar principalmente com o Audience Manager, certifique-se de envolver a equipe do Analytics nessa migração.

Se você usa [!DNL AppMeasurement] para a coleta de dados do Audience Manager, está usando atualmente a abordagem [!DNL Server-side Forwarding (SSF)] para enviar dados do Analytics para o Audience Manager. Nesta configuração, a solicitação de coleta de dados do Analytics é encaminhada ao Audience Manager, que também lida com a resposta do Audience Manager à página.

Essa tem sido a abordagem padrão por muitos anos e provavelmente é a sua configuração atual. Se a biblioteca [!DNL AppMeasurement] contiver o módulo `AudienceManagement` e suas chamadas de coleta de dados incluírem o caminho `/10/` na solicitação (`/b/ss/examplereportsuite/10/`), este guia será para você.

## Encaminhamento pelo lado do servidor (SSF) versus Fluxos de dados do SDK da Web {#data-flows}

Entender as diferenças de fluxo de dados entre o Analytics e o Audience Manager ao migrar para o SDK da Web (e o Edge Network) é fundamental para as instruções abaixo.

Com o encaminhamento pelo lado do servidor, o nó de coleção de dados regionais do Analytics coleta os dados, transforma-os em um sinal aceito pelo Audience Manager, envia-os para o Audience Manager e retorna a resposta Audience Manager para a página. O módulo [!DNL AudienceManagement] na biblioteca [!DNL AppMeasurement] manipula a resposta (por exemplo, descartando cookies, enviando destinos de URL). Esse processo é chamado de encaminhamento pelo lado do servidor porque o Analytics encaminha os dados para o Audience Manager usando servidores Adobe.

Com o SDK da Web, o Edge Network envia dados para o Analytics e o Audience Manager em ações separadas. O SDK da Web é uma biblioteca única que envia dados para todas as soluções, e o Edge Network transforma pontos de dados independentes de solução em formatos específicos de solução.

Neste novo fluxo de dados, todos os dados são enviados para um Edge Network [datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview), que você pode [configurar](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) para enviar dados para soluções de Adobe conforme necessário. Para o Audience Manager, habilitar o serviço Audience Manager na sequência de dados transforma os dados do [!DNL XDM] e do Analytics em sinais aceitos pelo Audience Manager. O Edge Network também retorna a resposta Audience Manager para a página, onde o SDK da Web manipula a resposta, de modo semelhante ao que o módulo [!DNL AppMeasurement] e [!DNL AudienceManagement] fizeram.

## Migração de tags versus não tags {#tags-vs-non-tags}

Se você estiver usando Tags com a extensão [!DNL AppMeasurement], a biblioteca [!DNL AppMeasurement] em outro sistema de gerenciamento de tags ou colocando [!DNL AppMeasurement] diretamente na página, as etapas de migração do Audience Manager para o SDK da Web serão as mesmas. Como a migração do Audience Manager depende da migração do Analytics, as etapas para migrar do [!DNL AppMeasurement] para o SDK da Web são determinadas durante a migração do Analytics.

Essas informações são abordadas na documentação do Analytics para implementações baseadas em [Tags](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) ou [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk).

## XDM e os nós `data.__adobe.` {#xdm-data-nodes}

Uma das principais funções do [SDK da Web](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) é enviar dados para o [Real-time Customer Data Platform (RTCDP)](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/home). Para alcançar isso e ainda coletar dados para outras soluções de Experience Cloud sem uma reimplementação completa, os dados específicos da solução são compartimentalizados dentro da chamada do servidor de coleta de dados. Esta chamada usa um esquema JSON padronizado chamado de [Experience Data Model (XDM)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home)

Elementos independentes de solução, como informações sobre o navegador e o dispositivo, são enviados para o Edge Network em uma estrutura XDM predeterminada. O Edge Network transforma esses dados em formatos específicos da solução. No entanto, os dados específicos do Target, Analytics e Audience Manager são armazenados em um nó `data.__adobe` dedicado na carga XDM.

Por exemplo:

* A variável do Analytics `s.eVar1` é representada na carga XDM como `data.__adobe.analytics.evar1`.
* Um parâmetro do Target relacionado ao status de fidelidade do cliente está armazenado como `data.__adobe.target.loyaltyStatus`.

Os dados no nó `__adobe` são enviados para as respectivas soluções (como Analytics e Audience Manager) sem serem enviados para Experience Platform, mesmo que o serviço Experience Platform esteja habilitado no fluxo de dados. Isso significa que você pode manter suas configurações atuais para o Analytics e o Audience Manager enquanto tem a flexibilidade de mapear quaisquer elementos de dados necessários para elementos de esquema XDM para casos de uso em tempo real no Experience Platform usando o [Preparo de dados para coleção](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep).

Por exemplo, a sequência de caracteres `s.products` do Analytics, usada para relatar o conteúdo do carrinho durante o check-out, ainda pode ser enviada para o Analytics e para o Audience Manager no formato original. Ao mesmo tempo, você pode usar os elementos dessa string para criar esquemas de carrinho XDM mais intuitivos para casos de uso de Experience Platform.

Como a maioria das implementações de Audience Manager depende dos dados do Analytics encaminhados para o Audience Manager, muitas das expressões de característica de Audience Manager provavelmente se baseiam em variáveis do Analytics (`c_evar#`, `c_prop#` e `c_events`). Para evitar a reconstrução de expressões de características usando formatos XDM durante a migração, o Edge Network é configurado por padrão para transformar qualquer variável do Analytics encontrada no nó `data.__adobe.analytics` em sinais de Audience Manager. Esse processo é semelhante ao fluxo de trabalho de encaminhamento do lado do servidor.

O Edge Network pode executar essa transformação porque uma única chamada de coleta de dados da página é enviada para um único fluxo de dados que alimenta várias soluções de Adobe. Portanto, a maioria das migrações do [!DNL AppMeasurement] para o SDK da Web para o Analytics e o Audience Manager usará principalmente o nó `data.__adobe.analytics`.

O Edge Network transforma os dados de dispositivo e navegador da carga XDM e cabeçalhos de pacote em sinais de Audience Manager. Isso permite que você continue usando as chaves de plataforma `h_` e `d_` em expressões de características de Audience Manager.

## O nó `data.__adobe.audiencemanager` {#data-note}

O nó `data.__adobe.audiencemanager` é usado para implementações de Audience Manager que não dependem do Analytics. Ele armazena pares de chaves/valores de Audience Manager personalizados que foram enviados anteriormente pela biblioteca [DIL](../dil/dil-overview.md), conforme descrito no [guia de migração de extensão de tag](dil-extension-to-web-sdk.md).

Embora o nó `data.__adobe.audiencemanager` não seja necessário para a migração descrita neste guia, o novo fluxo de dados explicado aqui permite que os dados sejam enviados para o Audience Manager sem serem registrados no Analytics.

Se você precisar enviar um par de chave/valor personalizado para o Audience Manager sem incluí-lo no Analytics, poderá usar o nó `data.__adobe.audiencemanager`. Qualquer conjunto de dados nesse nó será anexado aos dados do Analytics transformados em Audience Manager na chamada do servidor de coleta de dados.

## Vantagens e desvantagens desse caminho de implementação

O uso dessa abordagem de migração tem vantagens e desvantagens. Avalie cuidadosamente cada opção para decidir qual abordagem é a melhor para sua organização.

| Benefícios | Desvantagens |
| --- | --- |
| <ul><li>**Usa sua implementação existente**: embora esta abordagem exija algumas alterações de implementação, ela não requer uma implementação completamente nova do zero. Você pode usar sua camada de dados e código existentes com o mínimo de alterações na lógica de implementação.</li><li>**Não requer um esquema**: nesta fase da migração para o SDK da Web, você não precisa de um esquema XDM. Em vez disso, você pode preencher o objeto `data`, que envia dados diretamente para o Audience Manager. Quando a migração para o SDK da Web estiver concluída, você poderá criar um esquema para sua organização e usar o mapeamento de sequência de dados para preencher campos XDM aplicáveis. Se um esquema fosse necessário nesse estágio do processo de migração, sua organização seria forçada a usar um esquema XDM de Audience Manager. O uso desse esquema torna mais difícil para sua organização usar seu próprio esquema no futuro.</li></ul> | <ul><li>**Dívida técnica da implementação**: como esta abordagem usa uma forma modificada da sua implementação existente, pode ser mais difícil rastrear a lógica da implementação e realizar alterações no futuro, quando necessário.</li><li>**Requer mapeamento para enviar dados para a Platform**: quando sua organização estiver pronta para usar o Real-Time CDP, você deverá enviar dados para um conjunto de dados na Adobe Experience Platform. Esta ação requer que cada campo no objeto `data` seja uma entrada na ferramenta de mapeamento de sequência de dados que o atribui a um campo de esquema XDM. O mapeamento só precisa ser feito uma vez para esse fluxo de trabalho e não envolve fazer alterações de implementação. No entanto, essa é uma etapa extra que não é necessária ao enviar dados em um objeto XDM.</li></ul> |

A Adobe recomenda seguir esse caminho de implementação nos seguintes cenários:

* Você tem uma implementação existente usando a biblioteca JavaScript do Adobe Analytics AppMeasurement. Se você tiver uma implementação usando a extensão de tag do Audience Manager, siga [Migrar da extensão de tag do Audience Manager para a extensão de tag do SDK da Web](dil-extension-to-web-sdk.md).
* Você pretende usar o Real-Time CDP no futuro, mas não deseja substituir sua implementação de Audience Manager por uma implementação de SDK da Web do zero. Substituir sua implementação do zero no SDK da Web requer mais esforço, mas também oferece a arquitetura de implementação de longo prazo mais viável. Se a sua organização estiver disposta a realizar o esforço de uma implementação limpa do SDK da Web, consulte a [documentação do SDK da Web](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) para obter mais detalhes.

## Etapas necessárias para migrar para o SDK da Web

Siga as etapas abaixo para migrar a integração da coleção de dados para o SDK da Web.

+++**1. Migre sua implementação do Analytics**.

Trabalhe com sua equipe do Analytics para seguir as etapas de migração do Analytics nas implementações baseadas em [Marcas](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) ou [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk). Depois de migrar a implementação do Analytics, continue para a etapa a seguir.

+++

+++**2. Adicionar o serviço Audience Manager à sequência de dados**

Adicione o serviço Audience Manager à sequência de dados criada durante a etapa 1.

1. Navegue até [experience.adobe.com](https://experience.adobe.com) e faça logon usando suas credenciais.
1. Use a página inicial ou o seletor de produto na parte superior direita para navegar até **[!UICONTROL Data Collection]**.
1. Na navegação à esquerda, selecione **[!UICONTROL Datastreams]**.
1. Selecione o fluxo de dados criado como parte da migração do Analytics na etapa 1.
1. Selecione **[!UICONTROL Add Service]**.
1. No menu suspenso de serviço, selecione **[!UICONTROL Audience Manager]**.
1. Verifique as opções **[!UICONTROL Cookie Destinations Enabled]** e **[!UICONTROL URL Destinations Enabled]**. Essas opções permitem que o Edge Network retorne esses tipos de destino de Audience Manager para a página.
1. Verifique se o **[!UICONTROL Enable XDM Flattened Fields]** está desativado. Essa opção desativa a transformação automática das variáveis do Analytics em sinais de Audience Manager. Essa opção foi projetada para manter a compatibilidade com versões anteriores para usuários que migraram para o SDK da Web antes que o Edge Network transformasse automaticamente os dados do Analytics em sinais de Audience Manager.

   >[!NOTE]
   >
   >A migração para o SDK da Web com a opção **[!UICONTROL Enabled XDM Flattened Fields]** habilitada requer que todos os dados necessários no Audience Manager formatado como XDM e todas as características de Audience Manager usando props, eVars ou eventos sejam atualizados para procurar dados formatados em XDM. O Adobe recomenda deixar essa opção desativada.


   ![Adicionar serviço de Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

1. Selecione **[!UICONTROL Save]** para salvar a configuração da sequência de dados.

Seu fluxo de dados agora está pronto para receber e transmitir dados para o Audience Manager. Observe a ID de sequência de dados, pois essa ID é necessária ao configurar o SDK da Web no código.

+++

+++**3. Habilitar Sincronizações de ID de Terceiros e definir a ID do Contêiner de Audience Manager**

1. Navegue até [experience.adobe.com](https://experience.adobe.com) e faça logon usando suas credenciais.
1. Use a página inicial ou o seletor de produto na parte superior direita para navegar até **[!UICONTROL Data Collection]**.
1. Na navegação à esquerda, selecione **[!UICONTROL Datastreams]**.
1. Selecione o fluxo de dados criado como parte da migração do Analytics na etapa 1.
1. Selecione **[!UICONTROL Edit]** no canto superior direito da página de configuração da sequência de dados.
1. Expanda o menu suspenso **[!UICONTROL Advanced Options]** e habilite a funcionalidade **[!UICONTROL Third Party ID Sync]** se ela ainda não estiver habilitada. Essa opção informa o Edge Network a retornar Sincronizações de ID do parceiro para parceiros de dados Audience Manager e Experience Platform.

   ![Habilitar sincronização de ID de terceiros.](assets/third-party-id-sync.png) {style="border:1px solid lightslategray"}

1. Na maioria dos casos, você pode deixar o campo **[!UICONTROL Third Party ID Sync Container ID]** em branco. O padrão será `0`. No entanto, se você preferir garantir que a ID de contêiner correta seja usada, siga as próximas etapas:
   * Abra uma janela do navegador no modo incógnito ou privado e navegue até uma página que faça parte da migração.
   * Use as ferramentas de desenvolvedor do navegador para filtrar a chamada de rede para `dpm.demdex.net/id`. Essa chamada só será acionada na primeira página de uma primeira visita, por isso é necessário um navegador incógnito ou privado.
   * Visualize a carga da solicitação. Se o parâmetro `d_nsid` for diferente de zero, copie-o para o campo **[!UICONTROL Third Party ID Sync Container ID]**.

1. Selecione **[!UICONTROL Save]**.

Seu fluxo de dados agora está pronto para enviar dados para o Audience Manager e enviar as respostas do Audience Manager para o SDK da Web.

+++

## Configurar o encaminhamento pelo lado do servidor e o Audience Analytics na interface do usuário do Gerenciador de conjunto de relatórios do Analytics {#configure-ssf-analytics}

Se você conhece o recurso [encaminhamento pelo lado do servidor](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf) do Analytics, talvez se pergunte: &quot;*Devo desabilitar a configuração de encaminhamento pelo lado do servidor na interface do usuário do Gerenciador de Conjunto de Relatórios do Analytics para evitar o envio de dados do Analytics para o Audience Manager duas vezes?*&quot;.

A resposta é não, você não deve desativar essa configuração. Veja o porquê:

Quando essa configuração estiver ativada e o módulo [!DNL AudienceManagement] for adicionado à biblioteca [!DNL AppMeasurement] da sua página, todos os dados enviados para esse conjunto de relatórios também fluirão para o Audience Manager.

Para cumprir as regras de privacidade do GDPR, há cenários em que os dados podem ser coletados no Analytics, mas não no Audience Manager. Além disso, há casos envolvendo conjuntos de relatórios globais e casos de uso específicos de região em que algumas chamadas de coleta de dados não devem ser enviadas para o Audience Manager. Para resolver isso, o Adobe introduziu um &quot;botão off&quot; de encaminhamento do lado do servidor.

Conforme explicado na [página de conformidade do Analytics e do GDPR focada no encaminhamento pelo lado do servidor](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf-gdpr), adicionar a variável de contexto `cm.ssf=1` a um servidor de coleta de dados do Analytics impede que a chamada de coleta de dados seja encaminhada para o Audience Manager.

Há dois motivos pelos quais você não deve desativar essa configuração.

1. Quando o serviço Audience Manager está habilitado em uma sequência de dados, o Edge Network anexa a variável `cm.ssf` a todas as solicitações de coleta de dados enviadas ao Analytics. Isso impede que os dados do Analytics também sejam enviados para o Audience Manager. Quaisquer logs do Assurance usados para validar a migração do Analytics mostrarão a variável `cm.ssf=1` quando o serviço Audience Manager estiver habilitado na sequência de dados.
1. Esta configuração também habilita o fluxo de dados para a integração do [!DNL Audience Analytics]. Conforme descrito na [visão geral de Audience Analytics](https://experienceleague.adobe.com/en/docs/analytics/integration/audience-analytics/mc-audiences-aam), o encaminhamento pelo lado do servidor é necessário para essa integração porque a resposta de Audience Manager ao servidor de coleta de dados do Analytics é adicionada à ocorrência do Analytics antes do processamento. Um processo semelhante ocorre dentro do Edge Network. Quando o encaminhamento pelo lado do servidor está ativado, o Edge Network adiciona os segmentos necessários da resposta do Audience Manager aos dados enviados para o Analytics.

Em resumo, é importante que essa configuração permaneça ativada para que o Audience Analytics continue a funcionar com uma implementação do SDK da Web e nenhum dado seja contado duas vezes no Audience Manager.
