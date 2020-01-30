---
description: Por volta de 14 de outubro de 2019 eu notei que minhas populações de características integradas para o gráfico de ID de dispositivo caíram para 0, onde antes eram muito maiores.
seo-description: Por volta de 14 de outubro de 2019 eu notei que minhas populações de características integradas para o gráfico de ID de dispositivo caíram para 0, onde antes eram muito maiores.
seo-title: Por que minhas populações de traços Onboard caíram para 0 por volta de 15 de outubro?
solution: Audience Manager
title: Por que minhas populações de traços Onboard caíram para 0 por volta de 15 de outubro?
translation-type: tm+mt
source-git-commit: eb129bbf642cb666ce3ea05ff606c051e02f4d1e

---


# Por que minhas populações de traços Onboard caíram para 0 por volta de 15 de outubro? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

Por volta de 14 de outubro de 2019 eu notei que minhas populações de características integradas para o gráfico de ID de dispositivo caíram para 0, onde antes eram muito maiores.

![Imagem do menu suspenso ID do dispositivo](/help/using/support-issues/assets/device_id_populationdrop.png)

**Resposta**

Em 15 de outubro, uma atualização da funcionalidade Regra de mesclagem de perfis do Audience Manager foi alterada para onde os dados integrados removidos de uma ID CRM carregada em uma Fonte de dados entre dispositivos não estão mais sendo realizados em relação às IDs de dispositivos.  Anteriormente, o Audience Manager era detectado em relação à ID de dispositivo cruzado (ou ID de CRM), bem como copiando essas execuções para UUIDs do Audience Manager associadas (IDs de dispositivo).  A alteração foi feita para refletir com mais precisão a natureza dos dados de características e os perfis que estão sendo realizados.

Para exibir as realizações de características, selecione a opção &quot;ID entre dispositivos&quot; na lista suspensa no canto superior direito da exibição Características.

![Exibir Realizações por ID entre dispositivos](/help/using/support-issues/assets/deviceid-crossdevice.png)

