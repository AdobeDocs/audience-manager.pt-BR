---
description: Visão geral de como integrar o Google Ad Manager usando as Tags do Google Publisher (GPT).
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: Integrar o Google Ad Manager usando as Tags do Google Publisher (GPT)
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 8%

---

# Integrar [!DNL Google Ad Manager] (antigo DFP) usando Tags do Google Publisher (GPT)

Os artigos listados abaixo fornecem uma visão geral de como integrar [!DNL Google Ad Manager] uso das Tags do Google Publisher (GPT). Você pode usar uma integração do lado do servidor ou pode configurar o GPT como um destino para enviar dados de segmento do Audience Manager para o [!DNL Google Ad Manager]. Você também aprenderá as etapas necessárias para assimilar [!DNL Google Ad Manager] arquivos de log para relatórios no Audience Manager.

* [Requisitos e métodos de envio de segmentos para o Google Ad Manager usando as Tags do Google Publisher (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Você pode enviar segmentos qualificados para o [!DNL Google Ad Manager] por meio de uma integração do lado do cliente ou do lado do servidor. Os requisitos e as informações relacionadas sobre os dois métodos estão listados abaixo.

* [Criar um destino com GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Você pode enviar segmentos qualificados para o [!DNL Google Ad Manager] por meio de uma integração do lado do cliente (lado do navegador) ou do lado do servidor. Se você escolher a integração do lado do cliente, deverá criar um destino baseado em cookies para as Tags do Google Publisher no Audience Manager.

* [Modificar a chamada da API setTargeting GPT](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Adicione uma instrução if para verificar se há cookies Audience Manager antes de chamar o método .setTargeting da tag do Google Publisher.

* [Código do Audience Manager para Tags do Google Publisher](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt é uma função JavaScript que lê dados de cookies Audience Manager e envia essas informações para as Tags do Google Publisher.
