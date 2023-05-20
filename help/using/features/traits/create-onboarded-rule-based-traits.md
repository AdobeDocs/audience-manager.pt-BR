---
description: Descreve as etapas de configuração e os recursos específicos do processo de criação de características integrado e com base em regras.
keywords: criar característica;criar características
seo-description: Describes set up steps and features specific to the rules-based and onboarded trait creation process.
seo-title: Create Rules-Based or Onboarded Traits
solution: Audience Manager
title: Criar características integradas ou com base em regras
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
exl-id: cad318ee-93b2-4afa-8a2f-a67b068eec0a
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 7%

---

# Crie[!UICONTROL Rules-Based] ou [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

Descreve as etapas de configuração e os recursos específicos do [!UICONTROL rules-based] e [!UICONTROL onboarded] processo de criação de características.

<!-- c_tb_rules_traits.xml -->

## Informações básicas para características {#basics}

Entrada [!UICONTROL Trait Builder], o [!UICONTROL Basic Information] permitem criar novos arquivos ou editar arquivos existentes [!UICONTROL traits]. A variável [!UICONTROL Basic Information] as mesmas configurações para [!UICONTROL rules-based], [!UICONTROL onboarded] e [!UICONTROL algorithmic traits]. Para criar um novo [!UICONTROL trait], forneça um nome (evite caracteres especiais), uma [!UICONTROL data source]e selecione um [!UICONTROL storage folder]. Outro [!UICONTROL Basic Information] Os campos são opcionais.

<!-- c_tb_basics.xml -->

![create-trait](assets/create-trait.png)

### Campos de informações básicas definidos

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
   <td colname="col2"> <p>O nome da característica. Obrigatório. </p> <p>Tamanho máximo: 255 caracteres. </p> <p> <p>Observação: ao nomear características, evite estes caracteres especiais: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Vírgulas </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Traços </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Hífens </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Guias </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Símbolo de barra ou barra vertical </li> 
      </ul> </p> </p> <p>Isso ajuda a reduzir erros de processamento ao configurar um <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> transferência de arquivo de dados de entrada</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Descrição</span></b> </td> 
   <td colname="col2"> Algumas palavras para ajudar a descrever o propósito ou a função da característica. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Fonte de dados</span></b> </td> 
   <td colname="col2"> Associa a característica a um provedor de dados específico. Obrigatório. <p>Use o primeiro menu suspenso para filtrar entre fontes de dados de Audience Manager, conjuntos de relatórios do Adobe Analytics ou ambos. Em seguida, use o segundo menu suspenso para escolher a fonte de dados.</p><p> Se você não estiver usando conjuntos de relatórios do Adobe Analytics, o seletor de tipo de fonte de dados será desativado e assumirá como padrão apenas as fontes de dados de Audience Manager.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Tipo de evento</span></b> </td> 
   <td colname="col2"> Atribui a característica a um tipo ou categoria, geralmente de acordo com a função (por exemplo, conversão, visitante do site, parceiro, exibição de página etc.). Opcional. <p> Para saber como criar características de conversão, consulte a <a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Vídeo Criação de características de conversão no Audience Manager</a>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Código de integração</span></b> </td> 
   <td colname="col2"> Um campo para uma ID, SKU ou outro valor usado por seus processos comerciais internos. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Comentários</span></b> </td> 
   <td colname="col2"> Observações gerais sobre uma característica. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Armazenar em</span></b> </td> 
   <td colname="col2"> Determina a qual pasta de armazenamento a característica pertence. Obrigatório. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Categoria de dados</span></b> </td> 
   <td colname="col2"> Classifica as características de acordo com categorias comumente compreendidas. <p>Observação: as características pertencem apenas a uma única categoria. Opcional. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Defina um [!UICONTROL Trait] Intervalo de expiração {#set-expiration-interval}

Entrada [!UICONTROL Trait Builder], o [!UICONTROL Advanced Options] permite definir um tempo de vida útil ([!DNL TTL]) para um [!UICONTROL trait]. [!DNL TTL] define quantos dias um visitante qualificado permanece em uma [!UICONTROL trait] (120 dias é o padrão). Quando definido como 0, [!UICONTROL trait] a associação nunca expira.

<!-- t_tb_ttl.xml -->

### Defina o TTL para um [!UICONTROL trait]

1. Expanda a [!UICONTROL Advanced Options] e insira um número para definir uma [!DNL TTL] valor para o [!UICONTROL trait].
1. Clique em **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Explicação do tempo de vida do segmento](../../features/traits/segment-ttl-explained.md)

