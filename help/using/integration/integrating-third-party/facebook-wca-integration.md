---
description: Essa página ilustra o processo de criação de públicos-alvo personalizados de site do Facebook (WCA) pixels para fins de envio de segmentos de público-alvo do Audience Manager baseados na Web para o Facebook, para direcionamento de anúncios on-line com transparência aprimorada.
seo-description: Essa página ilustra o processo de criação de públicos-alvo personalizados de site do Facebook (WCA) pixels para fins de envio de segmentos de público-alvo do Audience Manager baseados na Web para o Facebook, para direcionamento de anúncios on-line com transparência aprimorada.
seo-title: Integração WCA do Facebook
solution: Audience Manager
title: Integração WCA do Facebook
translation-type: tm+mt
source-git-commit: 56999c1968a486bed0e2e672a4de1774d049e09d

---


# Facebook WCA Integration {#facebook-wca-integration}

Essa página ilustra o processo de criação de públicos-alvo personalizados de site do Facebook (WCA) pixels para fins de envio de segmentos de público-alvo do Audience Manager baseados na Web para o Facebook, para direcionamento de anúncios on-line com transparência aprimorada.

## Visão geral {#overview}

[Os Públicos-alvo personalizados do Facebook (WCA)](https://www.facebook.com/business/help/449542958510885) permitem criar uma lista de pessoas que visitaram determinadas páginas ou fizeram ações específicas em seu site. O Audience Manager permite a ativação em WCA usando destinos de URL, com os quais você pode configurar uma integração baseada em pixel personalizada para enviar públicos-alvo baseados na Web para o Facebook para segmentação.

![Integração WCA do Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> This capability requires that you select the Website audience for social platforms option in [URL destinations](/help/using/features/destinations/manage-destinations.md#configure-url-destination). As plataformas sociais exigem que as informações do referenciador sejam mascaradas quando enviadas para a plataforma. Observe que isso significa que a plataforma de destino/parceiro poderá ver informações no URL do referenciador.

## Pré-requisitos {#prerequisites}

1. Conta de anúncio do Facebook
2. Segmentos do Audience Manager, prontos para atribuir ao novo destino do Facebook. Here is [how to create a segment](/help/using/features/segments/segment-builder.md) in the Audience Manager UI.
3. Serviço da Adobe Experience Cloud ID (ECID) versão 4.1.0 ou mais recente. Download the latest version **[here](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Audience Manager Data Integration Library (DIL) version 9.0 or newer, downloadable from **[here](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Alternatively, if you use [Server-Side Forwarding (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) to import data into Audience Manager, you must use AppMeasurement version 2.12 or newer. Download AppMeasurement using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).

We recommend that you install or upgrade the libraries in steps 3 and 4 using [Adobe Launch](https://docs.adobelaunch.com/) or [Adobe Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

## Step 1 - Create a Facebook Destination in Audience Manager {#step-1-create-facebook-destination}

Crie um novo Destino de URL no Audience Manager e nomeie-o como Públicos personalizados personalizados do Facebook. Use as configurações abaixo ao criar o destino. You can also refer to the [Configure a URL Destination](/help/using/features/destinations/manage-destinations.md#configure-url-destination) page.

**Informações básicas**

* **Categoria**: Personalizado
* **Tipo**: URL
* Select the **Auto-fill Destination Mapping** check box, then select **Segment ID**.

**Rótulos de exportação de dados**

Select the option **This destination may enable a combination with personally identifiable information (PII)**.

>[!NOTE]
>
> Essa etiqueta de exportação impede que dados de terceiros e dados derivados de gráficos de dispositivo sejam incluídos nos segmentos.

**Configuração**

* **Tipo de URL**: Selecione **Público-alvo de site para plataformas sociais**. Ao selecionar essa opção Tipo de URL, o Audience Manager não oculta as informações do URL do referenciador ao acionar um pixel WCA do Facebook.
* **Serializar**: Selecione **Ativar**.
* In the **Base URL** and **Secure URL** field, enter the Facebook WCA pixel.
* **Delimitador**: ,

Base URL example: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemplo de pixel acionado da página. Este exemplo mostra um usuário que é qualificado para três segmentos do Audience Manager, com as IDs 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Parâmetro | Descrição |
---------|----------|
| `id` | Sua ID de pixel do Facebook, que pode ser encontrada na interface do usuário do Gerenciador de publicidade do Facebook ao criar pixels do público. |
| `ev` | Evento. Esse é um valor arbitrário, que aparecerá na interface do usuário do Gerenciador de publicidade do Facebook quando o pixel começar a ser acionado no site. See the Include item in [Step 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), for more information. |
| `cd[segID]` | Um parâmetro adicional, que começará a ser preenchido na interface do usuário do Gerenciador de publicidade do Facebook depois que o pixel começar a ser acionado no site. `segID` também é arbitrário. |
| `%ALIAS%` | Uma macro do Audience Manager, que será substituída dinamicamente pelas IDs de segmento do Audience Manager para as quais o visitante do site é qualificado, delimitado por vírgula, |

A configuração de destino do URL deve ser semelhante à imagem abaixo:

![Configuração de destintion](/help/using/integration/assets/facebook-wca.png)

Salve o destino. Then, you can proceed to the **Segment Mappings** step.

## Step 2 - Segment Mappings - Map Segment to Destination {#step-2-segment-mappings}

In the [Configure URL destination](/help/using/features/destinations/manage-destinations.md#configure-url-destination) workflow, map the applicable segment to your newly created destination. Observe que o valor de mapeamento é preenchido automaticamente com a ID do segmento do Audience Manager.

Digite uma data final se aplicável; caso contrário, deixe em branco sem data final.

## Step 3 - Create an Audience within Facebook Ads Manager {#step-3-create-audience}

See [Create a Website Custom Audience](https://www.facebook.com/business/help/666509013483225) in the Facebook help documentation. Selecione as opções Criar público-alvo na tabela abaixo:


| Item | Descrição |
---------|----------|
| Tráfego do site | Combinação personalizada |
| Incluir | <ul><li>Select **Event** &gt; Select **Adobe-Audience-Manager-Segment**. Esse era o valor do parâmetro ev no exemplo pixel na etapa 1. Note that if the pixel is yet to fire, the **Event** option or **Adobe-Audience-Manager-Segment** may not appear in the Facebook UI.</li><li>Add a parameter: Select `segID`.</li><li><p>Select the **contains** operator.</p><p>Isso é importante, considerando que os visitantes podem se qualificar para vários segmentos, pode haver várias IDs de segmento no parâmetro pixel. O uso do operador igual (=) pode não qualificar seus visitantes para o público-alvo, e você observará um volume menor.</p></li><li>Adicione um valor: Insira a ID do segmento do Audience Manager.</li></ul> |
| Adicionar nova condição | Configuração opcional. |
| Na última função | Configuração opcional. |
| Nome do público | Recomendamos que você use o mesmo nome de segmento do Audience Manager para fins de consistência, a menos que esteja adicionando condições adicionais a esse público. |

## Step 4 - Assign the Audience to a Campaign in Facebook Ads Manager {#step-4-assign-audience-to-campaign}

Depois de criar o Público-alvo personalizado, atribua-o a uma campanha publicitária. Crie uma nova campanha ou edite uma existente e você encontrará o público-alvo recém-criado na interface do usuário do Facebook. Sua campanha de publicidade direcionará os usuários que viram o pixel em seu navegador ao visitar seu site, se o Audience Manager incluí-los no segmento.

## Resumo {#summary}

Agora que você atribuiu o segmento do Audience Manager ao destino de WCA do Facebook, o Audience Manager irá disparar seletivamente o pixel WCA do Facebook a usuários de um determinado segmento com a respectiva ID de segmento no pixel para preencher o público do Facebook. Isso resulta em um aumento gradual no público do Facebook quanto mais a tag for acionada para o público-alvo aplicável em seu site.

>[!NOTE]
>
> Se um usuário deixar o segmento do Audience Manager, não há nenhum modo do Audience Manager informar o Facebook para remover o usuário do Público-alvo personalizado.

