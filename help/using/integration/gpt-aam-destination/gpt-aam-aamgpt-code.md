---
description: O AamGpt é uma função JavaScript que lê dados de cookies do Audience Manager e envia essas informações para as Tags do Google Publisher.
seo-description: O AamGpt é uma função JavaScript que lê dados de cookies do Audience Manager e envia essas informações para as Tags do Google Publisher.
seo-title: Código do Audience Manager para Tags do Google Publisher
solution: Audience Manager
title: Código do Audience Manager para Tags do Google Publisher
uuid: 24ff5d16-b360-46cc-a4c6-6db34d7fda75
feature: Integração de terceiros
exl-id: 04e74399-7b6a-400e-a1e6-94fe296e7209
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 19%

---

# Código do Audience Manager para Tags do Google Publisher {#audience-manager-code-for-google-publisher-tags}

`AamGpt` é uma  [!DNL JavaScript] função que lê dados de cookie do Audience Manager e envia essas informações para o  [!DNL Google Publisher Tags].

>[!NOTE]
>
>Essa função não é necessária se você tiver seu próprio código para ler os dados do cookie de Audience Manager dos cookies [!UICONTROL UUID] e de destino.

## Código de exemplo

Coloque o código `AamGpt` na parte superior da página, idealmente, dentro do bloco de código `<head>`. O código `AamGpt` está disponível abaixo:

```js
var AamGpt = {  
 strictEncode: function(str){ 
  return encodeURIComponent(str).replace(/[!'()]/g, escape).replace(/\*/g, "%2A"); 
 }, 
 getCookie: function(c_name) 
 { 
  var i,x,y,c=document.cookie.split(";"); 
  for (i=0;i<c.length;i++) 
  { 
   x=c[i].substr(0,c[i].indexOf("=")); 
   y=c[i].substr(c[i].indexOf("=")+1); 
   x=x.replace(/^\s+|\s+$/g,""); 
   if (x==c_name) 
   { 
    return unescape(y); 
   } 
  } 
 }, 
 getKey: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[0] != "undefined" && cList[0].match(/\w+/)) 
   { 
    return cList[0]; 
   } 
  }  
 }, 
 getValues: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D\w+/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[1] != "undefined" && cList[1].match(/\w+/)) 
   { 
    var vList=cList[1].split("%2C"); 
    if(typeof vList[0] != "undefined") 
    { 
     return vList; 
    } else { 
     return null; 
    }    
   } else { 
    return null; 
   } 
  } else { 
   return null; 
  } 
 } 
};
```
