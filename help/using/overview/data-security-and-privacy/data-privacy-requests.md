---
description: Este documento aborda os aspectos técnicos relacionados à conformidade com as regulamentações de privacidade de dados do Audience Manager.
seo-description: This document covers the technicalities related to data privacy regulations compliance for Audience Manager.
seo-title: Data Privacy Requests
solution: Audience Manager
keywords: Interface do usuário do GDPR, API do GDPR, CCPA, privacidade
title: Solicitações de privacidade de dados
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: a1fc9c21-3417-4899-a585-92ad2cb25362
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '1444'
ht-degree: 58%

---

# Solicitações de privacidade de dados {#data-privacy-requests}

## Visão geral {#overview}

Este documento fornece uma visão geral do gerenciamento de privacidade de dados individuais e de solicitações de recusa que você pode enviar para a [!DNL Audience Manager] através da [Interface do usuário do Privacy Service](https://privacyui.cloud.adobe.io/) e **[!DNL Privacy Service API]**.

Essas ferramentas permitem enviar solicitações de privacidade de dados do consumidor feitas em [!DNL GDPR] e [!DNL CCPA].

Antes de ler este artigo, recomendamos consultar o [Glossário do GDPR](../data-security-and-privacy/aam-gdpr-glossary.md) e o [Glossário da CCPA](aam-ccpa-glossary.md) para entender melhor a terminologia usada aqui.

Você pode enviar solicitações individuais para acessar e excluir dados do consumidor de [!DNL Audience Manager], de duas formas:

* Por meio da [Interface do usuário do Privacy Service](https://privacyui.cloud.adobe.io/). Consulte a documentação [aqui](https://docs.adobe.com/content/help/pt-BR/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Por meio da **[!DNL Privacy Service API]**. Consulte a documentação [aqui](https://docs.adobe.com/content/help/pt-BR/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)[!DNL API] e a referência da [aqui](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Ao enviar solicitações individuais de privacidade de dados, você pode enviar qualquer [!DNL Audience Manager] identificadores (IDs), conforme descrito no **[Identificadores de Audience Manager](data-privacy-ids.md)** , juntamente com suas respectivas IDs de namespace (IDs da fonte de dados).

O [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) oferece suporte a dois tipos de solicitações: acesso aos dados e solicitações de exclusão de dados.

## Solicitações de acesso a dados {#access-data}

Você pode enviar solicitações individuais de acesso aos dados por meio do [Interface do usuário do Privacy Service](https://privacyui.cloud.adobe.io) (documentação) [here](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=en) ou chamando a API do Privacy Service (documentação) [here](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=en) e [!DNL API] referência [here](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

A [Interface do usuário do Privacy Service](https://privacyui.cloud.adobe.io/) permite criar novas solicitações de trabalho usando o [!UICONTROL Request Builder] ou fazendo upload de um arquivo [!DNL JSON].

Para ver a aparência de um arquivo válido [!DNL JSON], é possível [ baixar uma amostra de JSON](../data-security-and-privacy/assets/access_request.json).

Compreendemos o seu compromisso de atender às suas solicitações de privacidade de dados dentro do período definido pela legislação.

## Solicitações de exclusão de dados  {#delete-data}

Você pode enviar solicitações de exclusão de dados por meio do [Interface do usuário do Privacy Service](https://privacyui.cloud.adobe.io) (documentação) [here](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=en) ou chamando a API do Privacy Service (documentação) [here](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=en) e [!DNL API] referência [here](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

A [Interface do usuário do Privacy Service](https://privacyui.cloud.adobe.io/) permite criar novas solicitações de trabalho usando o [!UICONTROL Request Builder] ou fazendo upload de um arquivo [!DNL JSON].

Para ver a aparência de um arquivo válido [!DNL JSON], é possível [ baixar uma amostra de JSON](../data-security-and-privacy/assets/access_request.json).

A Adobe entende seu compromisso de atender às solicitações de privacidade dos clientes em 30 dias. Por essa razão, [!DNL Adobe] O está comprometido a processar sua solicitação de exclusão de dados assim que possível.

Em resposta às solicitações de exclusão de dados do consumidor, [!DNL Audience Manager] exclui características e segmentos associados à variável [!DNL Audience Manager] identificador incluído na solicitação. Além disso, o respectivo [!DNL Audience Manager] identificadores para o indivíduo que recusou a recolha de dados por [!DNL Audience Manager] e os respectivos mapeamentos de ID serão removidos.

Ao enviar IDs declaradas, como IDs do [!DNL CRM] entre dispositivos ou IDs de , em solicitações de privacidade de dados, o executará a exclusão necessária em todos os dispositivos vinculados (até 100 dispositivos por ID declarada).[!DNL cookie][!DNL Audience Manager]

[!DNL Audience Manager]O tentará notificar os parceiros de ativação sobre solicitações de exclusão enviando informações de cancelamento de segmentos para os titulares dos dados que solicitam a exclusão de determinados dados. No entanto, alguns parceiros de ativação:

1. Não é possível oferecer suporte a solicitações de cancelamento (ou remoção de segmento) do [!DNL Audience Manager] e/ou
2. Não podem receber atualizações do [!DNL Audience Manager] com uma frequência inferior a 30 dias. Nesses casos, [!DNL Audience Manager] os clientes não podem enviar solicitações de exclusão para parceiros de ativação de forma automatizada [!DNL Audience Manager].

Nesses casos, não é possível enviar solicitações de exclusão para parceiros de ativação de forma automatizada pelo [!DNL Audience Manager].

Consulte nossa [documentação da lista de destinos com base em dispositivo](assets/AAM-Partners-October2019.xlsx) para ver qual [!DNL Audience Manager] os parceiros de ativação oferecem suporte ao cancelamento de segmentos.

## Solicitações de recusa {#opt-out-requests}

[!DNL Audience Manager] apoia as normas do setor em matéria de gestão de não participação. Leia para obter informações completas sobre os tipos de recusa compatíveis com o [!DNL Audience Manager].

Enquanto as solicitações de acesso e exclusão de dados são tratadas pelo [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en), as solicitações de recusa são feitas por meio da [!DNL DCS API]. Leia para saber qual é a opção de não participação [!DNL API] As chamadas devem parecer.

### Solicitações globais de recusa

A recusa global representa uma opção de não participação em [!DNL Audience Manager] e outros [!DNL Adobe Experience Cloud] soluções para todas as marcas. A tabela abaixo lista os métodos usados para a recusa global:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recusar para </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>A página <a href="https://www.adobe.com/br/privacy/opt-out.html#customeruse" format="http" scope="external"> Suas escolhas de privacidade </a> fornece recursos de 1 clique que permitem que os usuários finais controlem e excluam a coleta de dados pelas soluções de publicidade da Adobe Experience Cloud (incluindo o Audience Manager). Especificamente, consulte a seção <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external">Cliente comercial </a> da página Opções de privacidade. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chamadas de API diretas para o Audience Manager </p> </td> 
   <td colname="col2"> <p>Seus usuários podem recusar a coleta de dados por todas as marcas do Audience manager fazendo uma chamada para a API DCS abaixo e incluindo a <a href="../../reference/ids-in-aam.md"> ID de usuário do Audience Manager</a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Como resultado, definiremos os cookies <code>demdex=NOTARGET</code> e <code>dextp=NOTARGET</code> para a ID de usuário do Audience Manager enviada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dispositivos móveis </p> </td> 
   <td colname="col2"> <p>Consulte as configurações de recusa e privacidade para: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://experienceleague.adobe.com/docs/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Dispositivos Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://experienceleague.adobe.com/docs/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> Dispositivos iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Seus usuários finais também podem recusar a coleta global de dados ao acessar os sites de nossos parceiros padrão do setor.

* [The Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Seguindo as solicitações de recusa descritas acima:

* [!DNL Audience Manager]O interromperá toda a coleta de dados, segmentação ou ativação, desde que o usuário não limpe os cookies do navegador.
* Os dados históricos são removidos do perfil do usuário após 120 dias.

### Recusa em nível de parceiro com chamadas de ID declaradas

A recusa em nível de parceiro permite que você exclua seus usuários da coleta de dados por [!DNL Audience Manager] parceiros. Você pode enviar solicitações de recusa em nível de parceiro para IDs entre dispositivos, incluindo [!DNL CRM] IDs e endereços de email com hash.

Seguindo uma recusa em nível de parceiro com uma chamada de ID declarada:

* A [ID de CRM](../../reference/ids-in-aam.md) recusa a coleta de dados;
* A última ID de dispositivo ([ID de usuário exclusiva do Audience Manager](../../reference/ids-in-aam.md)) vinculada à [ID de CRM](../../reference/ids-in-aam.md) recusa a coleta de dados.
* [!DNL Audience Manager]O cessará toda a coleta, segmentação ou ativação de dados a partir de agora para a ID de e a última ID de dispositivo vinculada à ID de ;[!DNL CRM][!DNL CRM]
* [!DNL Audience Manager] cancela a segmentação do opted out [!DNL CRM] ID e ID do último dispositivo de todos os segmentos;
* [!UICONTROL Destination] os parceiros recebem a solicitação de cancelamento de segmentos para a [!DNL CRM] ID e ID do último dispositivo. O cancelamento de segmentos funciona para destinos [em tempo real](data-privacy-requests.md#aam-partners-with-unsegmentation) e em lote.
* Nenhum dado histórico é excluído.

When [!DNL Audience Manager] recebe uma solicitação de recusa em nível de parceiro, a variável [!DNL JSON] retornado pelo [!DNL DCS] contém a variável [código de erro 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), com a mensagem [!UICONTROL "Encountered opt out tag"], em vez de [!DNL Audience Manager] ID do usuário.

Você pode fazer uma solicitação de recusa de ID declarada com os pares de valor-chave `d_cid` e `d_cid_ic`. Os parâmetros herdados como `d_dpid` e `d_dpuuid` ainda funcionam, mas são considerados obsoletos. Consulte [CID substitui DPID e DPUUID](../../reference/cid.md). Nos exemplos, *itálico* indica um espaço reservado para variável.

#### Recusar com [!DNL CID] e [!DNL CID_IC]

Para obter uma descrição e sintaxe, consulte [Variáveis e sintaxe de URL para IDs declaradas](../../features/declared-ids.md#variables-and-syntax).

| Recusa de uso | Amostra de código |
|--- |--- |
| Uma ID de provedor de dados e ID de usuário. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Um código de integração e ID de usuário. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Vários  `d_cid`  e  `d_cid_ic`  pares de valores-chave. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Recusa em nível de parceiro com chamadas de ID de dispositivo

A recusa em nível de parceiro permite que você exclua seus usuários da coleta de dados por [!DNL Audience Manager] parceiros. Você pode recusar a coleta de dados em uma determinada ID de dispositivo para uma marca fazendo as seguintes chamadas para a [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Recusa de uso | Amostra de código |
|--- |--- |
| Um [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Um [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Leia mais sobre `uuid`, `mid` e `imsOrgId` no [Índice de IDs no Audience Manager](/help/using/reference/ids-in-aam.md).

Seguindo uma opção de recusa em nível de parceiro com uma chamada de ID de dispositivo:

* A ID do dispositivo recusa a coleta de dados.
* [!DNL Audience Manager]O encerrará toda a coleta de dados, segmentação ou ativação para o parceiro a partir da ID do dispositivo.
* [!DNL Audience Manager] cancela a segmentação da ID do dispositivo de todos os segmentos;
* Os parceiros de destino recebem a solicitação de cancelamento de segmentos para a ID do dispositivo. O cancelamento de segmentos funciona para destinos [em tempo real](data-privacy-requests.md#aam-partners-with-unsegmentation) e em lote.
* Nenhum dado histórico é excluído.

## [!DNL Audience Manager] Parceiros com recursos de cancelamento de segmentos {#aam-partners-with-unsegmentation}

Para ajudar você a automatizar as solicitações de privacidade de dados do consumidor, [!DNL Audience Manager] O tentará notificar os parceiros de ativação sobre solicitações de exclusão dos titulares de dados, enviando a eles informações de cancelamento (ou remoção de segmentos).

Entretanto, alguns de nossos parceiros e ativação:

1. Não é possível suportar solicitações de cancelamento de segmentos de [!DNL Audience Manager] e/ou
2. Não podem receber atualizações do [!DNL Audience Manager] mais frequentemente do que uma vez em 30 dias.

Nesses casos, não é possível enviar solicitações de exclusão para parceiros de ativação de forma automatizada pelo [!DNL Audience Manager].

Consulte a [lista de destinos com base em dispositivos](/help/using/features/destinations/device-based-destinations-list.md) para ver quais parceiros de ativação do oferecem suporte ao cancelamento de segmentos.[!DNL Audience Manager]

## Solicitações de correção de dados {#correction}

Dado que [!DNL Audience Manager] não for a fonte dos dados, há uma função limitada para a correção de dados no [!DNL Audience Manager]. A correção poderia significar que o consumidor solicitou a não qualificação de um erro [!UICONTROL trait]/[!UICONTROL segment] ou qualificados para [!UICONTROL trait]/[!UICONTROL segment].

[!DNL Audience Manager] os clientes podem optar por capturar os sinais/características/segmentos relevantes em relação aos perfis do usuário e enviar essas informações por meio de [assimilação de dados offline](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) para [!DNL Audience Manager]. Observe que o usuário continuará se qualificando para o original [!UICONTROL trait] e [!UICONTROL segments] se repetirem o seu comportamento.
