---
description: Descreve as etapas e os recursos configurados específicos do processo de criação de características e integração com base em regras.
keywords: criar característica; criar características
seo-description: Descreve as etapas e os recursos configurados específicos do processo de criação de características e integração com base em regras.
seo-title: Criar características baseadas em regras ou em onboar
solution: Audience Manager
title: Criar características baseadas em regras ou em onboar
uuid: 4243 e 09 f -1 f 96-443 a -864 a-d 6 e 6918079 fa
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# Criar características baseadas em regras ou em onboar {#create-rules-based-or-onboarded-traits}

Descreve as etapas e os recursos configurados específicos para o processo [!UICONTROL rules-based] de criação e [!UICONTROL onboarded] criação de características.

<!-- c_tb_rules_traits.xml -->

## Informações básicas para características {#basics}

Em [!UICONTROL Trait Builder], as [!UICONTROL Basic Information] configurações permitem criar novos ou editar já existentes. As [!UICONTROL Basic Information] configurações são as mesmas para características de algoritmo, onboard e algoritmo com base em regras. Para criar uma nova característica, forneça um nome (evite caracteres especiais), uma fonte de dados e selecione uma pasta de armazenamento. Outros [!UICONTROL Basic Information] campos são opcionais.

<!-- c_tb_basics.xml -->

### Campos básicos de informação definidos

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento da interface </th> 
   <th colname="col2" class="entry"> Explicação </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">Nome</span></b> </td> 
   <td colname="col2"> <p>O nome do traço. Obrigatório. </p> <p>Extensão máxima: 255 caracteres. </p> <p> <p>Observação: Ao nomear características, evite estes caracteres especiais: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Vírgulas </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Traços </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Hífens </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Guias </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Barra vertical ou símbolo de barra vertical </li> 
      </ul> </p> </p> <p>Isso ajuda a reduzir os erros de processamento ao configurar uma transferência de arquivo de dados <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> de entrada</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Descrição</span></b> </td> 
   <td colname="col2"> Algumas palavras para ajudar a descrever a finalidade ou a função característica. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Tipo de evento</span></b> </td> 
   <td colname="col2"> Atribui a característica a um tipo ou categoria, normalmente de acordo com a função (por exemplo, conversão, visitante do site, parceiro, exibição de página etc.). Opcional. <p> Para saber como criar características de conversão, consulte <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Criar características de conversão no vídeo do Audience Manager</a>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Fonte de dados</span></b> </td> 
   <td colname="col2"> Associa a característica a um provedor de dados específico. Obrigatório. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Código de integração</span></b> </td> 
   <td colname="col2"> Um campo de uma ID, SKU ou outro valor usado pelos processos comerciais internos. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Comentários</span></b> </td> 
   <td colname="col2"> Observações gerais sobre uma característica. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Armazenado em</span></b> </td> 
   <td colname="col2"> Determina a pasta de armazenamento à qual a característica pertence. Obrigatório. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Categoria de dados</span></b> </td> 
   <td colname="col2"> Classifica características de acordo com as categorias comumente compreendidas. <p>Observação: As características pertencem somente a uma única categoria. Opcional. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Definir um intervalo de expiração de características {#set-expiration-interval}

No [!UICONTROL Trait Builder], [!UICONTROL Advanced Options] permite definir um intervalo de tempo para live ([!DNL TTL]) para uma característica. [!DNL TTL] define quantos dias um visitante qualificado permanece em uma característica (120 dias é padrão). Quando definido como 0, a associação característica nunca expira.

<!-- t_tb_ttl.xml -->

### Definir o TTL de uma característica

1. Expanda a [!UICONTROL Advanced Options] seção e insira um número para definir um [!DNL TTL] valor para a característica.
2. Clique em **[!UICONTROL Save]**.
   ![](assets/TTL.png)

>[!MORE_ LIKE_ THIS]
>
>* [Tempo do segmento para explicação dinâmica](../../features/traits/segment-ttl-explained.md)

