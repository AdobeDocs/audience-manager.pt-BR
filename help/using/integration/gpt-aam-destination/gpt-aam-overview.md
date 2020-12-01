---
description: Visão geral de como integrar o Google Ad Manager usando o Google Publisher Tags (GPT).
seo-description: Visão geral de como integrar o Google Ad Manager usando Google Publisher Tags (GPT) no Adobe Audience Manager (AAM).
seo-title: Integre o Google Ad Manager usando Google Publisher Tags (GPT) no Adobe Audience Manager (AAM)
title: Integre o Google Ad Manager usando Google Publisher Tags (GPT)
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# Integre [!DNL Google Ad Manager] (antigo DFP) usando Google Publisher Tags (GPT)

Os artigos listados abaixo fornecem uma visão geral de como se integrar [!DNL Google Ad Manager] usando o Google Publisher Tags (GPT). Você pode usar uma integração do lado do servidor ou pode configurar o GPT como destino para enviar dados do segmento de Audience Manager para [!DNL Google Ad Manager]. Você também aprenderá as etapas necessárias para assimilar [!DNL Google Ad Manager] arquivos de registro para o relatórios no Audience Manager.

* [Requisitos e métodos de envio de segmentos ao Google Ad Manager usando Google Publisher Tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Você pode enviar segmentos qualificados para [!DNL Google Ad Manager] por meio de uma integração do lado do cliente ou do lado do servidor. Os requisitos e as informações relacionadas sobre ambos os métodos estão listados abaixo.

* [Criar um destino com GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Você pode enviar segmentos qualificados para [!DNL Google Ad Manager] por meio de uma integração do lado do cliente (navegador) ou de uma integração do lado do servidor. Se você escolher a integração do cliente, deverá criar um destino baseado em cookies para as Tags do Google Publisher no Audience Manager.

* [Modificar a chamada da API setTargeting GPT](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Adicione uma declaração if para verificar cookies de Audience Manager antes de chamar o método Google Publisher Tag .setTargeting.

* [Código do Audience Manager para Tags do Google Publisher](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   O AamGpt é uma função JavaScript que lê dados de cookies de Audience Manager e envia essas informações para as Tags do Google Publisher.
