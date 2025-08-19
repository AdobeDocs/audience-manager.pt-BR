---
description: O que fazer quando as planilhas retornarem um erro ou sua solicitação em massa falhar.
seo-description: What to do when the worksheets return an error or your bulk request fails.
seo-title: Troubleshooting Tips for Bulk Management Tools
solution: Audience Manager
title: Dicas de solução de problemas para ferramentas de gerenciamento em massa
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# Dicas de solução de problemas para ferramentas de gerenciamento em massa{#troubleshooting-tips-for-bulk-management-tools}

O que fazer quando as planilhas retornarem um erro ou sua solicitação em massa falhar.

>[!IMPORTANT]
>
>As Ferramentas de gerenciamento em massa não são uma oferta oficialmente compatível com o Adobe. A solução de problemas e o suporte por meio do Atendimento ao cliente serão tratados caso a caso.

<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>As [permissões do grupo RBAC](../../features/administration/administration-overview.md) atribuídas na interface do usuário [!DNL Audience Manager] são honradas no [!UICONTROL Bulk Management Tools].

Fatores como tráfego pesado de rede, uso de servidor e grandes conjuntos de dados podem causar falha ou tempo limite de uma solicitação em massa. Se houver um problema, a planilha parará de gravar dados e exibirá uma mensagem de erro. Quando isso acontecer, você deverá:

* Leia a mensagem de erro.
* Corrija o problema.
* Excluir todas as linhas que já foram atualizadas.
* Tente a solicitação em massa novamente.

## Erros de autenticação, longos atrasos ou comportamento sem resposta {#delays-behavior}

A tabela a seguir lista alguns problemas comuns que você pode encontrar ao fazer solicitações em massa com as planilhas. Tente corrigir esses problemas com as soluções recomendadas. Se as soluções recomendadas não resolverem o problema, salve seu trabalho, reinicie o computador e tente novamente sem iniciar ou trabalhar com outros aplicativos.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problema </th> 
   <th colname="col2" class="entry"> Solução </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Erro de autenticação</b> </td> 
   <td colname="col2"> 
    <b>Atualização para a versão mais recente do Microsoft Excel</b>: quando uma nova versão do Microsoft Excel é lançada e você está usando uma versão mais antiga, pode ocorrer um erro de autenticação na planilha de Gerenciamento em Massa. Atualize para a versão mais recente do Microsoft Excel para resolver o erro de autenticação.
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Atrasos longos</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Desativar modo de compatibilidade</b>: verifique se há outras planilhas abertas no modo de compatibilidade do Microsoft Excel. O modo de compatibilidade pode aumentar os tempos de execução. Feche todas as planilhas que você pode ter aberto neste modo e tente sua solicitação em massa novamente. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Recursos do sistema</b>: recursos limitados do sistema contribuem para longos atrasos. Tente fechar todos os outros programas antes de fazer uma solicitação em massa. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nenhuma resposta</b> </td> 
   <td colname="col2">Se você clicar em um botão de ação e nada acontecer: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Verifique se você tem o conjunto correto de cabeçalhos para a ação de seleção. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Verifique se você está usando a planilha correta para os cabeçalhos copiados. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Verifique a posição dos dados que deseja usar em uma operação em massa. Todos os cabeçalhos começam na coluna A, linha 1. Todos os dados são inseridos nos cabeçalhos correspondentes, começando na coluna A, linha 2 (imediatamente abaixo dos cabeçalhos). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Mensagens de erro

Às vezes, você pode receber mensagens de erro ao fazer alterações em massa. Para interpretar a mensagem de erro, consulte [Códigos de resposta definidos](/help/using/api/rest-api-main/aam-api-getting-started.md) na documentação da API.
