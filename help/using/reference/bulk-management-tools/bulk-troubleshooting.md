---
description: O que fazer quando as planilhas retornarem um erro ou sua solicitação em massa falhar.
seo-description: O que fazer quando as planilhas retornarem um erro ou sua solicitação em massa falhar.
seo-title: Dicas de solução de problemas para ferramentas de gerenciamento em massa
solution: Audience Manager
title: Dicas de solução de problemas para ferramentas de gerenciamento em massa
uuid: 550908 a 1-e 24 e -4 f 31-954 b -7132 c 0 c 8 dc 3 e
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Troubleshooting Tips for Bulk Management Tools{#troubleshooting-tips-for-bulk-management-tools}

O que fazer quando as planilhas retornarem um erro ou sua solicitação em massa falhar.



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Essa ferramenta é fornecida para conveniência e apenas como cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [As permissões de grupo RBAC](../../features/administration/administration-overview.md) atribuídas na [!DNL Audience Manager] interface do usuário são respeitadas [!UICONTROL Bulk Management Tools].

Fatores como tráfego de rede pesado, uso do servidor e grandes conjuntos de dados podem causar falha ou tempo limite de uma solicitação em massa. Se houver um problema, a planilha interromperá a gravação de dados e exibirá uma mensagem de erro. Quando isso acontece, você deve:

* Leia a mensagem de erro.
* Correção do problema.
* Exclua todas as linhas que já foram atualizadas.
* Tente novamente a solicitação em massa.

## Long delays or unresponsive behavior {#delays-behavior}

A tabela a seguir lista alguns problemas comuns que podem ser encontrados ao fazer solicitações em massa com as planilhas. Tente corrigir esses problemas com as soluções recomendadas. Se as soluções recomendadas não resolverem o problema, você deve salvar seu trabalho, reiniciar o computador e tentar a solicitação novamente sem iniciar ou trabalhar com outros aplicativos.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problema </th> 
   <th colname="col2" class="entry"> Solução </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Atrasos longos</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Desative o modo de compatibilidade</b>: Verifique se você tem outras planilhas abertas no modo de compatibilidade do Microsoft Excel. O modo de compatibilidade pode aumentar os tempos de execução. Feche qualquer planilha que você tenha aberto neste modo e tente sua solicitação em massa novamente. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Recursos do sistema</b>: Recursos limitados do sistema contribuem para atrasos longos. Tente fechar todos os outros programas antes de fazer uma solicitação em massa. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Sem resposta</b> </td> 
   <td colname="col2">Se você clicar em um botão de ação e nada acontece: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Certifique-se de ter o conjunto certo de cabeçalhos para a ação de seleção. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Certifique-se de usar a planilha correta para os cabeçalhos copiados. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Verifique a posição dos dados que deseja usar em uma operação em massa. Todos os cabeçalhos começam na coluna A, na linha 1. Todos os dados vão nos cabeçalhos correspondentes, começando na coluna A, na linha 2 (imediatamente abaixo dos cabeçalhos). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

