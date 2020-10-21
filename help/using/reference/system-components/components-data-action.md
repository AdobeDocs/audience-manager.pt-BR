---
description: Os componentes de ação de dados incluem Feeds de dados do cliente, Servidor de coleta de dados, editores SFTP/S3/HTTP, IRIS e Servidor de cache de Perfis.
seo-description: Os componentes de ação de dados incluem Feeds de dados do cliente, Servidor de coleta de dados, editores SFTP/S3/HTTP, IRIS e Servidor de cache de Perfis.
seo-title: Componentes de ação de dados
solution: Audience Manager
title: Componentes de ação de dados
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: system components
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 3%

---


# Componentes de ação de dados{#data-action-components}

Os componentes de ação de dados incluem Feeds de dados do cliente, Servidor de coleta de dados, editores SFTP/S3/HTTP, IRIS e Servidor de cache de Perfis.

<!-- 

c_compact.xml

 -->

Os componentes de ação são sistemas e processos que permitem que você mova dados para dentro e para fora [!DNL Audience Manager] e (por falta de uma frase melhor) faça coisas com ele. Esses [!DNL Audience Manager] componentes incluem:

## Feeds de dados do cliente (CDF) {#cdf}

[!UICONTROL CDF] são arquivos enviados por hora aos clientes. Elas contêm IDs de usuário juntamente com IDs de segmento associadas, IDs de característica e outros dados. Para obter mais informações, consulte Visão geral [do feed de dados do](../../features/cdf-files.md)cliente.

## Servidor de coleta de dados (DCS) {#dcs}

Consulte [Componentes da coleta de dados](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

Os [!UICONTROL SFTP/S3] editores recebem dados de ID sincronizada do [!UICONTROL Outbound Feed Converter]. Quando esses arquivos estiverem prontos, o [!UICONTROL SFTP/S3 publishers] enviará esses dados para um destino especificado pelo cliente. Esses arquivos contêm dados de ID sincronizados com um mapeamento de um para muitos das IDs de [!DNL Audience Manager] usuário (UUID) para:

* ID do dispositivo/ID do provedor de dados (DPUUID)
* IDs de segmento qualificadas
* IDs de características

[!DNL Audience Manager] os clientes não têm acesso a recursos que controlam diretamente o [!UICONTROL SFPT/S3 publishers]. Os clientes usam esse serviço indiretamente quando criam e enviam dados para destinos. O [!UICONTROL SFTP/S3] sistema é, essencialmente, um processo de trabalho automatizado que é executado em intervalos programados.

## IRIS {#iris}

Na mitologia grega, [!UICONTROL Iris] há uma figura que viaja e entrega mensagens rapidamente. O [!UICONTROL IRIS] sistema é um namesake que reflete as características dessa figura do mundo antigo. Em termos modernos, [!UICONTROL IRIS] é um serviço de sincronização de cookies de baixa latência e alta frequência e transferência de dados.

[!UICONTROL IRIS] funciona com o mesmo tipo de dados que o [!UICONTROL SFTP/S3] sistema. No entanto, [!UICONTROL IRIS] é diferente porque envia dados para destinos em tempo real em vez de em intervalos definidos. Este é um sistema separado porque os [!UICONTROL SFTP/S3] editores não podem enviar dados para um destino HTTP e eles não são projetados para transferências de dados em tempo real.

Não há controles de interface que permitam que os clientes trabalhem diretamente com [!UICONTROL IRIS]. Os clientes trabalham [!UICONTROL IRIS] indiretamente quando criam e enviam dados para destinos e para outros processos que exigem transferências rápidas de dados.

Exemplos de [!UICONTROL IRIS] serviços e recursos incluem:

* Fornecendo sincronização rápida (dentro de 30 segundos) para cookies e segmentos. Ele pode sincronizar o [!DNL Audience Manager] cookie, os cookies do parceiro ou ambos.
* Transferências de dados em tempo real. [!UICONTROL IRIS] é responsável por enviar eventos de qualificação de segmento em tempo real para um parceiro ou outro destino. Esses dados são formatados em JSON e enviados por meio de uma `POST` solicitação HTTP.

* Transferências de dados em massa de servidor para servidor: Se você trocar grandes quantidades de dados com [!DNL Audience Manager], [!UICONTROL IRIS] será o sistema com o qual seus servidores se envolvem para transferir dados.

* Infraestrutura confiável que funciona em escala e é tolerante a falhas. Os sistemas de alimentação [!UICONTROL IRIS] incluem Amazon SQS, Amazon EC2 e Cassandra.

**Regras de mapeamento de segmentos**

Para otimizar o tráfego entre destinos [!UICONTROL IRIS] e segmentos, [!UICONTROL IRIS] envia segmentos para destinos com base em um conjunto de regras.

1. **Nova qualificação** de segmento: quando um dispositivo se qualifica para um novo segmento, [!UICONTROL IRIS] envia todos os segmentos associados a esse dispositivo para todos os destinos mapeados para esses segmentos.

1. **Nova desqualificação** de segmento: quando um dispositivo não se qualifica mais para um segmento, [!UICONTROL IRIS] envia todas as qualificações e inqualificações de segmento associadas a esse dispositivo para todos os destinos mapeados para esses segmentos.

1. **Atualizações** de mapeamento de destino: quando um mapeamento de destino é atualizado, [!UICONTROL IRIS] envia todos os segmentos associados a um dispositivo para todos os destinos mapeados para esses segmentos, na próxima vez que o Audience Manager visualizar o dispositivo.

1. **Atualizações** de gráficos de dispositivos: quando qualquer ID de dispositivo é adicionada ou removida do gráfico de dispositivo usado para avaliar um segmento, [!UICONTROL IRIS] envia todos os segmentos associados a esse dispositivo para todos os destinos mapeados para esses segmentos, na próxima vez que o Audience Manager visualizar o dispositivo.

>[!IMPORTANT]
>
>Se o Audience Manager não detectar nenhuma das atualizações acima por 3 dias consecutivos, [!UICONTROL IRIS] enviará todos os segmentos associados a um dispositivo para todos os destinos mapeados para esses segmentos, na próxima vez que o Audience Manager visualizar o dispositivo.

**Arquivo de dados de amostra**

O exemplo a seguir contém dados de segmento em tempo real de [!UICONTROL IRIS]. Lembre-se de que esses dados são apenas de amostra. Cada cliente pode ter diferentes requisitos de formatação para que o conteúdo possa variar.

```
{
    "ProcessTime": "Tue Jul 21 19:12:45 UTC 2015",
    "Client_ID": "111111",
    "AAM_Destination_Id": "22222",
    "User_count": "5",
    "Users": [
        {
            "AAM_UUID": "28272096202945091600036434734793744071",
            "DataPartner_UUID": "CAESEFdv5pk-Lurd8vL9Yfb3qFg",
            "Segments": [
                {
                    "Segment_ID": "1200598",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:12 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "35183292386788708387827965829455926157",
            "DataPartner_UUID": "CAESEF_d8blvZjchQ2WTzdB65yk",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:15 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "28012470144260632050402316345856327572",
            "DataPartner_UUID": "CAESEEPfHBiRjhkzvBPXQ-0MFRE|UzCESAAABOnFeHJy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:33 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "18981483751565214534184221210627150539",
            "DataPartner_UUID": "CAK4NDH0ESEE6NBEhoWDkB7s7ZY|VPYFQQAAASXPElL0",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:36 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "04761851136483019318109155624251711702",
            "DataPartner_UUID": "CAESEDkM5aSaKMV8MfaBhgSspmE|VYnTNwAAASzvVhxy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:42 UTC 2015"
                }
            ]
        }
    ]
}
```

## Servidor de cache de perfil (PCS) {#pcs}

Consulte [Componentes da coleta de dados](../../reference/system-components/components-data-collection.md).
