---
description: Visualização uma lista das fontes de dados configuradas no momento, adicione novas fontes de dados e edite as fontes existentes.
seo-description: Visualização uma lista das fontes de dados configuradas no momento, adicione novas fontes de dados e edite as fontes existentes.
seo-title: Lista e configurações de fontes de dados
solution: Audience Manager
title: Lista e configurações de fontes de dados
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1118'
ht-degree: 3%

---


# [!UICONTROL Data Sources] Lista e configurações  {#data-sources-list-and-settings}

Visualização uma lista do [!UICONTROL data sources] configurado no momento, adicione novo [!UICONTROL data sources] e edite [!UICONTROL data sources] existente.

Você também pode gerenciar [!UICONTROL data sources] usando os métodos [!DNL API]. Para obter mais informações, consulte [Métodos da API da Fonte de Dados](../api/rest-api-main/aam-api-data-sources.md).

## [!UICONTROL Data Sources] Exibição em lista {#list-view}

O painel [!UICONTROL Data Sources] é um espaço de trabalho centralizado para gerenciar fontes de dados.

O painel [!UICONTROL Data Sources] (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) contém recursos e ferramentas que ajudam a:

* Veja todos os [!UICONTROL data sources] existentes, incluindo a descrição, o status e se são [!UICONTROL Inbound], [!UICONTROL Outbound], ambos ou [!UICONTROL Shared Provider] de cada fonte de dados.
* Procure [!UICONTROL data sources] pelo nome.
* Crie, edite e exclua [!UICONTROL data sources].

## [!DNL Data Source] Configurações e opções de menu  {#settings-menu-options}

As configurações nas diferentes seções da [!UICONTROL Data Source] interface de gerenciamento identificam seu [!DNL data source], determinam como ele é usado ou compartilhado e permitem ativar o relatórios de erro para o [!UICONTROL Onboarding Status Report].

## [!DNL Data Source] Detalhes {#details}

Além dos campos de texto, a seção [!UICONTROL Data Source Details] contém os controles e opções listados abaixo.

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuração </th> 
   <th colname="col2" class="entry"> Opções de menu </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tipo de ID</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: A ID do cookie que identifica um dispositivo. Você selecionaria isso quando sua fonte de dados for um navegador da Web ou ao trabalhar com dados anônimos ou dados que não podem ser associados a uma única pessoa. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID</span></b> de anúncio do dispositivo: O identificador do dispositivo móvel. Selecione essa opção quando a fonte de dados for um dispositivo móvel ou um dispositivo habilitado para Internet. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Entre dispositivos</span></b>: Uma ID autenticada fornecida pelo cliente. Selecione esta opção quando quiser criar: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Uma fonte de dados entre dispositivos e crie uma <span class="wintitle"> regra de mesclagem de Perfis</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Uma fonte de dados que usa links fornecidos pelo <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> ou outro gráfico de dispositivo de terceiros integrado ao <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Definição de ID</span></b> </p> </td> 
   <td colname="col2"> <p>As opções <b><span class="uicontrol"> Definição de ID</span></b> definem o relacionamento que uma fonte de dados tem com uma <span class="keyword"> Audience Manager</span> ID de usuário (UUID) e dispositivos associados vinculados pelo <span class="keyword"> Adobe Experience Cloud Device Co-op</span> ou outro gráfico de dispositivo de terceiros integrado a <span class="keyword"> Audience Manager</span>. As opções incluem: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Pessoa:</span></b> a ID usada para definir uma única pessoa. Essa ID pode ser mapeada para várias IDs <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Domicílio:</span></b> a ID usada para definir um grupo de pessoas. Essa ID pode ser mapeada para várias IDs de Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[Os ](../features/data-export-controls.md) controles de exportação de dados são regras de classificação opcionais que podem ser aplicadas a um  [!UICONTROL data source] e  [!UICONTROL destination]. Elas impedem que você envie dados para [!UICONTROL destination] quando essa ação viola uma privacidade de dados ou um contrato de uso. Ignore esta seção se você não usar [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>As restrições de exportação não funcionarão a menos que você defina um rótulo de exportação correspondente em [!UICONTROL destination].

As opções incluem:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] Configurações {#data-source-settings}

O [!UICONTROL Data Source Settings] contém os controles e opções listados abaixo. Algumas dessas configurações têm subopções e itens de menu adicionais que podem ser selecionados para modificar uma fonte de dados.

### [!UICONTROL Inbound Data Source] Configurações

Marque a caixa de seleção **[!UICONTROL Inbound]** quando sua fonte de dados for projetada para receber dados de entrada. Marcar a caixa de seleção **[!UICONTROL Inbound]** expõe 2 grupos adicionais de controles descritos abaixo.

>[!NOTE]
>
>A caixa de seleção **[!UICONTROL Inbound]** destina-se apenas a exibir ou ocultar os controles [!UICONTROL data source] descritos abaixo. Desmarcar a opção **[!UICONTROL Inbound]** não afeta a ingestão de dados de nenhuma forma. Seus dados integrados serão processados independentemente dessa opção estar sendo marcada.

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuração </th> 
   <th colname="col2" class="entry"> Opções de menu </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tipo de ID</span></b> </p> </td> 
   <td colname="col2"> <p>A opção <b><span class="uicontrol"> Inbound</span></b> requer um tipo de ID. As opções incluem: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID</span></b> do cliente: Identifica dados de entrada com uma ID do cliente. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID</span></b> do Audience Manager: Identifica dados de entrada com uma  <span class="keyword"> Audiência </span> ManagerID. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> ID</span></b> do Experience Cloud: Identifica dados de entrada com uma  <span class="keyword"> Experience </span> CloudID. Consulte <a href="https://docs.adobe.com/content/help/pt-BR/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies e a Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Solução de problemas de formato de arquivo</span></b> </p> </td> 
   <td colname="col2"> <p>Selecione <b><span class="uicontrol"> Ativar amostragem de erro de arquivo</span></b> quando precisar solucionar problemas com o processamento de arquivos de entrada. Este recurso gera um relatório de exemplo de erro que mostra o formato do arquivo e os erros de sintaxe. </p> <p>Consulte <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Relatório de status onboard: Sobre</a> para obter informações sobre relatórios de erros e amostragem de erros. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Outras configurações [!UICONTROL Data Source]

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuração </th> 
   <th colname="col2" class="entry"> Selecionar ao </th> 
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
   <td colname="col1"> <p> <b><span class="uicontrol"> Usar como um Perfil autenticado</span></b> </p> </td> 
   <td colname="col2"> <p>Sua fonte de dados entre dispositivos contém uma ID autenticada. Uma ID autenticada é coletada e sincronizada com uma ID <span class="keyword"> Audience Manager</span> durante um evento de autenticação (por exemplo, um usuário faz logon no site, no aplicativo etc.). A ID autenticada pode ser usada para dados a bordo de outras fontes que armazenam essa ID. Ele também pode ser usado para vincular várias IDs de dispositivo no <span class="wintitle"> Link do Perfil</span>. </p> <p>Essa opção expõe um campo de texto que permite renomear a fonte de dados com um alias. Se você usar um alias, esse novo nome substituirá o nome da fonte de dados e aparecerá em <span class="wintitle"> Opções de Perfil Autenticadas</span> quando você <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> criar uma regra de Mesclagem de Perfis</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Usar como um Gráfico de dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Cria uma fonte de dados como um gráfico de dispositivo que você pode fornecer a outros clientes <span class="keyword"> Audience Manager</span>. Antes de selecionar essa opção, informe com seu consultor <span class="keyword"> Audience Manager</span> quais clientes essa <span class="wintitle"> Fonte de Dados</span> deve ser compartilhada. Seu consultor terá que fornecer essas empresas através de nossos processos internos. </p> <p>Essa opção expõe um campo de texto que permite renomear a fonte de dados com um alias. Se você usar um alias, esse novo nome substituirá o nome da fonte de dados e aparecerá nas <span class="wintitle"> Opções do dispositivo</span> quando você <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> criar uma regra de Mesclagem de Perfis</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartilhar IDs de visitante ou dispositivo associadas com clientes de Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>Sua fonte de dados entre dispositivos contém IDs de um gráfico de dispositivos. Um gráfico de dispositivo é uma coleção de IDs que mapeiam para uma ou mais IDs <span class="keyword"> Audience Manager</span> de um cluster. Este cluster geralmente representa uma pessoa ou um grupo maior, do agregado familiar. Disponível somente para contas listadas como "Provedor de dados". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartilhar IDs de visitante ou dispositivo associadas na plataforma Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>Sua fonte de dados contém IDs de visitante ou dispositivo que podem ser compartilhadas em outras soluções <span class="keyword"> Experience Cloud</span>. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Retenção de dados para IDs de cliente inativas</span></b> </p> </td> 
   <td colname="col2"> <p>Permite definir o período de retenção de dados para IDs de cliente inativas. Isso determina por quanto tempo a Audience Manager mantém as IDs do cliente em nosso banco de dados após serem vistas pela última vez na plataforma do Audience Manager.</p> <p>O valor padrão é 24 meses (720 dias). O valor mínimo que você pode definir é 1 mês e o valor máximo é 5 anos. Observe que todos os meses são contados como 30 dias.</p> <p>O Audience Manager executa um processo que exclui IDs de clientes inativas uma vez por semana, de acordo com a retenção de dados definida para IDs de clientes inativas.</p> <p>O Audience Manager executa um processo que exclui IDs de clientes inativas uma vez por semana, de acordo com a retenção de dados definida para IDs de clientes inativas.</p> <p><b>Observação</b>: Esse controle está disponível somente para fontes de dados entre dispositivos. Consulte também, <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Criar uma fonte de dados entre dispositivos </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Códigos de integração de características exclusivas</span></b> </p> </td> 
   <td colname="col2"> <p>Você deseja impor que duas características da mesma fonte de dados não tenham o mesmo código de integração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Códigos de integração de segmento único</span></b> </p> </td> 
   <td colname="col2"> <p>Você deseja impor que dois segmentos da mesma fonte de dados não tenham o mesmo código de integração. </p> </td> 
  </tr>
 </tbody>
</table>
