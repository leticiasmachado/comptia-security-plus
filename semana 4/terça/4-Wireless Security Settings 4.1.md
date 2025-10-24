Resumo do vídeo **Wireless Security Settings – CompTIA Security+ SY0-701 – 4.1**

---

Redes wireless exigem alguns pilares de segurança:

1.  **Criptografia:** Garantir a confidencialidade, para que ninguém possa ler os dados.
2.  **Autenticação:** Garantir que apenas usuários autorizados possam acessar a rede.
3.  **Integridade:** Garantir que os dados não foram alterados no caminho (usando um **MIC - Message Integrity Check**).

#### **1. A Evolução da Criptografia: WPA2 vs. WPA3**

* **WPA2 (O Problema):**
    * Durante anos, foi o padrão de criptografia.
    * **Vulnerabilidade Grave:** Possui uma falha no "handshake" (negociação) inicial de 4 etapas.
    * **Método de Ataque:** Um invasor pode capturar o *hash* da chave (PSK - Pre-Shared Key) durante essa negociação.
    * Com o hash capturado, o invasor pode levá-lo "offline" e usar ataques de força bruta (com GPUs ou na nuvem) para descobrir a senha em questão de dias.

* **WPA3 (A Solução):**
    * Foi criado para corrigir a falha do WPA2.
    * **Criptografia Mais Forte:** Usa **GCMP (Galois Counter Mode Protocol)**, que é mais robusto e já inclui confidencialidade e integridade.
    * **Nova Autenticação (SAE):** Substitui o handshake vulnerável pelo **SAE (Simultaneous Authentication of Equals)**, também conhecido como "Dragonfly Handshake".
    * **Como Funciona o SAE:** Baseado em Diffie-Hellman, ele permite que o cliente e o ponto de acesso criem as chaves de sessão em seus próprios dispositivos (autenticação mútua), sem *nunca* enviar um hash pela rede.
    * **Resultado:** Como nenhum hash é transmitido, não há nada para o invasor capturar e atacar.
    * **Benefício Adicional:** Mesmo em uma rede com senha compartilhada (PSK), o WPA3 cria chaves de sessão *diferentes* para cada usuário, impedindo que um usuário espione o tráfego de outro.

#### **2. Métodos de Autenticação Wireless**

Existem duas formas principais de autenticar usuários em uma rede Wi-Fi:

* **1. Modo Pessoal (PSK - Pre-Shared Key):**
    * **Configuração:** `WPA3-Personal` (ou WPA-PSK).
    * **Uso:** É a "senha do Wi-Fi" que você usa em casa. Todos os usuários usam a mesma senha para se conectar.
    * **Risco:** Inseguro para ambientes corporativos, pois se a senha vazar, o invasor tem acesso total, e não há como saber *quem* está conectado.

* **2. Modo Empresarial (Enterprise / 802.1X):**
    * **Configuração:** `WPA3-Enterprise` (ou WPA3-802.1X).
    * **Uso:** Ambiente corporativo.
    * **Funcionamento:** Não usa uma senha compartilhada. Em vez disso, cada funcionário usa suas **próprias credenciais de rede** (nome de usuário e senha) para se conectar.
    * **Vantagem:** Permite controle de acesso individual e se conecta a um servidor de autenticação centralizado.

#### **3. O Framework "AAA" (Authentication, Authorization, Accounting)**

A autenticação empresarial (802.1X) depende de um servidor centralizado chamado **AAA**.

* **Identification (Identificação):** Quem é você? (O nome de usuário).
* **Authentication (Autenticação):** Prove que é você (A senha ou outro fator).
* **Authorization (Autorização):** O que você tem permissão para fazer/acessar depois de autenticado?
* **Accounting (Contabilização):** Registra o que você fez (hora de login/logout, dados transferidos, etc.).

* **RADIUS (Remote Authentication Dial-In User Service):** É o protocolo de servidor AAA mais popular e amplamente suportado. Embora o nome seja antigo ("dial-in"), ele é usado hoje para autenticar conexões de VPN, switches, roteadores e Wi-Fi (802.1X).

#### **4. O Processo de Autenticação 802.1X e EAP**

* **802.1X (ou NAC - Network Access Control):** É o padrão que *controla o acesso à porta* (seja ela física ou wireless). Ele bloqueia o acesso à rede até que o usuário forneça credenciais válidas.
* **EAP (Extensible Authentication Protocol):** É o *protocolo de transporte* que o 802.1X usa para "empacotar" e enviar as credenciais de forma segura.

**Os 3 Componentes do 802.1X:**

1.  **Supplicant (Suplicante):** O dispositivo cliente (seu notebook ou smartphone) que está pedindo acesso.
2.  **Authenticator (Autenticador):** O dispositivo de rede ao qual o suplicante está se conectando (o Ponto de Acesso Wi-Fi ou o switch).
3.  **Authentication Server (Servidor):** O servidor AAA (ex: RADIUS) que armazena as credenciais e toma a decisão.

**Fluxo da Autenticação (Simplificado):**

1.  O **Suplicante** tenta se conectar ao **Autenticador** (Ponto de Acesso).
2.  O Autenticador *bloqueia* o acesso à rede e pergunta: "Quem é você?" (Envia uma solicitação EAP).
3.  O Suplicante responde com seu nome de usuário (Resposta EAP).
4.  O Autenticador repassa o nome de usuário para o **Servidor de Autenticação** (RADIUS).
5.  O Servidor diz "Ok, peça a senha". O Autenticador pede a senha ao Suplicante.
6.  O Suplicante envia sua senha (dentro de um túnel EAP seguro).
7.  O Autenticador repassa a senha ao Servidor.
8.  O Servidor verifica as credenciais. Se estiverem corretas, ele envia uma mensagem de "Acesso Permitido" ao Autenticador.
9.  O **Autenticador** (Ponto de Acesso) finalmente *libera* o acesso do Suplicante à rede.