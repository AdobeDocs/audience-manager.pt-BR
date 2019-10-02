---
description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-title: Data Security
solution: Audience Manager
title: Data Security
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 34884e3212d50237c73fdc6aa163d90c29a642f5

---


# Data Security {#data-security}

O Audience Manager leva a segurança e privacidade dos dados muito a sério. We work to keep our systems secure and protect your valuable data.

As práticas de segurança do Audience Manager incluem auditorias externas e internas, registro de atividades, treinamento e outros procedimentos projetados para ajudar a proteger nossos sistemas e seus dados valiosos. Acreditamos que um produto seguro ajuda a criar e manter a confiança que os clientes depositam em nós.

No Audience Manager, pensamos sobre segurança em três categorias principais:

| Security Type | Fornece suporte para |
|---|---|
| **Segurança das informações** | Práticas de autenticação, criptografia e armazenamento de dados de nível empresarial |
| **Fuga/transparência de dados** | Insight profundo e acionável sobre atividades no local que constituem ou contribuem para a fuga de dados |
| **Aprimoramentos de processos/políticas** | Clientes, trabalhando com as práticas recomendadas do setor para privacidade e segurança de dados |

## Sistemas, treinamento e acesso {#systems-training-access}

Processos que ajudam a manter nosso sistema e seus dados protegidos.

**** Validação de Segurança Externa:  O Audience Manager testa a segurança anualmente e trimestralmente.

* Anualmente: Uma vez por ano, o Audience Manager é submetido a um teste completo de penetração realizado por uma empresa independente. O teste foi projetado para identificar vulnerabilidades de segurança no aplicativo. Os testes incluem varredura para script entre sites, injeções de SQL, manipulação de parâmetros de formulário e outras vulnerabilidades no nível do aplicativo.
* Trimestral: Uma vez a cada trimestre, as equipes internas verificam vulnerabilidades de segurança. Esses testes incluem verificações de rede em busca de portas abertas e vulnerabilidades de serviço.

**** Segurança de sistemas:  Para ajudar a manter os dados seguros e privados, o Audience Manager:

* Bloqueia solicitações de endereços IP não autorizados.
* Protege dados por trás de firewalls, VPNs e com armazenamento da Virtual Private Cloud.
* Tracks changes in the customer and control-information databases with trigger-based audit logging. Esses registros rastreiam todas as alterações no nível do banco de dados, incluindo a ID do usuário e o endereço IP dos quais as alterações são feitas.

**** Ativos de segurança:  O Audience Manager tem uma equipe dedicada de operações de rede que monitora firewalls e dispositivos de detecção de intrusão. Somente os principais funcionários têm acesso à nossa tecnologia e aos nossos dados de segurança.

**** Treinamento em segurança:  Internamente, nosso compromisso com a segurança se estende aos desenvolvedores que trabalham em nosso produto. A Adobe fornece treinamento formal para desenvolvedores sobre como criar aplicativos e serviços seguros.

**** Acesso seguro:  O Audience Manager requer senhas seguras para fazer logon no sistema. Consulte os requisitos [de](../../reference/password-requirements.md)senha.

## Privacy and Personally Identifiable Information (PII) {#pii}

Processes that help keep personal information safe. For additional privacy information, see the Adobe Privacy Center.[](https://www.adobe.com/privacy/advertising-services.html)

**** PII Data:  Audience Manager contractually prohibits customers and data partners from sending PII information into our system. Additionally, the Unique User ID (UUID) does not contain or use PII data as part of the ID-generation algorithm.

**** Endereços IP:  O Audience Manager coleta endereços IP. IP addresses are used in data-processing and log-aggregation processes. They are also required for geographic/location look-ups and targeting. Additionally, all IP addresses within retained log files are obfuscated within 90 days.

## Data Partitioning {#data-partitioning}

Processes that help protect data owned by individual clients.

**** Trait Data Partitioning:  Your data (traits, IDs, etc.) is partitioned by client. Isso ajuda a evitar a exposição acidental às informações entre clientes diferentes. For example, trait data in cookies is partitioned by customer and stored in a client-specific sub-domain. Não pode ser lido ou usado acidentalmente por outro cliente do Audience Manager. Furthermore, trait data stored in the  is also partitioned by customer. [!UICONTROL Profile Cache Servers (PCS)] Isso impede que outros clientes usem acidentalmente seus dados em uma chamada de evento ou outra solicitação.

**** Particionamento de dados em relatórios:  As IDs do cliente fazem parte da chave de identificação em todas as tabelas de relatórios e as consultas de relatório são filtradas por ID. Isso ajuda a impedir que seus dados apareçam nos relatórios de outro cliente do Audience Manager.

## Transferências S2S (Servidor para Servidor de Entrada) {#inbound-s2s}

O Adobe Audience Manager oferece suporte a dois métodos principais de transferência de arquivos de dados integrados S2S para nossos sistemas:

Ambos os métodos são projetados tendo em mente a segurança de nossos dados de clientes e parceiros enquanto os dados estão em voo entre seus sistemas e nosso sistema.

**** SFTP: Para a opção SFTP, a maioria dos clientes opta por fornecer arquivos por meio do protocolo FTP seguro (SFTP), que usa o protocolo SSH (Secure Shell). Este método garante que os arquivos sejam criptografados enquanto estiverem em voo entre os sistemas do cliente e o sistema da Adobe. Para cada cliente, criamos um local de caixa suspensa preso em nossos servidores SFTP, que está vinculado a uma conta de usuário no sistema. Somente os usuários do sistema interno credenciados e privilegiados do cliente podem acessar esse local da caixa suspensa. Esta prisão nunca é acessível a outros clientes.

**** Amazon Web Services S3 via HTTPS: Para a opção de entrega S3, recomendamos que todos os clientes configurem seus clientes S3 para usar o método de criptografia HTTPS para transferências de arquivos (esse não é o padrão, portanto, deve ser configurado explicitamente). A opção HTTPS é suportada pela ferramenta de linha de comando s3cmd, bem como pelas bibliotecas S3 disponíveis em todas as principais linguagens de programação. Com essa opção HTTPS ativada, os dados do cliente são criptografados enquanto estão em voo para nossos sistemas. Para cada cliente, criamos um subdiretório S3 bucket separado que pode ser acessado somente pelas credenciais desse cliente e das de nossos usuários internos do sistema.

Para adicionar criptografia PGP aos arquivos de dados, consulte Criptografia PGP [de arquivo para tipos](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)de dados de entrada.

## Proteção de dados por omissão {#escaping-data}

Observe que [!DNL Audience Manager] não escapa aos dados de saída para protegê-los contra possíveis scripts entre sites (XSS), etc. É responsabilidade do cliente escapar aos dados recebidos.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] é um mecanismo de segurança da Web em todo o setor que ajuda a proteger contra ataques de sequestro de cookies e downgrade de protocolos.

A política instrui o navegador da Web que, uma vez feita uma [!DNL HTTPS] chamada segura para um determinado domínio, nenhuma chamada ([!DNL HTTP]) não segura subsequente deverá ser permitida para esse domínio. This protects against man-in-the-middle attacks, where an attacker might try to downgrade  calls to unsecured  calls.”[!DNL HTTPS][!DNL HTTP]

Essa política melhora a segurança de dados entre clientes e servidores Adobe [Edge](../../reference/system-components/components-edge.md) .

### Exemplo {#hsts-example}

Digamos que o `yourcompany.demdex.com` domínio envia o tráfego para o [!DNL DCS] canal [!DNL HTTP]. [!DNL HSTS] atualiza as chamadas a serem usadas [!DNL HTTPS] em vez disso, e todas as [!DNL DCS] chamadas subsequentes provenientes de `yourcompany.demdex.com` serão usadas [!DNL HTTPS] em vez de [!DNL HTTP].

Consulte Segurança de Transporte Restrita [HTTP - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) para obter mais informações sobre HSTS.
