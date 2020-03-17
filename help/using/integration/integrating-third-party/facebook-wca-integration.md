---
description: Esta página ilustra o processo de criação de pixels de Públicos-alvo personalizados (WCA) do site do Facebook para fins de envio de segmentos de público-alvo do Audience Manager baseados na Web para o Facebook, para direcionamento de anúncios online com maior transparência.
seo-description: Esta página ilustra o processo de criação de pixels de Públicos-alvo personalizados (WCA) do site do Facebook para fins de envio de segmentos de público-alvo do Audience Manager baseados na Web para o Facebook, para direcionamento de anúncios online com maior transparência.
seo-title: Integração WCA do Facebook
solution: Audience Manager
title: Integração WCA do Facebook
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Integração WCA do Facebook {#facebook-wca-integration}

Esta página ilustra o processo de criação de pixels de Públicos-alvo personalizados (WCA) do site do Facebook para fins de envio de segmentos de público-alvo do Audience Manager baseados na Web para o Facebook, para direcionamento de anúncios online com maior transparência.

## Visão geral {#overview}

[Públicos-alvo personalizados do site do Facebook (WCA)](https://www.facebook.com/business/help/449542958510885) permite criar uma lista de pessoas que visitaram determinadas páginas ou realizaram ações específicas em seu site. O Audience Manager permite a ativação no WCA usando destinos de URL, com os quais você pode configurar uma integração personalizada baseada em pixels para enviar públicos-alvo baseados na Web para o Facebook para definição de metas.

![Integração WCA do Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Esse recurso exige que você selecione a opção Público-alvo do site para plataformas sociais em destinos [de](/help/using/features/destinations/create-url-destination.md)URL. As plataformas sociais exigem que as informações do referenciador sejam desmascaradas quando enviadas para a plataforma. Esteja ciente de que isso significa que a plataforma/parceiro de destino poderá ver informações no URL do referenciador.

## Pré-requisitos {#prerequisites}

1. Conta de anúncio do Facebook
2. Segmentos do Audience Manager, prontos para atribuir ao seu novo destino do Facebook. Veja [como criar um segmento](/help/using/features/segments/segment-builder.md) na interface do usuário do Audience Manager.
3. Adobe Adobe Experience Platform Identity Service (ECID) versão 4.1.0 ou mais recente. Baixe a versão mais recente **[aqui](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Biblioteca de integração de dados do Audience Manager (DIL) versão 9.0 ou mais recente, disponível para download **[aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Como alternativa, se você usar o[Server-Side Forwarding (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html)para importar dados para o Audience Manager, deverá usar o AppMeasurement versão 2.12 ou mais recente. Baixe o AppMeasurement usando o Gerenciador[de código do](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)Analytics.

Recomendamos que você instale ou atualize as bibliotecas nas etapas 3 e 4 usando o [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) ou o Gerenciamento [dinâmico de tags da](https://marketing.adobe.com/resources/help/en_US/dtm/)Adobe.

## Etapa 1 - Criar um destino do Facebook no Audience Manager {#step-1-create-facebook-destination}

Crie um novo Destino de URL no Audience Manager e nomeie-o como Públicos-alvo personalizados do site do Facebook. Use as configurações abaixo ao criar o destino. Você também pode consultar a página [Configurar um destino](/help/using/features/destinations/create-url-destination.md) de URL.

**Informações básicas**

* **Categoria**: Personalizado
* **Tipo**: URL
* Marque a caixa de seleção Mapeamento **de destino de preenchimento** automático e selecione ID **do** segmento.

**Rótulos de exportação de dados**

Selecione a opção **Este destino pode ativar uma combinação com informações pessoalmente identificáveis (PII)**.

>[!NOTE]
>
> Esse rótulo de exportação impede que dados de terceiros e dados derivados de gráficos de dispositivos sejam incluídos nos segmentos.

**Configuração**

* **Tipo** de URL: Selecione o público-alvo **do site para plataformas** sociais. Ao selecionar essa opção Tipo de URL, o Audience Manager não obscurece as informações de URL do referenciador ao disparar um pixel WCA do Facebook.
* **Serializar**: Selecione **Ativar**.
* No campo URL **** básico e URL **** seguro, insira o pixel WCA do Facebook.
* **Delimitador**: ,

Exemplo de URL básico: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemplo de pixel disparado da página. Este exemplo mostra um usuário que se qualifica para três segmentos do Audience Manager, com as IDs 3401321, 2993399 e 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Parâmetro | Descrição |
---------|----------|
| `id` | Sua ID de pixel do Facebook, que pode ser encontrada na interface do usuário do Gerenciador de publicidade do Facebook ao criar pixels de público-alvo. |
| `ev` | Evento. Esse é um valor arbitrário, que aparecerá na interface do usuário do Gerenciador de publicidade do Facebook assim que o pixel começar a ser acionado no site. Consulte o item Incluir na [Etapa 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)para obter mais informações. |
| `cd[segID]` | Um parâmetro adicional, que começará a ser preenchido na interface do usuário do Gerenciador de publicidade do Facebook assim que o pixel começar a ser acionado no site. `segID` também é arbitrário. |
| `%ALIAS%` | Uma macro do Audience Manager, que será substituída dinamicamente pelas IDs de segmento do Audience Manager para as quais o visitante do site se qualifica, delimitadas por vírgula, |

A configuração de destino do URL deve ser semelhante na imagem abaixo:

![Configuração de destino](/help/using/integration/assets/facebook-wca.png)

Salve o destino. Em seguida, você pode prosseguir para a etapa Mapeamentos **de** segmentos.

## Etapa 2 - Mapeamentos de segmento - Mapear segmento para destino {#step-2-segment-mappings}

No fluxo de trabalho [Configurar destino](/help/using/features/destinations/create-url-destination.md) de URL, mapeie o segmento aplicável para o destino recém-criado. Observe que o valor de mapeamento é preenchido automaticamente com a ID de segmento do Audience Manager.

Informe uma data de término, se aplicável, caso contrário, deixe em branco sem data de término.

## Etapa 3 - Criar um público-alvo no Gerenciador de anúncios do Facebook {#step-3-create-audience}

Consulte [Criar um público](https://www.facebook.com/business/help/666509013483225) personalizado do site na documentação de ajuda do Facebook. Selecione as opções Criar público-alvo na tabela abaixo:


| Item | Descrição |
---------|----------|
| Tráfego do site | Combinação personalizada |
| Incluir | <ul><li>Selecione **Evento** > Selecionar **Adobe-Audience-Manager-Segment**. Esse era o valor do parâmetro ev no exemplo pixel na etapa 1. Observe que, se o pixel ainda não for acionado, a opção **Evento** ou **Adobe-Audience-Manager-Segment** talvez não apareça na interface do usuário do Facebook.</li><li>Adicione um parâmetro: Selecione `segID`.</li><li><p>Selecione o operador **contém** .</p><p>Isso é importante, considerando que os visitantes podem se qualificar para vários segmentos, pode haver várias IDs de segmento no parâmetro de pixel. O uso do operador igual (=) pode não qualificar seus visitantes para o público-alvo e você observará um volume menor.</p></li><li>Adicione um valor: Insira a ID de segmento do Audience Manager.</li></ul> |
| Adicionar nova condição | Configuração opcional. |
| No último | Configuração opcional. |
| Nome do público-alvo | Recomendamos que você use o mesmo nome de segmento do Audience Manager para fins de consistência, a menos que esteja adicionando condições adicionais a esse Público-alvo. |

## Etapa 4 - Atribuir o público-alvo a uma campanha no Gerenciador de anúncios do Facebook {#step-4-assign-audience-to-campaign}

Depois de criar o Público personalizado, atribua-o a uma campanha de publicidade. Crie uma nova campanha ou edite uma existente e você encontrará seu Público recém-criado na interface do usuário do Facebook. Sua campanha publicitária direcionará os usuários que viram o pixel disparar em seu navegador ao visitar seu site, se o Audience Manager incluí-los no segmento.

## Resumo {#summary}

Agora que você atribuiu seu segmento do Audience Manager ao destino WCA do Facebook, o Audience Manager irá disparar seletivamente o pixel WCA do Facebook para os usuários de um determinado segmento com a respectiva ID de segmento no pixel para preencher o Público do Facebook. Isso resulta em um aumento gradual no Público-alvo do Facebook quanto mais a tag é acionada para o público-alvo aplicável em seu site.

>[!NOTE]
>
> Se um usuário sair do segmento Audience Manager, não há como o Audience Manager informar ao Facebook para remover o usuário do Público-alvo personalizado.

