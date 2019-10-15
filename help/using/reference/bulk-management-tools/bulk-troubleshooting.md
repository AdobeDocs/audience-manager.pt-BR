---
description: O que fazer quando as planilhas retornarem um erro ou sua solicitação em massa falhar.
seo-description: O que fazer quando as planilhas retornarem um erro ou sua solicitação em massa falhar.
seo-title: Dicas de solução de problemas para ferramentas de gerenciamento em massa
solution: Audience Manager
title: Dicas de solução de problemas para ferramentas de gerenciamento em massa
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
translation-type: tm+mt
source-git-commit: 6f13cefb2f56bbc2e0bfff9a6d31925001403c50

---


# Dicas de solução de problemas para ferramentas de gerenciamento em massa{#troubleshooting-tips-for-bulk-management-tools}

O que fazer quando as planilhas retornarem um erro ou sua solicitação em massa falhar.



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>Os [!UICONTROL Bulk Management Tools] não *são suportados por* [!DNL Audience Manager]. Esta ferramenta é fornecida apenas para conveniência e cortesia. Para alterações em massa, recomendamos que você trabalhe com as APIs [do](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [As permissões](../../features/administration/administration-overview.md) de grupo RBAC atribuídas na [!DNL Audience Manager] interface do usuário são respeitadas na [!UICONTROL Bulk Management Tools].

Fatores como tráfego intenso de rede, uso do servidor e grandes conjuntos de dados podem causar falha ou tempo limite de uma solicitação em massa. Se houver um problema, a planilha deixará de gravar dados e exibirá uma mensagem de erro. Quando isso acontecer, você deverá:

* Leia a mensagem de erro.
* Corrija o problema.
* Exclua todas as linhas que já foram atualizadas.
* Tente a solicitação em massa novamente.

## Longos atrasos ou comportamento sem resposta {#delays-behavior}

A tabela a seguir lista alguns problemas comuns que podem ocorrer ao fazer solicitações em massa com as planilhas. Tente corrigir esses problemas com as soluções recomendadas. Se as soluções recomendadas não resolverem o problema, você deve salvar seu trabalho, reiniciar seu computador e tentar a solicitação novamente sem iniciar ou trabalhar com outros aplicativos.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problema </th> 
   <th colname="col2" class="entry"> Solução </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Longos atrasos</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Desativar modo</b>de compatibilidade: Verifique se há outras planilhas abertas no modo de compatibilidade do Microsoft Excel. O modo de compatibilidade pode aumentar os tempos de execução. Feche todas as planilhas que possam ter sido abertas nesse modo e tente sua solicitação em massa novamente. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Recursos</b>do sistema: Os recursos limitados do sistema contribuem para longos atrasos. Tente fechar todos os outros programas antes de fazer uma solicitação em massa. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nenhuma resposta</b> </td> 
   <td colname="col2">Se você clicar em um botão de ação e nada acontecer: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Verifique se você tem o conjunto certo de cabeçalhos para a ação de seleção. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Verifique se você está usando a planilha correta para os cabeçalhos copiados. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Verifique a posição dos dados que deseja usar em uma operação em massa. Todos os cabeçalhos começam na coluna A, linha 1. Todos os dados vão para cabeçalhos correspondentes começando na coluna A, linha 2 (imediatamente abaixo dos cabeçalhos). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Mensagens de erro

Às vezes, você pode receber mensagens de erro ao fazer alterações em massa. Para interpretar a mensagem de erro, consulte Códigos de [resposta definidos](/help/using/api/rest-api-main/aam-api-getting-started.md) na documentação da API.

