---
description: Por volta de 14 de outubro de 2019 eu notei que minhas populações de características integradas para o gráfico de ID de dispositivo caíram para 0, onde antes eram muito maiores.
seo-description: Por volta de 14 de outubro de 2019 eu notei que minhas populações de características integradas para o gráfico de ID de dispositivo caíram para 0, onde antes eram muito maiores.
seo-title: Por que minhas populações de traços Onboard caíram para 0 por volta de 15 de outubro?
solution: Audience Manager
title: Por que minhas populações de traços Onboard caíram para 0 por volta de 15 de outubro?
translation-type: tm+mt
source-git-commit: 0487a15c5fcd0e653bedf0e7fd8326f5cc363660

---


# Por que minhas populações de traços Onboard caíram para 0 por volta de 15 de outubro? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## Pergunta

Por volta de 14 de outubro de 2019 eu notei que minhas populações de características integradas para o gráfico de ID de dispositivo caíram para 0, onde antes eram muito maiores. Por que isso aconteceu?

![Imagem do menu suspenso ID do dispositivo](assets/device_id_populationdrop.png)

## Resposta

Em 15 de outubro, uma atualização da funcionalidade Regra de mesclagem de Perfis do Gerenciador de Audiências foi alterada para onde os dados integrados de uma ID de CRM carregados em uma Fonte de Dados entre Dispositivos não estão mais sendo realizados em relação às IDs de dispositivos.  Anteriormente, o Gerenciador de Audiências se apercebia da ID entre dispositivos (ou da ID do CRM), bem como copiava essas conclusões para os UUIDs do Gerenciador de Audiências associados (IDs de dispositivo).  A alteração foi feita para refletir com mais precisão a natureza dos dados de características e os perfis que estão sendo realizados.

Para visualização das realizações de características, selecione a opção &quot;ID entre dispositivos&quot; na lista suspensa no canto superior direito da visualização de características.

![Realizações de Visualização por ID entre dispositivos](assets/deviceid-crossdevice.png)