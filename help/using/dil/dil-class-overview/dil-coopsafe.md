---
description: Uma configuração booleana opcional que determina se DIL envia (ou não) dados ao Adobe Experience Cloud Device Co-op.
seo-description: An optional, Boolean configuration that determines if DIL sends (or does not send) data to the Adobe Experience Cloud Device Co-op.
seo-title: isCoopSafe
solution: Audience Manager
title: isCoopSafe
uuid: c5362a38-93c0-4edb-bdcb-106e43f33a92
feature: DIL Implementation
exl-id: 33dca495-6923-4966-9ec3-8b0fd2f17649
hide: true
hidefromtoc: true
index: n
source-git-commit: 3f4a161ee856357b5cb5eb757ad779dee5357b09
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 76%

---

# isCoopSafe{#iscoopsafe}

>[!WARNING]
>
>Esse recurso foi substituído.

Uma configuração booleana opcional que determina se DIL envia (ou não) dados ao Adobe Experience Cloud Device Co-op.

## Requisitos {#requirements}

Para usar `isCoopSafe` você deve:

* Use [!UICONTROL DIL] v6.11 ou superior.
* Participar do [Experience Cloud Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/home.html). Os membros em potencial também devem consultar essa documentação para determinar se `isCoopSafe` responde possíveis dúvidas sobre como os dados são usados para criar o gráfico do dispositivo.

* Trabalhe com seu [!DNL Adobe] consultor da para definir uma  de lista de permissões ou um sinalizador de  de lista de bloqueios na conta do Device Co-op. Não há um caminho de autoatendimento para habilitar esses sinalizadores.

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
   <td colname="col2"> <p>Adicionar <code> isCoopSafe </code> para <span class="wintitle"> DIL </span> código para controlar como os dados para visitantes autenticados que aceitaram ou não os contratos de termos de uso são usados pelo Device Co-op para criar o gráfico do dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>DIL em sites de terceiros</b> </p> </td> 
   <td colname="col2"> <p>Adicionar <code> isCoopSafe </code> para <span class="wintitle"> DIL </span> código para uso em sites de terceiros onde você: </p> <p> 
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

Dependendo do sinalizador definido ( `true` ou `false`), [!UICONTROL DIL] traduções `isCoopSafe` nesses parâmetros de POST e os envia para [!DNL Adobe] em uma chamada de evento:

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
   <td colname="col2"> <p>Define o parâmetro POST <code> d_coop_safe=1 </code> em todas as chamadas de evento subsequentes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopUnsafe(); </code> </p> </td> 
   <td colname="col2"> <p>Define o parâmetro POST <code> d_coop_unsafe=1 </code> em todas as chamadas de evento subsequentes. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- 

Wiki page https://wiki.corp.adobe.com/x/RCfFTg

 -->
