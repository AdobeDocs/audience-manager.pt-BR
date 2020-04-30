---
description: Esta página ilustra o processo de criação de pixels de Audiências personalizadas (WCA) do site do Facebook para fins de envio de segmentos de audiência do Gerenciador de Audiências baseado na Web para o Facebook, para direcionamento de anúncios online com maior transparência.
seo-description: Esta página ilustra o processo de criação de pixels de Audiências personalizadas (WCA) do site do Facebook para fins de envio de segmentos de audiência do Gerenciador de Audiências baseado na Web para o Facebook, para direcionamento de anúncios online com maior transparência.
seo-title: Integração WCA do Facebook
solution: Audience Manager
title: Integração WCA do Facebook
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Integração WCA do Facebook {#facebook-wca-integration}

Esta página ilustra o processo de criação de pixels de Audiências personalizadas (WCA) do site do Facebook para fins de envio de segmentos de audiência do Gerenciador de Audiências baseado na Web para o Facebook, para direcionamento de anúncios online com maior transparência.

## Visão geral {#overview}

[As Audiências personalizadas do site do Facebook (WCA)](https://www.facebook.com/business/help/449542958510885) permitem que você crie uma lista de pessoas que visitaram determinadas páginas ou realizaram ações específicas em seu site. O Gerenciador de Audiências habilita a ativação no WCA usando destinos de URL, com os quais você pode configurar uma integração personalizada baseada em pixels para enviar audiências baseadas na Web para o Facebook para definição de metas.

![Integração WCA do Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Esse recurso exige que você selecione a opção audiência do site para plataformas sociais em destinos [de](/help/using/features/destinations/create-url-destination.md)URL. As plataformas sociais exigem que as informações de quem indicou sejam desmascaradas quando enviadas para a plataforma. Esteja ciente de que isso significa que a plataforma/parceiro de destino poderá ver informações no URL da quem indicou.

## Pré-requisitos {#prerequisites}

1. Conta de anúncio do Facebook
2. segmentos do Gerenciador de Audiências, prontos para atribuir ao seu novo destino do Facebook. Veja [como criar um segmento](/help/using/features/segments/segment-builder.md) na interface do usuário do Gerenciador de Audiências.
3. Adobe Adobe Experience Platform Identity Service (ECID) versão 4.1.0 ou mais recente. Baixe a versão mais recente **[aqui](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Biblioteca de integração de dados (DIL) do Audiência Manager versão 9.0 ou mais recente, disponível para download **[aqui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Como alternativa, se você usar o[Server-Side Forwarding (SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)para importar dados para o Audiência Manager, deverá usar o AppMeasurement versão 2.12 ou mais recente. Baixe o AppMeasurement usando o Gerenciador[de código do](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)Analytics.

Recomendamos que você instale ou atualize as bibliotecas nas etapas 3 e 4 usando o [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) ou o Gerenciamento [dinâmico de tags da](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html)Adobe.

## Etapa 1 - Criar um destino do Facebook no Gerenciador de Audiências {#step-1-create-facebook-destination}

Crie um novo Destino de URL no Gerenciador de Audiências e nomeie-o como Audiências personalizadas do site do Facebook. Use as configurações abaixo ao criar o destino. Você também pode consultar a página [Configurar um destino](/help/using/features/destinations/create-url-destination.md) de URL.

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

* **Tipo** de URL: Selecione audiência **do site para plataformas** sociais. Ao selecionar essa opção Tipo de URL, o Gerenciador de Audiências não obscurece as informações de URL da quem indicou ao acionar um pixel WCA do Facebook.
* **Serializar**: Selecione **Ativar**.
* No campo URL **** básico e URL **** seguro, insira o pixel WCA do Facebook.
* **Delimitador**: ,

Exemplo de URL básico: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemplo de pixel disparado da página. Este exemplo mostra um usuário que se qualifica para três segmentos do Gerenciador de Audiências, com as IDs 3401321, 2993399 e 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Parâmetro | Descrição |
---------|----------|
| `id` | Sua ID de pixel do Facebook, que pode ser encontrada na interface do usuário do Gerenciador de publicidade do Facebook ao criar pixels de audiência. |
| `ev` | Evento. Esse é um valor arbitrário, que aparecerá na interface do usuário do Gerenciador de publicidade do Facebook assim que o pixel começar a ser acionado no site. Consulte o item Incluir na [Etapa 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)para obter mais informações. |
| `cd[segID]` | Um parâmetro adicional, que começará a ser preenchido na interface do usuário do Gerenciador de publicidade do Facebook assim que o pixel começar a ser acionado no site. `segID` também é arbitrário. |
| `%ALIAS%` | Uma macro do Gerenciador de Audiências, que será substituída dinamicamente pelas IDs de segmento do Gerenciador de Audiências para as quais o visitante do site se qualifica, delimitadas por vírgula, |

A configuração de destino do URL deve ser semelhante na imagem abaixo:

![Configuração de destino](/help/using/integration/assets/facebook-wca.png)

Salve o destino. Em seguida, você pode prosseguir para a etapa Mapeamentos **de** segmentos.

## Etapa 2 - Mapeamentos de segmento - Mapear segmento para destino {#step-2-segment-mappings}

No fluxo de trabalho [Configurar destino](/help/using/features/destinations/create-url-destination.md) de URL, mapeie o segmento aplicável para o destino recém-criado. Observe que o valor de mapeamento é preenchido automaticamente com a ID de segmento do Gerenciador de Audiências.

Informe uma data de término, se aplicável, caso contrário, deixe em branco sem data de término.

## Etapa 3 - Criar uma Audiência no Gerenciador de anúncios do Facebook {#step-3-create-audience}

Consulte [Criar uma Audiência](https://www.facebook.com/business/help/666509013483225) personalizada do site na documentação de ajuda do Facebook. Selecione as opções Criar Audiência na tabela abaixo:


| Item | Descrição |
---------|----------|
| Tráfego do site | Combinação personalizada |
| Incluir | <ul><li>Selecione **Evento** > Selecionar **Adobe-Audiência-Manager-Segment**. Esse era o valor do parâmetro ev no exemplo pixel na etapa 1. Observe que, se o pixel ainda não for acionado, a opção **Evento** ou **Adobe-Audiência-Manager-Segment** talvez não apareça na interface do usuário do Facebook.</li><li>Adicione um parâmetro: Selecione `segID`.</li><li><p>Selecione o operador **contém** .</p><p>Isso é importante, considerando que os visitantes podem se qualificar para vários segmentos, pode haver várias IDs de segmento no parâmetro de pixel. O uso do operador igual (=) pode não qualificar seus visitantes para a audiência e você observará um volume menor.</p></li><li>Adicione um valor: Insira a ID de segmento do Gerenciador de Audiências.</li></ul> |
| Adicionar nova condição | Configuração opcional. |
| No último | Configuração opcional. |
| Nome da Audiência | Recomendamos que você use o mesmo nome de segmento do Gerenciador de Audiências para fins de consistência, a menos que esteja adicionando condições adicionais a essa Audiência. |

## Etapa 4 - Atribuir a Audiência a uma Campanha no Gerenciador de anúncios do Facebook {#step-4-assign-audience-to-campaign}

Depois de criar a Audiência personalizada, atribua-a a uma campanha de anúncio. Crie uma nova campanha ou edite uma existente e você encontrará sua Audiência recém-criada listada na interface do usuário do Facebook. Sua campanha de publicidade público alvo os usuários que viram o pixel disparar em seu navegador ao visitar seu site, se o Audiência Manager os incluir no segmento.

## Resumo {#summary}

Agora que você atribuiu seu segmento do Gerenciador de Audiências ao destino WCA do Facebook, o Gerenciador de Audiências disparará seletivamente o pixel WCA do Facebook para os usuários de um determinado segmento com a respectiva ID de segmento no pixel para preencher a Audiência do Facebook. Isso resulta em um aumento gradual na Audiência do Facebook, quanto mais a tag é acionada para a audiência aplicável em seu site.

>[!NOTE]
>
> Se um usuário sair do segmento Gerenciador de Audiências, não há como o Gerenciador de Audiências informar o Facebook para remover o usuário da Audiência Personalizada.

