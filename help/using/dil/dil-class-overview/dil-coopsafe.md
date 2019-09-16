---
description: Uma configuração booleana opcional que determina se DIL envia (ou não) dados ao Adobe Experience Cloud Device Co-op.
seo-description: Uma configuração booleana opcional que determina se DIL envia (ou não) dados ao Adobe Experience Cloud Device Co-op.
seo-title: isCoopSafe
solution: Audience Manager
title: isCoopSafe
uuid: c5362a38-93c0-4edb-bdcb-106e43f33a92
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# isCoopSafe{#iscoopsafe}

Uma configuração booleana opcional que determina se DIL envia (ou não) dados ao Adobe Experience Cloud Device Co-op.

## Exigências {#requirements}

To use `isCoopSafe` you must:

* Use [!UICONTROL DIL] v6.11 ou superior.
* Participar do [Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/). Os membros em potencial também devem consultar essa documentação para determinar se `isCoopSafe` responde possíveis dúvidas sobre como os dados são usados para criar o gráfico do dispositivo.

* Trabalhe com seu consultor da [!DNL Adobe] para definir um sinalizador de lista de permissões ou lista de bloqueios na conta do Device Co-op. Não há caminho de autoatendimento para ativar esses sinalizadores.

## Casos de uso {#use-cases}

`isCoopSafe` ajuda a resolver dois casos de uso relacionados à coleta de dados pelos membros atuais ou em potencial do Device Co-op. Esses casos de uso estão relacionados à forma como os dados do visitante do site são passados para o Device co-op para ajudar a criar o gráfico do dispositivo. A tabela a seguir descreve como o `isCoopSafe` funciona com esses casos de uso para bloquear ou enviar dados para o gráfico do dispositivo

<table id="table_A24C63D2A21F47EDBAC8FA5E7BE888D8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Visitantes autenticados</b> </p> </td> 
   <td colname="col2"> <p>Add <code> isCoopSafe </code> to your <span class="wintitle"> DIL </span> code to control how data for authenticated visitors who have or have not accepted term-of-use agreements is used by the Device Co-op to build the device graph. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>DIL em sites de terceiros</b> </p> </td> 
   <td colname="col2"> <p>Add <code> isCoopSafe </code> to your <span class="wintitle"> DIL </span> code for use on third-party sites where you: </p> <p> 
     <ul id="ul_C27BB26510314834A2A7CD99D46DA4AC"> 
      <li id="li_4E6AE574F18646F09C0CF4553EEA1A9E">Não pode garantir que os visitantes autenticados aceitaram ou não os contratos de termos de uso. </li> 
      <li id="li_26D0561BF32B4278B0A6B5082C17FED8">Precisa controlar como os dados são usados pelo Device Co-op para criar o gráfico do dispositivo. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sintaxe e amostra de código {#syntax-code-sample}

**Sintaxe:** `isCoopSafe: true | false`

As opções booleanas determinam como os dados do cliente são usados ou não pelo Device Co-op.

* `isCoopSafe: true`: os dados do visitante coletados por um SDK móvel ou site *podem* ser usados para ajudar a criar o gráfico do dispositivo.

* `isCoopSafe: false`: os dados do visitante coletados por um SDK móvel ou site *não podem* ser usados para ajudar a criar o gráfico do dispositivo.

**Amostra de código**

Defina isso quando o DIL for instanciado.

```js
var dilInstance = DIL.create({ 
     ... 
     isCoopSafe: true 
});
```

## Parâmetros POST da chamada de evento {#post-parameters}

Depending on the flag you set ( `true` or `false`), [!UICONTROL DIL] translates `isCoopSafe` into these POST parameters and sends them to [!DNL Adobe] in an event call:

* `d_coop_safe=1`
* `d_coop_unsafe=1`

Os parâmetros de POST informam o [!DNL Experience Cloud] Device Co-op se é possível incluir ou não os dados do usuário no gráfico do dispositivo. A tabela abaixo define a relação entre os sinalizadores booleanos `isCoopSafe` e os parâmetros POST passados em uma chamada de evento. Se você não usar `isCoopSafe`, nenhum é passado em uma chamada de evento.

<table id="table_0A544534CA904F4D9836A34B8C1EACBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Status da configuração </th> 
   <th colname="col2" class="entry"> Parâmetro POST </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: true </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_safe=1 </code> </p> <p>O Device Co-op pode usar os dados do visitante para ajudar a criar o gráfico do dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: false </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_unsafe=1 </code> </p> <p>O Device Co-op não pode usar os dados do visitante para ajudar a criar o gráfico do dispositivo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## APIs pós-instanciamento {#post-instantiation}

Essas APIs permitem que você substitua o status de `isCoopSafe`. Elas são necessárias, pois permitem que você altere um status de pós-instanciamento/pós-login de um visitante em um site ou em um aplicativo de página simples no qual a página não é atualizada. Por exemplo, é necessário chamar essas APIs se um usuário se autentica no seu site ou aplicativo e, posteriormente, aceita uma política de termos de uso que permite ao Device Co-op usar seus dados.

<table id="table_BAA96B1F82BE48C3A61A1AF1367BA45C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopSafe(); </code> </p> </td> 
   <td colname="col2"> <p>Define o parâmetro POST <code>d_coop_safe=1</code> em todas as chamadas de evento subsequentes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopUnsafe(); </code> </p> </td> 
   <td colname="col2"> <p>Define o parâmetro POST <code>d_coop_unsafe=1</code> em todas as chamadas de evento subsequentes. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- 

Wiki page https://wiki.corp.adobe.com/x/RCfFTg

 -->

