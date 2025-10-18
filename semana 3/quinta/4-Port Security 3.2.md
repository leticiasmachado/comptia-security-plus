Resumo do vídeo **Port Security – CompTIA Security+ SY0-701 – 3.2**

---

### 1. O Desafio: Segurança de Portas (Port Security)

* **O que é?** Refere-se à segurança aplicada diretamente nas **interfaces individuais** de um equipamento de rede, seja uma porta física em um **switch** (rede com fio) ou uma conexão a um **ponto de acesso** (rede wireless).
* **Exemplo Comum:** Quando você se conecta a uma rede Wi-Fi e precisa inserir um **nome de usuário e senha** (não apenas a "chave" do Wi-Fi), você está usando esse tipo de segurança.
* **Aplicação:** Embora seja muito eficaz e comum em redes sem fio, esse mesmo método de autenticação robusta pode (e deve) ser aplicado a portas de rede cabeadas tradicionais.

---

### 2. O Padrão e o Protocolo: 802.1X e EAP

Para fazer a segurança de portas funcionar, dois componentes principais trabalham juntos:

#### A. O Padrão: IEEE 802.1X
* **O que é?** É um padrão da IEEE (Institute of Electrical and Electronics Engineers) que **gerencia o processo de autenticação** de usuários e dispositivos na rede.
* **Nome Comum:** É frequentemente chamado de **NAC (Network Access Control)** ou "Controle de Acesso à Rede Baseado em Porta".
* **Como Funciona:** Quando você conecta um dispositivo (ex: um notebook) em uma porta de switch habilitada com 802.1X, essa porta fica em um estado **bloqueado**. Você não recebe acesso nenhum à rede (nem mesmo um endereço IP) até que sua identidade seja autenticada e autorizada.

#### B. O Protocolo: EAP (Extensible Authentication Protocol)
* **O que é?** O EAP é a **"linguagem" ou a estrutura (framework)** usada para realizar a autenticação. É o protocolo que transporta as informações de login.
* **A Vantagem ("Extensível"):** Por ser "extensível", ele não está preso a um único método de autenticação. Ele pode ser usado para transportar senhas, certificados digitais, tokens, etc. Isso permite que fabricantes de equipamentos com fio e sem fio usem o mesmo padrão para se autenticar.
* **Integração:** O 802.1X e o EAP trabalham juntos e se integram com bancos de dados de autenticação de back-end que sua empresa já possui, como **RADIUS**, **LDAP**, **Active Directory (Kerberos)** ou **TACACS+**.

---

### 3. Os 3 Componentes da Autenticação 802.1X

O processo 802.1X envolve três "atores" principais:

1.  **Suplicante (Supplicant):**
    * **Quem é?** O dispositivo do usuário final que está tentando acessar a rede (ex: seu notebook, smartphone).
    * **Função:** É quem "suplica" por acesso e fornece as credenciais.

2.  **Autenticador (Authenticator):**
    * **Quem é?** O equipamento de rede ao qual o suplicante está se conectando (ex: o **switch** ou o **ponto de acesso wireless**).
    * **Função:** Atua como o "porteiro". Ele bloqueia a porta e age como um intermediário, pedindo as credenciais ao Suplicante e verificando-as com o Servidor de Autenticação.

3.  **Servidor de Autenticação (Authentication Server):**
    * **Quem é?** O servidor de back-end que armazena o banco de dados de nomes de usuário e senhas (ex: **RADIUS**, **Active Directory**).
    * **Função:** É o "cérebro" da operação. Ele recebe as credenciais do Autenticador, verifica se estão corretas e envia a resposta de "Sucesso" ou "Falha".

---

### 4. O Processo de Autenticação Passo a Passo

Veja como os três componentes interagem quando você conecta um dispositivo:

1.  **Conexão Inicial:** O **Suplicante** (notebook) é conectado à porta do **Autenticador** (switch). O Autenticador **bloqueia a porta** imediatamente, não permitindo nenhum tráfego de rede.

2.  **Solicitação de Identidade (EAP Request):** O Autenticador percebe o novo dispositivo e envia uma mensagem (EAP Request) perguntando: "Quem é você?"

3.  **Resposta de Identidade (EAP Response):** O Suplicante responde com sua identidade (ex: seu nome de usuário).

4.  **Consulta ao Back-end:** O Autenticador pega esse nome de usuário e o repassa para o **Servidor de Autenticação** (ex: RADIUS).

5.  **Desafio (Challenge):** O Servidor de Autenticação responde ao Autenticador, dizendo: "OK, eu conheço esse usuário. Peça a ele a senha [ou outro tipo de credencial]."

6.  **Solicitação de Credenciais:** O Autenticador repassa esse "desafio" ao Suplicante, pedindo as credenciais (ex: a senha).

7.  **Envio de Credenciais:** O Suplicante envia suas credenciais (senha) para o Autenticador.

8.  **Verificação Final:** O Autenticador envia as credenciais recebidas para o Servidor de Autenticação para verificação final.

9.  **Decisão (Sucesso ou Falha):** O Servidor de Autenticação verifica se as credenciais estão corretas.
    * Se **corretas**, ele envia uma mensagem de "Sucesso" para o Autenticador.
    * Se **incorretas**, ele envia uma mensagem de "Falha".

10. **Acesso Concedido:** Ao receber a mensagem de "Sucesso", o Autenticador finalmente **abre a porta** e permite que o Suplicante (notebook) acesse a rede.