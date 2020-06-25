---
description: Por volta de 14 de outubro de 2019 eu notei que minhas populações de características integradas para o gráfico de ID de dispositivo caíram para 0, onde antes eram muito maiores.
seo-description: Por volta de 14 de outubro de 2019 eu notei que minhas populações de características integradas para o gráfico de ID de dispositivo caíram para 0, onde antes eram muito maiores.
seo-title: Por que minhas populações de traços Onboard caíram para 0 por volta de 15 de outubro?
solution: Audience Manager
title: Por que minhas populações de traços Onboard caíram para 0 por volta de 15 de outubro?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---


# Por que minhas populações de traços Onboard caíram para 0 por volta de 15 de outubro? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## Pergunta

Por volta de 14 de outubro de 2019 eu notei que minhas populações de características integradas para o gráfico de ID de dispositivo caíram para 0, onde antes eram muito maiores. Por que isso aconteceu?

![Imagem do menu suspenso ID do dispositivo](assets/device_id_populationdrop.png)

## Resposta

Em 15 de outubro, uma atualização para a funcionalidade Regra de mesclagem do Perfil foi alterada para onde os dados integrados removidos de uma ID do CRM carregados em uma Fonte de Dados entre Dispositivos não estão mais sendo realizados em relação às IDs do dispositivo.  Anteriormente, o Audience Manager estava se dando conta da ID entre dispositivos (ou da ID do CRM) e copiando essas conclusões para as UUIDs de Audience Manager (IDs de dispositivo) associadas.  A alteração foi feita para refletir com mais precisão a natureza dos dados de características e os perfis que estão sendo realizados.

Para visualização das realizações de características, selecione a opção &quot;ID entre dispositivos&quot; na lista suspensa no canto superior direito da visualização de características.

![Realizações de Visualização por ID entre dispositivos](assets/deviceid-crossdevice.png)