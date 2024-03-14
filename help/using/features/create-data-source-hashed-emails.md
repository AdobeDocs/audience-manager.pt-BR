---
title: Configurar uma fonte de dados para fluxos de trabalho de email com hash
description: Saiba como criar uma fonte de dados para armazenar emails com hash para fluxos de trabalho de email com hash.
solution: Audience Manager
feature: Data Sources
source-git-commit: b88f180808ec9723a2a5324441733f6383f6302d
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---


# Configurar uma fonte de dados para fluxos de trabalho de email com hash

Fluxos de trabalho de email com hash, como Destinos com base em pessoas, exigem a criação de uma fonte de dados para armazenar os endereços de email com hash.

Siga as etapas abaixo para criar e configurar uma fonte de dados para emails com hash.

1. Faça logon na sua conta Audience Manager e acesse **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** e clique em **[!UICONTROL Add New]**.
1. Insira um **[!UICONTROL Name]** e **[!UICONTROL Description]** para sua nova fonte de dados.
1. No **[!UICONTROL ID Type]** selecione **[!UICONTROL Cross Device]**.
   ![Imagem da interface do Audience Manager mostrando a seção de detalhes da fonte de dados.](../features/assets/create-hashed-email-data-source.png)
1. No **[!UICONTROL Data Source Settings]** selecione a opção **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e habilite a opção **[!UICONTROL Share associated cross-device IDs in people-based destinations]** opção.
1. Use o menu suspenso para selecionar o **[!UICONTROL Emails(SHA256, lowercased)]** rótulo para esta fonte de dados.

   >[!IMPORTANT]
   >
   >Essa opção rotula apenas a fonte de dados como contendo dados com hash com esse algoritmo específico. O Audience Manager não faz o hash dos dados nesta etapa. Verifique se os endereços de email que você planeja armazenar nessa fonte de dados já estão com o hash [!DNL SHA256] algoritmo. Caso contrário, você não poderá usá-lo para workflows de email com hash.

   ![Imagem da interface do Audience Manager mostrando a seção de configurações da fonte de dados.](../features/assets/data-source-settings.png)


