---
description: Código exigido pelo DART Enterprise (e outros tipos de destino) para capturar o valor da ID de usuário exclusiva do Audience Manager (UUID).
seo-description: Código exigido pelo DART Enterprise (e outros tipos de destino) para capturar o valor da ID de usuário exclusiva do Audience Manager (UUID).
seo-title: Código get_aamCookie
solution: Audience Manager
title: Código get_aamCookie
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 7d0735fa9620b7765db7be8d3a7c8731536ffd32
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 11%

---


# Código get_aamCookie {#get-aamcookie-code}

Código exigido por [!DNL DART Enterprise] (e outros tipos de destino) para capturar o valor da ID de usuário exclusiva ([!DNL UUID]) do Audience Manager.

Defina essa função na parte superior da página, idealmente no bloco de `<head>` código.

<!-- r_aam_de_cookie.xml -->

```js
<script type="text/javascript">
function get_aamCookie (c_name)
{
var i,x,y,ARRcookies=document.cookie.split(";");
for (i=0;i<ARRcookies.length;i++)
   {
   x=ARRcookies[i].substr(0,ARRcookies[i].indexOf("="));
   y=ARRcookies[i].substr(ARRcookies[i].indexOf("=")+1);
   x=x.replace(/^\s+|\s+$/g,"");
   if (x==c_name)
      { 
      return unescape(y);
      }
   }
}
</script>
```
