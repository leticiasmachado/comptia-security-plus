Resumo do vídeo **Misconfiguration Vulnerabilities – CompTIA Security+ SY0-701 – 2.3**

---

Esta aula aborda erros de segurança básicos, mas extremamente comuns, que muitas vezes são a porta de entrada para ataques bem-sucedidos.

#### **1. Dados Deixados em Aberto (Permissões Abertas) 📂**

Uma das maneiras mais fáceis de vazar dados é simplesmente deixá-los em um local público na internet, sem qualquer tipo de proteção. Atacantes rotineiramente varrem serviços de nuvem em busca de repositórios de dados (como *buckets* Amazon S3) que foram acidentalmente deixados abertos.

* **Exemplo Real: Vazamento da Verizon (2017)**
    * 14 milhões de registros de clientes da Verizon foram encontrados em um repositório Amazon S3, completamente aberto e sem senha.
    * A falha foi de uma empresa terceirizada que esqueceu de proteger os dados.
    * Felizmente, a brecha foi descoberta por um pesquisador de segurança, e não por um atacante, evitando um desastre maior.

#### **2. Contas de Administrador Não Protegidas 🔑**

As contas de superusuário (`root` no Linux, `Administrator` no Windows) são os alvos mais valiosos. O erro comum não é deixá-las sem senha, mas sim usar **senhas extremamente fracas e fáceis de adivinhar** (como "123456" ou "senha"), o que as torna vulneráveis a ataques de força bruta.

* **Boa Prática (Best Practice):**
    * **Desabilite o login direto** com a conta de administrador.
    * Exija que o usuário faça login com uma conta normal e, somente quando necessário, **eleve seus privilégios** (usando o comando `sudo` no Linux ou a opção "Executar como administrador" no Windows).
    * Limite ao máximo o número de contas com privilégios de administrador.

#### **3. Protocolos Inseguros (Comunicação em Texto Puro) Plaintext**

Utilizar protocolos antigos que **não criptografam a comunicação** é um risco enorme. Protocolos como **Telnet, FTP, SMTP, IMAP e HTTP** enviam todos os dados, incluindo nomes de usuário e senhas, em texto puro pela rede. Qualquer pessoa que capture o tráfego pode ler tudo.

* **Exemplo Real: O "Mural da Vergonha" (Wall of Sheep) da DEFCON**
    * Na famosa conferência de segurança DEFCON, os organizadores monitoram a rede Wi-Fi.
    * Quando alguém usa um protocolo inseguro, suas credenciais (usuário, parte da senha, IP) são capturadas e **exibidas em um telão** para todos verem.
    * Isso serve como uma lição pública e chocante sobre os perigos de não usar as versões seguras dos protocolos (como **SSH, SFTP, HTTPS**).

#### **4. Credenciais Padrão em Dispositivos (Especialmente IoT) 📷**

Muitos dispositivos, especialmente os de **Internet das Coisas (IoT)** como câmeras, roteadores e campainhas, vêm de fábrica com um nome de usuário e senha padrão. Muitos usuários instalam esses dispositivos e **nunca alteram essas credenciais**.

* **Exemplo Real: O Botnet Mirai**
    * O Mirai é um malware que varre a internet em busca de dispositivos IoT.
    * Ele possui uma lista com mais de 60 credenciais padrão de fábrica.
    * Ao encontrar um dispositivo vulnerável, ele o infecta e o adiciona a uma rede de "zumbis" (botnet) para ser usado em ataques DDoS.
    * O código-fonte do Mirai é aberto, o que significa que qualquer pessoa pode usá-lo para encontrar dispositivos desprotegidos.

#### **5. Portas e Serviços Abertos Desnecessariamente 🚪**

Cada serviço rodando em um servidor (web, e-mail, etc.) abre uma "porta" na rede para receber conexões. Cada porta aberta é uma **potencial porta de entrada** para um atacante.

* **O Problema da Complexidade:**
    * **Firewalls** são usados para controlar o acesso a essas portas.
    * No entanto, as regras de um firewall podem se tornar muito grandes e complexas, facilitando a ocorrência de erros. Um administrador pode acidentalmente deixar uma porta aberta que deveria estar fechada.
* **Boa Prática (Best Practice):**
    * **Limite ao mínimo** o número de portas abertas para a internet.
    * Realize **auditorias periódicas** nas regras do firewall para garantir que não existam acessos indevidos e corrigir configurações incorretas.
