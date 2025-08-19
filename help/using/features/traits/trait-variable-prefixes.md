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
source-wordcount: '317'
ht-degree: 0%

---

# Requisitos de prefixo para variáveis-chave {#prefix-requirements-for-key-variables}

Este artigo descreve os prefixos que você deve anexar às variáveis principais ao criar regras de características.

<!-- r_tb_variable_prefixes.xml -->

## Finalidade dos prefixos de variáveis-chave

Ao criar regras do [!UICONTROL Trait Builder], é importante colocar um prefixo recomendado na variável principal. Esses prefixos identificam o tipo de dados transmitidos e ajudam a evitar conflitos de namespace em [!DNL Audience Manager]. Geralmente, você pode dar qualquer nome a uma variável, mas os dados de uma regra não serão processados se o nome da variável principal não corresponder ao nome da variável em uma chamada de evento.

## Prefixos para variáveis-chave

A tabela a seguir define os prefixos comuns usados por [!UICONTROL Trait Builder].

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
   <td colname="col2"> <p>No nível <span class="keyword"> Audience Manager</span>. Estes dados são uniformes em todo o ecossistema do <span class="keyword"> Audience Manager</span>. Consulte <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Atributos compatíveis com as chamadas de API DCS</a> para obter uma lista mais completa.</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Que contém informações do <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> cabeçalho HTTP</a>. Inclui parâmetros de cabeçalho como <code> referer</code>,<code> IP</code>, <code> accept-language</code>, etc. </p> <p> <p>Observação: para clientes que usam versões do DIL anteriores à 9.0, a coleta de dados usando o sinal <code> h_referer</code> não funcionará em navegadores Safari. Com a introdução do <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, os navegadores Safari podem classificar o domínio demdex.net como um rastreador e truncarão o referenciador na solicitação de coleta de dados para conter apenas a origem em vez da URL completa. Consulte <a href="../../dil/dil-overview.md#get-implement-dil-code">Obtendo e implementando o Código DIL</a> para obter a versão mais recente do DIL.<p>Os sinais que usam este prefixo não aparecem na <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Pesquisa de Sinal</a>.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Nossos <span class="wintitle"> Servidores de Coleta de Dados</span> permitem a passagem de parâmetros privados. Basicamente, qualquer parâmetro que comece com <code> p_</code> será usado para avaliação de características, mas não será registrado em log downstream nem armazenado. </p> <p>Exemplo: dado <code> /event?p_age=23</code> e uma característica como <code> YoungPeople = p_age &lt; 25</code>, a característica será realizada, mas o par de valor-chave <code> p_age=23</code> será descartado após a solicitação e não será registrado. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Visão Geral das Informações Básicas](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Gerenciamento de regras de características](../../features/traits/manage-trait-rules.md#managing-trait-rules)
