---
description: Adicione o módulo Gerenciamento de público-alvo ao Adobe Analytics AppMeasurement para encaminhar os dados do Analytics para o Audience Manager, em vez de fazer com que o código de Data Integration Library (DIL) de Audience Manager envie um pixel da página.
keywords: audience analytics, analytics, ssf, encaminhamento pelo lado do servidor
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: Implementar o módulo Gerenciamento de público-alvo
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---

# Como encaminhar dados do [!DNL Adobe Analytics] para [!DNL Audience Manager] {#implement-the-audience-management-module}

Siga as etapas deste tutorial para avançar [!DNL Analytics] dados para [!DNL Audience Manager] em vez de ter o [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) enviam um pixel da página.

>[!TIP]
>
>Recomendamos que você use [!DNL Adobe Experience Platform Tags] para encaminhar [!UICONTROL Analytics] entrada de dados [!DNL Audience Manager]. Ao usar [!UICONTROL Tags], não é necessário copiar o código manualmente para [!DNL AppMeasurement], conforme mostrado nesta página.

## Pré-requisitos {#prereqs}

Além de ativar as extensões ou implementar o código descrito neste documento, você também deve:

* Implementar o [Serviço de identidade da Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html).
* Ativar [Encaminhamento pelo lado do servidor](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) para conjuntos de relatórios na [!UICONTROL Adobe Analytics Admin Console].

## Implementação {#implementation}

Há dois métodos para implementar o encaminhamento de dados do [!DNL Adobe Analytics] para [!DNL Audience Manager], dependendo da solução de gerenciamento de tags usada.

### Implementação usando o [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] A recomenda a utilização do [Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) extensão do instrumento [!DNL Adobe Analytics] e [!DNL Audience Manager] em suas propriedades. Nesse caso, não é necessário copiar manualmente nenhum código. Em vez disso, você deve ativar o compartilhamento de dados na [!DNL Analytics] conforme mostrado na imagem abaixo. Consulte também a [Extensão do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager) documentação.

>[!TIP]
>
>Se você instalar o [!DNL Adobe Analytics] extensão, *não* instale também o [!DNL Audience Manager] extensão. Encaminhamento de dados do [!DNL Analytics] A extensão substitui a [!DNL Audience Manager] funcionalidade de extensão.

![Como ativar o compartilhamento de dados da extensão do Adobe Analytics para o Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Elementos de código definidos {#code-elements-defined}

A tabela a seguir define variáveis importantes na amostra de código.

| Parâmetro | Descrição |
|--- |--- |
| `partner` | Obrigatório. Este é um nome de parceiro atribuído a você por [!DNL Adobe]. Às vezes, é chamado de [!UICONTROL partner ID] ou subdomínio do parceiro.  Entre em contato com [!DNL Adobe] consultor ou [Atendimento ao cliente](https://helpx.adobe.com/br/marketing-cloud/contact-support.html) se você não souber o nome do seu parceiro. |
| `containerNSID` | Obrigatório. A maioria dos clientes pode simplesmente definir  `"containerNSID":0` . No entanto, se sua empresa precisa personalizar sincronizações de ID com um contêiner diferente, você pode especificar essa ID de contêiner aqui. |
| `uuidCookie` | Opcional. Essa configuração permite definir uma variável [!DNL Adobe] cookie no domínio próprio. Este [!DNL cookie] contém o [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Obrigatório. A variável `namespace` é necessário se você usar o parâmetro [!DNL AudienceManagement] módulo incluído com [!UICONTROL AppMeasurement] versão 2.10 ou mais recente. Este [!UICONTROL AudienceManagement] o módulo exige que você use [!UICONTROL Adobe Experience Platform Identity Service] 3.3 ou mais recente. <br><br>A variável [!UICONTROL Experience Cloud Organization ID] é a ID que uma empresa recebe ao se inscrever na [!UICONTROL Experience Cloud]. Descubra a ID da organização da sua empresa em [Organizações e vinculação de contas](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html). |

## Resultados: encaminhamento de dados para [!DNL Audience Manager] {#results-data-forwarding}

Seu [!DNL Analytics] a implementação envia dados para o [!DNL Audience Manager] depois de ter:

* Ativado [!UICONTROL Server-Side Forwarding] (fale com o consultor sobre esse recurso);
* Implementou o [!DNL Adobe Experience Platform Identity Service];
* Seguidas as etapas de implementação deste tutorial.

Esse processo envia dados para o [!DNL Audience Manager]:

* Em chamadas de exibição de página;
* A partir de links rastreados;
* Das visualizações de marco e pulsação de vídeo do vídeo.

>[!NOTE]
>
>As variáveis enviadas para o [!DNL Audience Manager] de [!DNL Analytics] use prefixos especiais. É necessário compreender e considerar esses prefixos ao criar [!DNL Audience Manager] características. Para obter mais informações sobre esses prefixos, consulte [Requisitos de prefixo para variáveis-chave](../../features/traits/trait-variable-prefixes.md).
