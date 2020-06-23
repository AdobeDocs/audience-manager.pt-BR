---
description: O Audience Manager ajuda a coletar e gerenciar dados primários, de terceiros e de terceiros.
seo-description: O Audience Manager ajuda a coletar e gerenciar dados primários, de terceiros e de terceiros.
seo-title: Tipos de dados coletados
solution: Audience Manager
title: Tipos de dados coletados
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
translation-type: tm+mt
source-git-commit: 620730ab1596d4777a768de4453b73538671279d
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 1%

---


# Tipos de dados coletados {#types-of-data-collected}

[!DNL Audience Manager] ajuda a coletar e gerenciar dados primários, de terceiros e de terceiros.

Desbloquear os ativos de informações do cliente armazenados em vários silos é um dos maiores desafios de dados enfrentados pelo empresa atualmente. Desde [!DNL CRM] bancos de dados, sistemas de registro, servidores de anúncios, e assim por diante, as empresas exigem ferramentas que ajudem a centralizar dados valiosos e a gerenciar informações de clientes/audiências como um único ativo de dados estratégico. [!DNL Audience Manager] ajuda a desbloquear informações isoladas do cliente e gerenciar a coleta de dados de várias fontes. Os dados coletados podem ser gerenciados com base em valores de tempo de vida útil ([!DNL TTL]) do elemento de dados, o que ajuda o editor a controlar a expiração dos dados em todas as fontes. [!DNL Audience Manager] é projetado para ajudar a gerenciar os seguintes tipos de dados:

| Tipo de dados | De onde os dados vêm |
|---|---|
| **Primeiro partido** | Clientes. Os dados são coletados online (de interações do consumidor em seus sites) ou offline. |
| **Segundo partido** | Parceiros estratégicos e anunciantes. |
| **Terceiros** | Fornecedores de dados e/ou intercâmbios. Os dados podem incluir informações como intenção, demografia, estilo de vida/social, psicográfico e muito mais. |

## First-Party Data Collection {#first-party-data}

A coleta de dados primários é um [!DNL Audience Manager] recurso principal. Essa competência principal atende às necessidades de nossos clientes (editores ou anunciantes) que desejam usar dados proprietários como a pedra angular de seus programas de marketing ou para segmentar e modelar em relação a outras fontes de dados.

[!DNL Audience Manager] trabalha com clientes para entender sua estratégia de dados e mapeia essa estratégia de volta para um plano de coleta de dados personalizado. Nossa equipe de soluções de parceiros trabalha com você para avaliar sites, sinais de dados brutos e outras interações de usuários em seus sites. Com essas informações, ajudaremos você a criar uma estratégia de coleta de dados personalizada que capture sinais de dados no nível do usuário de várias páginas em seu inventário. Os dados capturados são armazenados e mapeados de volta para uma taxonomia predefinida, que pode ser atualizada a qualquer momento, conforme as necessidades de sua empresa mudam.

O exemplo a seguir ilustra como elementos de dados potenciais podem ser capturados de uma página de compras de amostra.

![dados do carrinho de compras](assets/shopping-cart-data.png)

| Item | Descrição |
|---|---|
| 1 | **Gênero**. O nome do comprador geralmente indica o sexo. Em nosso exemplo, o nome do comprador é Mary, então sabemos que o comprador é uma mulher. Os nomes nunca são armazenados por Audience Manager. |
| 2 | **Interesses**. Os itens no carrinho de compras podem indicar vários interesses. Em nosso exemplo, Maria gasta muito em equipamentos de fitness. |
| 3 | **Tipo** de alojamento. Com base nos endereços de envio e/ou faturamento, você pode deduzir se a Mary compra equipamentos de adequação para si mesma ou para uma empresa. |
| 4 | **Localização**. [!DNL ZIP] os códigos são mais confiáveis do que [!DNL IP] endereços quando se trata de identificar um local. |
| 5 | **Afinidade** de promoção. Se um comprador usa códigos promocionais ou cartões-presente, provavelmente ele é um caçador de barganhas procurando os melhores acordos. |
| 6 | **Gastando energia**. Os dados de preço correlacionados aos [!DNL ZIP+4] códigos indicam o poder de gasto de um determinado local. |

Depois que os dados brutos são coletados, eles são mapeados de volta às características definidas pelo cliente na [!DNL Audience Manager] plataforma. A taxonomia e os mapeamentos de dados podem ser ajustados a qualquer momento sem fazer alterações no código de coleta de dados.

## Coleta de dados de terceiros {#second-party-data}

Os dados de terceiros vêm de um parceiro comercial estratégico (não são dados do editor). Essas informações são coletadas e gerenciadas da mesma forma que os dados primários.

Em um cenário de dados de terceiros, os anunciantes enviam seus próprios ativos de dados para os editores para que eles possam combinar essas informações com os dados do editor e, em seguida, executar um programa de publicidade mais direcionado. Além disso, os editores podem estender sua audiência através de parcerias com seus anunciantes. Na maioria dos casos, esses acordos envolvem relações contratuais limitadas à colocação da tag do [!DNL Audience Manager] container no site do parceiro para facilitar a coleta e o compartilhamento de dados.

Um exemplo de coleta e recomercialização de dados de terceiros poderia envolver um varejista de roupas coletando dados sobre seus produtos e depois compartilhando essas informações com os principais parceiros. Nesse caso, o varejista poderia oferecer anúncios diferentes em um site de [!DNL Audience Manager] parceiros para consumidores que escolhiam várias cores e tamanhos da jaqueta.

![](assets/shopping-cart-traits.png)

## Third-Party Data Collection {#third-party-data}

Dados de terceiros são informações coletadas e compartilhadas por fornecedores fora do [!DNL Audience Manager].

Dados de terceiros podem ser usados para qualificar dados existentes [!UICONTROL segments] (por exemplo, idade, renda familiar e assim por diante), fornecer dados que estão sob demanda mas não estão disponíveis de outra forma, ou ser usados em modelagem semelhante a uma base de usuários conhecida a partir de dados primários e de terceiros. [!DNL Audience Manager] funciona com vários provedores de dados de terceiros e o ajudará a entender o tipo de dados que esses provedores coletam para que você possa fazer as negociações estratégicas certas com cada provedor.

>[!NOTE]
>
>Para obter uma lista completa de provedores de dados de terceiros suportados pelo [!DNL Audience Manager], consulte o Localizador [de Audiências da](https://www.adobe-audience-finder.com/)Adobe.

[!DNL Audience Manager] integra-se com outros provedores de dados com base em seus conjuntos de dados [!DNL APIs] e disponíveis. A coleta de dados funciona em tempo real, à medida que um usuário navega em seu site, ou por metodologias fora de banda nas quais as IDs são sincronizadas entre parceiros e os dados são transferidos entre servidores depois que um usuário deixa seu site. Em ambos os casos, [!DNL Audience Manager] os clientes têm a vantagem de ter dados de terceiros sincronizados em nossa plataforma, o que significa que cada cliente, ou domínio, não precisa executar sua própria sincronização. Isso ajuda a aumentar o alcance e a reduzir as chamadas do servidor da página.

## Parceiros de correspondência {#match-partners}

Muitos clientes escolhem trabalhar com parceiros de correspondência de dados de terceiros. Essas entidades têm relacionamentos com sites que têm requisitos de registro e podem processar arquivos de dados do cliente, combinando-os (em tempo real) com base em sua rede de registro.

![correspondência entre provedores de dados](assets/data-provider-match.png)
