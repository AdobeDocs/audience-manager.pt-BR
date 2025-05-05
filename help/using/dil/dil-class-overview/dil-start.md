---
description: Descreve os requisitos de autenticação e a formatação de texto usada na documentação do DIL de nível de classe.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Introdução às APIs de DIL de nível de classe
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 0%

---

# Introdução às APIs de DIL de nível de classe{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>A partir de julho de 2023, o Adobe descontinuou o desenvolvimento da extensão [!DNL Data Integration Library (DIL)] e [!DNL DIL].
>
>Os clientes existentes podem continuar usando a implementação [!DNL DIL]. Entretanto, o Adobe não desenvolverá [!DNL DIL] além deste ponto. Os clientes são incentivados a avaliar o [SDK da Web do Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR) para sua estratégia de coleta de dados de longo prazo.
>
>Os clientes que desejam implementar novas integrações de coleção de dados após julho de 2023 devem usar o [SDK da Web do Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR).

As APIs de DIL em nível de classe permitem criar e trabalhar programaticamente com objetos Audience Manager. As APIs de nível de classe funcionam com as outras funções de nível de instância para definir valores ou retornar dados.

## Introdução às APIs de DIL de nível de classe {#get-started}

Descreve os requisitos de autenticação e a formatação de texto usada na documentação de nível de classe [!UICONTROL DIL].

<!-- 

c_class_start.xml

 -->

Ao trabalhar com as APIs [!UICONTROL DIL] de nível de classe:

* O Access exige um nome de parceiro e uma ID de namespace de contêiner (NSID). Entre em contato com o gerente de conta do Audience Manager para obter essas informações.
* Substitua qualquer texto de amostra *em itálico* na documentação da API por valor, ID ou outra variável, conforme exigido pelo método com o qual você está trabalhando.
* [!UICONTROL DIL] grava dados codificados em um cookie de destino. Por exemplo, espaços são codificados como `%20` e ponto e vírgula como `%3B`.
