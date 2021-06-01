---
description: Este artigo descreve dois recursos que fornecem funcionalidade avançada para o Modelo de alocação de duplicata do Audience Lab e Retenção de segmento.
seo-description: Este artigo descreve dois recursos que fornecem funcionalidade avançada para o Modelo de alocação de duplicata do Audience Lab e Retenção de segmento.
seo-title: Funcionalidade avançada do Audience Lab
solution: Audience Manager
title: Funcionalidade avançada do Audience Lab
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
feature: 'Audience Lab '
exl-id: 40b2c8c2-63c0-485d-8217-beab34d7a7f1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 2%

---

# [!DNL Audience Lab] Funcionalidade avançada  {#audience-lab-advanced-functionality}

Este artigo descreve dois recursos que fornecem funcionalidade avançada para [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] e [!DNL Segment Holdout].

## Duplicar Modelo de Alocação {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

Em [!DNL Audience Lab], [!DNL Allocation Template] representa as várias seleções feitas ao criar um grupo de teste:

* A distribuição de dispositivos entre segmentos de ensaio;
* O mapeamento dos segmentos de teste para destinos;
* As características de conversão usadas para um grupo de teste;
* O intervalo de datas no qual o grupo de teste é publicado para os destinos selecionados.

Ao duplicar um modelo de alocação, é possível reutilizar a mesma distribuição de segmentos de teste e destinos para um segmento base diferente, em um novo grupo de teste. Um exemplo de um template de alocação é ilustrado abaixo. A imagem é tirada da etapa [!UICONTROL Summary & Finalize] no fluxo de trabalho **Criar grupo de teste** .

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Usando modelo de alocação duplicado

Crie um grupo de teste inicial e selecione **[!UICONTROL Duplicate Allocation Template]** para reutilizar as mesmas configurações em vários grupos de teste. Por exemplo, você pode usar esse recurso se estiver executando um teste no qual deseja determinar a eficácia de vários destinos para vários segmentos.

1. Na exibição principal do Audience Lab, pesquise pelo grupo de teste cujo modelo de alocação você deseja reproduzir em um novo grupo de teste. Na caixa suspensa , selecione **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. No assistente [!UICONTROL Create Test Group], você pode especificar um segmento base e renomear os segmentos de teste, se desejar.
3. Você *não pode* modificar:

   * A distribuição de dispositivos entre segmentos de ensaio;
   * A(s) característica(s) de conversão;
   * O mapeamento de segmentos de teste para destinos. Você só pode preencher a chave de mapeamento para os destinos que exigem uma.
   * O intervalo de datas no qual o grupo de teste será publicado nos destinos selecionados.

4. Revise as informações adicionadas nas etapas anteriores e selecione **[!UICONTROL Finalize Group]**.

## Testar Retenção de Segmento {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] O é uma funcionalidade avançada, ativada mediante solicitação do cliente. Entre em contato com [!DNL Customer Care] ou [!DNL Adobe Consulting] para ativar esse recurso.

Use esse recurso para impedir que parte do público-alvo seja incluído no teste. A porcentagem selecionada fica fora do teste. Dessa forma, você pode medir e comparar o número de conversões de públicos-alvo direcionados (ativados em destinos) e não direcionados (grupo de espera).

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Uso da Retenção de segmento de teste

1. Crie um novo grupo de teste usando o assistente [!UICONTROL Create Test Group].
1. Na etapa **[!UICONTROL Allocate Test Segment]**, você pode selecionar uma parte do público-alvo a ser retido nos testes.

   ![Listar item](assets/test-segment-holdout.png)

1. Use o controle deslizante para ajustar quantos dispositivos você deseja excluir dos testes. Observe como o Segmento de teste 1 e o Segmento de teste 2 agora realizam apenas 70% do total de dispositivos.

   ![](assets/test-segment-holdout-selected.png)

1. Percorra o restante das etapas no workflow **[!UICONTROL Create Test Group]** e selecione **[!UICONTROL Finalize Group]** quando estiver satisfeito com sua seleção. Agora você tem um grupo de teste com parte do público-alvo retido nos testes.
