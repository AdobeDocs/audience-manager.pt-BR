---
description: Exiba uma lista das fontes de dados configuradas no momento, adicione novas fontes de dados e edite as fontes existentes.
seo-description: View a list of your currently configured data sources, add new data sources, and edit existing sources.
seo-title: Data Sources List and Settings
solution: Audience Manager
title: Lista e configurações de fontes de dados
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 0%

---

# Lista e configurações de [!UICONTROL Data Sources] {#data-sources-list-and-settings}

Exiba uma lista do [!UICONTROL data sources] configurado no momento, adicione um novo [!UICONTROL data sources] e edite o [!UICONTROL data sources] existente.

Você também pode gerenciar [!UICONTROL data sources] usando métodos [!DNL API]. Para obter mais informações, consulte [Métodos da API do Data Source](../api/rest-api-main/aam-api-data-sources.md).

## Exibição em lista de [!UICONTROL Data Sources] {#list-view}

O painel [!UICONTROL Data Sources] é um espaço de trabalho centralizado para gerenciamento de fontes de dados.

O painel [!UICONTROL Data Sources] (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) contém recursos e ferramentas que ajudam a:

* Veja todos os [!UICONTROL data sources] existentes, incluindo a descrição, o status e se é [!UICONTROL Inbound], [!UICONTROL Outbound], ambos ou [!UICONTROL Shared Provider] da fonte de dados.
* Pesquise por [!UICONTROL data sources] por nome.
* Criar, editar e excluir [!UICONTROL data sources].

## Opções de Menu e Configurações do [!DNL Data Source] {#settings-menu-options}

As configurações nas diferentes seções da interface de gerenciamento do [!UICONTROL Data Source] identificam o [!DNL data source], determinam como ele é usado ou compartilhado e permitem habilitar o relatório de erros para o [!UICONTROL Onboarding Status Report].

## Detalhes de [!DNL Data Source] {#details}

Além dos campos de texto, a seção [!UICONTROL Data Source Details] contém os controles e opções listados abaixo.

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuração </th> 
   <th colname="col2" class="entry"> Opções de Menu </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tipo de ID</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: a ID do cookie que identifica um dispositivo. Você selecionaria essa opção quando sua fonte de dados fosse um navegador da Web ou ao trabalhar com dados anônimos ou dados que não possam ser associados a uma única pessoa. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID do Device Advertising </span></b>: o identificador do dispositivo móvel. Selecione esta opção quando a fonte de dados for um dispositivo móvel ou um dispositivo habilitado para a Internet. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> entre dispositivos</span></b>: uma ID autenticada fornecida pelo cliente. Selecione esta opção quando quiser criar: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Uma fonte de dados entre dispositivos e a compilação de uma <span class="wintitle"> Regra de mesclagem de perfis</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Uma fonte de dados que usa links fornecidos por um gráfico de dispositivos de terceiros integrado ao Audience Manager <span class="keyword"> </span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Definição de ID</span></b> </p> </td> 
   <td colname="col2"> <p>As opções <b><span class="uicontrol"> Definição de ID</span></b> definem a relação que uma fonte de dados tem com uma UUID (ID de usuário) de <span class="keyword"> Audience Manager</span> e dispositivos associados vinculados por um gráfico de dispositivos de terceiros que está integrado com o Audience Manager <span class="keyword"> </span>. As opções incluem: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Pessoa:</span></b> A ID usada para definir uma única pessoa. Esta ID pode ser mapeada para vários Audience Manager <span class="keyword"> IDs </span>. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Família:</span></b> A ID usada para definir um grupo de pessoas. Essa ID pode ser mapeada para várias IDs de Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[Os Controles da Exportação de Dados](../features/data-export-controls.md) são regras de classificação opcionais que você pode aplicar a um [!UICONTROL data source] e [!UICONTROL destination]. Eles impedem que você envie dados para um [!UICONTROL destination] quando essa ação viola a privacidade dos dados ou o contrato de uso. Pule esta seção se você não usar [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Restrições de exportação não funcionarão a menos que você defina um rótulo de exportação correspondente em um [!UICONTROL destination].

As opções incluem:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Configurações de [!UICONTROL Data Source] {#data-source-settings}

O [!UICONTROL Data Source Settings] contém os controles e opções listados abaixo. Algumas dessas configurações têm subopções adicionais e itens de menu que você pode selecionar para modificar uma fonte de dados.

### Configurações de [!UICONTROL Inbound Data Source]

Marque a caixa de seleção **[!UICONTROL Inbound]** quando a fonte de dados tiver sido projetada para receber dados de entrada. Selecionar a caixa de seleção **[!UICONTROL Inbound]** expõe dois grupos adicionais de controles descritos abaixo.

>[!NOTE]
>
>A caixa de seleção **[!UICONTROL Inbound]** destina-se apenas a exibir ou ocultar os controles [!UICONTROL data source] descritos abaixo. Desmarcar a opção **[!UICONTROL Inbound]** não afeta a assimilação de dados de forma alguma. Seus dados integrados serão processados independentemente dessa opção estar marcada.

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuração </th> 
   <th colname="col2" class="entry"> Opções de Menu </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tipo de ID</span></b> </p> </td> 
   <td colname="col2"> <p>A opção <b><span class="uicontrol"> de Entrada</span></b> requer um tipo de ID. As opções incluem: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID do cliente </span></b>: identifica dados de entrada com uma ID do cliente. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID do Audience Manager </span></b>: identifica dados de entrada com um ID do Audience Manager <span class="keyword">.</span> </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> ID do Experience Cloud </span></b>: identifica dados de entrada com um ID do Experience Cloud <span class="keyword">. </span> Consulte Cookies <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> e a ID de Experience Cloud </a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Solução de Problemas de Formato de Arquivo</span></b> </p> </td> 
   <td colname="col2"> <p>Selecione <b><span class="uicontrol"> Habilitar amostragem de erros de arquivo</span></b> quando precisar solucionar problemas com o processamento de arquivos de entrada. Esse recurso gera um relatório de amostra de erro que mostra os erros de formato de arquivo e sintaxe. </p> <p>Consulte <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Relatório de status onboard: Sobre </a> para obter informações sobre relatório de erros e amostragem de erros. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Outras Configurações de [!UICONTROL Data Source]

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuração </th> 
   <th colname="col2" class="entry"> Selecionar quando </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Saída</span></b> </p> </td> 
   <td colname="col2"> <p>Sua fonte de dados envia dados a um destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartilhamento Habilitado</span></b> </p> </td> 
   <td colname="col2"> <p>Sua fonte de dados pode ser compartilhada com outros parceiros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Uso como um Perfil Autenticado</span></b> </p> </td> 
   <td colname="col2"> <p>Sua fonte de dados entre dispositivos contém uma ID autenticada. Uma ID autenticada é coletada e sincronizada com uma ID do Audience Manager</span> do <span class="keyword"> durante um evento de autenticação (por exemplo, um usuário faz logon no site, no aplicativo etc.). A ID autenticada pode ser usada para dados integrados de outras fontes que armazenam essa ID. Ele também pode ser usado para vincular várias IDs de dispositivo em <span class="wintitle"> Link de Perfil</span>. </p> <p>Essa opção expõe um campo de texto que permite renomear a fonte de dados com um alias. Se você usa um alias, esse novo nome substitui o nome da fonte de dados e aparece nas <span class="wintitle"> Opções de Perfil Autenticado</span> quando você <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> cria uma regra de Mesclagem de Perfis</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Uso como Gráfico de Dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Cria uma fonte de dados como um gráfico de dispositivos que você pode fornecer a outros clientes do Audience Manager<span class="keyword"></span>. Antes de selecionar esta opção, informe com seu consultor do <span class="keyword"> Audience Manager</span> com quais clientes este <span class="wintitle"> Data Source</span> deve ser compartilhado. Seu consultor terá que provisionar essas empresas por meio de nossos processos internos. </p> <p>Essa opção expõe um campo de texto que permite renomear a fonte de dados com um alias. Se você usa um alias, esse novo nome substitui o nome da fonte de dados e aparece nas <span class="wintitle"> Opções de Dispositivo</span> quando você <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> cria uma regra de Mesclagem de Perfis</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartilhar IDs de visitante ou dispositivo associados com Clientes Audience Manager específicos</span></b> </p> </td> 
   <td colname="col2"> <p>Sua fonte de dados entre dispositivos contém IDs de um gráfico de dispositivos. Um gráfico de dispositivos é uma coleção de IDs que mapeiam para um ou mais Audience Manager <span class="keyword"> IDs do </span> para um cluster. Normalmente, este grupo representa uma pessoa ou um grupo doméstico maior. Disponível somente para contas listadas como "Provedor de dados". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartilhar IDs de visitante ou dispositivo associadas na Plataforma Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>Sua fonte de dados contém IDs de visitante ou dispositivo que podem ser compartilhadas em outras soluções do Experience Cloud</span> do <span class="keyword">. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Retenção de dados para IDs de clientes inativas</span></b> </p> </td> 
   <td colname="col2"> <p>Permite definir o período de retenção de dados para IDs de cliente inativas. Isso determina por quanto tempo o Audience Manager mantém as IDs do cliente em nosso banco de dados após serem vistas pela última vez na plataforma Audience Manager.</p> <p>O valor padrão é de 24 meses (720 dias). O valor mínimo que pode ser definido é 1 mês e o máximo é 5 anos. Observe que contamos todos os meses como 30 dias.</p> <p>O Audience Manager executa um processo que exclui IDs do cliente inativas uma vez por semana, de acordo com a retenção de dados definida para IDs do cliente inativas.</p> <p>O Audience Manager executa um processo que exclui IDs do cliente inativas uma vez por semana, de acordo com a retenção de dados definida para IDs do cliente inativas.</p> <p><b>Observação</b>: este controle está disponível somente para fontes de dados entre dispositivos. Consulte também <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Criar uma Source de Dados entre Dispositivos </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Códigos de integração de características únicas</span></b> </p> </td> 
   <td colname="col2"> <p>Você deseja impor que duas características da mesma fonte de dados não tenham o mesmo código de integração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Códigos de integração de segmento exclusivos</span></b> </p> </td> 
   <td colname="col2"> <p>Você deseja impor que dois segmentos da mesma fonte de dados não tenham o mesmo código de integração. </p> </td> 
  </tr>
 </tbody>
</table>
