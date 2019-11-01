---
description: Este artigo descreve os prefixos que você deve anexar às variáveis principais ao criar regras de características.
seo-description: Este artigo descreve os prefixos que você deve anexar às variáveis principais ao criar regras de características.
seo-title: Requisitos de prefixo para variáveis-chave
solution: Audience Manager
title: Requisitos de prefixo para variáveis-chave
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Requisitos de prefixo para variáveis-chave {#prefix-requirements-for-key-variables}

Este artigo descreve os prefixos que você deve anexar às variáveis principais ao criar regras de características.

<!-- r_tb_variable_prefixes.xml -->

## Objetivo dos prefixos de variável de chave

Ao criar [!UICONTROL Trait Builder] regras, é importante pré-posicionar a variável principal com um prefixo recomendado. Esses prefixos identificam o tipo de dados passados e ajudam a evitar conflitos de namespace no [!DNL Audience Manager]. Geralmente, você pode dar qualquer nome a uma variável, mas os dados de uma regra não serão processados se o nome da variável principal não corresponder ao nome da variável em uma chamada de evento.

## Prefixos para variáveis-chave

A tabela a seguir define os prefixos comuns usados por [!UICONTROL Trait Builder].

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prefixo da variável de chave </th> 
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
   <td colname="col2"> <p>No nível do <span class="keyword"> Audience Manager</span> . Esses dados são uniformes em todo o ecossistema do <span class="keyword"> Audience Manager</span> . Consulte <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Atributos suportados para chamadas</a> de API DCS para obter uma lista mais completa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Isso contém informações de cabeçalho <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"></a> HTTP. Inclui parâmetros de cabeçalho como <code> referer</code>,<code> IP</code>, <code> accept-language</code>etc. </p> <p> <p>Observação: Para clientes que usam versões DIL anteriores à 9.0, a coleta de dados que usa o <code> h_referer</code> sinal não funcionará nos navegadores Safari. Com a introdução do <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, os navegadores Safari podem classificar o domínio demdex.net como um rastreador e truncarão o referenciador na solicitação de coleta de dados para conter apenas a origem em vez do URL completo. Consulte <a href="../../dil/dil-overview.md#get-implement-dil-code">Obtendo e implementando o código</a> DIL para obter a versão mais recente do DIL. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Nossos servidores <span class="wintitle"></span> de coleta de dados permitem a passagem de parâmetros privados. Basicamente, qualquer parâmetro que começa com <code> p_</code> será usado para avaliação de características, mas não será registrado como downstream nem armazenado. </p> <p>Exemplo: dado <code> /event?p_age=23</code> e uma característica como <code> YoungPeople = p_age &lt; 25</code>, a característica será realizada, mas o par de valor- <code> p_age=23</code> chave será descartado após a solicitação e não será registrado. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Visão geral das informações básicas](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Gerenciando regras de características](../../features/traits/manage-trait-rules.md#managing-trait-rules)

