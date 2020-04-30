---
description: Adicione o Módulo de gerenciamento de Audiências ao Adobe Analytics AppMeasurement para encaminhar os dados do Analytics para o Audiência Manager, em vez de fazer com que o código da Biblioteca de integração de dados (DIL) do Audiência Manager envie um pixel da página.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Adicione o Módulo de gerenciamento de Audiências ao Adobe Analytics AppMeasurement para encaminhar os dados do Analytics para o Audiência Manager, em vez de fazer com que o código da Biblioteca de integração de dados (DIL) do Audiência Manager envie um pixel da página.
seo-title: Implementação do módulo de gerenciamento de Audiências
solution: Audience Manager
title: Implementação do módulo de gerenciamento de Audiências
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Como encaminhar dados do Adobe Analytics para o Audiência Manager {#implement-the-audience-management-module}

Siga as etapas neste tutorial para encaminhar [!DNL Analytics] dados para o Gerenciador de Audiências em vez de fazer com que o código do Gerenciador de Audiências [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) envie um pixel da página.

>[!TIP]
>
>Recomendamos que você use [!DNL Adobe Experience Platform Launch] para encaminhar [!UICONTROL Analytics] dados para o Gerenciador de Audiências. Ao usar [!UICONTROL Launch], não é necessário copiar manualmente o código para [!UICONTROL AppMeasurement], conforme mostrado nesta página.

## Pré-requisitos {#prereqs}

Além de ativar as extensões ou implementar o código descrito neste documento, você também deve:

* Implemente o serviço [de identidade da plataforma](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience.
* Ative o encaminhamento [pelo lado do](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) servidor para conjuntos de relatórios no [!UICONTROL Adobe Analytics Admin Console].

## Implementação {#implementation}

Há dois métodos para implementar o encaminhamento de dados do Adobe Analytics para o Audiência Manager, dependendo da solução de gerenciamento de tags usada.

### Implementação usando o Adobe Experience Platform Launch

A Adobe recomenda que você use a extensão [Iniciar](https://docs.adobe.com/content/help/en/launch/using/overview.html) para instrumentar o Adobe Analytics e o Gerenciador de Audiências em suas propriedades. Nesse caso, não é necessário copiar manualmente qualquer código. Em vez disso, você deve ativar o compartilhamento de dados na extensão do Analytics Launch, como mostrado na imagem abaixo. Consulte também a documentação do [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) .

>[!TIP]
>
>Se você instalar a extensão do Adobe Analytics, *não* instale também a extensão do Gerenciador de Audiências. O encaminhamento de dados da extensão do Analytics substitui a funcionalidade de extensão do Gerenciador de Audiências.

![Como ativar o compartilhamento de dados da extensão do Adobe Analytics para o Gerenciador de Audiências](/help/using/integration/assets/analytics-to-aam.png)

### Implementação usando o Adobe Digital Tag Management (DTM) ou qualquer outra solução de gerenciamento de tags


>[!WARNING]
>
>A Adobe lançou planos para encerrar o DTM até o final de 2020. Para obter mais informações e agendamento, consulte Planos do DTM para um Sunset nos fóruns [da comunidade](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)Adobe.

Para implementar o [!UICONTROL Audience Management Module] usando o [Adobe DTM](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) ou outra solução de gerenciamento de tags:

1. Baixe [!UICONTROL AppMeasurement] usando o Gerenciador [de código do](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html) Analytics (requer a versão 1.5 ou posterior).
1. Atualize seu [!UICONTROL AppMeasurement] código para a versão incluída no arquivo zip baixado.
1. Copie todo o código do arquivo `AppMeasurement_Module_AudienceManagement.js` zip. Cole-o no `appMeasurement.js` ficheiro logo acima do texto. `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Adicione o código, `s.loadModule("AudienceManagement");`, logo acima do `AppMeasurement_Module_AudienceManagement.js` código que você acabou de adicionar na etapa anterior.
1. Atualize e copie o código abaixo e adicione-o à `doPlugins` função em seu `AppMeasurement.js` arquivo.

```js
s.AudienceManagement.setup({ 
     "partner":"INSERT-YOUR-PARTNER-NAME-HERE", 
     "containerNSID":0, 
     "uuidCookie": { 
          "name":"aam_uuid", 
          "days":30
     },
     "visitorService": {
          "namespace": "INSERT-EXPERIENCE-CLOUD-ORGID-HERE" 
     } 
});
```

>[!TIP]
>
>A `audienceManagement.setup` função compartilha parâmetros com a `DIL.create` função do Gerenciador de Audiências, que você pode configurar neste código. Para obter mais informações sobre esses parâmetros, consulte Criação [de](../../dil/dil-class-overview/dil-create.md#dil-create)DIL.

## Elementos de código definidos {#code-elements-defined}

A tabela a seguir define variáveis importantes na amostra de código.

| Parâmetro | Descrição |
|--- |--- |
| `partner` | Obrigatório. Este é um nome de parceiro atribuído a você pela Adobe. Às vezes, é chamada de &quot;ID do parceiro&quot; ou &quot;subdomínio do parceiro&quot;.  Entre em contato com seu consultor da Adobe ou com o [Atendimento](https://helpx.adobe.com/marketing-cloud/contact-support.html) ao cliente se você não souber o nome do seu parceiro. |
| `containerNSID` | Obrigatório. A maioria dos clientes pode definir `"containerNSID":0` . No entanto, se sua empresa precisar personalizar sincronizações de ID com um container diferente, você pode especificar essa ID de container aqui. |
| `uuidCookie` | Opcional. Essa configuração permite que você defina um cookie da Adobe no domínio primário. Este cookie contém o [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Obrigatório. O `namespace` parâmetro é necessário se você usar o módulo AudienceManagement fornecido com a [!UICONTROL AppMeasurement] versão 2.10 ou mais recente. Este [!UICONTROL AudienceManagement] módulo requer o uso da versão [!UICONTROL Adobe Experience Platform Identity Service] 3.3 ou mais recente. <br> A ID [!UICONTROL Experience Cloud Organization ID] é fornecida por uma empresa ao se inscrever no [!UICONTROL Experience Cloud]. Descubra a ID da organização da empresa em [Organizações e vinculação](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html)de contas. |

## Resultados: Encaminhamento de dados para o Gerenciador de Audiências {#results-data-forwarding}

Sua [!DNL Analytics] implementação envia dados para o Gerenciador de Audiências depois que você:

* Ativado [!UICONTROL Server-Side Forwarding] (fale com o seu consultor sobre este recurso);
* O Adobe Experience Platform Identity Service foi implementado;
* Seguidas as etapas de implementação neste tutorial.

Esse processo envia dados para [!DNL Audience Manager]:

* Chamadas de visualização na página;
* De links rastreados;
* De visualizações de vídeo de marco e pulsação.

>[!NOTE]
>
>As variáveis enviadas para o Gerenciador de Audiências [!DNL Analytics] usam prefixos especiais. Você precisa entender e levar esses prefixos em conta ao criar características do Gerenciador de Audiências. Para obter mais informações sobre esses prefixos, consulte Requisitos de [prefixo para variáveis](../../features/traits/trait-variable-prefixes.md)-chave.