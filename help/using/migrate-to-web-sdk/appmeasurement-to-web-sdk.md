---
title: Atualize sua biblioteca de coleção de dados para o Audience Manager da biblioteca JavaScript do AppMeasurement para a biblioteca JavaScript do SDK da Web.
description: Entenda as etapas para atualizar sua biblioteca de coleção de dados para o Audience Manager da biblioteca JavaScript do AppMeasurement para a biblioteca JavaScript do SDK da Web.
source-git-commit: b0c35d79a07b481e332ddf8f4aedab5484416a51
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%

---


# Atualize sua biblioteca de coleção de dados para o Audience Manager da biblioteca JavaScript do AppMeasurement para a biblioteca JavaScript do SDK da Web

## Público-alvo {#intended-audience}

Esta página destina-se aos clientes do Audience Manager que usam o AppMeasurement para trazer dados de coleção da Web para o Audience Manager. Para clientes que usam o [extensão de tag do Audience Manager](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview), leia o guia sobre como atualizar a biblioteca de coleta de dados do Audience Manager [da extensão de tag Audience Manager para a extensão de tag do SDK da Web](dil-extension-to-web-sdk.md).

## Vantagens e desvantagens desse caminho de implementação

O uso dessa abordagem de migração tem vantagens e desvantagens. Avalie cuidadosamente cada opção para decidir qual abordagem é a melhor para sua organização.

| Benefícios | Desvantagens |
| --- | --- |
| <ul><li>**Usa sua implementação existente**: Embora essa abordagem exija algumas alterações de implementação, ela não requer uma implementação totalmente nova do zero. Você pode usar sua camada de dados e código existentes com o mínimo de alterações na lógica de implementação.</li><li>**Não requer um esquema**: nessa etapa de migração para o SDK da Web, você não precisa de um esquema XDM. Em vez disso, você pode preencher o `data` objeto, que envia dados diretamente para o Audience Manager. Quando a migração para o SDK da Web estiver concluída, você poderá criar um esquema para sua organização e usar o mapeamento de sequência de dados para preencher campos XDM aplicáveis. Se um esquema fosse necessário nesse estágio do processo de migração, sua organização seria forçada a usar um esquema XDM de Audience Manager. O uso desse esquema torna mais difícil para sua organização usar seu próprio esquema no futuro.</li></ul> | <ul><li>**Dívida técnica de implementação**: como essa abordagem usa uma forma modificada da implementação existente, pode ser mais difícil rastrear a lógica de implementação e realizar alterações no futuro, quando necessário.</li><li>**Requer mapeamento para enviar dados para a Plataforma**: quando sua organização estiver pronta para usar o Real-Time CDP, você deverá enviar dados para um conjunto de dados na Adobe Experience Platform. Essa ação exige que todos os campos na `data` ser uma entrada na ferramenta de mapeamento de sequência de dados que o atribui a um campo de esquema XDM. O mapeamento só precisa ser feito uma vez para esse fluxo de trabalho e não envolve fazer alterações de implementação. No entanto, essa é uma etapa extra que não é necessária ao enviar dados em um objeto XDM.</li></ul> |

A Adobe recomenda seguir esse caminho de implementação nos seguintes cenários:

* Você tem uma implementação existente usando a biblioteca JavaScript do Adobe Analytics AppMeasurement. Se você tiver uma implementação usando a extensão de tag Audience Manager, siga [Migração da extensão de tag do Audience Manager para a extensão de tag do SDK da Web](dil-extension-to-web-sdk.md) em vez disso.
* Você pretende usar o Real-Time CDP no futuro, mas não deseja substituir sua implementação de Audience Manager por uma implementação de SDK da Web do zero. Substituir sua implementação do zero no SDK da Web requer mais esforço, mas também oferece a arquitetura de implementação de longo prazo mais viável. Se a empresa estiver disposta a realizar o esforço de uma implementação limpa do SDK da Web, consulte a [Documentação do SDK da Web](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) para obter mais detalhes.

## Etapas necessárias para migrar para o SDK da Web

As etapas a seguir contêm objetivos concretos a serem atingidos. Clique em cada etapa para obter instruções detalhadas sobre como realizá-la.

+++**1. Criar e configurar um fluxo de dados**

Crie um fluxo de dados na Coleção de dados da Adobe Experience Platform. Ao enviar dados para esse fluxo de dados, ele encaminha os dados para o Audience Manager. No futuro, esse mesmo fluxo de dados encaminha dados para o Real-Time CDP.

1. Navegue até [experience.adobe.com](https://experience.adobe.com) e faça logon usando suas credenciais.
1. Use a página inicial ou o seletor de produto no canto superior direito para navegar até **[!UICONTROL Data Collection]**.
1. Na navegação à esquerda, selecione **[!UICONTROL Datastreams]**.
1. Selecionar **[!UICONTROL New Datastream]**.
1. Insira o nome desejado e selecione **[!UICONTROL Save]**.
1. Depois que o fluxo de dados for criado, selecione **[!UICONTROL Add Service]**.
1. No menu suspenso do serviço, selecione **[!UICONTROL Audience Manager]**.

   ![Adicionar serviço Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

Seu fluxo de dados agora está pronto para receber e transmitir dados para o Audience Manager. Observe a ID de sequência de dados, pois essa ID é necessária ao configurar o SDK da Web no código.

+++

+++**2. Instalar a biblioteca JavaScript do SDK da Web**

Consulte [Instale o SDK da Web usando a biblioteca JavaScript do](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) para obter detalhes e blocos de código a serem usados. Faça referência à versão mais recente de `alloy.js` para que suas chamadas de método possam ser usadas.

+++

+++**3. Configurar o SDK da Web**

Configure sua implementação para apontar para o fluxo de dados criado na etapa 1 usando o SDK da Web [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) comando. A variável `configure` O comando deve ser definido em cada página para que você possa incluí-lo junto com o código de instalação da biblioteca.

Use o [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) e [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) propriedades no SDK da Web `configure` comando:

* Defina o `edgeConfigId` para a ID de fluxo de dados recuperada da etapa anterior.
* Defina o `orgId` para a ID da organização IMS.

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Opcionalmente, é possível definir outras propriedades na variável [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) dependendo dos requisitos de implementação da organização.

+++

+++**4. Atualizar a lógica do código para usar uma carga JSON**

Altere a implementação do Audience Manager para que ele não dependa de `AppMeasurement.js` ou o `s` objeto. Em vez disso, defina as variáveis em um objeto JavaScript formatado corretamente, que é convertido em um objeto JSON quando enviado para o Adobe. Ter um [camada de dados](https://experienceleague.adobe.com/en/docs/analytics/implementation/prepare/data-layer) no seu site ajuda muito ao definir valores, pois você pode continuar fazendo referência a esses mesmos valores.

Para enviar dados para o Audience Manager, a carga do SDK da Web deve usar `data.__adobe.audiencemanager` com todas as variáveis do analytics definidas neste objeto. As variáveis nesse objeto compartilham nomes e formatos idênticos aos de suas contrapartes da variável AppMeasurement. Por exemplo, se você definir a variável `products` não a divida em objetos individuais, como faria com o XDM. Em vez disso, inclua-o como uma string. Exatamente é se você definir a variável `s.products` Variável:

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

Em última análise, essa carga contém todos os valores desejados e todas as referências à `s` objetos na implementação do são removidos. Você pode usar qualquer um dos recursos fornecidos pelo JavaScript para definir esse objeto de carga útil, incluindo a notação de pontos para definir valores individuais.

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

Atualizar todas as instâncias para as quais você chamar [`s.t()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/t-method) e [`s.tl()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/tl-method), substituindo-os pelo [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) comando. Há três cenários a serem considerados:

* **Rastreamento de exibição de página**: substitua a chamada de rastreamento de exibição de página pelo SDK da Web `sendEvent` comando:

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Rastreamento automático de links**: A variável [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) a propriedade de configuração é ativada por padrão. Ela define automaticamente as variáveis de rastreamento de link corretas para enviar dados ao Audience Manager. Se quiser desativar o rastreamento automático de links, defina essa propriedade como `false` no prazo de [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) comando.

* **Rastreamento manual de links**: o SDK da Web não tem comandos separados entre chamadas de exibição de página e de não exibição de página. Forneça essa distinção no objeto de carga.

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

Depois de remover todas as referências ao AppMeasurement e à `s` objeto, publique as alterações no ambiente de desenvolvimento para validar se a nova implementação funciona. Depois de validar que tudo funciona corretamente, você poderá publicar suas atualizações para produção.

Se migrado corretamente, `AppMeasurement.js` O não é mais necessário no site e todas as referências a esse script podem ser removidas.

+++

Neste ponto, a implementação do Audience Manager é totalmente migrada para o SDK da Web e está preparada para mudar para o Real-Time CDP no futuro.
