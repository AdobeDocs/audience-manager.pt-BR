---
description: Visão geral de como integrar o DFP usando o Google Publisher Tags (GPT).
seo-description: Visão geral de como integrar o DFP usando Google Publisher Tags (GPT) no Adobe Audience Manager (AAM).
seo-title: Integre o DFP usando tags do Google Publisher (GPT) no Adobe Audience Manager (AAM)
title: Integrar o DFP usando as tags do Google Publisher (GPT)
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Integrar o DFP usando as tags do Google Publisher (GPT)

Os artigos listados abaixo fornecem uma visão geral de como integrar o DFP usando o Google Publisher Tags (GPT). Você pode usar uma integração do lado do servidor ou configurar o GPT como destino para enviar dados de segmento do Audience Manager para o DFP. Você também aprenderá as etapas necessárias para assimilar arquivos de registro DFP para relatórios no Audience Manager.

* [Requisitos e métodos de envio de segmentos para DFP usando Google Publisher Tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Você pode enviar segmentos qualificados para o DFP por meio de uma integração do lado do cliente ou do lado do servidor. Os requisitos e as informações relacionadas sobre ambos os métodos estão listados abaixo.

* [Criar um destino GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Você pode enviar segmentos qualificados para o DFP por meio de uma integração do lado do cliente (navegador) ou de uma integração do lado do servidor. Se você escolher a integração do cliente, deverá criar um destino baseado em cookies para as Tags do Google Publisher no Audience Manager.

* [Modificar a chamada da API setTargeting GPT](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Adicione uma declaração if para verificar os cookies do Audience Manager antes de chamar o método Google Publisher Tag .setTargeting.

* [Código do Audience Manager para tags do Google Publisher](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   O AamGpt é uma função JavaScript que lê os dados de cookies do Audience Manager e envia essas informações para as Tags do Google Publisher.
