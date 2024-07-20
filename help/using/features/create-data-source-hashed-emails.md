---
title: Configurar uma fonte de dados para fluxos de trabalho de email com hash
description: Saiba como criar uma fonte de dados para armazenar emails com hash para fluxos de trabalho de email com hash.
solution: Audience Manager
feature: Data Sources
exl-id: fb235dcb-e02f-41ac-ba3f-a1feb30b23dd
source-git-commit: d55dbc4f9630e3d22dfb988f6725f33993229c48
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Configurar uma fonte de dados para fluxos de trabalho de email com hash

Fluxos de trabalho de email com hash, como Destinos com base em pessoas, exigem a criação de uma fonte de dados para armazenar os endereços de email com hash.

Siga as etapas abaixo para criar e configurar uma fonte de dados para emails com hash.

1. Faça logon em sua conta do Audience Manager, vá para **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** e clique em **[!UICONTROL Add New]**.
1. Insira um **[!UICONTROL Name]** e **[!UICONTROL Description]** para sua nova fonte de dados.
1. No menu suspenso **[!UICONTROL ID Type]**, selecione **[!UICONTROL Cross Device]**.
   ![imagem da interface do usuário do Audience Manager mostrando a seção de detalhes da fonte de dados.](../features/assets/create-hashed-email-data-source.png)
1. Na seção **[!UICONTROL Data Source Settings]**, selecione as opções **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e habilite a opção **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Use o menu suspenso para selecionar o rótulo **[!UICONTROL Emails(SHA256, lowercased)]** para esta fonte de dados.

   >[!IMPORTANT]
   >
   >Essa opção rotula apenas a fonte de dados como contendo dados com hash com esse algoritmo específico. O Audience Manager não faz o hash dos dados nesta etapa. Verifique se os endereços de email que você planeja armazenar nesta fonte de dados já foram atribuídos a hash com o algoritmo [!DNL SHA256]. Caso contrário, você não poderá usá-lo para workflows de email com hash.

   ![Imagem da interface do Audience Manager mostrando a seção de configurações da fonte de dados.](../features/assets/data-source-settings.png)
