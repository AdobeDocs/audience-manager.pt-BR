---
description: O AamGpt é uma função JavaScript que lê os dados de cookies do Audience Manager e envia essas informações para as Tags do Google Publisher.
seo-description: O AamGpt é uma função JavaScript que lê os dados de cookies do Audience Manager e envia essas informações para as Tags do Google Publisher.
seo-title: Código do Audience Manager para tags do Google Publisher
solution: Audience Manager
title: Código do Audience Manager para tags do Google Publisher
uuid: 24ff5d16-b360-46cc-a4c6-6db34d7fda75
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Código do Audience Manager para tags do Google Publisher {#audience-manager-code-for-google-publisher-tags}

`AamGpt` é uma [!DNL JavaScript] função que lê os dados de cookies do Audience Manager e envia essas informações para [!DNL Google Publisher Tags].

>[!NOTE]
>
>Essa função não é necessária se você tiver seu próprio código para ler os dados de cookies do Audience Manager dos cookies [!UICONTROL UUID] e de destino.

## Código de exemplo

Coloque o `AamGpt` código na parte superior da página, idealmente dentro do bloco de `<head>` código. O `AamGpt` código está disponível abaixo:

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
