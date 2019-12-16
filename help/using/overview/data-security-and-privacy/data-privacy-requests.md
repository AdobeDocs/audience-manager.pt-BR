---
description: Este documento aborda os aspectos técnicos relacionados à conformidade das regulamentações de privacidade de dados para o Audience Manager.
seo-description: Este documento aborda os aspectos técnicos relacionados à conformidade das regulamentações de privacidade de dados para o Audience Manager.
seo-title: Solicitações de privacidade de dados
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Solicitações de privacidade de dados
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: ff4bf70c9012f99289ea82824a552db97430fbf2

---


# Solicitações de privacidade de dados {#data-privacy-requests}

## Visão geral {#overview}

Este documento fornece uma visão geral do gerenciamento de privacidade de dados individuais e de solicitações de não participação que você pode enviar para o Audience Manager por meio da interface do usuário [do](https://gdprui.cloud.adobe.io/) Privacy Service e do **[!DNL Privacy Service API]**.

Essas ferramentas permitem que você envie solicitações de privacidade de dados do consumidor feitas sob RGPD e CCPA.

Antes de ler este artigo, recomendamos passar pelo Glossário [do](../data-security-and-privacy/aam-gdpr-glossary.md) RGPD e pelo Glossário [do](aam-ccpa-glossary.md)CCPA para entender melhor a terminologia usada aqui.

Você pode enviar solicitações individuais para acessar e excluir dados do consumidor do Audience Manager de duas formas:

* Por meio da interface do usuário do [Privacy Service](https://gdprui.cloud.adobe.io/). Consulte a documentação [aqui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Através do **[!DNL Privacy Service API]**. Consulte a documentação [aqui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) e a referência da API [aqui](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Ao enviar solicitações individuais de privacidade de dados, você pode enviar identificadores (IDs) do Audience Manager, conforme descrito na seção Identificadores **[do](data-privacy-ids.md)** Audience Manager, juntamente com suas respectivas IDs de namespace (IDs de fonte de dados).

O [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) suporta dois tipos de solicitações: acesso aos dados e solicitações de exclusão de dados.

## Solicitações de acesso a dados {#access-data}

Você pode enviar solicitações individuais de acesso aos dados por meio da interface do usuário [do](https://gdprui.cloud.adobe.io/) Privacy Service (documentação [aqui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) ou chamando a [!DNL Privacy Service API] (documentação [aqui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) e [!DNL API] referência [aqui](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

A interface do usuário [do](https://gdprui.cloud.adobe.io/) Privacy Service permite que você crie novas solicitações de trabalho usando o [!UICONTROL Request Builder] ou fazendo upload de um [!DNL JSON] arquivo.

Para ver a aparência de um [!DNL JSON] arquivo válido, é possível [baixar uma amostra de JSON](../data-security-and-privacy/assets/access_request.json).

Compreendemos o seu compromisso de atender às suas solicitações de privacidade de dados dentro do período definido pela legislação.

## Solicitações de exclusão de dados{#delete-data}

Você pode enviar solicitações de exclusão de dados por meio da interface do usuário [do](https://gdprui.cloud.adobe.io/) Privacy Service (documentação [aqui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) ou chamando a [!DNL Privacy Service API] (documentação [aqui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) e referência da API [aqui](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

A interface do usuário [do](https://gdprui.cloud.adobe.io/) Privacy Service permite que você crie novas solicitações de trabalho usando o [!UICONTROL Request Builder] ou fazendo upload de um [!DNL JSON] arquivo.

Para ver a aparência de um [!DNL JSON] arquivo válido, é possível [baixar uma amostra de JSON](../data-security-and-privacy/assets/access_request.json).

A Adobe entende seu compromisso de atender às solicitações de privacidade dos seus clientes dentro de 30 dias. Por esse motivo, a Adobe tem compromisso de processar sua solicitação de exclusão de dados assim que possível.

Em resposta às solicitações de exclusão de dados do consumidor, o Audience Manager exclui características e segmentos associados ao identificador do Audience Manager incluído na solicitação. Além disso, os respectivos identificadores do Audience Manager para o indivíduo que optou por não fazer mais coleta de dados pelo Audience Manager e os respectivos mapeamentos de ID serão removidos.

Quando você envia IDs declaradas, como IDs de dispositivo cruzado ou IDs de cookie, em solicitações de privacidade de dados, o Audience Manager executa a exclusão necessária em todos os dispositivos vinculados (até 100 dispositivos por ID declarada). [!DNL CRM]

O Audience Manager tentará notificar os parceiros de ativação sobre solicitações de exclusão enviando-lhes informações de cancelamento de segmentos para os Indivíduos de dados que solicitam a exclusão de determinados dados. No entanto, alguns parceiros de ativação:

1. Não é possível suportar solicitações de cancelamento de segmento (ou remoção de segmento) do Audience Manager e/ou
2. Não é possível receber atualizações do Audience Manager com uma frequência inferior a 30 dias. Nesses casos, os clientes do Audience Manager não podem enviar solicitações de exclusão para parceiros de ativação de forma automatizada por meio do Audience Manager.

Nesses casos, não é possível enviar solicitações de exclusão para parceiros de ativação de forma automatizada pelo Audience Manager.

Baixe nossa planilha [do Excel do](assets/AAM-Partners-October2019.xlsx) Parceiro para ver quais parceiros de ativação do Audience Manager suportam a anulação de segmentos.

## Solicitações de recusa {#opt-out-requests}

O Audience Manager suporta padrões em todo o setor no que diz respeito ao gerenciamento de opções. Leia para obter informações completas sobre os tipos de opção de não participação suportados pelo Audience Manager.

Enquanto as solicitações de acesso e exclusão de dados são tratadas pelo [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), as solicitações de cancelamento são suportadas por meio da DCS API. Leia para saber como as chamadas de API de opção de não participação devem ser exibidas.

### Solicitações globais de cancelamento

A opção de não participação global representa uma opção de não participação no Audience Manager e em outras soluções da Adobe Experience Cloud para todas as marcas. A tabela abaixo lista os métodos usados para opção de não participação global:

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
   <td colname="col2"> <p>A página <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Suas escolhas de privacidade </a> fornece recursos de 1 clique que permitem que os usuários finais controlem e excluam a coleta de dados pelas soluções de publicidade da Adobe Experience Cloud (incluindo o Audience Manager). Especificamente, consulte a seção Cliente <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> comercial </a> da página Opções de privacidade. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chamadas de API diretas para o Audience Manager </p> </td> 
   <td colname="col2"> <p>Seus usuários podem optar por não participar da coleta de dados por todas as marcas do Audience Manager, fazendo uma chamada para a API DCS abaixo e incluindo a ID de usuário do <a href="../../reference/ids-in-aam.md"> Audience Manager </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Como resultado, definiremos <code>demdex=NOTARGET</code> e <code>dextp=NOTARGET</code> cookies para a ID de usuário do Audience Manager enviada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dispositivos móveis </p> </td> 
   <td colname="col2"> <p>Consulte as configurações de não participação e privacidade para: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Dispositivos Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> Dispositivos iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Seus usuários finais também podem optar por não participar da coleta global de dados visitando os sites de nossos parceiros de padrões do setor.

* [A Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Seguindo as solicitações de opção de não participação descritas acima:

* O Audience Manager encerrará toda a coleta, segmentação ou ativação de dados, desde que o usuário não limpe os cookies do navegador.
* Os dados históricos são removidos do perfil do usuário após 120 dias.

### Recusar nível de parceiro com chamadas de ID declaradas

A opção de não participação em nível de parceiro permite que você exclua seus usuários da coleta de dados por parceiros específicos do Audience Manager. Você pode enviar solicitações de recusa de nível de parceiro para IDs de vários dispositivos, incluindo IDs CRM e endereços de email com hash.

Seguindo uma opção de não participação em nível de parceiro com uma chamada de ID declarada:

* A ID [do](../../reference/ids-in-aam.md) CRM não está incluída na coleta de dados;
* A última ID de dispositivo (ID[de usuário exclusiva do](../../reference/ids-in-aam.md)Audience Manager) vinculada à ID [do](../../reference/ids-in-aam.md) CRM é excluída da coleta de dados.
* O Audience Manager cessará toda a coleta, segmentação ou ativação de dados para a ID do CRM e a última ID do dispositivo vinculada à ID do CRM;
* O Audience Manager cancela a segmentação da ID do CRM que não foi incluída e da ID do último dispositivo de todos os segmentos;
* Os parceiros de destino recebem a solicitação de cancelamento de segmento para a ID do CRM e a ID do último dispositivo. A dessegmentação funciona para destinos em tempo [real](data-privacy-requests.md#aam-partners-with-unsegmentation) e em lote.
* Nenhum dado histórico é excluído.

Quando o Audience Manager recebe uma solicitação de recusa de nível de parceiro, o JSON retornado pelo DCS contém o código de [erro 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), com a mensagem [!UICONTROL "Encountered opt out tag"], em vez da ID de usuário do Audience Manager.

Você pode fazer uma solicitação de recusa de ID declarada com os pares de valor-chave `d_cid` e `d_cid_ic` e IDs declaradas. Os parâmetros herdados como `d_dpid` e `d_dpuuid` ainda funcionam, mas são considerados obsoletos. Consulte [CID substitui DPID e DPUUID](../../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

#### Recusar com CID e CID_IC

Para obter uma descrição e sintaxe, consulte Variáveis e sintaxe [URL para IDs](../../features/declared-ids.md#variables-and-syntax)declaradas.

| Opção de não participação usando | Amostra de código |
|--- |--- |
| Uma ID de provedor de dados e ID de usuário. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Um código de integração e ID de usuário. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Vários pares de valores chave d_cid e d_cid_ic. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Recusar nível de parceiro com chamadas de ID de dispositivo

A opção de não participação em nível de parceiro permite que você exclua seus usuários da coleta de dados por parceiros específicos do Audience Manager. Você pode optar por não participar da coleta de dados em uma determinada ID de dispositivo para uma marca, fazendo as seguintes chamadas para a API [do](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)DCS:

| Opção de não participação usando | Amostra de código |
|--- |--- |
| Uma ID de usuário exclusiva (`uuid`) do Audience Manager. | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Uma Experience Cloud ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Leia mais sobre `uuid`, `mid` e `imsOrgId` no [Índice de IDs no Audience Manager](/help/using/reference/ids-in-aam.md).

Seguindo uma opção de não participação em nível de parceiro com uma chamada de ID de dispositivo:

* A ID do dispositivo é excluída da coleta de dados.
* O Audience Manager encerrará toda a coleta, segmentação ou ativação de dados, para o parceiro, a partir da ID do dispositivo.
* O Audience Manager dessegmenta a ID do dispositivo de todos os segmentos;
* Os parceiros de destino recebem a solicitação de cancelamento de segmento para a ID do dispositivo. A dessegmentação funciona para destinos em tempo [real](data-privacy-requests.md#aam-partners-with-unsegmentation) e em lote.
* Nenhum dado histórico é excluído.

## Parceiros Do Audience Manager Com Recursos De Dessegmentação {#aam-partners-with-unsegmentation}

Para ajudá-lo a automatizar suas solicitações de privacidade de dados do consumidor, o Audience Manager tentará notificar os parceiros de ativação sobre solicitações de exclusão de Indivíduos de dados enviando-lhes informações de dessegmento (ou removendo segmento).

Entretanto, alguns de nossos parceiros de ativação:

1. Não é possível suportar solicitações de cancelamento de segmento do Audience Manager e/ou
2. Não é possível receber atualizações do Audience Manager com mais frequência que uma vez em 30 dias.

Nesses casos, não é possível enviar solicitações de exclusão para parceiros de ativação de forma automatizada pelo Audience Manager.

Baixe nossa planilha [do Excel do](assets/AAM-Partners-December2019.xlsx) Parceiro para ver quais parceiros de ativação do Audience Manager suportam a anulação de segmentos.

## Solicitações de correção de dados {#correction}

Como o Audience Manager não é a fonte dos dados, há uma função limitada para a correção de dados no Audience Manager. A correção poderia significar que o consumidor solicitou a não qualificação de um traço/segmento incorreto ou a qualificação para o traço/segmento desejado.

Os clientes do Audience Manager podem optar por capturar os sinais/características/segmentos relevantes em relação aos perfis do usuário e enviar essas informações por meio da ingestão [de dados](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) offline para o Audience Manager. Observe que o usuário continuará se qualificando para a característica original e os segmentos se eles repetirem seu comportamento.
