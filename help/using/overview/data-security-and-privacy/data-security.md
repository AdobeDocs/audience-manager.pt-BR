---
description: O Audience Manager leva a segurança e privacidade dos dados muito a sério. Trabalhamos para manter nossos sistemas protegidos e proteger seus dados valiosos.
seo-description: O Audience Manager leva a segurança e privacidade dos dados muito a sério. Trabalhamos para manter nossos sistemas protegidos e proteger seus dados valiosos.
seo-title: Segurança de dados
solution: Audience Manager
title: Segurança de dados
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: b76e905ec890dbe8270177d142dddb351438b039

---


# Segurança de dados {#data-security}

O Audience Manager leva a segurança e privacidade dos dados muito a sério. Trabalhamos para manter nossos sistemas protegidos e proteger seus dados valiosos.

Audience Manager security practices include external and internal audits, activity logging, training, and other procedures designed to help protect our systems and your valuable data. We believe a secure product helps build and maintain the trust customers place in us.

In Audience Manager, we think about security in three main categories:

| Security Type | Fornece suporte para |
|---|---|
| **Information security** | Práticas de autenticação, criptografia e armazenamento de dados de nível empresarial |
| **Data leakage/transparency** | Insight profundo e acionável sobre atividades no local que constituem ou contribuem para a fuga de dados |
| **Aprimoramentos de processos/políticas** | Clients, by working with industry best practices for privacy and data security |

## Sistemas, treinamento e acesso {#systems-training-access}

Processes that help keep our system and your data secure.

**** External Security Validation:  Audience Manager tests security on an annual and quarterly basis.

* Yearly: Once a year, Audience Manager undergoes a full penetration test conducted by an independent third-party company. The test is designed to identify security vulnerabilities in the application. The tests include scanning for cross-site scripting, SQL injections, form parameter manipulation, and other application-level vulnerabilities.
* Trimestral: Uma vez a cada trimestre, as equipes internas verificam vulnerabilidades de segurança. Esses testes incluem verificações de rede em busca de portas abertas e vulnerabilidades de serviço.

**** Segurança de sistemas:  Para ajudar a manter os dados seguros e privados, o Audience Manager:

* Bloqueia solicitações de endereços IP não autorizados.
* Protege dados por trás de firewalls, VPNs e com armazenamento da Virtual Private Cloud.
* Rastreia alterações nos bancos de dados de informações de controle e cliente com registro de auditoria baseado em disparador. Esses registros rastreiam todas as alterações no nível do banco de dados, incluindo a ID do usuário e o endereço IP dos quais as alterações são feitas.

**** Ativos de segurança:  O Audience Manager tem uma equipe dedicada de operações de rede que monitora firewalls e dispositivos de detecção de intrusão. Somente os principais funcionários têm acesso à nossa tecnologia e aos nossos dados de segurança.

**** Treinamento em segurança:  Internamente, nosso compromisso com a segurança se estende aos desenvolvedores que trabalham em nosso produto. A Adobe fornece treinamento formal para desenvolvedores sobre como criar aplicativos e serviços seguros.

**** Acesso seguro:  O Audience Manager requer senhas seguras para fazer logon no sistema. Consulte os requisitos [de](../../reference/password-requirements.md)senha.

## Privacidade e informações pessoais identificáveis (PII) {#pii}

Processos que ajudam a manter as informações pessoais seguras. Para obter informações adicionais sobre privacidade, consulte o Centro [de privacidade da](https://www.adobe.com/privacy/advertising-services.html)Adobe.

**** Dados de PII:  O Audience Manager proíbe por contrato que clientes e parceiros de dados enviem informações PII para nosso sistema. Além disso, a ID de usuário exclusiva (UUID) não contém nem usa dados PII como parte do algoritmo de geração de ID.

**** Endereços IP:  O Audience Manager coleta endereços IP. IP addresses are used in data-processing and log-aggregation processes. Eles também são necessários para pesquisas geográficas/locais e definição de metas. Além disso, todos os endereços IP nos arquivos de log retidos são ofuscados em 90 dias.

## Particionamento de dados {#data-partitioning}

Processos que ajudam a proteger dados de propriedade de clientes individuais.

**** Trait Data Partitioning:  Your data (traits, IDs, etc.) is partitioned by client. This helps prevent accidental information exposure between different clients. For example, trait data in cookies is partitioned by customer and stored in a client-specific sub-domain. It cannot be read or used accidentally by another Audience Manager client. Além disso, os dados de características armazenados no [!UICONTROL Profile Cache Servers (PCS)] são também particionados pelo cliente. Isso impede que outros clientes usem acidentalmente seus dados em uma chamada de evento ou outra solicitação.

**** Particionamento de dados em relatórios:  As IDs do cliente fazem parte da chave de identificação em todas as tabelas de relatórios e as consultas de relatório são filtradas por ID. Isso ajuda a impedir que seus dados apareçam nos relatórios de outro cliente do Audience Manager.

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager supports two main methods of transferring S2S on-boarded data files to our systems:

Both methods are designed with the security of our customer and partner data in mind while data is in flight between their systems and our system.

**** SFTP: For the SFTP option, most customers choose to deliver files via the Secure FTP (SFTP) protocol, which uses the Secure Shell (SSH) protocol. Este método garante que os arquivos sejam criptografados enquanto estiverem em voo entre os sistemas do cliente e o sistema da Adobe. Para cada cliente, criamos um local de caixa suspensa preso em nossos servidores SFTP, que está vinculado a uma conta de usuário no sistema. Somente os usuários do sistema interno credenciados e privilegiados do cliente podem acessar esse local da caixa suspensa. Esta prisão nunca é acessível a outros clientes.

**** Amazon Web Services S3 via HTTPS: Para a opção de entrega S3, recomendamos que todos os clientes configurem seus clientes S3 para usar o método de criptografia HTTPS para transferências de arquivos (esse não é o padrão, portanto, deve ser configurado explicitamente). A opção HTTPS é suportada pela ferramenta de linha de comando s3cmd, bem como pelas bibliotecas S3 disponíveis em todas as principais linguagens de programação. Com essa opção HTTPS ativada, os dados do cliente são criptografados enquanto estão em voo para nossos sistemas. Para cada cliente, criamos um subdiretório S3 bucket separado que pode ser acessado somente pelas credenciais desse cliente e das de nossos usuários internos do sistema.

Para adicionar criptografia PGP aos arquivos de dados, consulte Criptografia PGP [de arquivo para tipos](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)de dados de entrada.

## Proteção de dados por omissão {#escaping-data}

Observe que [!DNL Audience Manager] não escapa aos dados de saída para protegê-los contra possíveis scripts entre sites (XSS), etc. É responsabilidade do cliente escapar aos dados recebidos.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] é um mecanismo de segurança da Web em todo o setor que ajuda a proteger contra ataques de sequestro de cookies e downgrade de protocolos.

A política instrui o navegador da Web que, uma vez feita uma [!DNL HTTPS] chamada segura para um determinado domínio, nenhuma chamada ([!DNL HTTP]) não segura subsequente deverá ser permitida para esse domínio. Isso protege contra ataques do homem no meio, onde um atacante pode tentar diminuir [!DNL HTTPS] chamadas para [!DNL HTTP] chamadas não seguras."

Essa política melhora a segurança de dados entre clientes e servidores Adobe [Edge](../../reference/system-components/components-edge.md) .

### Exemplo {#hsts-example}

When trying to access ,  will automatically upgrade the request to  , in case the browser doesn’t automatically request the  domain.`http://bank.demdex.com`[!DNL HSTS]`https://bank.demdex.com`[!DNL HTTPS]

Consulte Segurança de Transporte Restrita [HTTP - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) para obter mais informações sobre HSTS.
