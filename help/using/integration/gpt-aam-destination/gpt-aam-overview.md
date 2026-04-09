---
description: Visão geral de como integrar o Google Ad Manager usando as Tags do Google Publisher (GPT).
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: Integrar o Google Ad Manager usando as Tags do Google Publisher (GPT)
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
TQID: https://experienceleague.adobe.com/29V5C3MbEondd3-qWLBfi3jaGid1I1UM9nYIl9nZWVo
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 212
ht-degree: 0%

---

# Integrar o [!DNL Google Ad Manager] (antigo DFP) usando o Google Publisher Tags (GPT)

Os artigos listados abaixo fornecem uma visão geral de como integrar o [!DNL Google Ad Manager] usando o Google Publisher Tags (GPT). Você pode usar uma integração do lado do servidor ou pode configurar o GPT como destino para enviar dados de segmento do Audience Manager para [!DNL Google Ad Manager]. Você também aprenderá as etapas necessárias para assimilar arquivos de log do [!DNL Google Ad Manager] para relatórios no Audience Manager.

* [Requisitos e métodos de envio de segmentos para o Google Ad Manager usando as Tags do Google Publisher (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

  Você pode enviar segmentos qualificados para [!DNL Google Ad Manager] por meio de uma integração do lado do cliente ou do lado do servidor. Os requisitos e as informações relacionadas sobre os dois métodos estão listados abaixo.

* [Criar um destino GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

  Você pode enviar segmentos qualificados para o [!DNL Google Ad Manager] por meio de uma integração do lado do cliente (lado do navegador) ou de uma integração do lado do servidor. Se você escolher a integração do lado do cliente, deverá criar um destino baseado em cookies para as Tags do Google Publisher no Audience Manager.

* [Modificar a chamada da API setTargeting GPT](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

  Adicione uma instrução if para verificar se há cookies do Audience Manager antes de chamar o método .setTargeting de tag do Google Publisher.

* [Código Audience Manager para tags do Google Publisher](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

  AamGpt é uma função do JavaScript que lê dados de cookies do Audience Manager e envia essas informações para as Tags do Google Publisher.
