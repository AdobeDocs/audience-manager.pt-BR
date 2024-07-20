---
title: Atualize sua biblioteca de coleção de dados para o Audience Manager da biblioteca JavaScript do AppMeasurement para a biblioteca JavaScript do SDK da Web.
description: Entenda as etapas para atualizar sua biblioteca de coleção de dados para o Audience Manager da biblioteca JavaScript do AppMeasurement para a biblioteca JavaScript do SDK da Web.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: a50aaeb5e384685100dc3ecc1d6d45f1c41461d0
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%

---

# Atualize sua biblioteca de coleção de dados para o Audience Manager da biblioteca JavaScript do AppMeasurement para a biblioteca JavaScript do SDK da Web

## Público-alvo {#intended-audience}

Esta página destina-se aos clientes do Audience Manager que usam o AppMeasurement para trazer dados de coleção da Web para o Audience Manager. Para clientes que usam a [extensão de tag do Audience Manager](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview), leia o guia sobre como atualizar a biblioteca de coleta de dados para o Audience Manager [da extensão de tag do Audience Manager para a extensão de tag do SDK da Web](dil-extension-to-web-sdk.md).

## Vantagens e desvantagens desse caminho de implementação

O uso dessa abordagem de migração tem vantagens e desvantagens. Avalie cuidadosamente cada opção para decidir qual abordagem é a melhor para sua organização.

| Benefícios | Desvantagens |
| --- | --- |
| <ul><li>**Usa sua implementação existente**: embora esta abordagem exija algumas alterações de implementação, ela não requer uma implementação completamente nova do zero. Você pode usar sua camada de dados e código existentes com o mínimo de alterações na lógica de implementação.</li><li>**Não requer um esquema**: nesta fase da migração para o SDK da Web, você não precisa de um esquema XDM. Em vez disso, você pode preencher o objeto `data`, que envia dados diretamente para o Audience Manager. Quando a migração para o SDK da Web estiver concluída, você poderá criar um esquema para sua organização e usar o mapeamento de sequência de dados para preencher campos XDM aplicáveis. Se um esquema fosse necessário nesse estágio do processo de migração, sua organização seria forçada a usar um esquema XDM de Audience Manager. O uso desse esquema torna mais difícil para sua organização usar seu próprio esquema no futuro.</li></ul> | <ul><li>**Dívida técnica da implementação**: como esta abordagem usa uma forma modificada da sua implementação existente, pode ser mais difícil rastrear a lógica da implementação e realizar alterações no futuro, quando necessário.</li><li>**Requer mapeamento para enviar dados para a Platform**: quando sua organização estiver pronta para usar o Real-Time CDP, você deverá enviar dados para um conjunto de dados na Adobe Experience Platform. Esta ação requer que cada campo no objeto `data` seja uma entrada na ferramenta de mapeamento de sequência de dados que o atribui a um campo de esquema XDM. O mapeamento só precisa ser feito uma vez para esse fluxo de trabalho e não envolve fazer alterações de implementação. No entanto, essa é uma etapa extra que não é necessária ao enviar dados em um objeto XDM.</li></ul> |

A Adobe recomenda seguir esse caminho de implementação nos seguintes cenários:

* Você tem uma implementação existente usando a biblioteca JavaScript do Adobe Analytics AppMeasurement. Se você tiver uma implementação usando a extensão de tag do Audience Manager, siga [Migrar da extensão de tag do Audience Manager para a extensão de tag do SDK da Web](dil-extension-to-web-sdk.md).
* Você pretende usar o Real-Time CDP no futuro, mas não deseja substituir sua implementação de Audience Manager por uma implementação de SDK da Web do zero. Substituir sua implementação do zero no SDK da Web requer mais esforço, mas também oferece a arquitetura de implementação de longo prazo mais viável. Se a sua organização estiver disposta a realizar o esforço de uma implementação limpa do SDK da Web, consulte a [documentação do SDK da Web](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) para obter mais detalhes.

## Etapas necessárias para migrar para o SDK da Web

As etapas a seguir contêm objetivos concretos a serem atingidos. Clique em cada etapa para obter instruções detalhadas sobre como realizá-la.

+++**1. Criar e configurar uma sequência de dados**

Crie um fluxo de dados na Coleção de dados da Adobe Experience Platform. Ao enviar dados para esse fluxo de dados, ele encaminha os dados para o Audience Manager. No futuro, esse mesmo fluxo de dados encaminha dados para o Real-Time CDP.

1. Navegue até [experience.adobe.com](https://experience.adobe.com) e faça logon usando suas credenciais.
1. Use a página inicial ou o seletor de produto na parte superior direita para navegar até **[!UICONTROL Data Collection]**.
1. Na navegação à esquerda, selecione **[!UICONTROL Datastreams]**.
1. Selecione **[!UICONTROL New Datastream]**.
1. Insira o nome desejado e selecione **[!UICONTROL Save]**.
1. Após criar a sequência de dados, selecione **[!UICONTROL Add Service]**.
1. No menu suspenso de serviço, selecione **[!UICONTROL Audience Manager]**.

   ![Adicionar serviço de Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

Seu fluxo de dados agora está pronto para receber e transmitir dados para o Audience Manager. Observe a ID de sequência de dados, pois essa ID é necessária ao configurar o SDK da Web no código.

+++

+++**2. Instalar a biblioteca JavaScript do SDK da Web**

Consulte [Instalar o SDK da Web usando a biblioteca JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) para obter detalhes e blocos de código a serem usados. Referencie a versão mais recente de `alloy.js` para que suas chamadas de método possam ser usadas.

+++

+++**3. Configurar o SDK da Web**

Configure sua implementação para apontar para a sequência de dados criada na etapa 1 usando o comando [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) do SDK da Web. O comando `configure` deve ser definido em todas as páginas, para que você possa incluí-lo junto com o código de instalação da biblioteca.

Use as propriedades [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) e [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) no comando `configure` do SDK da Web:

* Defina o `edgeConfigId` com a ID de sequência de dados recuperada da etapa anterior.
* Defina o `orgId` como a ID da organização IMS.

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Opcionalmente, é possível definir outras propriedades no comando [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview), dependendo dos requisitos de implementação da organização.

+++

+++**4. Atualizar lógica de código para usar uma carga JSON**

Altere a implementação do Audience Manager para que ele não dependa do objeto `AppMeasurement.js` ou `s`. Em vez disso, defina as variáveis em um objeto JavaScript formatado corretamente, que é convertido em um objeto JSON quando enviado para o Adobe. Ter uma [camada de dados](https://experienceleague.adobe.com/en/docs/analytics/implementation/prepare/data-layer) no site ajuda muito na definição de valores, pois você pode continuar fazendo referência a esses mesmos valores.

Para enviar dados para o Audience Manager, a carga do SDK da Web deve usar `data.__adobe.audiencemanager` com todas as variáveis de análise definidas neste objeto. As variáveis nesse objeto compartilham nomes e formatos idênticos aos de suas contrapartes da variável AppMeasurement. Por exemplo, se você definir a variável `products`, não a divida em objetos individuais, como faria com o XDM. Em vez disso, inclua-o como uma cadeia de caracteres exatamente é se você definir a variável `s.products`:

```json
{
  "data": {
    "__adobe": {
      "audiencemanager": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

Por fim, esta carga contém todos os valores desejados e todas as referências ao objeto `s` na sua implementação são removidas. Você pode usar qualquer um dos recursos fornecidos pelo JavaScript para definir esse objeto de carga, incluindo a notação de pontos para definir valores individuais.

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {audiencemanager: {}}}};
dataObj.data.__adobe.audiencemanager.pageName = window.document.title;
dataObj.data.__adobe.audiencemanager.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{audiencemanager:{...a}}}};
```

+++

+++**5. Atualizar chamadas de método para usar o SDK da Web**

Atualize todas as instâncias nas quais você chama [`s.t()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/t-method) e [`s.tl()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/tl-method), substituindo-as pelo comando [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview). Há três cenários a serem considerados:

* **Rastreamento de exibição de página**: substitua a chamada de rastreamento de exibição de página pelo comando `sendEvent` do SDK da Web:

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Rastreamento automático de links**: a propriedade de configuração [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) está habilitada por padrão. Ela define automaticamente as variáveis de rastreamento de link corretas para enviar dados ao Audience Manager. Para desabilitar o rastreamento automático de links, defina esta propriedade como `false` no comando [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview).

* **Rastreamento manual de links**: o SDK da Web não tem comandos separados entre chamadas pageview e não pageview. Forneça essa distinção no objeto de carga.

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.audiencemanager.linkName = "Example custom link";
  dataObj.data.__adobe.audiencemanager.linkType = "o";
  dataObj.data.__adobe.audiencemanager.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6. Validar e publicar alterações**

Depois de remover todas as referências ao AppMeasurement e ao objeto `s`, publique as alterações no ambiente de desenvolvimento para validar se a nova implementação funciona. Depois de validar que tudo funciona corretamente, você poderá publicar suas atualizações para produção.

Se tiver sido migrado corretamente, `AppMeasurement.js` não será mais necessário no site, e todas as referências a esse script poderão ser removidas.

+++

Neste ponto, a implementação do Audience Manager é totalmente migrada para o SDK da Web e está preparada para mudar para o Real-Time CDP no futuro.
