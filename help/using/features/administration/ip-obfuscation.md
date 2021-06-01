---
description: Sua empresa pode desejar ofuscar o endereço IP em muitos países devido aos regulamentos globais de privacidade. O Audience Manager permite ofuscar os endereços IP de visitantes em uma base global ou de país por país.
seo-description: Sua empresa pode desejar ofuscar o endereço IP em muitos países devido aos regulamentos globais de privacidade. O Audience Manager permite ofuscar os endereços IP de visitantes em uma base global ou de país por país.
solution: Audience Manager
title: Ofuscação de endereço IP
feature: Governança e privacidade de dados
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 22%

---

# Ofuscação de endereço IP {#ip-obfuscation}

Use esse recurso para ofuscar endereços IP coletados no Audience Manager.

## Visão geral e metodologia {#overview-and-methodology}

Sua empresa pode desejar ofuscar o endereço IP em muitos países devido aos regulamentos globais de privacidade. O Audience Manager permite ofuscar os endereços IP de visitantes em uma base global ou de país por país.

### Metodologia de ofuscação de IP

Seguindo os princípios de &quot;Privacidade por design&quot;, o Adobe Audience Manager permite que os clientes habilitem a ofuscação de IP da interface do usuário, globalmente em todas as regiões geográficas ou para países específicos. Ao ativar essa configuração, o último octeto (a última parte) do endereço IP é imediatamente descartado quando o endereço IP é assimilado no Audience Manager. O Audience Manager descarta essa parte do endereço IP antes do processamento (incluindo antes de qualquer pesquisa geográfica ou registro opcional do endereço IP). Por exemplo:

* Antes da ofuscação: `255.255.255.255`
* Após ofuscação: `255.255.255.0`

Consulte também Coleta de endereços IP e ofuscação de endereço IP em nossa [seção da Privacidade de dados](/help/using/overview/data-security-and-privacy/data-privacy.md).

## Requisitos de ofuscação de endereço IP {#ip-obfuscation-requirements}

A ofuscação de endereço IP está disponível somente para contas de administrador do Audience Manager. Consulte [Criar usuários](/help/using/features/administration/administration-overview.md#create-users) para entender como atribuir privilégios de administrador a um usuário.

>[!NOTE]
>
> Devido ao grande volume de dados processados pelo Audience Manager, as alterações de ofuscação de IP podem levar até 4 horas para entrarem em vigor, a partir do momento em que você atualizar as configurações.

## Configurar ofuscação de endereço IP {#configure-ip-obfuscation}

Siga as etapas abaixo para configurar a ofuscação do endereço IP.

1. Faça logon no Audience Manager com uma conta de administrador e acesse **Administration > Privacy**.
2. Escolha o tipo de ofuscação de IP que deseja usar.
   1. **Ofuscar todos os endereços IP:** selecione essa opção para ofuscar o último octeto de todos os endereços IP de visitante, independentemente da região de onde eles são originários.
   2. **Ofuscar endereços IP de países específicos:** selecione essa opção para que o Audience Manager ofusque o último octeto de endereços IP de visitantes de países específicos. Use a **Lista de países** ou o campo **Procurar** correspondente para localizar os países para ativar a ofuscação de IP e clique no ícone + para adicioná-los à lista **Selecionado para Ofuscação**. Depois de ter adicionado todos os países necessários à lista **Selecionado para Ofuscação**, clique em **Salvar**.

![](assets/ip-obfuscation.png)

## Desative a ofuscação de endereço IP {#disable-ip-obfuscation}

Para desativar a ofuscação de endereço IP globalmente, vá para **Administration > Privacy**, selecione **Do not ofuscate IP addresses** e clique em **Save**.

Para desativar a ofuscação de endereço IP para países específicos, encontre os países na lista **Selecionado para Ofuscação** e clique no ícone **X** correspondente. Clique em **Salvar** quando terminar.

## Conceitos relacionados {#related-concepts}

* [Privacidade de dados](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Demonstração de vídeo de ofuscação de endereço IP
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
