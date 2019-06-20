---
description: Este artigo descreve dois recursos que fornecem funcionalidade avançada para o Modelo de alocação duplicada do Audience Lab e o Segmento Holdout.
seo-description: Este artigo descreve dois recursos que fornecem funcionalidade avançada para o Modelo de alocação duplicada do Audience Lab e o Segmento Holdout.
seo-title: Funcionalidade avançada do Audience Lab
solution: Audience Manager
title: Funcionalidade avançada do Audience Lab
uuid: 0 f 57 d 634-caa 0-40 da -81 a 2-c 23 fbd 299 bfd
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# [!DNL Audience Lab] Funcionalidade avançada {#audience-lab-advanced-functionality}

This article describes two features which provide advanced functionality for [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] and [!DNL Segment Holdout].

## Duplicate Allocation Template {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

In [!DNL Audience Lab], the [!DNL Allocation Template] represents the various selections you make when creating a test group:

* A distribuição de dispositivos entre segmentos de teste;
* O mapeamento de segmentos de teste para destinos;
* As características de conversão usadas para um grupo de teste;
* O intervalo de datas no qual o grupo de teste publica para os destinos selecionados.

Ao duplicar um modelo de alocação, você pode reutilizar a mesma distribuição de segmentos de teste e destinos para um segmento base diferente, em um novo grupo de teste. Um exemplo de um modelo de alocação é ilustrado abaixo. The image is taken from the [!UICONTROL Summary & Finalize] step in the **Create Test Group** workflow.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Usar modelo de alocação duplicado

Create an initial test group, then select **[!UICONTROL Duplicate Allocation Template]** to reuse the same settings across multiple test groups. Por exemplo, você pode usar esse recurso se estiver executando um teste em que deseja determinar a eficácia de vários destinos para vários segmentos.

1. Na exibição principal do Audience Lab, pesquise pelo grupo de teste cujo modelo de alocação você deseja reproduzir em um novo grupo de teste. In the drop-down box, select **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. In the [!UICONTROL Create Test Group] wizard, you can specify a base segment and rename your test segments, if you wish.
3. You *cannot* modify:

   * A distribuição de dispositivos entre segmentos de teste;
   * As características de conversão;
   * O mapeamento de segmentos de teste para destinos. Você só pode preencher a tecla de mapeamento para os destinos que exigem uma.
   * O intervalo de datas no qual seu grupo de teste será publicado nos destinos selecionados.

4. Review the information you added in the previous steps and select **[!UICONTROL Finalize Group]**.

## Test Segment Holdout {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] é uma funcionalidade avançada, ativada na solicitação do cliente. Please contact [!DNL Customer Care] or [!DNL Adobe Consulting] to activate this feature.

Use este recurso para impedir que parte do público-alvo seja incluída no teste. A porcentagem selecionada é deixada fora do teste. Dessa forma, você pode medir e comparar o número de conversões de públicos-alvo direcionados (ativados em destinos) e públicos-alvo sem nome (holdout).

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Usando o segmento de teste Holdout

1. Create a new test group by using the [!UICONTROL Create Test Group] wizard.
1. In the **[!UICONTROL Allocate Test Segment]** step, you can select a part of the audience to be withheld from testing.

   ![Item de lista](assets/test-segment-holdout.png)

1. Use o controle deslizante para ajustar quantos dispositivos você deseja excluir do teste. Observe como o Teste do segmento 1 e o Segmento de teste 2 agora só obtêm 70% do total de dispositivos.

   ![](assets/test-segment-holdout-selected.png)

1. Go through the rest of the steps in the **[!UICONTROL Create Test Group]** workflow and select **[!UICONTROL Finalize Group]** when you&#39;re satisfied with your selection. Agora, você tem um grupo de teste com parte do público-alvo negado ao teste.
