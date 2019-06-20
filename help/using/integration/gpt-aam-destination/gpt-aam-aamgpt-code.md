---
description: Aamgpt é uma função javascript que lê os dados do cookie do Audience Manager e envia essas informações para as Tags do Google Publisher.
seo-description: Aamgpt é uma função javascript que lê os dados do cookie do Audience Manager e envia essas informações para as Tags do Google Publisher.
seo-title: Código do Audience Manager para tags do Editor do Google
solution: Audience Manager
title: Código do Audience Manager para tags do Editor do Google
uuid: 24 ff 5 d 16-b 360-46 cc-a 4 c 6-6 db 34 d 7 fda 75
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Audience Manager Code for Google Publisher Tags {#audience-manager-code-for-google-publisher-tags}

`AamGpt` é [!DNL JavaScript] uma função que lê os dados do cookie do Audience Manager e a envia [!DNL Google Publisher Tags]para.

>[!NOTE]
>
>This function is not required if you have your own code to read Audience Manager cookie data from the [!UICONTROL UUID] and destination cookies.

## Código de exemplo

Place the `AamGpt` code at the top of the page, ideally within the `<head>` code block. The `AamGpt` code is available below:

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
