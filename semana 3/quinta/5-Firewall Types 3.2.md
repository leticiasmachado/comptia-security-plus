Resumo do vídeo **Firewall Types – CompTIA Security+ SY0-701 – 3.2**

---

### 1. O que é um Firewall?

Um **firewall** é um dispositivo de segurança projetado para **controlar o fluxo de tráfego** entre dois pontos (por exemplo, entre a sua rede interna e a internet). Eles são onipresentes, encontrados em nossas casas, escritórios e até mesmo integrados aos nossos sistemas operacionais.

**Principais Funções:**
* **Gerenciamento de Fluxo:** Controlar o tráfego de entrada e saída, essencial em grandes ambientes com milhares de usuários.
* **Controle de Conteúdo:** Usado em empresas para bloquear sites ou em residências para controle dos pais.
* **Segurança Adicional:** Por inspecionar todo o tráfego, é o local perfeito para integrar controles de **antivírus** e **anti-malware**.

---

### 2. A Evolução: Camada 4 vs. Camada 7

Os firewalls evoluíram na forma como inspecionam o tráfego, o que é melhor descrito usando o modelo OSI:

* **Firewalls Tradicionais (Camada 4):**
    * Controlam o tráfego com base na **Camada 4 (Transporte)**.
    * Eles tomam decisões olhando apenas para **números de porta** TCP ou UDP (Ex: `Permitir porta 80`, `Bloquear porta 23`).

* **Firewalls Modernos (Camada 7):**
    * Conseguem inspecionar a **Camada 7 (Aplicação)**.
    * Eles tomam decisões com base na **aplicação** que está sendo usada, independentemente da porta. (Ex: `Permitir Facebook, mas bloquear jogos do Facebook`).

**Funções Adicionais:**
Muitos firewalls também atuam como dispositivos de **Camada 3 (Rede)**, funcionando como um **roteador**. Por estarem na borda da rede, eles comumente realizam **NAT (Network Address Translation)** e executam protocolos de roteamento. Eles também podem integrar serviços como **VPN (Virtual Private Network)**.

---

### 3. Tipo 1: UTM (Unified Threat Management)

* **O que é?** Um **UTM (Gerenciamento Unificado de Ameaças)** é um tipo mais antigo de firewall, também conhecido como "Web Security Gateway" ou "Appliance All-in-One".
* **A Proposta:** Agrupar **múltiplas funções de segurança** em um único dispositivo.
* **Recursos Comuns:**
    * Filtragem de URL e inspeção de conteúdo.
    * Identificação de Malware.
    * Filtro de Spam.
    * IDS/IPS (Detecção/Prevenção de Intrusão).
    * Modelagem de Banda (QoS).
    * Funcionalidade de Firewall, Roteamento e VPN.
* **Os Desafios do UTM:**
    1.  **Desempenho:** Tentar executar todas essas funções simultaneamente em um único hardware muitas vezes causa uma **grande lentidão** no dispositivo.
    2.  **Limitação:** Muitos UTMs operam apenas na **Camada 4** (portas), não tendo visibilidade real das aplicações.

---

### 4. Tipo 2: NGFW (Next-Generation Firewall)

* **O que é?** Um **NGFW (Firewall de Próxima Geração)** é o firewall moderno padrão.
* **Característica Principal:** Opera na **Camada 7 (Aplicação)**. É "consciente das aplicações".
* **Outros Nomes:** Application Layer Gateway, Stateful Multilayer Inspection, Deep Packet Inspection (DPI).
* **Como Funciona?** O NGFW realiza uma **"decodificação completa do pacote" (deep packet inspection)**. Ele analisa todo o tráfego e consegue identificar:
    * Quem está enviando o tráfego.
    * Para onde o tráfego está indo.
    * O que está **dentro** do tráfego (qual aplicação).
* **O Poder da Camada 7 (Exemplos):**
    Um NGFW pode diferenciar aplicações que usam a **mesma porta**. Por exemplo, todo o tráfego abaixo pode estar usando a porta 443 (HTTPS):
    1.  `PERMITIR` tráfego do Microsoft SQL Server (mesmo que ele use uma porta não padrão).
    2.  `PERMITIR` *visualizar* o Twitter, mas `BLOQUEAR` *postar* no Twitter.
    3.  `BLOQUEAR` acesso a vídeos do YouTube.
* **Recursos Adicionais do NGFW:**
    * **IPS Integrado:** Possui um banco de dados de vulnerabilidades conhecidas e pode bloqueá-las ativamente.
    * **Filtragem de URL/Categoria:** Pode bloquear o acesso a categorias inteiras de sites (ex: "Jogos de Azar") ou URLs específicas (ex: `espn.com`).

---

### 5. Tipo 3: WAF (Web Application Firewall)

* **O que é?** Um **WAF (Firewall de Aplicação Web)** é um tipo de firewall altamente especializado. **Ele não é um UTM nem um NGFW.**
* **Foco Exclusivo:** O WAF é projetado para analisar a **ENTRADA (INPUT) de dados** em aplicações web (tráfego HTTP/HTTPS) e bloquear ataques comuns contra essas aplicações.
* **O que ele protege?** O WAF protege contra ataques como:
    * **SQL Injection (Injeção de SQL)**
    * **Cross-Site Scripting (XSS)**
    * Erros de lógica de aplicação web.
* **Como é usado?** É muito comum ver um **WAF posicionado *junto* com um NGFW**.
    * O **NGFW** protege a rede (bloqueando portas, aplicações indesejadas, malware).
    * O **WAF** protege o servidor web (bloqueando ataques nos campos de formulário e URLs).
* **Obrigatoriedade:** Padrões de segurança, como o **PCI-DSS** (padrão de segurança de dados da indústria de cartões de pagamento), exigem o uso de um WAF para proteger aplicações que lidam com dados de cartão de crédito.
* **Exemplo de Log:** Um log de WAF mostrará ataques bloqueados como "SQL Injection in Parameter" ou "Cross-Site Scripting", que são muito diferentes dos logs de um firewall de rede tradicional.