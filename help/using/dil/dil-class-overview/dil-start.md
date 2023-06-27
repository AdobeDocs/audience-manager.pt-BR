---
description: Descreve os requisitos de autenticação e a formatação de texto usada na documentação do DIL de nível de classe.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Introdução às DIL APIs em nível de classe
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: 152b3101e69e99dfe19c1be93edceaea6adc4fec
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 8%

---

# Introdução às DIL APIs em nível de classe{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>A partir de julho de 2023, a Adobe interrompeu o desenvolvimento do [!DNL Data Integration Library (DIL)] e a variável [!DNL DIL] extensão.
><br><br>
>Os clientes existentes podem continuar usando seus [!DNL DIL] execução. No entanto, o Adobe não estará em desenvolvimento [!DNL DIL] além deste ponto. Os clientes são incentivados a avaliar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para a sua estratégia de recolha de dados a longo prazo.
><br><br>
>Os clientes que desejam implementar novas integrações de coleta de dados após julho de 2023 devem usar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) em vez disso.

As APIs de DIL em nível de classe permitem criar e trabalhar programaticamente com objetos Audience Manager. As APIs de nível de classe funcionam com as outras funções de nível de instância para definir valores ou retornar dados.

## Introdução às DIL APIs em nível de classe {#get-started}

Descreve os requisitos de autenticação e a formatação de texto usada no nível de classe [!UICONTROL DIL] documentação.

<!-- 

c_class_start.xml

 -->

Ao trabalhar com o nível de classe [!UICONTROL DIL] APIs:

* O Access exige um nome de parceiro e uma ID de namespace de contêiner (NSID). Entre em contato com o gerente de conta do Audience Manager para obter essas informações.
* Substituir qualquer amostra *itálico* texto na documentação da API com valor, ID ou outra variável, conforme exigido pelo método com o qual você está trabalhando.
* [!UICONTROL DIL] grava dados codificados em um cookie de destino. Por exemplo, espaços são codificados como `%20` e ponto e vírgula como `%3B`.
