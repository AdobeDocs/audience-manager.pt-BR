---
description: Este artigo descreve os prefixos que você deve anexar às variáveis principais ao criar regras de características.
seo-description: This article describes the prefixes you must attach to key variables when creating trait rules.
seo-title: Prefix Requirements for Key Variables
solution: Audience Manager
title: Requisitos de prefixo para variáveis-chave
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: Traits
exl-id: 67fe0c74-6831-48cb-90cf-417ebbf7f272
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 4%

---

# Requisitos de prefixo para variáveis-chave {#prefix-requirements-for-key-variables}

Este artigo descreve os prefixos que você deve anexar às variáveis principais ao criar regras de características.

<!-- r_tb_variable_prefixes.xml -->

## Finalidade dos prefixos de variáveis-chave

Ao criar [!UICONTROL Trait Builder] regras, é importante adicionar à variável principal um prefixo recomendado. Esses prefixos identificam o tipo de dados transmitido e ajudam a evitar conflitos de namespace no [!DNL Audience Manager]. Geralmente, você pode dar qualquer nome a uma variável, mas os dados de uma regra não serão processados se o nome da variável principal não corresponder ao nome da variável em uma chamada de evento.

## Prefixos para variáveis-chave

A tabela a seguir define os prefixos comuns usados pelo [!UICONTROL Trait Builder].

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prefixo da variável principal </th> 
   <th colname="col2" class="entry"> Identifica a variável </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>Como específico do cliente. Esses são dados principais enviados por suas próprias propriedades. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>No <span class="keyword"> Audience Manager</span> nível. Esses dados são uniformes em toda a <span class="keyword"> Audience Manager</span> ecossistema. Consulte <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Atributos compatíveis com chamadas de DCS API</a> para obter uma lista mais completa.</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Que contém <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> Cabeçalho HTTP</a> informações. Inclui parâmetros de cabeçalho, como <code> referer</code>,<code> IP</code>, <code> accept-language</code>, etc. </p> <p> <p>Observação: para clientes que usam versões do DIL anteriores a 9.0, a coleta de dados usando o <code> h_referer</code> O sinal não funcionará em navegadores Safari. Com a introdução do <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, os navegadores Safari podem classificar o domínio demdex.net como um rastreador e truncarão o referenciador na solicitação de coleta de dados para conter apenas a origem em vez do URL completo. Consulte <a href="../../dil/dil-overview.md#get-implement-dil-code">Obter e implementar o código DIL</a> para obter a versão mais recente do DIL.<p>Os sinais que usam esse prefixo não são exibidos no <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Pesquisa de sinal</a>.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Nosso <span class="wintitle"> Servidores de coleta de dados</span> permitir a transmissão de parâmetros privados. Basicamente, qualquer parâmetro que comece com <code> p_</code> serão usados para avaliação de características, mas não serão registrados em log downstream nem armazenados. </p> <p>Exemplo: dado <code> /event?p_age=23</code> e uma característica como <code> YoungPeople = p_age &lt; 25</code>, a característica será realizada, mas a variável <code> p_age=23</code> o par de valor-chave será descartado após a solicitação e não será registrado. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Visão geral das informações básicas](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Gerenciamento de regras de características](../../features/traits/manage-trait-rules.md#managing-trait-rules)

