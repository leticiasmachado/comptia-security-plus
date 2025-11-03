Resumo do vídeo **Identity and Access Management – CompTIA Security+ SY0-701 – 4.6**

---

### 1. O que é Gerenciamento de Identidade e Acesso (IAM)?

Usamos muitas aplicações (em desktops, laptops, dispositivos móveis) que acessam dados de vários locais (locais, data centers, nuvem). Além disso, temos diferentes tipos de usuários (funcionários, fornecedores, clientes) que precisam de diferentes níveis de acesso.

**IAM (Identity and Access Management)** é o processo de segurança que garante que as **permissões corretas** sejam dadas às **pessoas corretas** nos **momentos corretos**.

---

### 2. O Ciclo de Vida e Componentes do IAM

O IAM gerencia todo o ciclo de vida de um usuário, desde sua contratação (onboarding) até seu desligamento (offboarding) ou mudança de função (promoção).

* **Provisionamento (Provisioning):** É o processo de **criar** a conta de um usuário e atribuir suas permissões iniciais (acesso a email, aplicações principais, etc.).
* **Desprovisionamento (Deprovisioning):** É o processo de **desativar** ou remover a conta e seus acessos quando o usuário sai da empresa.
* **Controle de Acesso:** O objetivo principal é aplicar o **"princípio do menor privilégio"**. Isso significa que um usuário deve receber *apenas* as permissões estritamente necessárias para realizar seu trabalho, e nada mais. (Por exemplo, nem todos recebem acesso de administrador).
* **Registro (Logging) e Monitoramento:** O IAM também envolve registrar e monitorar quem acessa quais dados, o que é crucial para a segurança e para atender a exigências regulatórias.

---

### 3. Verificação de Identidade (Identity Proofing)

Antes de conceder acesso, o IAM precisa **provar** que um usuário é realmente quem ele diz ser. Isso é feito em algumas etapas:

* **Resolução (Resolution):** O processo formal de verificar a identidade.
* **Validação:** O usuário fornece algo que só ele sabe (ex: senha, respostas a perguntas de segurança).
* **Atestado (Attestation):** A verificação da identidade usando provas externas. Isso pode incluir:
    * Documentos governamentais (passaporte, carteira de motorista).
    * Uma verificação presencial.
    * Verificações automatizadas (ex: perguntas baseadas em seu relatório de crédito, como "Em qual dessas ruas você já morou?").

---

### 4. Conceitos-Chave de Autenticação

* **Single Sign-On (SSO):**
    * É o processo de fazer login **uma única vez** (ex: ao entrar no Windows) e ganhar acesso a todos os recursos da rede (como impressoras ou pastas compartilhadas) sem precisar digitar suas credenciais novamente.
    * Geralmente funciona com um temporizador (ex: por 24 horas).

* **Federação (Federation):**
    * Permite que você use credenciais de um serviço terceirizado para logar em outro site, sem precisar criar uma conta local.
    * É o que acontece quando você vê os botões **"Logar com Google"**, **"Logar com Facebook"** ou "Logar com LinkedIn" em um site.
    * Isso exige uma relação de confiança pré-estabelecida entre o site e o provedor de identidade (Google, Facebook, etc.).

---

### 5. Protocolos e Frameworks de Autenticação/Autorização

#### A. LDAP (Lightweight Directory Access Protocol)
* É um protocolo padrão (baseado na especificação X.500) para acessar e consultar grandes diretórios de dados em uma rede.
* É a tecnologia central por trás de serviços como o **Active Directory** da Microsoft.
* Ele organiza os dados em uma estrutura de árvore (Directory Information Tree), permitindo organizar por país, organização, departamentos (Unidades Organizacionais) e usuários/dispositivos (Nomes Comuns).

#### B. SAML (Security Assertion Markup Language)
* É um padrão que permite que um usuário se autentique em um serviço usando um banco de dados de terceiros (um Provedor de Identidade).
* **Fluxo Básico:**
    1.  O usuário (Cliente) tenta acessar um **Servidor de Recursos**.
    2.  O Servidor de Recursos vê que o usuário não está logado e o redireciona para um **Servidor de Autorização**.
    3.  O usuário insere suas credenciais no Servidor de Autorização.
    4.  O servidor valida as credenciais e envia de volta ao usuário um **"Token SAML"** (uma prova de autenticação).
    5.  O usuário apresenta esse Token ao Servidor de Recursos, que então concede o acesso.
* **Desafio:** O SAML não foi originalmente projetado para dispositivos móveis ou múltiplos logins simultâneos.

#### C. OAuth
* É um **framework de autorização** moderno, construído para funcionar bem com dispositivos móveis e APIs.
* OAuth **não lida com autenticação** (quem você é); ele lida com **autorização** (o que você pode acessar).
* É frequentemente usado em conjunto com o **OpenID**, que fornece a camada de autenticação.
* **Exemplo:** Quando você permite que um aplicativo de terceiros (como o Zapier) acesse seu Google Drive para "ver, editar, criar e deletar" seus arquivos. Você está concedendo autorização via OAuth.

---

### 6. O Desafio da Interoperabilidade

Ao escolher tecnologias de IAM, as organizações precisam garantir que elas sejam **interoperáveis** (que "conversem" entre si).

* **Exemplo 1:** Uma empresa compra um novo concentrador de VPN que suporta autenticação **LDAP**. A empresa já usa o **Active Directory** (que é baseado em LDAP). Essa é uma combinação perfeita.
* **Exemplo 2:** Uma nova aplicação usa **OAuth** para autorização. A empresa precisará garantir que seu sistema de autenticação possa se comunicar com o framework OAuth (provavelmente via API) para que o processo funcione.3