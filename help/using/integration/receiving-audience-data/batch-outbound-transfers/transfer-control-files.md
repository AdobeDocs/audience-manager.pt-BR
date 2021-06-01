---
description: Os arquivos de controle de transferência (.info) fornecem informações de metadados sobre transferências de arquivos para que os parceiros possam verificar se o Audience Manager lidou com transferências de arquivos corretamente.
seo-description: Os arquivos de controle de transferência (.info) fornecem informações de metadados sobre transferências de arquivos para que os parceiros possam verificar se o Audience Manager lidou com transferências de arquivos corretamente.
seo-title: Arquivos de controle de transferência para transferências de arquivos de log
solution: Audience Manager
title: Arquivos de controle de transferência para transferências de arquivos de log
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Transferências de dados de saída
exl-id: 4fd1aab1-2dc2-4de9-97be-58e79825db40
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 6%

---

# Arquivos de controle de transferência para transferências de arquivos de log {#transfer-control-files-for-log-file-transfers}

Os arquivos de controle de transferência ([!DNL .info]) fornecem informações de metadados sobre transferências de arquivos para que os parceiros possam verificar se as transferências de arquivos tratadas pelo Audience Manager foram feitas corretamente.

[!DNL Audience Manager] envia um arquivo de controle de transferência para um parceiro com cada transferência de arquivo. Devido à natureza de vários threads do editor [!DNL FTP], o arquivo de controle de transferência pode ser enviado antes que os arquivos reais sejam transferidos.

Os metadados no arquivo [!DNL .info] permitem aos parceiros:

* Determinar quando um ciclo de transferência completo está concluído (o número total de arquivos na sequência foi entregue);
* Determine se um determinado arquivo na sequência está completo/correto (examinando o tamanho do arquivo em bytes e o número total de linhas);
* Valide o número de linhas em arquivos brutos em relação ao número de linhas depois que os arquivos tiverem sido carregados no banco de dados no final do recebimento (tamanho do arquivo em linhas).

## Convenções de nomenclatura de arquivo {#file-naming-conventions}

O arquivo de controle de transferência tem o mesmo nome da raiz do lote/sequência com uma extensão de arquivo [!DNL .info].s

Por exemplo, se o primeiro arquivo na sequência tiver sido nomeado: [!DNL ftp_12345_67890_full_1500727351632-1.sync], o arquivo de controle seria nomeado como [!DNL ftp_12345_67890_iter_1500727351632.info].

## Formato do arquivo {#file-format}

```
{
  Files: [
    {
      FileByteSize: 293029329,
      FileLineCount: 36893908,
      FileName: "ftp_12345_67890_full_1500727351632-1.sync.gz",
      FileSequenceNumber: 1,
      md5: "983g634be2ad5263c6a6c4958bf61d9f"
    },
    {
      FileByteSize: 293039238,
      FileLineCount: 36895184,
      FileName: "ftp_12345_67890_full_1500727351632-2.sync.gz",
      FileSequenceNumber: 2,
      md5: "6sn9907c8e78cfd78409622e7b55a984"
    },
    {
      FileByteSize: 293050833,
      FileLineCount: 36896787,
      FileName: "ftp_12345_67890_full_1500727351632-3.sync.gz",
      FileSequenceNumber: 3,
      md5: "7cdfb8e74cd6cec1jy6vel21ccb4a962"
    },
    {
      FileByteSize: 218425764,
      FileLineCount: 27498226,
      FileName: "ftp_12345_67890_full_1500727351632-4.sync.gz",
      FileSequenceNumber: 4,
      md5: "7hs53149f8a2444457g968f04cbbdee5"
    }
  ],
  Totals: {
    FileName: "ftp_12345_67890_full_1500727351632.sync",
    TotalByteSize: 1097545164,
    TotalNumberFiles: 4,
    TotalNumberLines: 138184105
    }
}
```

>[!NOTE]
>
> Os números totais do lote são exclusivos do próprio arquivo [!DNL .info]. Ou seja, os totais não incluem o arquivo [!DNL .info], o tamanho do byte ou a contagem de linhas.
>
> Os tamanhos de bytes de arquivos e contagens de linha incluem qualquer linha/linha de cabeçalho e espaçador (em branco). Para obter a contagem de linhas/linhas de dados reais, subtraia cabeçalhos.
>
> O total de linhas em lote e o total de bytes incluem qualquer linha de cabeçalho e espaço.
