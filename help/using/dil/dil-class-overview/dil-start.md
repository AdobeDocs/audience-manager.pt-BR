---
description: Descreve os requisitos de autenticação e a formatação de texto usada na documentação do DIL em nível de classe.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Introdução às APIs do DIL em nível de classe
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
TQID: https://experienceleague.adobe.com/RlkKHc2IuInFWfWOnTKS94XhBmbDbQYjtQZI40DsU-8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2:
  - id: d7e573ad-4eda-46ec-90c4-239e75362af9
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 203
ht-degree: 0%

---

# Introdução às APIs do DIL em nível de classe{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>A partir de julho de 2023, a Adobe descontinuou o desenvolvimento do [!DNL Data Integration Library (DIL)] e da extensão [!DNL DIL].
>
>Os clientes existentes podem continuar usando a implementação [!DNL DIL]. Entretanto, a Adobe não desenvolverá [!DNL DIL] além deste ponto. Os clientes são incentivados a avaliar o [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR) para sua estratégia de coleta de dados de longo prazo.
>
>Os clientes que desejam implementar novas integrações de coleta de dados após julho de 2023 devem usar o [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR).

As APIs do DIL em nível de classe permitem criar e trabalhar de forma programática com objetos do Audience Manager. As APIs de nível de classe funcionam com as outras funções de nível de instância para definir valores ou retornar dados.

## Introdução às APIs do DIL em nível de classe {#get-started}

Descreve os requisitos de autenticação e a formatação de texto usada na documentação de nível de classe [!UICONTROL DIL].

<!-- 

c_class_start.xml

 -->

Ao trabalhar com as APIs [!UICONTROL DIL] de nível de classe:

* O Access exige um nome de parceiro e uma ID de namespace de contêiner (NSID). Entre em contato com o gerente de conta da Audience Manager para obter essas informações.
* Substitua qualquer texto de amostra *em itálico* na documentação da API por valor, ID ou outra variável, conforme exigido pelo método com o qual você está trabalhando.
* [!UICONTROL DIL] grava dados codificados em um cookie de destino. Por exemplo, espaços são codificados como `%20` e ponto e vírgula como `%3B`.
