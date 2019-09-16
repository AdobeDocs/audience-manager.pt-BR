---
description: Exiba uma lista das fontes de dados configuradas no momento, adicione novas fontes de dados e edite as fontes existentes.
seo-description: Exiba uma lista das fontes de dados configuradas no momento, adicione novas fontes de dados e edite as fontes existentes.
seo-title: Lista e configurações das fontes de dados
solution: Audience Manager
title: Lista e configurações das fontes de dados
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Lista e configurações das fontes de dados {#data-sources-list-and-settings}

Exiba uma lista das fontes de dados configuradas no momento, adicione novas fontes de dados e edite as fontes existentes.

<!-- c_datasources.xml -->

Você também pode gerenciar fontes de dados usando [!DNL API] métodos. Para obter mais informações, consulte Métodos [da API da fonte de](../api/rest-api-main/aam-api-data-sources.md)dados.

## Exibição de lista de fontes de dados {#list-view}

O [!UICONTROL Data Sources] painel é um espaço de trabalho centralizado para gerenciar fontes de dados.

<!-- c_datasources_list.xml -->

O [!UICONTROL Data Sources] painel (**[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**) contém recursos e ferramentas que ajudam você a:

* Veja todas as fontes de dados existentes, incluindo a descrição, o status e se são [!UICONTROL Inbound], [!UICONTROL Outbound]ambos ou um [!UICONTROL Shared Provider].
* Procure fontes de dados por nome.
* Criar, editar e excluir fontes de dados.

## Configurações da fonte de dados e opções de menu {#settings-menu-options}

As configurações nas diferentes seções da interface de [!UICONTROL Data Source] gerenciamento identificam sua fonte de dados, determinam como ela é usada ou compartilhada e permitem ativar o relatório de erros para o [!UICONTROL Onboarding Status Report].

## Detalhes da fonte de dados {#details}

<!-- datasource-settings-definitions.xml -->

Além dos campos de texto, a [!UICONTROL Data Source Details] seção contém os controles e opções listados abaixo.

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
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID</span></b>de anúncio do dispositivo: O identificador do dispositivo móvel. Selecione essa opção quando a fonte de dados for um dispositivo móvel ou um dispositivo habilitado para Internet. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Entre dispositivos</span></b>: Uma ID autenticada fornecida pelo cliente. Selecione esta opção quando quiser criar: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Uma fonte de dados entre dispositivos e crie uma Regra <span class="wintitle"> de mesclagem de</span>perfis. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Uma fonte de dados que usa links fornecidos pelo <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> ou outro gráfico de dispositivo de terceiros integrado ao <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Definição de ID</span></b> </p> </td> 
   <td colname="col2"> <p>As opções de Definição <b><span class="uicontrol"> de</span></b> ID definem o relacionamento que uma fonte de dados tem com uma ID de usuário do <span class="keyword"> Audience Manager</span> (UUID) e dispositivos associados vinculados pelo <span class="keyword"> Adobe Experience Cloud Device Co-op</span> ou outro gráfico de dispositivo de terceiros integrado ao <span class="keyword"> Audience Manager</span>. As opções incluem: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"></span></b> Pessoa: A ID usada para definir uma única pessoa. Essa ID pode ser mapeada para várias IDs do Audience Manager <span class="keyword"></span> . </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"></span></b> Doméstico: A ID usada para definir um grupo de pessoas. Essa ID pode ser mapeada para várias IDs do Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Controles da exportação de dados {#export-controls}

[Os Controles](../features/data-export-controls.md) de exportação de dados são regras de classificação opcionais que podem ser aplicadas a uma fonte de dados e destino. Elas impedem que você envie dados para um destino quando essa ação viola a privacidade dos dados ou o contrato de uso. Ignore esta seção se não usar [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>As restrições de exportação não funcionarão a menos que você defina um rótulo de exportação correspondente em um destino.

As opções incluem:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Data Source Settings {#data-source-settings}

O [!UICONTROL Data Source Settings] contém os controles e opções listados abaixo. Algumas dessas configurações têm subopções e itens de menu adicionais que podem ser selecionados para modificar uma fonte de dados.

### Configurações da fonte de dados de entrada

Marque a caixa de **[!UICONTROL Inbound]** seleção quando sua fonte de dados for projetada para receber dados de entrada. Marcar a caixa de **[!UICONTROL Inbound]** seleção expõe 2 grupos adicionais de controles descritos abaixo.

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
   <td colname="col2"> <p>A opção <b><span class="uicontrol"> Entrada</span></b> requer um tipo de ID. As opções incluem: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID</span></b>do cliente: Identifica dados de entrada com uma ID do cliente. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID</span></b>do Audience Manager: Identifica dados de entrada com uma ID do <span class="keyword"> Audience Manager</span> . </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: Identifica dados de entrada com uma <span class="keyword"> Experience Cloud</span> ID. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Solução de problemas de formato de arquivo</span></b> </p> </td> 
   <td colname="col2"> <p>Selecione <b><span class="uicontrol"> Ativar amostragem</span></b> de erro de arquivo quando precisar solucionar problemas com o processamento de arquivos de entrada. Este recurso gera um relatório de exemplo de erro que mostra o formato do arquivo e os erros de sintaxe. </p> <p>Consulte Relatório <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> de status onboard: Sobre</a> informações sobre relatórios de erros e amostragem de erros. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Outras configurações de fonte de dados

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
   <td colname="col1"> <p> <b><span class="uicontrol"> Usar como um perfil autenticado</span></b> </p> </td> 
   <td colname="col2"> <p>Sua fonte de dados entre dispositivos contém uma ID autenticada. Uma ID autenticada é coletada e sincronizada com uma ID do Audience Manager <span class="keyword"></span> durante um evento de autenticação (por exemplo, um usuário faz logon no site, no aplicativo etc.). A ID autenticada pode ser usada para dados a bordo de outras fontes que armazenam essa ID. Também pode ser usado para vincular várias IDs de dispositivo no <span class="wintitle"> Link</span>de perfil. </p> <p>Essa opção expõe um campo de texto que permite renomear a fonte de dados com um alias. Se você usar um alias, esse novo nome substituirá o nome da fonte de dados e aparecerá nas Opções <span class="wintitle"> de perfil autenticadas quando você</span> criar uma regra <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"></a>Mesclar perfis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Usar como um Gráfico de dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Cria uma fonte de dados como um gráfico de dispositivo que pode ser fornecido a outros clientes do <span class="keyword"> Audience Manager</span> . Antes de selecionar essa opção, informe com seu consultor do Audience Manager <span class="keyword"> quais clientes essa Fonte</span> de <span class="wintitle"></span> Dados deve ser compartilhada. O seu consultor terá que suprir essas empresas através de nossos processos internos. </p> <p>Essa opção expõe um campo de texto que permite renomear a fonte de dados com um alias. Se você usar um alias, esse novo nome substituirá o nome da fonte de dados e aparecerá nas Opções <span class="wintitle"> do</span> dispositivo quando você <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> criar uma regra</a>Mesclar perfis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartilhar IDs de visitantes ou dispositivos associados com clientes específicos do Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>Sua fonte de dados entre dispositivos contém IDs de um gráfico de dispositivos. Um gráfico de dispositivo é uma coleção de IDs que mapeiam para uma ou mais IDs do Audience Manager <span class="keyword"></span> para um cluster. Este cluster geralmente representa uma pessoa ou um grupo maior, do agregado familiar. Disponível somente para contas listadas como "Provedor de dados". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartilhar IDs de visitante ou dispositivo associadas na plataforma Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>Sua fonte de dados contém IDs de visitante ou dispositivo que podem ser compartilhadas em outras soluções da <span class="keyword"> Experience Cloud</span> . </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Retenção de dados para IDs de cliente inativas</span></b> </p> </td> 
   <td colname="col2"> <p>Permite definir o período de retenção de dados para IDs de cliente inativas. Isso determina por quanto tempo o Audience Manager mantém as IDs do cliente em nosso banco de dados após serem vistas pela última vez na plataforma do Audience Manager.</p> <p>O valor padrão é 24 meses (720 dias). O valor mínimo que você pode definir é 1 mês e o valor máximo é 5 anos. Observe que todos os meses são contados como 30 dias.</p> <p>O Audience Manager executa um processo que exclui IDs de cliente inativas uma vez por semana, de acordo com a retenção de dados definida para IDs de cliente inativas.</p> <p>O Audience Manager executa um processo que exclui IDs de cliente inativas uma vez por semana, de acordo com a retenção de dados definida para IDs de cliente inativas.</p> <p><b>Observação</b>: Esse controle está disponível somente para fontes de dados entre dispositivos. Consulte também <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Criar uma fonte de dados entre dispositivos </a>.</p></td> 
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
