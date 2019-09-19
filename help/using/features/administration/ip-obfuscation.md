---
description: Sua empresa pode desejar ofuscar o endereço IP em muitos países devido aos regulamentos globais de privacidade. O Audience Manager permite ofuscar os endereços IP de visitantes em uma base global ou de país por país.
seo-description: Sua empresa pode desejar ofuscar o endereço IP em muitos países devido aos regulamentos globais de privacidade. O Audience Manager permite ofuscar os endereços IP de visitantes em uma base global ou de país por país.
solution: Audience Manager
title: Ofuscação de endereço IP
translation-type: tm+mt
source-git-commit: f7206fda4b16a22c8a8bfcf97529cdaea24b0898

---


# Ofuscação de endereço IP {#ip-obfuscation}

Use esse recurso para ofuscar endereços IP coletados no Audience Manager.

## Visão geral e metodologia {#overview-and-methodology}

Sua empresa pode desejar ofuscar o endereço IP em muitos países devido aos regulamentos globais de privacidade. O Audience Manager permite ofuscar os endereços IP de visitantes em uma base global ou de país por país.

### Metodologia de ofuscação de IP

Seguindo os princípios de "Privacidade por design", o Adobe Audience Manager permite que os clientes habilitem a ofuscação de IP da interface do usuário, globalmente em todas as regiões geográficas ou para países específicos. Quando você habilita essa configuração, o último octeto (a última parte) do endereço IP é descartado imediatamente quando o endereço IP é ingerido no Audience Manager. O Audience Manager descarta essa parte do endereço IP antes do processamento (incluindo antes de qualquer pesquisa geográfica ou registro opcional do endereço IP). Por exemplo:

* Antes da ofuscação: `255.255.255.255`
* Após ofuscação: `255.255.255.0`

Consulte também, Coletando endereços IP e ofuscação de endereço IP na seção [Privacidade de](/help/using/overview/data-security-and-privacy/data-privacy.md)dados.

## Requisitos de ofuscação de endereço IP {#ip-obfuscation-requirements}

A ofuscação de endereço IP está disponível somente para contas de administrador do Audience Manager. Consulte [Criar usuários](/help/using/features/administration/administration-overview.md#create-users) para entender como atribuir privilégios de administrador a um usuário.

>[!NOTE]
>
> Devido ao grande volume de dados processados pelo Audience Manager, as alterações na ofuscação de IP podem levar até 4 horas para entrar em vigor, a partir do momento em que você atualiza as configurações.

## Configurar ofuscação de endereço IP {#configure-ip-obfuscation}

Siga as etapas abaixo para configurar a ofuscação do endereço IP.

1. Faça logon no Audience Manager com uma conta de administrador e vá para **Administração &gt; Privacidade**.
2. Escolha o tipo de ofuscação de IP que deseja usar.
   1. **** Ofuscar todos os endereços IP: selecione essa opção para que o Audience Manager ofusque o último octeto de todos os endereços IP do visitante, independentemente da região de onde eles são originários.
   2. **** Ofuscar endereços IP para países específicos: selecione essa opção para que o Audience Manager ofusque o último octeto de endereços IP de visitantes para países específicos. Use a **Lista de países** ou o campo **Pesquisar** correspondente para localizar os países para habilitar a ofuscação de IP e clique no ícone + para adicioná-los à lista **Selecionados para ofuscação** . Depois de adicionar todos os países necessários à lista **Selecionados para ofuscação** , clique em **Salvar**.

![](assets/ip-obfuscation.png)

## Desativar ofuscação de endereço IP {#disable-ip-obfuscation}

Para desativar a ofuscação de endereço IP globalmente, vá para **Administração &gt; Privacidade**, selecione **Não ofuscar endereços** IP e clique em **Salvar**.

Para desativar a ofuscação de endereço IP para países específicos, localize os países na lista **Selecionados para ofuscação** e clique no ícone **X** correspondente. Click **Save** when you're done.

## Conceitos relacionados {#related-concepts}

* [Privacidade de dados](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Demonstração de vídeo de ofuscação de endereço IP
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=por_br)

