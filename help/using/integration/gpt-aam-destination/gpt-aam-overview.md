---
description: Visão geral de como integrar o Google Ad Manager usando Google Publisher Tags (GPT).
seo-description: Visão geral de como integrar o Google Ad Manager usando Google Publisher Tags (GPT) no Adobe Audience Manager (AAM).
seo-title: Integrar o Google Ad Manager usando as Tags do Google Publisher (GPT) no Adobe Audience Manager (AAM)
title: Integrar o Google Ad Manager usando as Tags do Google Publisher (GPT)
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# Integre [!DNL Google Ad Manager] (antigo DFP) usando Google Publisher Tags (GPT)

Os artigos listados abaixo fornecem uma visão geral de como integrar [!DNL Google Ad Manager] usando Tags do Google Publisher (GPT). Você pode usar uma integração do lado do servidor ou configurar o GPT como destino para enviar dados de segmento do Audience Manager para [!DNL Google Ad Manager]. Você também aprenderá as etapas necessárias para assimilar arquivos de log [!DNL Google Ad Manager] para relatórios no Audience Manager.

* [Requisitos e métodos de envio de segmentos para o Google Ad Manager usando Google Publisher Tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Você pode enviar segmentos qualificados para [!DNL Google Ad Manager] por meio de uma integração do lado do cliente ou de um servidor. Os requisitos e informações relacionadas sobre ambos os métodos estão listados abaixo.

* [Criar um destino com GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Você pode enviar segmentos qualificados para [!DNL Google Ad Manager] por meio de uma integração do lado do cliente (do lado do navegador) ou de uma integração do lado do servidor. Se você escolher a integração no lado do cliente, deve criar um destino baseado em cookies para as Tags do Google Publisher no Audience Manager.

* [Modificar a chamada da API setTargeting GPT](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Adicione uma declaração if para verificar os cookies do Audience Manager antes de chamar o método .setTargeting da tag do Google Publisher.

* [Código do Audience Manager para Tags do Google Publisher](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   O AamGpt é uma função JavaScript que lê dados de cookies do Audience Manager e envia essas informações para as Tags do Google Publisher.
