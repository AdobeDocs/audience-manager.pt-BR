---
description: A Audience Manager leva a segurança e a privacidade dos dados muito a sério. Trabalhamos para manter nossos sistemas protegidos e proteger seus dados valiosos.
seo-description: A Audience Manager leva a segurança e a privacidade dos dados muito a sério. Trabalhamos para manter nossos sistemas protegidos e proteger seus dados valiosos.
seo-title: Segurança de dados no Audience Manager
solution: Audience Manager
title: Segurança de dados no Audience Manager
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 0%

---


# Segurança de dados no Audience Manager {#data-security}

A Audience Manager leva a segurança e a privacidade dos dados muito a sério. Trabalhamos para manter nossos sistemas protegidos e proteger seus dados valiosos.

As práticas de segurança do Audience Manager incluem auditorias externas e internas, registro de atividades, treinamento e outros procedimentos projetados para ajudar a proteger nossos sistemas e seus valiosos dados. Acreditamos que um produto seguro ajuda a criar e manter a confiança que os clientes depositam em nós.

No Audience Manager, pensamos em segurança em três categorias principais:

| Tipo de segurança | Fornece suporte para |
|---|---|
| **Segurança das informações** | Práticas de autenticação, criptografia e armazenamento de dados de nível empresarial |
| **Fuga/transparência de dados** | Insight profundo e acionável sobre atividades no local que constituem ou contribuem para o vazamento de dados |
| **Aprimoramentos de processos/políticas** | Clientes, trabalhando com as práticas recomendadas do setor para privacidade e segurança de dados |

## Sistemas, treinamento e acesso {#systems-training-access}

Processos que ajudam a manter nosso sistema e seus dados protegidos.

**Validação de Segurança Externa:**  A Audience Manager testa a segurança numa base anual e trimestral.

* Anualmente: Uma vez por ano, o Audience Manager é submetido a um teste de penetração total realizado por uma empresa independente. O teste foi projetado para identificar vulnerabilidades de segurança no aplicativo. Os testes incluem varredura para script entre sites, injeções de SQL, manipulação de parâmetros de formulário e outras vulnerabilidades no nível do aplicativo.
* Trimestral: Uma vez a cada trimestre, as equipes internas verificam vulnerabilidades de segurança. Esses testes incluem verificações de rede em busca de portas abertas e vulnerabilidades de serviço.

**Segurança de sistemas:**  Para ajudar a manter os dados seguros e privados, Audience Manager:

* Bloqueia solicitações de endereços IP não autorizados.
* Protege dados por trás de firewalls, VPNs e com armazenamento da Virtual Private Cloud.
* Rastreia alterações nos bancos de dados de informações de controle e cliente com registro de auditoria baseado em disparador. Esses registros rastreiam todas as alterações no nível do banco de dados, incluindo a ID do usuário e o endereço IP a partir dos quais as alterações são feitas.

**Ativos de segurança:**  A Audience Manager tem uma equipe dedicada de operações de rede que monitora firewalls e dispositivos de detecção de intrusão. Somente o pessoal-chave tem acesso à nossa tecnologia e aos nossos dados de segurança.

**Treinamento em segurança:**  Internamente, nosso compromisso com a segurança se estende aos desenvolvedores que trabalham em nosso produto. A Adobe fornece treinamento formal para desenvolvedores sobre como criar aplicativos e serviços seguros.

**Acesso seguro:**  O Audience Manager requer senhas seguras para fazer logon no sistema. Consulte os requisitos [de](../../reference/password-requirements.md)senha.

## Privacidade e informações pessoais identificáveis (PII) {#pii}

Processos que ajudam a manter as informações pessoais seguras. Para obter informações adicionais sobre privacidade, consulte o Centro [de privacidade da](https://www.adobe.com/privacy/advertising-services.html)Adobe.

**Dados de PII:**  A Audience Manager proíbe por contrato que clientes e parceiros de dados enviem informações de PII para nosso sistema. Além disso, a ID de usuário exclusiva (UUID) não contém nem usa dados PII como parte do algoritmo de geração de ID.

**Endereços IP:**  O Audience Manager coleta endereços IP. Os endereços IP são usados em processos de processamento de dados e agregação de log. Eles também são necessários para pesquisas geográficas/locais e definição de metas. Além disso, todos os endereços IP nos arquivos de log retidos são ofuscados em 90 dias.

## Particionamento de dados {#data-partitioning}

Processos que ajudam a proteger dados de propriedade de clientes individuais.

**Particionamento de dados de características:**  Seus dados ([!UICONTROL traits], IDs etc.) é particionado pelo cliente. Isso ajuda a evitar a exposição acidental às informações entre clientes diferentes. Por exemplo, os dados de características em cookies são particionados pelo cliente e armazenados em um subdomínio específico do cliente. Não pode ser lida ou usada acidentalmente por outro cliente Audience Manager. Além disso, os dados de características armazenados no [!UICONTROL Profile Cache Servers (PCS)] são também particionados pelo cliente. Isso evita que outros clientes usem acidentalmente seus dados em uma chamada de evento ou outra solicitação.

**Particionamento de dados em relatórios:**  As IDs do cliente fazem parte da chave de identificação em todas as tabelas de relatórios e os query de relatório são filtrados pela ID. Isso ajuda a impedir que seus dados apareçam nos relatórios de outro cliente do Audience Manager.

## Transferências S2S (Servidor para Servidor de Entrada) {#inbound-s2s}

O Adobe Audience Manager suporta dois métodos principais de transferência de arquivos de dados integrados S2S para nossos sistemas:

Ambos os métodos são projetados tendo em mente a segurança de nossos dados de clientes e parceiros enquanto os dados estão em voo entre seus sistemas e nosso sistema.

**SFTP:** Para a opção SFTP, a maioria dos clientes opta por fornecer arquivos por meio do protocolo FTP seguro (SFTP), que usa o protocolo SSH (Secure Shell). Este método garante que os arquivos sejam criptografados enquanto estiverem em voo entre os sistemas do cliente e o sistema da Adobe. Para cada cliente, criamos um local de caixa suspensa preso em nossos servidores SFTP, que está vinculado a uma conta de usuário no sistema. Somente os usuários do sistema interno credenciados e privilegiados do cliente podem acessar esse local da caixa suspensa. Esta prisão nunca é acessível a outros clientes.

**[!UICONTROL Amazon Web Services S3]por HTTPS:**Para a opção delivery S3, recomendamos que todos os clientes configurem seus clientes S3 para usar o método de criptografia HTTPS para transferências de arquivos (esse não é o padrão, portanto, ele deve estar configurado explicitamente). A opção HTTPS é suportada pela ferramenta de linha de comando s3cmd, bem como pelas bibliotecas S3 disponíveis em todas as principais linguagens de programação. Com essa opção HTTPS ativada, os dados do cliente são criptografados enquanto estão em voo para nossos sistemas. Para cada cliente, criamos um subdiretório S3 bucket separado que pode ser acessado somente pelas credenciais desse cliente e das de nossos usuários internos do sistema.

Para adicionar criptografia PGP aos arquivos de dados, consulte Criptografia PGP [de arquivo para tipos](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)de dados de entrada.

## Proteção de dados por omissão {#escaping-data}

Observe que [!DNL Audience Manager] não escapa aos dados de saída para protegê-los contra possíveis scripts entre sites (XSS), etc. É responsabilidade do cliente escapar aos dados recebidos.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] é um mecanismo de segurança da Web em todo o setor que ajuda a proteger contra ataques de sequestro de cookies e downgrade de protocolos.

A política instrui o navegador da Web que, uma vez feita uma [!DNL HTTPS] chamada segura para um determinado domínio, nenhuma chamada ([!DNL HTTP]) não segura subsequente deverá ser permitida para esse domínio. Isso protege contra ataques do homem no meio, onde um atacante pode tentar diminuir [!DNL HTTPS] as chamadas para [!DNL HTTP] chamadas não seguras.&quot;

Essa política melhora a segurança de dados entre clientes e servidores Adobe [Edge](../../reference/system-components/components-edge.md) .

### Exemplo {#hsts-example}

Digamos que o `yourcompany.demdex.com` domínio envie tráfego para a [!DNL DCS] via [!DNL HTTP]. [!DNL HSTS] atualiza as chamadas a serem usadas [!DNL HTTPS] em vez disso, e todas as [!DNL DCS] chamadas subsequentes provenientes de `yourcompany.demdex.com` serão usadas [!DNL HTTPS] em vez de [!DNL HTTP].

Consulte Segurança de Transporte Restrita [HTTP - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) para obter mais informações sobre HSTS.
