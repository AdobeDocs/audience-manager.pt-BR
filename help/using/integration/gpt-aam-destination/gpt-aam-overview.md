---
description: Visão geral de como integrar DFP usando Tags do Google Publisher (GPT).
seo-description: Visão geral de como integrar DFP usando Tags do Google Publisher (GPT) no Adobe Audience Manager (AAM).
seo-title: Integrar DFP usando Tags do Google Publisher (GPT) no Adobe Audience Manager (AAM)
title: Integrar DFP usando Tags do Google Publisher (GPT)
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Integrar DFP usando Tags do Google Publisher (GPT)

Os artigos listados abaixo fornecem uma visão geral de como integrar o DFP usando Tags do Google Publisher (GPT). Você pode usar uma integração com o servidor ou configurar o GPT como destino para enviar dados de segmento do Audience Manager para DFP. Você também aprenderá as etapas necessárias para assimilar arquivos de log DFP para relatórios no Audience Manager.

* [Requisitos e métodos de envio de segmentos para DFP usando Google Publisher Tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   É possível enviar segmentos qualificados para DFP por meio de um cliente ou por meio de uma integração com o servidor. Os requisitos e informações relacionadas sobre os dois métodos estão listados abaixo.

* [Criar um destino GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Você pode enviar segmentos qualificados para DFP por meio de uma integração do lado do cliente (no navegador) ou uma integração do servidor. Se você escolher a integração do cliente, deverá criar um destino baseado em cookies para Tags do Google Publisher no Audience Manager.

* [Modificar a chamada da API de definição de metas do GPT](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Adicione uma declaração if para verificar os cookies do Audience Manager antes de chamar o método Tag Er Tag. settargeting.

* [Código do Audience Manager para tags do Editor do Google](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   Aamgpt é uma função javascript que lê os dados do cookie do Audience Manager e envia essas informações para as Tags do Google Publisher.
