Resumo do vídeo **States of Data – CompTIA Security+ SY0-701 – 3.3**

---

### 1. Os Três Estados dos Dados

Os dados não existem de uma única forma; eles passam por três "estados" distintos. Cada estado possui riscos e métodos de proteção específicos.

#### A. Dados em Repouso (Data at Rest)

* **Definição:** Quaisquer dados que estão **armazenados** em um dispositivo de armazenamento.
* **Exemplos:** Arquivos em um HD (disco rígido), SSD, pen drive, fita de backup, etc.
* **Ponto Chave:** Os dados são considerados "em repouso" **mesmo que não estejam criptografados**.
* **Como Proteger (Dados em Repouso):**
    1.  **Criptografia:**
        * **Criptografia de Disco Inteiro (Full Disk Encryption):** Criptografa *tudo* no dispositivo (ex: BitLocker, FileVault).
        * **Criptografia de Banco de Dados:** Criptografa apenas os dados dentro do banco.
        * **Criptografia de Arquivo/Pasta:** O sistema operacional permite criptografar arquivos ou pastas individuais.
    2.  **Controle de Acesso:**
        * Aplicar **direitos e permissões** (ACLs - Listas de Controle de Acesso) em nível de usuário ou grupo para limitar quem pode ler, escrever ou executar os dados.

#### B. Dados em Trânsito (Data in Transit)

* **Definição:** Quaisquer dados que estão sendo **transferidos pela rede** (seja a rede interna ou a internet).
* **Outro Nome:** Dados em Movimento (Data in Motion).
* **Risco Principal:** Se os dados não estiverem criptografados, qualquer pessoa que consiga "grampear" a rede (sniffing) pode ler todo o seu conteúdo enquanto eles passam por switches, roteadores e firewalls.
* **Como Proteger (Dados em Trânsito):**
    1.  **Controle de Rede:**
        * **Firewall e IPS:** Usar políticas para permitir tráfego bom e conhecido, e bloquear qualquer coisa suspeita ou maliciosa.
    2.  **Criptografia (Essencial):**
        * **TLS (Transport Layer Security):** Usado para criptografar conexões específicas, mais comumente o tráfego web (HTTPS).
        * **VPN (IPsec - Internet Protocol Security):** Usado para criar um "túnel" criptografado e proteger *todo* o tráfego entre dois pontos (ex: uma VPN site-to-site ou um cliente de acesso remoto).

#### C. Dados em Uso (Data in Use)

* **Definição:** Dados que foram puxados do armazenamento (HD/SSD), carregados na **memória (RAM)** e estão sendo ativamente processados pela **CPU**.
* **A Vulnerabilidade Crítica:** Para que a CPU possa realizar operações (cálculos, manipulações), os dados precisam estar **decriptografados (em texto claro)** dentro da memória RAM.
* **Foco do Invasor:** É por isso que os invasores adoram atacar a memória do sistema. Eles sabem que, se conseguirem "ler" a RAM, encontrarão os dados em um formato legível.
* **Exemplo de Ataque (Target Corp., 2013):**
    * Os invasores colocaram um código malicioso (malware) em todos os terminais de ponto de venda (POS - as máquinas de cartão) da Target.
    * A Target *estava* usando criptografia para dados em trânsito (na rede) e dados em repouso (no disco).
    * No entanto, o malware "roubou" 110 milhões de números de cartão de crédito **diretamente da memória (RAM)** das máquinas no exato momento em que o cartão era processado (ou seja, **dados em uso**), antes que pudessem ser criptografados para armazenamento.

---

### 2. Soberania de Dados (Data Sovereignty)

* **Definição:** É um conceito legal que afirma que os dados armazenados digitalmente em um país estão **sujeitos às leis e regulamentos desse país**.
* **Implicações:**
    * Se seus dados estiverem na "nuvem" em um servidor no País X, as leis do País X se aplicam a eles.
    * Isso é crucial para processos legais, ordens judiciais e conformidade (compliance).
* **Exemplo (GDPR):**
    * O **GDPR (General Data Protection Regulation)** é um regulamento da União Europeia (UE).
    * Ele determina que quaisquer dados coletados sobre cidadãos da UE **devem ser armazenados fisicamente dentro da UE**. Se sua empresa está nos EUA, mas coleta dados de clientes europeus, você não pode simplesmente armazenar esses dados nos seus servidores locais; você deve usar um data center localizado na UE.

---

### 3. Geolocalização (Geolocation)

* **Definição:** O processo de usar várias tecnologias para determinar a **localização física** de um usuário.
* **Tecnologias Usadas:** GPS, informações de redes Wi-Fi (802.11) próximas, dados da operadora de celular.

#### Controle de Acesso Baseado em Geolocalização

Podemos usar a localização de um usuário para decidir que tipo de acesso ele terá:

* **Exemplo 1 (Bloqueio):** Você tenta assistir a um canal de TV (streaming) de outro país, e o serviço exibe uma mensagem dizendo que "este conteúdo não está disponível em sua região". Ele sabe onde você está.
* **Exemplo 2 (Acesso Contextual):** Uma organização pode aplicar regras como:
    * Se o funcionário está **dentro do prédio** da empresa (verificado pela rede Wi-Fi), ele tem **acesso total** aos dados.
    * Se o funcionário está **fora do prédio** (em casa, em outra cidade), ele tem **acesso limitado** (talvez não possa acessar os dados mais sensíveis).