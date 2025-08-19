---
description: Adicione o módulo Gerenciamento de público-alvo ao Adobe Analytics AppMeasurement para encaminhar os dados do Analytics para o Audience Manager em vez de fazer com que o código do Audience Manager Data Integration Library (DIL) envie um pixel da página.
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
source-wordcount: '457'
ht-degree: 1%

---

# Como encaminhar dados de [!DNL Adobe Analytics] para [!DNL Audience Manager] {#implement-the-audience-management-module}

Siga as etapas deste tutorial para encaminhar os dados do [!DNL Analytics] para [!DNL Audience Manager] em vez de fazer com que o código [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) envie um pixel da página.

>[!TIP]
>
>Recomendamos que você use o [!DNL Adobe Experience Platform Tags] para encaminhar os dados do [!UICONTROL Analytics] para o [!DNL Audience Manager]. Ao usar o [!UICONTROL Tags], você não precisa copiar manualmente o código para o [!DNL AppMeasurement], conforme mostrado nesta página.

## Pré-requisitos {#prereqs}

Além de ativar as extensões ou implementar o código descrito neste documento, você também deve:

* Implementar o [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR).
* Habilitar o [Encaminhamento pelo Lado do Servidor](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=pt-BR) para conjuntos de relatórios no [!UICONTROL Adobe Analytics Admin Console].

## Implementação {#implementation}

Há dois métodos para implementar o encaminhamento de dados de [!DNL Adobe Analytics] para [!DNL Audience Manager], dependendo da solução de gerenciamento de tags usada.

### Implementação usando [!DNL Adobe Experience Platform Tags]

A [!DNL Adobe] recomenda usar a extensão [Marcas](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR) para instrumentar [!DNL Adobe Analytics] e [!DNL Audience Manager] em suas propriedades. Nesse caso, não é necessário copiar manualmente nenhum código. Em vez disso, você deve habilitar o compartilhamento de dados na extensão [!DNL Analytics], conforme mostrado na imagem abaixo. Consulte também a documentação da [Extensão do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=pt-BR#adobe-audience-manager).

>[!TIP]
>
>Se você instalar a extensão [!DNL Adobe Analytics], *não* instale também a extensão [!DNL Audience Manager]. O encaminhamento de dados da extensão [!DNL Analytics] substitui a funcionalidade de extensão [!DNL Audience Manager].

![Como habilitar o compartilhamento de dados da extensão do Adobe Analytics para o Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Elementos de código definidos {#code-elements-defined}

A tabela a seguir define variáveis importantes na amostra de código.

| Parâmetro | Descrição |
|--- |--- |
| `partner` | Obrigatório. Este é um nome de parceiro atribuído a você por [!DNL Adobe]. Às vezes, ele é chamado de [!UICONTROL partner ID] ou subdomínio do parceiro.  Entre em contato com o consultor do [!DNL Adobe] ou com o [Atendimento ao cliente](https://helpx.adobe.com/br/marketing-cloud/contact-support.html) se você não souber o nome do parceiro. |
| `containerNSID` | Obrigatório. A maioria dos clientes pode simplesmente definir `"containerNSID":0`. No entanto, se sua empresa precisa personalizar sincronizações de ID com um contêiner diferente, você pode especificar essa ID de contêiner aqui. |
| `uuidCookie` | Opcional. Essa configuração permite que você defina um cookie [!DNL Adobe] no domínio próprio. Este [!DNL cookie] contém o [UUID](../../reference/ids-in-aam.md). |
| `visitorService` - `namespace` | Obrigatório. O parâmetro `namespace` é necessário se você usar o módulo [!DNL AudienceManagement] agrupado com a versão [!UICONTROL AppMeasurement] 2.10 ou mais recente. Este módulo [!UICONTROL AudienceManagement] requer o uso do [!UICONTROL Adobe Experience Platform Identity Service] 3.3 ou mais recente. <br><br>O [!UICONTROL Experience Cloud Organization ID] é a ID que uma empresa recebe ao se inscrever no [!UICONTROL Experience Cloud]. Descubra a ID de organização da sua empresa em [Organizações e Vinculação de Contas](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=pt-BR). |

## Resultados: Encaminhamento de Dados para [!DNL Audience Manager] {#results-data-forwarding}

Sua implementação do [!DNL Analytics] envia dados para [!DNL Audience Manager] após:

* Habilitado [!UICONTROL Server-Side Forwarding] (fale com seu consultor sobre este recurso);
* Implementou o [!DNL Adobe Experience Platform Identity Service];
* Seguidas as etapas de implementação deste tutorial.

Este processo envia dados para [!DNL Audience Manager]:

* Em chamadas de exibição de página;
* A partir de links rastreados;
* Das visualizações de marco e pulsação de vídeo do vídeo.

>[!NOTE]
>
>As variáveis enviadas para [!DNL Audience Manager] de [!DNL Analytics] usam prefixos especiais. Você precisa entender e considerar esses prefixos ao criar características de [!DNL Audience Manager]. Para obter mais informações sobre esses prefixos, consulte [Requisitos de prefixo para variáveis-chave](../../features/traits/trait-variable-prefixes.md).
