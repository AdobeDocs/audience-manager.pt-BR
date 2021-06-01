---
description: Este artigo descreve os prefixos que devem ser anexados às variáveis-chave ao criar regras de características.
seo-description: Este artigo descreve os prefixos que devem ser anexados às variáveis-chave ao criar regras de características.
seo-title: Requisitos de prefixo para variáveis-chave
solution: Audience Manager
title: Requisitos de prefixo para variáveis-chave
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: 'Características '
exl-id: 67fe0c74-6831-48cb-90cf-417ebbf7f272
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 5%

---

# Requisitos de prefixo para variáveis-chave {#prefix-requirements-for-key-variables}

Este artigo descreve os prefixos que devem ser anexados às variáveis-chave ao criar regras de características.

<!-- r_tb_variable_prefixes.xml -->

## Finalidade dos prefixos de variável de chave

Quando você cria regras [!UICONTROL Trait Builder], é importante colocar o prefixo da variável principal em um prefixo recomendado. Esses prefixos identificam o tipo de dados transmitidos e ajudam a evitar conflitos de namespace em [!DNL Audience Manager]. Geralmente, é possível atribuir qualquer nome a uma variável, mas os dados de uma regra não serão processados se o nome da variável de chave não corresponder ao nome da variável em uma chamada de evento.

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
   <td colname="col2"> <p>Como cliente específico. Esses são dados principais enviados de suas próprias propriedades. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>No nível <span class="keyword"> Audience Manager</span>. Esses dados são uniformes no ecossistema <span class="keyword"> Audience Manager</span>. Consulte <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Atributos compatíveis para chamadas de API DCS</a> para obter uma lista mais completa.</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Que contém informações de <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> cabeçalho HTTP</a>. Inclui parâmetros de cabeçalho como <code> referer</code>,<code> IP</code>, <code> accept-language</code>, etc. </p> <p> <p>Observação: Para clientes que usam versões do DIL anteriores à 9.0, a coleta de dados usando o sinal <code> h_referer</code> não funcionará em navegadores Safari. Com a introdução de <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, os navegadores Safari podem classificar o domínio demdex.net como rastreador e truncarão o referenciador na solicitação de coleta de dados para conter apenas a origem em vez do URL completo. Consulte <a href="../../dil/dil-overview.md#get-implement-dil-code">Obter e implementar o código DIL</a> para obter a versão mais recente do DIL.<p>Os sinais que usam este prefixo não são exibidos em <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Signal Search</a>.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Nossos <span class="wintitle"> Servidores de coleta de dados</span> permitem a passagem de parâmetros privados. Basicamente, qualquer parâmetro que começa com <code> p_</code> será usado para avaliação de característica, mas não será registrado downstream nem armazenado. </p> <p>Exemplo: considerando <code> /event?p_age=23</code> e uma característica como <code> YoungPeople = p_age &lt; 25</code>, a característica será realizada, mas o par de valor-chave <code> p_age=23</code> será descartado após a solicitação e não será registrado. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Visão geral das informações básicas](../../features/traits/create-onboarded-rule-based-traits.md)
* [Gerenciamento de regras de características](../../features/traits/manage-trait-rules.md#managing-trait-rules)

