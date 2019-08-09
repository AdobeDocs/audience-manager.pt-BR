---
description: Essa página ilustra o processo de criação de públicos-alvo personalizados de site do Facebook (WCA) pixels para fins de envio de segmentos de público-alvo do Audience Manager baseados na Web para o Facebook, para direcionamento de anúncios on-line com transparência aprimorada.
seo-description: Essa página ilustra o processo de criação de públicos-alvo personalizados de site do Facebook (WCA) pixels para fins de envio de segmentos de público-alvo do Audience Manager baseados na Web para o Facebook, para direcionamento de anúncios on-line com transparência aprimorada.
seo-title: Integração WCA do Facebook
solution: Audience Manager
title: Integração WCA do Facebook
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Integração WCA do Facebook {#facebook-wca-integration}

Essa página ilustra o processo de criação de públicos-alvo personalizados de site do Facebook (WCA) pixels para fins de envio de segmentos de público-alvo do Audience Manager baseados na Web para o Facebook, para direcionamento de anúncios on-line com transparência aprimorada.

## Visão geral {#overview}

[Os Públicos-alvo personalizados do Facebook (WCA)](https://www.facebook.com/business/help/449542958510885) permitem criar uma lista de pessoas que visitaram determinadas páginas ou fizeram ações específicas em seu site. O Audience Manager permite a ativação em WCA usando destinos de URL, com os quais você pode configurar uma integração baseada em pixel personalizada para enviar públicos-alvo baseados na Web para o Facebook para segmentação.

![Integração WCA do Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Esse recurso exige que você selecione o público-alvo de site para plataformas sociais nos [destinos de URL](/help/using/features/destinations/create-url-destination.md). As plataformas sociais exigem que as informações do referenciador sejam mascaradas quando enviadas para a plataforma. Observe que isso significa que a plataforma de destino/parceiro poderá ver informações no URL do referenciador.

## Pré-requisitos {#prerequisites}

1. Conta de anúncio do Facebook
2. Segmentos do Audience Manager, prontos para atribuir ao novo destino do Facebook. Veja [como criar um segmento](/help/using/features/segments/segment-builder.md) na interface do usuário do Audience Manager.
3. Serviço da Adobe Experience Cloud ID (ECID) versão 4.1.0 ou mais recente. Baixe a versão mais recente **[aqui](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. versão 9.0 ou mais recente da Biblioteca de integração de dados do Manager Manager (DIL), disponível para download **[aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Como alternativa, se você usar [o encaminhamento pelo lado do servidor (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) para importar dados para o Audience Manager, deverá usar a versão 2.12 ou mais recente do appmeasurement. Baixe o appmeasurement usando o Gerenciador de código [do Analytics](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).

Recomendamos que você instale ou atualize as bibliotecas nas etapas 3 e 4 usando [o Adobe Launch](https://docs.adobelaunch.com/) ou [o Gerenciamento dinâmico de tags da Adobe](https://marketing.adobe.com/resources/help/en_US/dtm/).

## Etapa 1 - Criar um destino do Facebook no Audience Manager {#step-1-create-facebook-destination}

Crie um novo Destino de URL no Audience Manager e nomeie-o como Públicos personalizados personalizados do Facebook. Use as configurações abaixo ao criar o destino. Você também pode consultar a [página Configurar destino](/help/using/features/destinations/create-url-destination.md) de URL.

**Informações básicas**

* **Categoria**: Personalizado
* **Tipo**: URL
* Marque a **caixa** de seleção Mapeamento de destino de preenchimento automático e selecione **ID do segmento**.

**Rótulos de exportação de dados**

Selecione a opção **Esse destino pode permitir uma combinação com informações de identificação pessoal (PII)**.

>[!NOTE]
>
> Essa etiqueta de exportação impede que dados de terceiros e dados derivados de gráficos de dispositivo sejam incluídos nos segmentos.

**Configuração**

* **Tipo de URL**: Selecione **Público-alvo de site para plataformas sociais**. Ao selecionar essa opção Tipo de URL, o Audience Manager não oculta as informações do URL do referenciador ao acionar um pixel WCA do Facebook.
* **Serializar**: Selecione **Ativar**.
* No campo URL **de base** e **URL seguro** , insira o pixel WCA do Facebook.
* **Delimitador**: ,

Exemplo de URL básico: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemplo de pixel acionado da página. Este exemplo mostra um usuário que é qualificado para três segmentos do Audience Manager, com as IDs 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Parâmetro | Descrição |
---------|----------|
| `id` | Sua ID de pixel do Facebook, que pode ser encontrada na interface do usuário do Gerenciador de publicidade do Facebook ao criar pixels do público. |
| `ev` | Evento. Esse é um valor arbitrário, que aparecerá na interface do usuário do Gerenciador de publicidade do Facebook quando o pixel começar a ser acionado no site. Consulte o item Incluir na [etapa 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)para obter mais informações. |
| `cd[segID]` | Um parâmetro adicional, que começará a ser preenchido na interface do usuário do Gerenciador de publicidade do Facebook depois que o pixel começar a ser acionado no site. `segID` também é arbitrário. |
| `%ALIAS%` | Uma macro do Audience Manager, que será substituída dinamicamente pelas IDs de segmento do Audience Manager para as quais o visitante do site é qualificado, delimitado por vírgula, |

A configuração de destino do URL deve ser semelhante à imagem abaixo:

![Configuração de destintion](/help/using/integration/assets/facebook-wca.png)

Salve o destino. Em seguida, você pode seguir para a **etapa Mapeamentos** de segmentos.

## Etapa 2 - Mapeamentos de segmento - Mapear segmento para destino {#step-2-segment-mappings}

No [fluxo de trabalho de destino](/help/using/features/destinations/create-url-destination.md#) Configurar URL, mapeie o segmento aplicável para o destino criado recentemente. Observe que o valor de mapeamento é preenchido automaticamente com a ID do segmento do Audience Manager.

Digite uma data final se aplicável; caso contrário, deixe em branco sem data final.

## Etapa 3 - Criar um público-alvo no Gerenciador de anúncios do Facebook {#step-3-create-audience}

Consulte [Criar um público personalizado de site](https://www.facebook.com/business/help/666509013483225) na documentação de ajuda do Facebook. Selecione as opções Criar público-alvo na tabela abaixo:


| Item | Descrição |
---------|----------|
| Tráfego do site | Combinação personalizada |
| Incluir | <ul><li>Selecione **Evento** &gt; Selecionar **o Adobe-Audience-Manager-Segmento**. Esse era o valor do parâmetro ev no exemplo pixel na etapa 1. Observe que, se o pixel ainda for acionado, a opção **Evento** ou **o Adobe-Audience-Manager-Segment** podem não aparecer na interface do usuário do Facebook.</li><li>Adicione um parâmetro: Selecione `segID`.</li><li><p>Selecione o **operador contém** .</p><p>Isso é importante, considerando que os visitantes podem se qualificar para vários segmentos, pode haver várias IDs de segmento no parâmetro pixel. O uso do operador igual (=) pode não qualificar seus visitantes para o público-alvo, e você observará um volume menor.</p></li><li>Adicione um valor: Insira a ID do segmento do Audience Manager.</li></ul> |
| Adicionar nova condição | Configuração opcional. |
| Na última função | Configuração opcional. |
| Nome do público | Recomendamos que você use o mesmo nome de segmento do Audience Manager para fins de consistência, a menos que esteja adicionando condições adicionais a esse público. |

## Etapa 4 - Atribuir o público-alvo a uma campanha no Gerenciador de anúncios do Facebook {#step-4-assign-audience-to-campaign}

Depois de criar o Público-alvo personalizado, atribua-o a uma campanha publicitária. Crie uma nova campanha ou edite uma existente e você encontrará o público-alvo recém-criado na interface do usuário do Facebook. Sua campanha de publicidade direcionará os usuários que viram o pixel em seu navegador ao visitar seu site, se o Audience Manager incluí-los no segmento.

## Resumo {#summary}

Agora que você atribuiu o segmento do Audience Manager ao destino de WCA do Facebook, o Audience Manager irá disparar seletivamente o pixel WCA do Facebook a usuários de um determinado segmento com a respectiva ID de segmento no pixel para preencher o público do Facebook. Isso resulta em um aumento gradual no público do Facebook quanto mais a tag for acionada para o público-alvo aplicável em seu site.

>[!NOTE]
>
> Se um usuário deixar o segmento do Audience Manager, não há nenhum modo do Audience Manager informar o Facebook para remover o usuário do Público-alvo personalizado.

