---
description: Os componentes da ação de dados incluem Feeds de dados do cliente, o Servidor de coleta de dados, editores SFTP/S3/HTTP, IRIS e o Servidor de cache de perfis.
seo-description: Data action components include Customer Data Feeds, the Data Collection Server, SFTP/S3/HTTP publishers, IRIS, and the Profile Cache Server.
seo-title: Data Action Components
solution: Audience Manager
title: Componentes de ação de dados
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: System Components
exl-id: 8065c19f-1930-4164-a952-1686aa5cb622
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 1%

---

# Componentes de ação de dados{#data-action-components}

Os componentes da ação de dados incluem Feeds de dados do cliente, o Servidor de coleta de dados, editores SFTP/S3/HTTP, IRIS e o Servidor de cache de perfis.

<!-- 

c_compact.xml

 -->

Os componentes de ação são sistemas e processos que permitem mover dados de e para [!DNL Audience Manager] e (por falta de uma frase melhor) fazer coisas com eles. Estes [!DNL Audience Manager] componentes incluem:

## Feeds de dados do cliente (CDF) {#cdf}

[!UICONTROL CDF] são arquivos enviados de hora em hora para os clientes. Eles contêm IDs de usuário juntamente com IDs de segmento associadas, IDs de característica e outros dados. Para obter mais informações, consulte [Visão geral do feed de dados do cliente](../../features/cdf-files.md).

## Servidor de coleta de dados (DCS) {#dcs}

Consulte [Componentes da coleta de dados](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

Os editores [!UICONTROL SFTP/S3] recebem dados de ID sincronizados de [!UICONTROL Outbound Feed Converter]. Quando esses arquivos estiverem prontos, o [!UICONTROL SFTP/S3 publishers] enviará esses dados para um destino especificado pelo cliente. Esses arquivos contêm dados de ID sincronizados com um mapeamento de um para muitos de [!DNL Audience Manager] IDs de usuário (UUID) para:

* ID de dispositivo/IDs de provedor de dados (DPUUID)
* IDs de segmento qualificado
* IDs de características

[!DNL Audience Manager] clientes não têm acesso a recursos que controlam diretamente o [!UICONTROL SFPT/S3 publishers]. Os clientes usam esse serviço indiretamente ao criar e enviar dados para destinos. O sistema [!UICONTROL SFTP/S3] é, essencialmente, um processo de trabalho automatizado que é executado em intervalos programados.

## ÍRIS {#iris}

Na mitologia grega, [!UICONTROL Iris] é uma figura que viaja e entrega mensagens rapidamente. O sistema [!UICONTROL IRIS] é um homônimo que reflete as características desta figura do mundo antigo. Em termos modernos, o [!UICONTROL IRIS] é um serviço de sincronização de cookies de baixa latência e alta frequência e de transferência de dados.

[!UICONTROL IRIS] funciona com o mesmo tipo de dados que o sistema [!UICONTROL SFTP/S3]. No entanto, [!UICONTROL IRIS] é diferente porque envia dados para destinos em tempo real, em vez de em intervalos definidos. Este é um sistema separado porque os editores do [!UICONTROL SFTP/S3] não podem enviar dados para um destino HTTP e não foram projetados para transferências de dados em tempo real.

Não há controles de interface do usuário que permitam aos clientes trabalhar diretamente com [!UICONTROL IRIS]. Os clientes trabalham indiretamente com o [!UICONTROL IRIS] ao criar e enviar dados para destinos, bem como para outros processos que exigem transferências rápidas de dados.

Exemplos de serviços e recursos do [!UICONTROL IRIS] incluem:

* Fornecendo sincronização rápida (em 30 segundos) para cookies e segmentos. Ele pode sincronizar o cookie [!DNL Audience Manager], os cookies de parceiros ou ambos.
* Transferências de dados em tempo real. [!UICONTROL IRIS] é responsável por enviar eventos de qualificação de segmento em tempo real a um parceiro ou outro destino. Esses dados são formatados em JSON e enviados por uma solicitação HTTP `POST`.

* Transferências de dados em massa de servidor para servidor: se você trocar grandes quantidades de dados com o [!DNL Audience Manager], o [!UICONTROL IRIS] será o sistema usado pelos seus servidores para transferir dados.

* Infraestrutura confiável que funciona em escala e é tolerante a falhas. Os sistemas que alimentam o [!UICONTROL IRIS] incluem o Amazon SQS, o Amazon EC2 e o Cassandra.

**Regras de Mapeamento de Segmentos**

Para otimizar o tráfego entre [!UICONTROL IRIS] e destinos de segmentos, [!UICONTROL IRIS] envia segmentos para destinos com base em um conjunto de regras.

1. **Nova qualificação de segmento**: quando um dispositivo se qualifica para um novo segmento, o [!UICONTROL IRIS] envia todos os segmentos associados a esse dispositivo para todos os destinos mapeados para esses segmentos.

1. **Nova desqualificação de segmento**: quando um dispositivo não se qualifica mais para um segmento, [!UICONTROL IRIS] envia todas as qualificações e desqualificações de segmento associadas a esse dispositivo para todos os destinos mapeados para esses segmentos.

1. **Atualizações do mapeamento de destino**: quando um mapeamento de destino é atualizado, o [!UICONTROL IRIS] envia todos os segmentos associados a um dispositivo para todos os destinos mapeados para esses segmentos, na próxima vez que o Audience Manager visualizar o dispositivo.

1. **Atualizações do gráfico de dispositivos**: quando qualquer ID de dispositivo é adicionada ou removida do gráfico de dispositivos usado para avaliar um segmento, o [!UICONTROL IRIS] envia todos os segmentos associados a esse dispositivo para todos os destinos mapeados para esses segmentos, na próxima vez que o Audience Manager visualizar o dispositivo.

>[!IMPORTANT]
>
>Se o Audience Manager não detectar nenhuma das atualizações acima por 3 dias consecutivos, o [!UICONTROL IRIS] enviará todos os segmentos associados a um dispositivo para todos os destinos mapeados para esses segmentos, na próxima vez que o Audience Manager encontrar o dispositivo.

**Arquivo de dados de exemplo**

O exemplo a seguir contém dados de segmento em tempo real de [!UICONTROL IRIS]. Lembre-se de que isto é apenas dados de amostra. Cada cliente pode ter requisitos de formatação diferentes, de modo que o conteúdo pode variar.

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
