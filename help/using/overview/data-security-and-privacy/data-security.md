---
description: O Audience Manager leva a segurança e a privacidade de dados muito a sério. Trabalhamos para manter nossos sistemas protegidos e proteger seus dados valiosos.
seo-description: O Audience Manager leva a segurança e a privacidade de dados muito a sério. Trabalhamos para manter nossos sistemas protegidos e proteger seus dados valiosos.
seo-title: Segurança de dados
solution: Audience Manager
title: Segurança de dados
uuid: 33 ad 19 ca -4690-4 d 97-853 b -1882 d 7 d 4 ac 01
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Security {#data-security}

O Audience Manager leva a segurança e a privacidade de dados muito a sério. Trabalhamos para manter nossos sistemas protegidos e proteger seus dados valiosos.

As práticas de segurança do Audience Manager incluem auditorias externas e internas, registro de atividades, treinamento e outros procedimentos projetados para ajudar a proteger nossos sistemas e seus dados valiosos. Acreditamos que um produto seguro ajuda a criar e manter os clientes confiáveis colocados em nós.

No Audience Manager, pensamos em segurança em três categorias principais:

| Tipo de segurança | Oferece suporte para |
|---|---|
| **Segurança de informações** | Práticas de autenticação, criptografia e armazenamento de dados no nível empresarial |
| **Vazamento de dados/transparência** | Insight profundo e acionável sobre atividades no site que constituem ou contribuem para o vazamento de dados |
| **Aprimoramentos de processo/política** | Clientes, trabalhando com as práticas recomendadas do setor para privacidade e segurança de dados |

## Systems, Training, and Access {#systems-training-access}

Processos que ajudam a manter nosso sistema e seus dados protegidos.

**Validação de segurança externa:** O Audience Manager testa segurança de forma anual e trimestral.

* Anualmente: Uma vez por ano, o Audience Manager passa a ser um teste de penetração completo conduzido por uma empresa terceirizada independente. O teste foi projetado para identificar vulnerabilidades de segurança no aplicativo. Os testes incluem digitalização para scripts entre sites, entradas SQL, manipulação do parâmetro de formulário e outras vulnerabilidades de nível de aplicativo.
* Trimestral: Uma vez a cada trimestre, as equipes internas verificam vulnerabilidades de segurança. Esses testes incluem varredura de rede para portas abertas e vulnerabilidades de serviço.

**Segurança Systems:** Para ajudar a manter os dados seguros e privados, o Audience Manager:

* Bloqueia solicitações de endereços IP não autorizados.
* Protege dados por trás de firewalls, vpns e com armazenamento virtual da nuvem virtual.
* Rastreia alterações nos bancos de dados de clientes e informações de controle com registro de auditoria baseado em acionamento. Esses logs rastreiam todas as alterações no nível do banco de dados, incluindo a ID do usuário e o endereço IP a partir do qual as alterações são feitas.

**Ativos de segurança:** O Audience Manager tem uma equipe dedicada de operações de rede que monitora firewalls e dispositivos de detecção intrusão. Somente a equipe-chave tem acesso à nossa tecnologia de segurança e dados.

**Treinamento de segurança:** Internamente, nosso compromisso com a segurança se estende para desenvolvedores que trabalham em nosso produto. A Adobe fornece treinamento formal aos desenvolvedores sobre como construir aplicativos e serviços seguros.

**Acesso seguro:** O Audience Manager requer senhas fortes para fazer logon no sistema. See [password requirements](../../reference/password-requirements.md).

## Privacy and Personally Identifiable Information (PII) {#pii}

Processos que ajudam a manter as informações pessoais seguras. For additional privacy information, see the [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

**Dados PII:** O Audience Manager proíbe que os clientes e os parceiros de dados enviem informações PII para o nosso sistema. Além disso, a ID de usuário exclusiva (UUID) não contém ou usa dados PII como parte do algoritmo de geração de ID.

**Endereços IP:** O Audience Manager coleta endereços IP. Endereços IP são usados em processos de processamento de dados e agregação de log. Eles também são necessários para consultas e segmentações geográficas/locais. Além disso, todos os endereços IP nos arquivos de log retidos são ofuscados dentro de 90 dias.

## Data Partitioning {#data-partitioning}

Processos que ajudam a proteger os dados de propriedade dos clientes individuais.

**Partitagem de dados de características:** Seus dados (características, IDs etc.) é dividido por cliente. Isso ajuda a evitar a exposição acidental de informações entre clientes diferentes. Por exemplo, os dados características em cookies são divididos por clientes e armazenados em um subdomínio específico do cliente. Ele não pode ser lido ou usado acidentalmente por outro cliente do Audience Manager. Furthermore, trait data stored in the [!UICONTROL Profile Cache Servers (PCS)] is also partitioned by customer. Isso impede que outros clientes usem acidentalmente seus dados em uma chamada de evento ou outra solicitação.

**Separação de dados em relatórios:** As IDs de cliente fazem parte da chave de identificação em todas as tabelas de relatório e as consultas de relatório são filtradas por ID. Isso ajuda a impedir que seus dados apareçam nos relatórios de outro cliente do Audience Manager.

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

O Adobe Audience Manager oferece suporte a dois métodos principais para transferir arquivos de dados S 2 S integrados para nossos sistemas:

Ambos os métodos são projetados com a segurança de nossos dados do cliente e do parceiro em mente enquanto os dados estão em voos entre seus sistemas e nosso sistema.

**SFTP:** Para a opção SFTP, a maioria dos clientes escolhe entregar arquivos por meio do protocolo FTP seguro (SFTP), que usa o protocolo Seguro de shell (SSH). Esse método garante que os arquivos sejam criptografados enquanto estiverem em voos entre os sistemas do cliente e o sistema da Adobe. Para cada cliente, criamos um local de queda de caixa enviado em nossos servidores SFTP, que é vinculado a uma conta de usuário nesse sistema. Somente os usuários internos dos sistemas internos e neutros do cliente podem acessar esse local de caixa de soltar enviado. Este jail nunca pode ser acessado para outros clientes.

**Amazon Web Services S 3 via HTTPS:** Para a opção de entrega S 3, recomendamos que todos os clientes configurem seus clientes S 3 para usar o método de criptografia HTTPS para transferências de arquivos (esse não é o padrão, portanto, deve ser explicitamente configurado). A opção HTTPS é suportada pela ferramenta de linha de comando s 3 cmd, bem como as bibliotecas S 3 disponíveis em cada linguagem de programação importante. Com essa opção HTTPS ativada, os dados do cliente são criptografados enquanto estão em voos para nossos sistemas. Para cada cliente, criamos um subdiretório S 3 separado, que pode ser acessado apenas pelas credenciais do cliente e pelos de nossos usuários internos do sistema.

To add PGP encryption to your data files, see [File PGP Encryption for Inbound Data Types](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Protecting Data by Escaping {#escaping-data}

Note that [!DNL Audience Manager] does not escape outgoing data to secure it against possible cross-site scripting (XSS), etc. É responsabilidade do cliente ignorar os dados de entrada.
