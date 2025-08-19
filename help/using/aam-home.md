---
description: O Audience Manager proporciona serviços líderes do setor para o gerenciamento online de dados. Nossos produtos e serviços proporcionam aos anunciantes e editores as ferramentas necessárias para controlar e aproveitar seus ativos de dados com o objetivo de ajudar a aumentar o sucesso das vendas.
seo-description: Technical documentation and self help for Audience Manager (AAM). AAM provides industry-leading services for online audience data management, and give digital advertisers and publishers the tools they need to control and leverage their data assets to help drive sales success.
seo-title: Adobe Audience Manager Product Technical Documentation
solution: Audience Manager
title: Guia do Audience Manager
uuid: 48267e3b-70e6-42ae-99b1-884f4d0916be
feature: Overview
exl-id: a47bf8ba-4ec0-4b3b-ad20-4afb7c9f924b
source-git-commit: 5044a38c751abace922008f00b9ff463ea9c7e57
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 92%

---

# Guia do Audience Manager {#audience-manager-product-documentation}

Este guia de documentação técnica oferece assistência de autoajuda para o Audience Manager, um serviço líder do setor para gestão de dados de públicos online. Nossos produtos e serviços proporcionam aos anunciantes e editores as ferramentas necessárias para controlar e aproveitar seus ativos de dados com o objetivo de ajudar a aumentar o sucesso das vendas.

## Usando este guia

* Explore o conteúdo por tópico e subtópico na **navegação à esquerda**.
* Use o campo de **pesquisa** na parte superior da página se você souber o que está procurando.
* Use o botão **Log an Issue** na parte superior direita da página para sinalizar qualquer documentação incorreta ou desatualizada. Consulte a visão geral [Guia de colaboração](https://experienceleague.adobe.com/docs/contributor/contributor-guide/introduction.html?lang=pt-BR) para saber como começar a contribuir.

## Como ler esta página

* Comece explorando a seção **Funcionalidade principal do Audience manager** para obter um instantâneo dos problemas que o Audience Manager pode ajudar a resolver. Consulte também a [Visão geral do Audience Manager](/help/using/overview/aam-overview.md) e retorne a essa página.
* Em seguida, leia **Introdução ao Audience Manager** para se familiarizar com os conceitos do Audience Manager. Verifique também os guias de implementação técnica e comercial.
* Consulte as notas de versão mais recentes do Audience Manager e leia sobre os recursos mais recentes na seção **Notas de versão e recursos mais recentes**.
* Por fim, você pode explorar mais recursos da Experience Cloud, como fóruns, tutoriais em vídeo, cursos de treinamento presenciais e online na seção **Centro de aprendizado - Recursos recomendados do Audience Manager e da Experience Cloud**.

## Funcionalidade principal do Audience Manager

<table style="table-layout:fixed">
   <td>
      <img alt="Entrada de dados" src="/help/using/overview/assets/data-in.png"/>
      <div>
         <b>Importar dados</b>
      </div>
      <p>
         <em><ul><li><a href="/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md">Servidores de coleta de dados</a></li><li><a href="/help/using/integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md">Assimilação de dados em lote</a></li><li><a href="/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md">Inscrição de log</a></li><li><a href="/help/using/integration/integration-other-solutions/audience-management-module.md">Encaminhar dados do Adobe Analytics para o Audience Manager</a></li></ul></em>
      <p>
   </td>
   <td>
      <img alt="Enriquecer e segmentar" src="/help/using/overview/assets/enrich-segment.png"/>
      <div>
         <b>Enriquecer e segmentar</b>
      </div>
      <p>
       <em><ul><li><a href="/help/using/features/segments/segments-purpose.md">Segmentação</a></li><li><a href="/help/using/features/profile-merge-rules/merge-rules-overview.md">Regras de mesclagem de perfis</a></li><li><a href="/help/using/features/algorithmic-models/understanding-models.md">Modelagem algorítmica</a></li><li><a href="/help/using/overview/data-types-collected.md">Dados secundários e de terceiros</a></li></ul></em>
      <p>
   </td>
   <td>
      <img alt="Saída de dados" src="/help/using/overview/assets/data-out.png"/>
      </a>
      <div>
         <b>Exportar dados</b>
      </div>
      <p>
      <p>
         <em><ul><li><a href="/help/using/integration/receiving-audience-data/receiving-audience-data-overview.md">Exportação de dados em lote e em tempo real</a></li><li><a href="/help/using/features/destinations/destinations.md">Visão geral dos destinos</a></li><li><a href="/help/using/features/destinations/device-based-destinations-list.md">Lista de destinos de acordo com o dispositivo</a></li><li><a href="/help/using/features/destinations/people-based-destinations-overview.md">Destinos com base em pessoas</a></li></ul></em> 
      <p>
      <p>
   </td>
</table>


## Introdução ao Audience Manager

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Documentação conceitual importante</b></p>
   <p>Leia as páginas abaixo para obter uma compreensão mais profunda dos conceitos do Audience Manager: 
   <ul><li><a href="/help/using/overview/aam-overview.md"> Visão geral do Audience Manager</a></li><li><a href="/help/using/reference/signal-trait-segment.md">Sinais, características e segmentos</a></li><li><a href="/help/using/reference/aam-glossary.md"> Glossário</a> </li><li><a href="/help/using/reference/ids-in-aam.md">Índice de IDs</a></li></ul></p>

<p><b>Implementar o Audience Manager</b></p>
   <p> Comece a implementar o Audience Manager lendo as páginas abaixo:
     <ul>
     <li><a href="/help/using/integration/data-integration-methods.md">Métodos de integração de dados</a></li>
     <li><a href="/help/using/integration/implement-audience-manager.md">Guia de implementação</a></li>
     </ul> </p>

<p> <b>Guias de implementação técnica</b> </p> <p>Comece com as APIs do Audience Manager e configure o Audience Manager no seu aplicativo:</p> <p> 
     <ul id="ul_47C012F6AB3E4B73BA357027F4D15369">
     <li><a href="/help/using/api/rest-api-main/aam-api-getting-started.md">Introdução às REST APIs</a></li>
     <li><a href="/help/using/api/dcs-intro/dcs-event-calls/dcs-event-calls.md">Introdução à DCS API</a></li>
     <li><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html?lang=pt-BR">Adicionar a extensão do Audience Manager em Tags do Adobe Experience Platform</a></li>
    <li><a href="https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/data-management/aam-dil-extension.html?lang=pt-BR">Adicionar o Audience Manager ao seu aplicativo</a></li>
     </ul> </p>
    </td>

</tr> 
 </tbody> 
</table>

<!--

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Important Conceptual Documentation</b></p>
   <p>Read the pages below for a deeper understanding of Audience Manager concepts: 
   <ul><li><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/aam-overview.html?lang=pt-BR"> Audience Manager Overview</a></li><li><a href="https://docs.adobe.com/help/en/audience-manager/user-guide/reference/aam-glossary.html"> Glossary</a> </li><li><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/ids-in-aam.html?lang=pt-BR">Index of IDs</a></li><li><a href="https://docs.adobe.com/help/en/audience-manager/user-guide/reference/signal-trait-segment.html">Signals, Traits, and Segments</a></li></ul></p>
   <br>&nbsp;
   <p><b>Implement Audience Manager</b></p>
   <p> Get started with implementing Audience Manager by reading the pages below:
     <ul>
     <li><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/data-integration-methods.html?lang=pt-BR">Data Integration Methods</a></li>
     <li><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/implement-audience-manager.html?lang=pt-BR">Implementation Guide</a></li>
     </ul> </p>
     <br>&nbsp;
   <p> <b>Technical Implementation Guides</b> </p> <p>Get started with Audience Manager APIs and set up Audience Manager in your app:</p> <p> 
     <ul id="ul_47C012F6AB3E4B73BA357027F4D15369">
     <li><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/rest-apis/aam-api-getting-started.html?lang=pt-BR">Getting Started with REST APIs</a></li>
     <li><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-event-calls/dcs-event-calls.html?lang=pt-BR">Get started with the DCS API</a></li>
     <li><a href="https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html?lang=pt-BR">Add the Audience Manager extension to Adobe Experience Platform Launch</a></li>
    <li><a href="https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/data-management/aam-dil-extension.html?lang=pt-BR">Add Audience Manager to your app</a></li>
     </ul> </p>
    </td>
   <td colname="col2">  <p> <b>Collaborative Documentation</b> </p>
     <p>We welcome contributions to our documentation from all our readers. See the <a href="https://experienceleague.adobe.com/docs/contributor/contributor-guide/introduction.html?lang=pt-BR">Collaboration Guide Overview</a> to learn how to start contributing.</p>
   <br>&nbsp;
   <p> <b>Release Notes</b> </p> <p> 
     See the latest <a href="https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR" format="https" scope="external"> Experience Cloud Release Notes</a> for new features and fixes.</p> <br>&nbsp;
     <p> <b>Experience Cloud Resources</b> </p> <p> 
     <ul id="ul_E30EC96BDC624B5591F0470D430B7F41"> 
      <li id="li_F3A5CCFAE0F247CEB41A03CA8E03106B"><a href="https://forums.adobe.com/community/experience-cloud/analytics-cloud/audience-manager" format="https" scope="external"> Audience Manager Community Forums</a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/overview.html?lang=pt-BR" format="http" scope="external"> Audience Manager Tutorials</a> </li> 
      <li id="li_1737D63307024F26B1F967621613A5AC"><a href="https://www.adobe.com/privacy.html" format="http" scope="external"> Adobe Privacy Center</a> </li>  
      <li id="li_1938F7044F544481A6CC0F45CC22B80A"> <a href="https://helpx.adobe.com/br/learning.html?promoid=KAUDK" scope="external" format="http"> Adobe Training and Certifications</a> </li> 
      <li id="li_C71459E0D1464C05B8B9387C43541F17"> <a href="https://helpx.adobe.com/br/support/experience-cloud.html" scope="external" format="https">Experience Cloud Product Documentation Home</a> </li> 
      <li id="li_0DB1997FEB87484EBC07E03FD40AA39F"><a href="https://helpx.adobe.com/br/support/audience-manager.html" format="https" scope="external"> Audience Manager Learn &amp; Support</a> </li> 
     </ul> </p> 
     <br>&nbsp;
     <p>See also, <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/documentation-updates/docs-2020.html?lang=pt-BR"> 2020 Documentation Updates</a>. </p> </td>
  </tr> 
 </tbody> 
</table>

-->

## Notas de versão e recursos mais recentes

<table> 
 <tbody> 
  <tr> 
   <td> <p> <b>Notas de versão</b> </p> <p> 
     Consulte as <a href="https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR" format="https" scope="external">Notas de versão da Experience Cloud</a> para obter novos recursos e correções.</p> 
     <p> <b>Recursos mais recentes</b> </p> <p> 
     Leia sobre os recursos mais recentes do Audience Manager:</p>
     <p><ul><li><a href="/help/using/docs-updates/docs-2021.md">Migração de usuário do Audience Manager para o Admin Console</a></li><li><a href="/help/using/features/destinations/people-based-destinations-prerequisites.md">Correspondência de cliente do Google para destinos com base em pessoas</a></li><li><a href="/help/using/overview/data-security-and-privacy/aam-iab-plugin.md">Plug-in do Audience Manager para TCF do IAB v2.2</a></li><li><a href="/help/using/features/algorithmic-models/predictive-audiences.md">Públicos preditivos</a></li><li><a href="/help/using/features/administration/activity-usage-reporting.md">Relatórios de uso de atividade</a></li>
     </ul></p>
    </td>
  </tr> 
 </tbody> 
</table>

<!--

**Release Notes**

See the latest [Experience Cloud Release Notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR) for new features and fixes.

<br>&nbsp;

**Latest features**

Read about the latest Audience Manager features:
* [Activity Usage Reporting](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/activity-usage-reporting.html?lang=pt-BR)
* [California Consumer Privacy Act (CCPA) Support and Privacy Documentation Overhaul](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html?lang=pt-BR)
* [Intelligent Recommendations for Audience Marketplace Data, powered by Adobe Sensei](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/trait-recommendations.html?lang=pt-BR)
* [Profile Merge Rules Enhancements](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/profile-merge-rules/merge-rules-overview.html?lang=pt-BR)
* [Bulk Management Tools Update](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/bulk-management-tools/bulk-management-intro.html?lang=pt-BR)

-->


## Centro de aprendizado - Recursos recomendados do Audience Manager e da Experience Cloud


<table> 
 <tbody> 
  <tr> 
   <td colname="col2"> 
     <p> <b>Recursos da Experience Cloud</b> </p>
     <p>Acesse os links abaixo para conectar-se com outros clientes do Audience Manager nos fóruns da comunidade, assistir a tutoriais em vídeo dos nossos recursos ou solucionar problemas no centro de aprendizado e suporte.</p>
     <p> 
     <ul id="ul_E30EC96BDC624B5591F0470D430B7F41"> 
      <li id="li_F3A5CCFAE0F247CEB41A03CA8E03106B"><a href="https://forums.adobe.com/community/experience-cloud/analytics-cloud/audience-manager" format="https" scope="external"> Fóruns da comunidade do Audience Manager</a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/overview.html?lang=pt-BR" format="http" scope="external"> Tutoriais do Audience Manager</a> </li> 
      <li id="li_1737D63307024F26B1F967621613A5AC"><a href="https://www.adobe.com/br/privacy.html" format="http" scope="external"> Centro de privacidade da Adobe</a> </li>  
      <li id="li_1938F7044F544481A6CC0F45CC22B80A"> <a href="https://helpx.adobe.com/br/learning.html?promoid=KAUDK" scope="external" format="http"> Treinamento e certificações da Adobe</a> </li> 
      <li id="li_C71459E0D1464C05B8B9387C43541F17"> <a href="https://helpx.adobe.com/pt/support/experience-cloud.html" scope="external" format="https">Página inicial de documentação do produto da Experience Cloud</a> </li> 
      <li id="li_0DB1997FEB87484EBC07E03FD40AA39F"><a href="https://helpx.adobe.com/br/support/audience-manager.html" format="https" scope="external"> Aprendizagem e suporte do Audience Manager</a> </li> 
     </ul> </p> 
     <p>Consulte também, <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/documentation-updates/docs-2021.html?lang=pt-BR"> Atualizações da documentação de 2021</a>. </p> </td>
  </tr> 
 </tbody> 
</table>
