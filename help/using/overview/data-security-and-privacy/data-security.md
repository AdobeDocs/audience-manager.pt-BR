---
description: O Audience Manager leva a segurança e a privacidade dos dados muito a sério. Trabalhamos para proteger nossos sistemas e seus valiosos dados.
seo-description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-title: Data Security in Audience Manager
solution: Audience Manager
title: Segurança de dados no Audience Manager
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
feature: Data Governance & Privacy
exl-id: 94b70250-dca3-4c50-b4dd-bc37178a587e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 92%

---

# Segurança de dados no Audience Manager {#data-security}

O Audience Manager leva a segurança e a privacidade dos dados muito a sério. Trabalhamos para proteger nossos sistemas e seus valiosos dados.

As práticas de segurança do Audience Manager incluem auditorias externas e internas, registro de atividades, treinamento e outros procedimentos projetados para ajudar a proteger nossos sistemas e seus valiosos dados. Acreditamos que um produto seguro ajuda a criar e manter a confiança que os clientes depositam em nós.

No Audience Manager, dividimos a segurança em três categorias principais:

| Tipo de segurança | Oferece suporte para |
|---|---|
| **Segurança das informações** | Práticas de autenticação, criptografia e armazenamento de dados de nível empresarial |
| **Vazamento/transparência de dados** | Insight profundo e acionável sobre atividades no local que constituem ou contribuem para o vazamento de dados |
| **Aprimoramentos de processos/políticas** | Clientes, trabalhando com as práticas recomendadas do setor para manter a privacidade e a segurança dos dados |

## Sistemas, treinamento e acesso {#systems-training-access}

Processos que ajudam a manter nosso sistema e seus dados seguros.

**Validação de segurança externa:** O Audience Manager testa a segurança anualmente e trimestralmente.

* Anual: uma vez por ano, o Audience Manager é submetido a um teste de penetração completo feito por uma empresa independente de terceiros. O teste foi projetado para identificar vulnerabilidades de segurança no aplicativo. Os testes incluem varredura para script entre sites, injeções de SQL, manipulação de parâmetros de formulário e outras vulnerabilidades no nível do aplicativo.
* Trimestral: uma vez a cada trimestre, as equipes internas verificam vulnerabilidades de segurança. Esses testes incluem verificações de rede em busca de portas abertas e vulnerabilidades de serviço.

**Segurança de sistemas:**  Para ajudar a manter os dados seguros e privados, o Audience Manager:

* Bloqueia solicitações de endereços IP não autorizados.
* Protege dados por trás de firewalls, VPNs e com armazenamento da Nuvem privada virtual.
* Rastreia alterações nos bancos de dados de informações de controle e cliente com registro de auditoria com disparador. Esses registros rastreiam todas as alterações no nível do banco de dados, incluindo a ID do usuário e o endereço IP a partir dos quais as alterações são feitas.

**Ativos de segurança:** O Audience Manager tem uma equipe dedicada de operações de rede que monitora firewalls e dispositivos de detecção de intrusão. Somente o pessoal especializado tem acesso à nossa tecnologia e aos nossos dados de segurança.

**Treinamento em segurança:**  Internamente, nosso compromisso com a segurança se estende aos desenvolvedores que trabalham em nosso produto. A Adobe fornece treinamento formal para desenvolvedores sobre como criar aplicativos e serviços seguros.

**Acesso seguro:** O Audience Manager exige senhas seguras para fazer logon no sistema. Consulte os [requisitos de senha](../../reference/password-requirements.md).

## Privacidade e informações pessoais identificáveis (PII) {#pii}

Processos que ajudam a manter as informações pessoais seguras. Para obter mais informações sobre privacidade, consulte o [Centro de privacidade da Adobe](https://www.adobe.com/pt/privacy/advertising-services.html).

**Dados de PII:** O Audience Manager proíbe por contrato que clientes e parceiros de dados enviem informações PII para nosso sistema. Além disso, a ID de usuário exclusiva (UUID) não contém nem usa dados PII como parte do algoritmo de geração de ID.

**Endereços IP:** O Audience Manager coleta endereços IP. Os endereços IP são usados no processamento de dados e agregação de log. Eles também são necessários para pesquisas geográficas/locais e definição de metas. Além disso, todos os endereços IP nos arquivos de log retidos são ofuscados em 90 dias.

## Particionamento de dados {#data-partitioning}

Processos que ajudam a proteger dados de propriedade de clientes individuais.

**Particionamento de dados de características:** Seus dados ([!UICONTROL traits], IDs etc.) são particionados pelo cliente. Isso ajuda a evitar a exposição acidental às informações entre clientes diferentes. Por exemplo, os dados de características em cookies são particionados pelo cliente e armazenados em um subdomínio específico do cliente. Eles não podem ser lidos ou usados acidentalmente por outro cliente do Audience Manager. Além disso, os dados de características armazenados no [!UICONTROL Profile Cache Servers (PCS)] também são particionados pelo cliente. Isso evita que outros clientes usem acidentalmente seus dados em uma chamada de evento ou outra solicitação.

**Particionamento de dados em relatórios:** As IDs do cliente fazem parte da chave de identificação em todas as tabelas de relatórios e os queries de relatório são filtrados pela ID. Isso ajuda a impedir que seus dados apareçam nos relatórios de outro cliente do Audience Manager.

## Transferências S2S (Servidor para servidor de entrada) {#inbound-s2s}

O Adobe Audience Manager oferece suporte a dois métodos principais de transferência de arquivos de dados integrados S2S para nossos sistemas:

Ambos os métodos são projetados tendo em mente a segurança dos dados de clientes e parceiros enquanto os dados estão transitando entre seus sistemas e nosso sistema.

**SFTP:** Para a opção SFTP, a maioria dos clientes opta por fornecer arquivos por meio do protocolo FTP seguro (SFTP), que usa o protocolo SSH (Secure Shell). Esse método garante que os arquivos sejam criptografados enquanto estiverem transitando entre os sistemas do cliente e o sistema da Adobe. Para cada cliente, criamos um local de caixa suspensa aprisionado em nossos servidores SFTP, que está vinculado a uma conta de usuário no sistema. Somente os usuários do sistema interno credenciados e privilegiados do cliente podem acessar esse local da caixa suspensa. Esta prisão nunca é acessível a outros clientes.

**[!UICONTROL Amazon Web Services S3]via HTTPS:** Para a opção delivery S3, recomendamos que todos os clientes configurem seus clientes S3 para usar o método de criptografia HTTPS para transferências de arquivos (esse não é o padrão, portanto, ele deve estar configurado explicitamente). A opção HTTPS é compatível com a ferramenta de linha de comando s3cmd, bem como pelas bibliotecas S3 disponíveis em todas as principais linguagens de programação. Com essa opção HTTPS ativada, os dados do cliente são criptografados enquanto estão em trânsito para nossos sistemas. Para cada cliente, criamos um subdiretório S3 bucket separado que pode ser acessado somente pelas credenciais desse cliente e das de nossos usuários internos do sistema.

Para adicionar criptografia PGP aos arquivos de dados, consulte [Criptografia PGP de arquivo para tipos de dados de entrada](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Proteção de dados por omissão {#escaping-data}

Observe que o [!DNL Audience Manager] não omite dados de saída para protegê-los contra possíveis scripts entre sites (XSS), etc. É responsabilidade do cliente omitir dados recebidos.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] é um mecanismo de segurança da Web em todo o setor que ajuda a proteger contra ataques de sequestro de cookies e downgrade de protocolos.

A política instrui o navegador da Web que, uma vez feita uma chamada segura [!DNL HTTPS] para um determinado domínio, nenhuma chamada ([!DNL HTTP]) não segura subsequente deverá ser permitida para esse domínio. Essa ação protege contra ataques intermediários, onde um invasor pode tentar fazer o downgrade das chamadas [!DNL HTTPS] para chamadas [!DNL HTTP] não seguras.

Essa política melhora a segurança de dados entre clientes e servidores Adobe [Edge](../../reference/system-components/components-edge.md).

### Exemplo {#hsts-example}

Digamos que o domínio `yourcompany.demdex.com` envie tráfego para [!DNL DCS] via [!DNL HTTP]. O [!DNL HSTS] atualiza as chamadas para usar [!DNL HTTPS], e todas as chamadas [!DNL DCS] subsequentes provenientes de `yourcompany.demdex.com` usarão [!DNL HTTPS] em vez de [!DNL HTTP].

Consulte [HTTP Strict Transport Security - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) para obter mais informações sobre HSTS.
