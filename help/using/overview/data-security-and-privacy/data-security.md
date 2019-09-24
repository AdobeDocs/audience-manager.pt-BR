---
description: O Audience Manager leva a segurança e privacidade dos dados muito a sério. Trabalhamos para manter nossos sistemas protegidos e proteger seus dados valiosos.
seo-description: O Audience Manager leva a segurança e privacidade dos dados muito a sério. We work to keep our systems secure and protect your valuable data.
seo-title: Segurança de dados
solution: Audience Manager
title: Segurança de dados
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 9e1abb305c66a4adf6a42a7873144222491692f9

---


# Segurança de dados {#data-security}

O Audience Manager leva a segurança e privacidade dos dados muito a sério. Trabalhamos para manter nossos sistemas protegidos e proteger seus dados valiosos.

As práticas de segurança do Audience Manager incluem auditorias externas e internas, registro de atividades, treinamento e outros procedimentos projetados para ajudar a proteger nossos sistemas e seus dados valiosos. Acreditamos que um produto seguro ajuda a criar e manter a confiança que os clientes depositam em nós.

No Audience Manager, pensamos sobre segurança em três categorias principais:

| Tipo de segurança | Fornece suporte para |
|---|---|
| **Segurança das informações** | Práticas de autenticação, criptografia e armazenamento de dados de nível empresarial |
| **Fuga/transparência de dados** | Insight profundo e acionável sobre atividades no local que constituem ou contribuem para a fuga de dados |
| **Aprimoramentos de processos/políticas** | Clientes, trabalhando com as práticas recomendadas do setor para privacidade e segurança de dados |

## Sistemas, treinamento e acesso {#systems-training-access}

Processos que ajudam a manter nosso sistema e seus dados protegidos.

**** Validação de Segurança Externa:  O Audience Manager testa a segurança anualmente e trimestralmente.

* Anualmente: Uma vez por ano, o Audience Manager é submetido a um teste completo de penetração realizado por uma empresa independente. O teste foi projetado para identificar vulnerabilidades de segurança no aplicativo. Os testes incluem varredura para script entre sites, injeções de SQL, manipulação de parâmetros de formulário e outras vulnerabilidades no nível do aplicativo.
* Trimestral: Uma vez a cada trimestre, as equipes internas verificam vulnerabilidades de segurança. These tests include network scans for open ports and service vulnerabilities.

**** Systems Security:  To help keep data safe and private, Audience Manager:

* Blocks requests from unauthorized IP addresses.
* Protege dados por trás de firewalls, VPNs e com armazenamento da Virtual Private Cloud.
* Tracks changes in the customer and control-information databases with trigger-based audit logging. Esses registros rastreiam todas as alterações no nível do banco de dados, incluindo a ID do usuário e o endereço IP dos quais as alterações são feitas.

**** Ativos de segurança:  O Audience Manager tem uma equipe dedicada de operações de rede que monitora firewalls e dispositivos de detecção de intrusão. Only key personnel have access to our security technology and data.

**** Security Training:  Internally, our commitment to security extends to developers who work on our product. Adobe provides formal training to developers on how to build secure applications and services.

**** Secure Access:  Audience Manager requires strong passwords to log on to the system. See password requirements.[](../../reference/password-requirements.md)

## Privacy and Personally Identifiable Information (PII) {#pii}

Processes that help keep personal information safe. Para obter informações adicionais sobre privacidade, consulte o Centro [de privacidade da](https://www.adobe.com/privacy/advertising-services.html)Adobe.

**** PII Data:  Audience Manager contractually prohibits customers and data partners from sending PII information into our system. Additionally, the Unique User ID (UUID) does not contain or use PII data as part of the ID-generation algorithm.

**** Endereços IP:  O Audience Manager coleta endereços IP. Os endereços IP são usados em processos de processamento de dados e agregação de log. They are also required for geographic/location look-ups and targeting. Additionally, all IP addresses within retained log files are obfuscated within 90 days.

## Particionamento de dados {#data-partitioning}

Processos que ajudam a proteger dados de propriedade de clientes individuais.

**** Particionamento de dados de características:  Seus dados (características, IDs etc.) é particionado pelo cliente. Isso ajuda a evitar a exposição acidental às informações entre clientes diferentes. Por exemplo, os dados de características em cookies são particionados pelo cliente e armazenados em um subdomínio específico do cliente. Não pode ser lido ou usado acidentalmente por outro cliente do Audience Manager. Além disso, os dados de características armazenados no [!UICONTROL Profile Cache Servers (PCS)] são também particionados pelo cliente. Isso impede que outros clientes usem acidentalmente seus dados em uma chamada de evento ou outra solicitação.

**** Particionamento de dados em relatórios:  As IDs do cliente fazem parte da chave de identificação em todas as tabelas de relatórios e as consultas de relatório são filtradas por ID. Isso ajuda a impedir que seus dados apareçam nos relatórios de outro cliente do Audience Manager.

## Transferências S2S (Servidor para Servidor de Entrada) {#inbound-s2s}

O Adobe Audience Manager oferece suporte a dois métodos principais de transferência de arquivos de dados integrados S2S para nossos sistemas:

Ambos os métodos são projetados tendo em mente a segurança de nossos dados de clientes e parceiros enquanto os dados estão em voo entre seus sistemas e nosso sistema.

**** SFTP: Para a opção SFTP, a maioria dos clientes opta por fornecer arquivos por meio do protocolo FTP seguro (SFTP), que usa o protocolo SSH (Secure Shell). Este método garante que os arquivos sejam criptografados enquanto estiverem em voo entre os sistemas do cliente e o sistema da Adobe. Para cada cliente, criamos um local de caixa suspensa preso em nossos servidores SFTP, que está vinculado a uma conta de usuário no sistema. Somente os usuários do sistema interno credenciados e privilegiados do cliente podem acessar esse local da caixa suspensa. Esta prisão nunca é acessível a outros clientes.

**** Amazon Web Services S3 via HTTPS: Para a opção de entrega S3, recomendamos que todos os clientes configurem seus clientes S3 para usar o método de criptografia HTTPS para transferências de arquivos (esse não é o padrão, portanto, deve ser configurado explicitamente). A opção HTTPS é suportada pela ferramenta de linha de comando s3cmd, bem como pelas bibliotecas S3 disponíveis em todas as principais linguagens de programação. Com essa opção HTTPS ativada, os dados do cliente são criptografados enquanto estão em voo para nossos sistemas. Para cada cliente, criamos um subdiretório S3 bucket separado que pode ser acessado somente pelas credenciais desse cliente e das de nossos usuários internos do sistema.

Para adicionar criptografia PGP aos arquivos de dados, consulte Criptografia PGP [de arquivo para tipos](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)de dados de entrada.

## Protecting Data by Escaping {#escaping-data}

Note that  does not escape outgoing data to secure it against possible cross-site scripting (XSS), etc. [!DNL Audience Manager] It is the responsibility of the client to escape incoming data.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] é um mecanismo de política de segurança da Web que ajuda a proteger contra ataques de sequestro de cookies e downgrade de protocolos, não permitindo o [!DNL HTTP] tráfego e atualizando de forma transparente todo o [!DNL HTTP] tráfego para [!DNL HTTPS].

Essa política melhora a segurança de dados entre clientes e servidores Adobe Edge.

### Exemplo {#hsts-example}

When trying to access ,  will automatically upgrade the request to  , in case the browser doesn’t automatically request the  domain.`http://bank.demdex.com`[!DNL HSTS]`https://bank.demdex.com`[!DNL HTTPS]

See HTTP Strict Transport Security - Wikipedia for more information about HSTS.[](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)
