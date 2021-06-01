---
description: Código exigido pelo DART Enterprise (e outros tipos de destino) para capturar o valor Audience Manager da ID de usuário exclusiva (UUID).
seo-description: Código exigido pelo DART Enterprise (e outros tipos de destino) para capturar o valor Audience Manager da ID de usuário exclusiva (UUID).
seo-title: Código get_aamCookie
solution: Audience Manager
title: Código get_aamCookie
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Noções básicas sobre o destino
exl-id: 66e61a4b-908e-4950-8953-37a9920b67b5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 9%

---

# `get_aamCookie` Código {#get-aamcookie-code}

Código exigido por [!DNL DART Enterprise] (e outros tipos de destino) para capturar o valor da ID de usuário exclusiva do Audience Manager ([!DNL UUID]).

Defina essa função na parte superior da página, idealmente no bloco de código `<head>` .

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
