---
description: Exiba uma lista das fontes de dados configuradas atualmente, adicione novas fontes de dados e edite as fontes existentes.
seo-description: Exiba uma lista das fontes de dados configuradas atualmente, adicione novas fontes de dados e edite as fontes existentes.
seo-title: Lista e configurações de fontes de dados
solution: Audience Manager
title: Lista e configurações de fontes de dados
uuid: 280 a 6 acd-fef 0-4737-a 96 d -9 e 22 fbc 8 bfaf
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Data Sources List and Settings {#data-sources-list-and-settings}

Exiba uma lista das fontes de dados configuradas atualmente, adicione novas fontes de dados e edite as fontes existentes.

<!-- c_datasources.xml -->

You can also manage data sources using [!DNL API] methods. For more information, see [Data Source API Methods](../api/rest-api-main/aam-api-data-sources.md).

## Data Sources List View {#list-view}

The [!UICONTROL Data Sources] dashboard is a centralized workspace for managing data sources.

<!-- c_datasources_list.xml -->

The [!UICONTROL Data Sources] dashboard (**[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**) contains features and tools that help you:

* See all your existing data sources, including each data source&#39;s description, status, and whether it is [!UICONTROL Inbound], [!UICONTROL Outbound], both, or a [!UICONTROL Shared Provider].
* Pesquise por fontes de dados por nome.
* Crie, edite e exclua fontes de dados.

## Data Source Settings and Menu Options {#settings-menu-options}

The settings in the different sections of the [!UICONTROL Data Source] management interface identify your data source, determine how it is used or shared, and let you enable error reporting for the [!UICONTROL Onboarding Status Report].

## Data Source Details {#details}

<!-- datasource-settings-definitions.xml -->

In addition to text fields, the [!UICONTROL Data Source Details] section contains the controls and options listed below.

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuração </th> 
   <th colname="col2" class="entry"> Opções do menu </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tipo de ID</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: A ID do cookie que identifica um dispositivo. Você pode selecionar isso quando sua fonte de dados é um navegador da Web ou ao trabalhar com dados anônimos ou dados que não podem ser associados a uma única pessoa. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID de publicidade do dispositivo</span></b>: O identificador do dispositivo móvel. Selecione isso quando sua fonte de dados for um dispositivo móvel ou dispositivo habilitado para Internet. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Dispositivo</span></b>cruzado: Uma ID autenticada pelo cliente. Selecione esta opção quando quiser criar: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">A cross-device data source and build a <span class="wintitle"> Profile Merge Rule</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">A data source that uses links provided by the <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> or another, third-party device graph that is integrated with <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Definição da ID</span></b> </p> </td> 
   <td colname="col2"> <p>The <b><span class="uicontrol"> ID Definition</span></b> options define the relationship a data source has to an <span class="keyword"> Audience Manager</span> user ID (UUID) and associated devices linked by the <span class="keyword"> Adobe Experience Cloud Device Co-op</span> or another, third-party device graph that is integrated with <span class="keyword"> Audience Manager</span>. As opções incluem: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Pessoa:</span></b> A ID usada para definir uma única pessoa. This ID can be mapped to multiple <span class="keyword"> Audience Manager</span> IDs. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Família:</span></b> A ID usada para definir um grupo de pessoas. Essa ID pode ser mapeada para várias IDs do Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Controles da exportação de dados {#export-controls}

[Os controles de exportação de dados](../features/data-export-controls.md) são regras de classificação opcionais que podem ser aplicadas a uma fonte de dados e destino. Eles impedem que você envie dados para um destino quando essa ação violar a privacidade de dados ou usar o contrato. Skip this section if you do not use [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>As restrições de exportação não funcionarão a menos que você defina uma etiqueta de exportação correspondente em um destino.

As opções incluem:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Data Source Settings {#data-source-settings}

The [!UICONTROL Data Source Settings] contains the controls and options listed below. Algumas dessas configurações possuem subopções e itens de menu adicionais que você pode selecionar para modificar uma fonte de dados.

### Configurações de fonte de dados de entrada

Select the **[!UICONTROL Inbound]** check box when your data source is designed to receive inbound data. Selecting the **[!UICONTROL Inbound]** check box exposes 2 additional groups of controls described below.

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuração </th> 
   <th colname="col2" class="entry"> Opções do menu </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tipo de ID</span></b> </p> </td> 
   <td colname="col2"> <p>The <b><span class="uicontrol"> Inbound</span></b> option requires an ID type. As opções incluem: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID do cliente</span></b>: Identifica dados de entrada com uma ID do cliente. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID do Audience Manager</span></b>: Identifica dados de entrada com uma <span class="keyword"> ID do Audience Manager</span> . </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: Identifica dados de entrada com uma <span class="keyword"> Experience Cloud</span> ID. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Resolução de problemas de formato de arquivo</span></b> </p> </td> 
   <td colname="col2"> <p>Select <b><span class="uicontrol"> Enable file error sampling</span></b> when you need to troubleshoot problems with inbound file processing. Esse recurso gera um relatório de exemplo que mostra o formato de arquivo e os erros de sintaxe. </p> <p>See <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Onboarding Status Report: About</a> for information about error reporting and error sampling. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Outras configurações de fonte de dados

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuração </th> 
   <th colname="col2" class="entry"> Selecione quando </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Saída</span></b> </p> </td> 
   <td colname="col2"> <p>Sua fonte de dados envia dados para um destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartilhamento ativado</span></b> </p> </td> 
   <td colname="col2"> <p>Sua fonte de dados pode ser compartilhada com outros parceiros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Usar como perfil autenticado</span></b> </p> </td> 
   <td colname="col2"> <p>Sua fonte de dados entre dispositivos contém uma ID autenticada. An Authenticated ID is collected and synced to an <span class="keyword"> Audience Manager</span> ID during an authentication event (e.g, a user logs in on-site, in-app, etc.). A ID autenticada pode ser usada para dados no quadro de outras fontes que armazenam essa ID. It can also be used to link multiple device IDs in <span class="wintitle"> Profile Link</span>. </p> <p>Essa opção expõe um campo de texto que permite renomear a fonte de dados com um alias. If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Authenticated Profile Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Usar como um Gráfico de dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Creates a data source as a device graph which you can provide to other <span class="keyword"> Audience Manager</span> customers. Before you select this option, tell with your <span class="keyword"> Audience Manager</span> consultant which customers this <span class="wintitle"> Data Source</span> should be shared with. Seu consultor terá que provisionar essas empresas por meio de nossos processos internos. </p> <p>Essa opção expõe um campo de texto que permite renomear a fonte de dados com um alias. If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Device Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartilhar IDs de visitante ou de dispositivo associadas com clientes do Audience Manager específicos</span></b> </p> </td> 
   <td colname="col2"> <p>Sua fonte de dados entre dispositivos contém IDs de um gráfico de dispositivo. A device graph is a collection of IDs which map to one or more <span class="keyword"> Audience Manager</span> IDs to a cluster. Esse cluster geralmente representa uma pessoa ou um grupo maior, doméstico. Disponível apenas para contas listadas como um "Provedor de dados". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartilhar IDs de visitante ou de dispositivo associadas na plataforma do Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>Your data source contains visitor or device IDs that can be shared across other <span class="keyword"> Experience Cloud</span> solutions. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Retenção de dados para IDs inativas do cliente</span></b> </p> </td> 
   <td colname="col2"> <p>Permite definir o período de retenção de dados para IDs inativas do cliente. Isso determina quanto tempo o Audience Manager mantém as IDs do cliente em nosso banco de dados depois que elas foram vistas pela última vez na plataforma do Audience Manager.</p> <p>O valor padrão é de 24 meses (720 dias). O valor mínimo que pode ser definido é de 1 mês e o valor máximo é de 5 anos. Observe que contamos todos os meses como 30 dias.</p> <p>O Audience Manager executa um processo que exclui IDs inativas do cliente uma vez por semana, de acordo com a retenção de dados definida para IDs inativas do cliente.</p> <p>O Audience Manager executa um processo que exclui IDs inativas do cliente uma vez por semana, de acordo com a retenção de dados definida para IDs inativas do cliente.</p> <p><b>Observação</b>: Esse controle está disponível apenas para fontes de dados entre dispositivos. See also, <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Códigos de integração de característica exclusiva</span></b> </p> </td> 
   <td colname="col2"> <p>Você quiser impor que duas características da mesma fonte de dados não tenham o mesmo código de integração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Códigos de integração de segmento exclusivos</span></b> </p> </td> 
   <td colname="col2"> <p>Você quiser aplicar que dois segmentos da mesma fonte de dados não tenham o mesmo código de integração. </p> </td> 
  </tr>
 </tbody>
</table>
