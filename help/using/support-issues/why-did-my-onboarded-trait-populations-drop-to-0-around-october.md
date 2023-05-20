---
description: Por volta de 14 de outubro de 2019, notei que minhas populações de características integradas do gráfico de ID de dispositivo caíram para 0, mas antes elas eram muito maiores.
seo-description: Around October 14th, 2019 I noticed that my onboarded trait populations for the Device ID graph have dropped to 0, where previously they were much higher.
seo-title: Why did my Onboarded trait populations drop to 0 around October 15th?
solution: Audience Manager
title: Por que minhas populações de características integradas caíram para 0 por volta de 15 de outubro?
feature: Support
exl-id: e93cee15-7d05-4f81-8f14-a3e03f214542
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 100%

---

# Por que minhas populações de características integradas caíram para 0 por volta de 15 de outubro? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## Pergunta

Por volta de 14 de outubro de 2019, notei que minhas populações de características integradas do gráfico de ID de dispositivo caíram para 0, mas antes elas eram muito maiores. Por que isso aconteceu?

![Imagem do menu suspenso ID de dispositivo](assets/device_id_populationdrop.png)

## Resposta

Em 15 de outubro, uma atualização da funcionalidade da Regra de mesclagem de perfis do Audience Manager foi alterada para onde os dados integrados digitados de um ID de CRM carregado em uma fonte de dados entre dispositivos não estão mais sendo realizados com relação aos IDs de dispositivo.  Anteriormente, o Audience Manager realizava a ID entre dispositivos (ou a ID do CRM) e copiava essas realizações nos UUIDs do Audience Manager (IDs do dispositivo) associados.  A alteração foi feita para refletir com mais precisão a natureza dos dados de características e os perfis que estão sendo realizados.

Para visualizar as realizações de características, selecione a opção &quot;Cross-Device ID&quot; na lista suspensa no canto superior direito da visualização de características.

![Visualizar realizações por ID entre dispositivos](assets/deviceid-crossdevice.png)
