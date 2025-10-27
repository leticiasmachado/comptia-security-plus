Resumo do vídeo **Operating System Security – CompTIA Security+ SY0-701 – 4.5**

---

### 1. O que é o Active Directory (AD)?

Em ambientes com muitos dispositivos Windows, o **Active Directory (AD)** é o principal serviço de gerenciamento. Ele funciona como um **banco de dados centralizado** que contém todos os componentes da rede.

**O que o AD armazena:**
* Contas de usuários
* Computadores e outros dispositivos
* Grupos de segurança
* Compartilhamentos de arquivos e impressoras
* Qualquer outro componente que compõe a rede

**Principais Funções do AD:**
1.  **Autenticação Centralizada:** Como todas as contas de usuário estão neste banco de dados, o AD é usado para validar logins (usuário e senha) quando alguém tenta acessar um dispositivo ou recurso na rede.
2.  **Gerenciamento de Permissões de Acesso:** O AD permite aos administradores atribuir permissões de acesso. Eles podem conceder direitos a um usuário individual ou criar grupos (ex: "Equipe de Finanças") e atribuir permissões a esse grupo inteiro. Todas as tarefas de adicionar contas, modificar senhas e remover acessos são feitas aqui.

---

### 2. O que é a Group Policy (Política de Grupo)?

A **Group Policy (Política de Grupo)** é um conjunto de regras e configurações que são aplicadas "por cima" dos objetos (usuários e computadores) armazenados no Active Directory.

* **Gerenciamento:** É configurada a partir de um console central chamado **Editor de Gerenciamento de Política de Grupo** (Group Policy Management Editor).
* **Funções Comuns:**
    * Configurar **scripts de login** (ações que rodam automaticamente quando o usuário entra).
    * Definir configurações de rede (como **Qualidade de Serviço - QoS**).
    * Forçar **parâmetros de segurança** que todos os dispositivos e usuários devem seguir.

A combinação do **Active Directory** (o banco de dados de quem é quem) e da **Group Policy** (as regras do que eles podem fazer) cria um mecanismo de controle abrangente para toda a rede.

---

### 3. Controle de Acesso no Linux: DAC vs. MAC

O Linux, por padrão, opera de forma diferente do ambiente AD.

* **Controle de Acesso Discricionário (DAC - Discretionary Access Control):**
    * Este é o padrão do Linux.
    * Significa que o **próprio usuário** (o "dono" de um arquivo) tem a discrição (o poder) de atribuir direitos e permissões a outros usuários.

* **Controle de Acesso Mandatório (MAC - Mandatory Access Control):**
    * Usado em ambientes de alta segurança onde o DAC não é apropriado.
    * No MAC, os direitos e permissões são definidos por um **administrador central** e não podem ser alterados pelos usuários comuns.

---

### 4. O que é o SELinux?

O **Security-Enhanced Linux (SELinux)** é a implementação mais conhecida do Controle de Acesso Mandatório (MAC) no Linux, geralmente adicionada através de patches no sistema.

* **Objetivo Principal (Princípio do Menor Privilégio):** O SELinux permite ao administrador forçar o **"princípio do menor privilégio"**. Isso garante que um usuário ou processo receba *exatamente* as permissões necessárias para realizar seu trabalho, e nada mais.
* **Benefício de Segurança:** Se ocorrer uma violação (seja por um invasor ou malware), o dano é contido. O processo malicioso terá um escopo muito limitado do que pode fazer no sistema, pois o SELinux bloqueará qualquer ação que não esteja explicitamente permitida em sua política.
* O SELinux é de **código aberto** (open source) e pode ser instalado em muitas distribuições Linux.