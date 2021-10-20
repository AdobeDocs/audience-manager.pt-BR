---
description: Adicione o Módulo de gerenciamento de público-alvo ao Adobe Analytics AppMeasurement para encaminhar os dados do Analytics para o Audience Manager, em vez de ter o código de Data Integration Library de Audience Manager (DIL) para enviar um pixel da página.
keywords: análise de público-alvo; análises; ssf; encaminhamento pelo lado do servidor
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

Siga as etapas neste tutorial para avançar [!DNL Analytics] para [!DNL Audience Manager] em vez de ter a [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) envia um pixel da página.

>[!TIP]
>
>Recomendamos que você use [!DNL Adobe Experience Platform Tags] para encaminhar [!UICONTROL Analytics] dados em [!DNL Audience Manager]. Ao usar [!UICONTROL Tags], não é necessário copiar manualmente o código no [!DNL AppMeasurement], conforme mostrado nesta página.

## Pré-requisitos {#prereqs}

Além de ativar as extensões ou implementar o código descrito neste documento, você também deve:

* Implemente o [Serviço de identidade da Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html).
* Habilitar [Encaminhamento pelo lado do servidor](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) para conjuntos de relatórios na [!UICONTROL Adobe Analytics Admin Console].

## Implementação {#implementation}

Há dois métodos para implementar o encaminhamento de dados do [!DNL Adobe Analytics] para [!DNL Audience Manager], dependendo da solução de gerenciamento de tags usada.

### Implementação usando [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] A recomenda usar a variável [Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) extensão ao instrumento [!DNL Adobe Analytics] e [!DNL Audience Manager] nas propriedades. Nesse caso, não é necessário copiar manualmente qualquer código. Em vez disso, você deve ativar o compartilhamento de dados no [!DNL Analytics] , conforme mostrado na imagem abaixo. Consulte também a [Extensão do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager) documentação.

>[!TIP]
>
>Se você instalar o [!DNL Adobe Analytics] extensão, *não* instale também o [!DNL Audience Manager] extensão. Encaminhamento de dados do [!DNL Analytics] substitui [!DNL Audience Manager] funcionalidade de extensão.

![Como habilitar o compartilhamento de dados da extensão do Adobe Analytics para o Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Elementos de código definidos {#code-elements-defined}

A tabela a seguir define variáveis importantes na amostra de código.

| Parâmetro | Descrição |
|--- |--- |
| `partner` | Obrigatório. Este é um nome de parceiro atribuído a você [!DNL Adobe]. Às vezes, ela é chamada de [!UICONTROL partner ID] ou subdomínio do parceiro.  Entre em contato com seu [!DNL Adobe] consultor ou [Atendimento ao cliente](https://helpx.adobe.com/br/marketing-cloud/contact-support.html) se você não souber o nome do seu parceiro. |
| `containerNSID` | Obrigatório. A maioria dos clientes pode apenas definir  `"containerNSID":0` . No entanto, se sua empresa precisar personalizar sincronizações de ID com um contêiner diferente, especifique essa ID do contêiner aqui. |
| `uuidCookie` | Opcional. Essa configuração permite que você defina uma [!DNL Adobe] no domínio primário. Essa [!DNL cookie] contém a variável [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Obrigatório. O `namespace` é necessário se você usar a variável [!DNL AudienceManagement] módulo fornecido com [!UICONTROL AppMeasurement] versão 2.10 ou mais recente. Essa [!UICONTROL AudienceManagement] O módulo requer que você use [!UICONTROL Adobe Experience Platform Identity Service] 3.3 ou mais recente. <br><br>O [!UICONTROL Experience Cloud Organization ID] é a ID que uma empresa fornece ao se inscrever para a [!UICONTROL Experience Cloud]. Descubra a ID da organização de sua empresa em [Organizações e vinculação de contas](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html). |

## Resultados: Encaminhamento de dados para [!DNL Audience Manager] {#results-data-forwarding}

Seu [!DNL Analytics] implementação envia dados para [!DNL Audience Manager] depois de:

* Ativado [!UICONTROL Server-Side Forwarding] (fale com o seu consultor sobre esse recurso);
* Implementou o [!DNL Adobe Experience Platform Identity Service];
* Seguidas as etapas de implementação neste tutorial.

Esse processo envia dados para o [!DNL Audience Manager]:

* Em chamadas de exibição de página;
* A partir de links rastreados;
* De marcos de vídeo e exibições de vídeo de pulsação.

>[!NOTE]
>
>As variáveis enviadas para [!DNL Audience Manager] from [!DNL Analytics] use prefixos especiais. Você precisa entender e levar esses prefixos em consideração ao criar [!DNL Audience Manager] características. Para obter mais informações sobre esses prefixos, consulte [Requisitos de prefixo para variáveis-chave](../../features/traits/trait-variable-prefixes.md).
