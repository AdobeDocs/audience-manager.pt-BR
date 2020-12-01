---
description: Descreve as etapas e os recursos específicos do processo de criação de características integradas e baseadas em regras.
keywords: create trait;create traits
seo-description: Descreve as etapas e os recursos específicos do processo de criação de características integradas e baseadas em regras.
seo-title: Criar características integradas ou com base em regras
solution: Audience Manager
title: Criar características integradas ou com base em regras
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 8%

---


# Crie[!UICONTROL Rules-Based] ou [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

Descreve as etapas de configuração e os recursos específicos do processo de criação de características [!UICONTROL rules-based] e [!UICONTROL onboarded].

<!-- c_tb_rules_traits.xml -->

## Informações básicas sobre características {#basics}

Em [!UICONTROL Trait Builder], as configurações de [!UICONTROL Basic Information] permitem criar novas ou editar [!UICONTROL traits] existentes. As configurações [!UICONTROL Basic Information] são as mesmas para [!UICONTROL rules-based], [!UICONTROL onboarded] e [!UICONTROL algorithmic traits]. Para criar um novo [!UICONTROL trait], forneça um nome (evite caracteres especiais), um [!UICONTROL data source] e selecione um [!UICONTROL storage folder]. Outros campos [!UICONTROL Basic Information] são opcionais.

<!-- c_tb_basics.xml -->

![create-trait](assets/create-trait.png)

### Definição de campos de informações básicas

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de interface </th> 
   <th colname="col2" class="entry"> Explicação </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Nome</span></b> </td> 
   <td colname="col2"> <p>O nome da característica. Obrigatório. </p> <p>Comprimento máximo: 255 caracteres. </p> <p> <p>Observação: Ao nomear características, evite estes caracteres especiais: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Vírgulas </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Traços </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Hífens </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Guias </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Barra vertical ou símbolo de barra vertical </li> 
      </ul> </p> </p> <p>Isso ajuda a reduzir os erros de processamento ao configurar uma <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> transferência de arquivo de dados de entrada</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Descrição</span></b> </td> 
   <td colname="col2"> Algumas palavras para ajudar a descrever o propósito ou a função do traço. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Fonte de dados</span></b> </td> 
   <td colname="col2"> Associa a característica a um provedor de dados específico. Obrigatório. <p>Use o primeiro menu suspenso para filtrar entre fontes de dados Audience Manager, conjuntos de relatórios da Adobe Analytics ou ambos. Em seguida, use o segundo menu suspenso para escolher sua fonte de dados.</p><p> Se você não estiver usando conjuntos de relatórios da Adobe Analytics, o seletor de tipo de fonte de dados será desativado e o padrão será somente fontes de dados Audience Manager.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Tipo de evento</span></b> </td> 
   <td colname="col2"> Atribui a característica a um tipo ou categoria, normalmente de acordo com a função (por exemplo, conversão, visitante do site, parceiro, visualização da página etc.). Opcional. <p> Para saber como criar características de conversão, consulte <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Criando características de conversão em Audience Manager video</a>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Código de integração</span></b> </td> 
   <td colname="col2"> Um campo para uma ID, SKU ou outro valor usado pelos seus processos comerciais internos. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Comentários</span></b> </td> 
   <td colname="col2"> O General anota sobre uma característica. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Armazenar em</span></b> </td> 
   <td colname="col2"> Determina a pasta de armazenamento à qual a característica pertence. Obrigatório. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Categoria de dados</span></b> </td> 
   <td colname="col2"> Classifica características de acordo com categorias comumente compreendidas. <p>Observação:  As características pertencem apenas a uma única categoria. Opcional. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Definir um [!UICONTROL Trait] Intervalo de Expiração {#set-expiration-interval}

Em [!UICONTROL Trait Builder], [!UICONTROL Advanced Options] permite definir um intervalo de tempo de vida ([!DNL TTL]) para um [!UICONTROL trait]. [!DNL TTL] define quantos dias um visitante qualificado permanece em um  [!UICONTROL trait] (120 dias é o padrão). Quando definida como 0, a associação [!UICONTROL trait] nunca expira.

<!-- t_tb_ttl.xml -->

### Defina o TTL para um [!UICONTROL trait]

1. Expanda a seção [!UICONTROL Advanced Options] e insira um número para definir um valor [!DNL TTL] para [!UICONTROL trait].
1. Clique em **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Explicação do tempo de segmento ao vivo](../../features/traits/segment-ttl-explained.md)

