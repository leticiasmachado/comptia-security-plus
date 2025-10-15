Resumo do vídeo **Hardening Techniques – CompTIA Security+ SY0-701 – 2.5**

---

**Hardening** (ou "enrijecimento") é o processo de tornar um sistema computacional o mais seguro possível, minimizando sua **superfície de ataque**. Isso envolve uma série de boas práticas aplicadas a servidores, sistemas operacionais e dispositivos de usuários.

### **I. Hardening de Servidores e Sistemas Operacionais**

A base da segurança de qualquer servidor começa com o seu sistema operacional.

* **1. Mantenha Tudo Atualizado:** A primeira e mais importante etapa. Aplique sempre os **patches de segurança** mais recentes para o sistema operacional e para as aplicações.
* **2. Proteja as Contas de Usuário:**
    * **Políticas de Senhas Fortes:** Exija senhas com tamanho mínimo e complexidade (letras maiúsculas, minúsculas, números e símbolos).
    * **Princípio do Menor Privilégio:** Um usuário deve ter apenas as permissões estritamente necessárias para fazer seu trabalho. Nem todo mundo precisa ser administrador!
* **3. Limite o Acesso à Rede:** Configure regras (como ACLs) para permitir que apenas uma faixa de IPs específica possa se conectar ao servidor.
* **4. Criptografe os Dados:**
    * **Nível de Arquivo (EFS):** Criptografe pastas ou arquivos específicos.
    * **Disco Inteiro (FDE - BitLocker/FileVault):** Criptografe todo o disco rígido. Essencial para a segurança física de servidores e notebooks.
    * **Em Trânsito (VPN/HTTPS):** Criptografe os dados enquanto eles viajam pela rede.

### **II. Hardening de Endpoints (Seu Computador e Dispositivos)**

"Endpoints" são os dispositivos dos usuários finais, como desktops, notebooks e celulares. Eles são um alvo comum e precisam de proteção robusta.

* **EDR (Endpoint Detection and Response): O Antivírus com Superpoderes** 🦸
    O EDR é a nova geração de proteção. Ele vai além das assinaturas tradicionais.
    * **Análise Comportamental:** Observa o que as aplicações *fazem* para detectar atividades maliciosas, mesmo de malwares desconhecidos.
    * **Machine Learning:** Usa inteligência artificial para identificar novas ameaças rapidamente.
    * **Resposta Automatizada:** Ao detectar uma ameaça, o EDR pode **isolar o sistema da rede, colocar o malware em quarentena e até reverter as alterações** feitas por ele, tudo automaticamente.

* **Firewall de Host:** Pense nele como o **"segurança particular"** de cada computador. Ele controla todo o tráfego de rede que entra e sai do dispositivo, podendo bloquear processos suspeitos de se comunicarem.

* **HIPS (Sistema de Prevenção de Invasão de Host):** É o **"detetive"** que roda no seu PC. Ele procura por atividades suspeitas dentro do próprio sistema operacional, como alterações não autorizadas no registro, modificações em arquivos de sistema ou tentativas de explorar vulnerabilidades como um *buffer overflow*.

### **III. Boas Práticas Essenciais de Hardening**

Estas são regras que se aplicam a quase todos os dispositivos.

* **🚪 Feche as Portas Desnecessárias:**
    Cada porta de rede aberta em um servidor é uma possível entrada para um invasor. A regra é: **feche tudo o que não for estritamente necessário**. Use uma ferramenta como o **Nmap** para escanear seus sistemas e descobrir quais portas estão abertas.

* **🔑 Mude as Configurações Padrão:**
    Roteadores, firewalls e aplicações vêm de fábrica com senhas padrão (como `admin`/`admin`). Os invasores conhecem todas elas. **A primeira coisa a se fazer em um equipamento novo é mudar a senha padrão**.

* **🗑️ Remova Softwares Inutilizados:**
    "Menos é mais". Cada programa instalado no seu sistema é uma potencial vulnerabilidade que precisa ser atualizada. Se você não usa mais uma aplicação, **desinstale-a**. Isso reduz a superfície de ataque e simplifica o gerenciamento de patches.