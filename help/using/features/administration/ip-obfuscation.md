---
description: Sua empresa pode desejar ofuscar o endereço IP em muitos países devido aos regulamentos globais de privacidade. O Audience Manager permite ofuscar os endereços IP de visitantes em uma base global ou de país por país.
seo-description: Sua empresa pode desejar ofuscar o endereço IP em muitos países devido aos regulamentos globais de privacidade. O Audience Manager permite ofuscar os endereços IP de visitantes em uma base global ou de país por país.
solution: Audience Manager
title: Ofuscação de endereço IP
translation-type: tm+mt
source-git-commit: f7206fda4b16a22c8a8bfcf97529cdaea24b0898

---


# Ofuscação de endereço IP {#ip-obfuscation}

Use este recurso para ofuscar endereços IP coletados no Audience Manager.

## Overview and Methodology {#overview-and-methodology}

Sua empresa pode desejar ofuscar o endereço IP em muitos países devido aos regulamentos globais de privacidade. O Audience Manager permite ofuscar os endereços IP de visitantes em uma base global ou de país por país.

### Metodologia de ofuscação de IP

Seguindo os princípios de «Privacidade por design», o Adobe Audience Manager permite que os clientes ativem a ofuscação de IP da interface do usuário, seja globalmente por todas as regiões geográficas ou para países específicos. Quando você ativa essa configuração, o último octeto (a última parte) do endereço IP é descartado imediatamente quando o endereço IP é assimilado no Audience Manager. O Audience Manager descarta essa parte do endereço IP antes do processamento (incluindo antes de qualquer pesquisa geográfica opcional ou registro do endereço IP). Por exemplo:

* Before obfuscation: `255.255.255.255`
* After obfuscation: `255.255.255.0`

See also, Collecting IP addresses and IP Address Obfuscation in our [Data Privacy section](/help/using/overview/data-security-and-privacy/data-privacy.md).

## IP Address Obfuscation Requirements {#ip-obfuscation-requirements}

A ofuscação de endereço IP está disponível somente para contas de administrador do Audience Manager. See [Create Users](/help/using/features/administration/administration-overview.md#create-users) to understand how to assign administrator privileges for a user.

>[!NOTE]
>
> Devido ao grande volume de dados processados pelo Audience Manager, as alterações de ofuscação de IP podem levar até 4 horas para entrarem em vigor, a partir do momento em que as configurações são atualizadas.

## Configure IP Address Obfuscation {#configure-ip-obfuscation}

Siga as etapas abaixo para configurar a ofuscação de endereço IP.

1. Log in to Audience Manager with an administrator account and go to **Administration &gt; Privacy**.
2. Escolha o tipo de ofuscação de IP que deseja usar.
   1. **Ofuscar todos os endereços IP:** selecione esta opção para que o Audience Manager ofuscate o último octeto de todos os endereços IP do visitante, independentemente da região de origem.
   2. **Ofuscar endereços IP de países específicos:** selecione esta opção para que o Audience Manager ofuscate o último octeto dos endereços IP do visitante para países específicos. Use the **List of Countries** or the corresponding **Search** field to find the countries to enable IP obfuscation for, and click the + icon to add them to the **Selected for Obfuscation** list. Once you&#39;ve added all the required countries to the **Selected for Obfuscation** list, click **Save**.

![](assets/ip-obfuscation.png)

## Disable IP Address Obfuscation {#disable-ip-obfuscation}

To disable IP address obfuscation globally, go to **Administration &gt; Privacy**, select **Do not obfuscate IP addresses**, and click **Save**.

To disable IP address obfuscation for specific countries, find the countries in the **Selected for Obfuscation** list, then click their corresponding **X** icon. Click **Save** when you&#39;re done.

## Conceitos relacionados {#related-concepts}

* [Privacidade de dados](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Demonstração de vídeo ofuscação de endereço IP
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=por_br)

