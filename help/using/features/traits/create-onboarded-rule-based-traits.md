---
description: Descreve as etapas e os recursos da configuração específicos do processo de criação de características integrado e baseado em regras.
keywords: criar característica; criar características
seo-description: Descreve as etapas e os recursos da configuração específicos do processo de criação de características integrado e baseado em regras.
seo-title: Criar características integradas ou com base em regras
solution: Audience Manager
title: Criar características integradas ou com base em regras
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: 'Características '
exl-id: cad318ee-93b2-4afa-8a2f-a67b068eec0a
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 8%

---

# Crie[!UICONTROL Rules-Based] ou [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

Descreve as etapas e os recursos de configuração específicos do processo de criação de características [!UICONTROL rules-based] e [!UICONTROL onboarded].

<!-- c_tb_rules_traits.xml -->

## Informações básicas sobre características {#basics}

Em [!UICONTROL Trait Builder], as configurações [!UICONTROL Basic Information] permitem criar novas ou editar [!UICONTROL traits] existentes. As configurações [!UICONTROL Basic Information] são as mesmas para [!UICONTROL rules-based], [!UICONTROL onboarded] e [!UICONTROL algorithmic traits]. Para criar um novo [!UICONTROL trait], forneça um nome (evite caracteres especiais), um [!UICONTROL data source] e selecione um [!UICONTROL storage folder]. Outros campos [!UICONTROL Basic Information] são opcionais.

<!-- c_tb_basics.xml -->

![create-trait](assets/create-trait.png)

### Campos básicos de informações definidos

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento da interface </th> 
   <th colname="col2" class="entry"> Explicação </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Nome</span></b> </td> 
   <td colname="col2"> <p>O nome da característica. Obrigatório. </p> <p>Comprimento máximo: 255 caracteres. </p> <p> <p>Observação: Ao nomear características, evite esses caracteres especiais: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Vírgulas </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Traços </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Hifens </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Guias </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Barra vertical ou símbolo da barra vertical </li> 
      </ul> </p> </p> <p>Isso ajuda a reduzir erros de processamento ao configurar uma <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> transferência de arquivos de dados de entrada</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Descrição</span></b> </td> 
   <td colname="col2"> Algumas palavras para ajudar a descrever o propósito ou a função da característica. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Fonte de dados</span></b> </td> 
   <td colname="col2"> Associa a característica a um provedor de dados específico. Obrigatório. <p>Use o primeiro menu suspenso para filtrar entre fontes de dados Audience Manager, conjuntos de relatórios do Adobe Analytics ou ambos. Em seguida, use o segundo menu suspenso para escolher sua fonte de dados.</p><p> Se você não estiver usando conjuntos de relatórios do Adobe Analytics, o seletor de tipo de fonte de dados será desativado e o padrão será apenas fontes de dados Audience Manager.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Tipo de evento</span></b> </td> 
   <td colname="col2"> Atribui a característica a um tipo ou categoria, normalmente de acordo com a função (por exemplo, conversão, visitante do site, parceiro, exibição de página etc.). Opcional. <p> Para saber como criar características de conversão, consulte <a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Criação de características de conversão em Audience Manager video</a>. </p></td> 
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
   <td colname="col2"> Determina a pasta de armazenamento à qual a característica pertence. Obrigatório. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Categoria de dados</span></b> </td> 
   <td colname="col2"> Classifica características de acordo com categorias comumente compreendidas. <p>Observação:  As características pertencem apenas a uma única categoria. Opcional. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Definir um Intervalo de Expiração [!UICONTROL Trait] {#set-expiration-interval}

Em [!UICONTROL Trait Builder], o [!UICONTROL Advanced Options] permite que você defina um intervalo de tempo de vida ([!DNL TTL]) para um [!UICONTROL trait]. [!DNL TTL] define quantos dias um visitante qualificado permanece em um  [!UICONTROL trait] (120 dias é padrão). Quando definido como 0, a associação [!UICONTROL trait] nunca expira.

<!-- t_tb_ttl.xml -->

### Defina o TTL para um [!UICONTROL trait]

1. Expanda a seção [!UICONTROL Advanced Options] e insira um número para definir um valor [!DNL TTL] para o [!UICONTROL trait].
1. Clique em **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Explicação do tempo de vida do segmento](../../features/traits/segment-ttl-explained.md)

