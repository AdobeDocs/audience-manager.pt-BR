---
title: Configurar uma fonte de dados para fluxos de trabalho de email com hash
description: Saiba como criar uma fonte de dados para armazenar emails com hash para fluxos de trabalho de email com hash.
solution: Audience Manager
feature: Data Sources
exl-id: fb235dcb-e02f-41ac-ba3f-a1feb30b23dd
TQID: 'https://experienceleague.adobe.com/dPV7bJC5zIBkj1EX43q4FWU7XP0gs-dhBYTcW8mApL4'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: c814092e-2730-45e8-a12d-e084529f52cb
    internal-label: Destinations
  - id: d8f86c1e-15ad-457f-9d6f-5e756573fad4
    internal-label: Audience Marketplace
subfeature_v2:
  - id: d921db59-bd4a-43dc-97e6-4ff4611f1ae8
    internal-label: Data sources
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 0%
---
# Configurar uma fonte de dados para fluxos de trabalho de email com hash

Fluxos de trabalho de email com hash, como Destinos com base em pessoas, exigem a criação de uma fonte de dados para armazenar os endereços de email com hash.

Siga as etapas abaixo para criar e configurar uma fonte de dados para emails com hash.

1. Faça logon em sua conta da Audience Manager, vá para **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** e clique em **[!UICONTROL Add New]**.
1. Insira um **[!UICONTROL Name]** e **[!UICONTROL Description]** para sua nova fonte de dados.
1. No menu suspenso **[!UICONTROL ID Type]**, selecione **[!UICONTROL Cross Device]**.
   ![Imagem da interface do Audience Manager mostrando a seção de detalhes da fonte de dados.](../features/assets/create-hashed-email-data-source.png)
1. Na seção **[!UICONTROL Data Source Settings]**, selecione as opções **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e habilite a opção **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Use o menu suspenso para selecionar o rótulo **[!UICONTROL Emails(SHA256, lowercased)]** para esta fonte de dados.

   >[!IMPORTANT]
   >
   >Essa opção rotula apenas a fonte de dados como contendo dados com hash com esse algoritmo específico. A Audience Manager não faz o hash dos dados nesta etapa. Verifique se os endereços de email que você planeja armazenar nesta fonte de dados já foram atribuídos a hash com o algoritmo [!DNL SHA256]. Caso contrário, você não poderá usá-lo para workflows de email com hash.

   ![Imagem da interface do Audience Manager mostrando a seção de configurações da fonte de dados.](../features/assets/data-source-settings.png)
