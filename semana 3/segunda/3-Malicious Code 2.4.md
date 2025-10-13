Resumo do vídeo **Malicious Code – CompTIA Security+ SY0-701 – 2.4**

---

### **O Que é Código Malicioso (Malware)?**

"Código malicioso" é um termo abrangente para qualquer tipo de software ou script projetado para causar danos ou obter acesso não autorizado a um sistema. Ele pode vir de várias formas:

* **Executáveis:** Programas maliciosos que você baixa e instala sem saber.
* **Scripts:** Pequenos pedaços de código que rodam em sites ou no seu sistema.
* **Vírus de Macro:** Código malicioso embutido em documentos do Office (Word, Excel).
* **Cavalos de Troia (Trojans):** Malware disfarçado de software legítimo.
* E muitos outros...

### **Construindo a Defesa: Múltiplas Camadas de Proteção 🏰**

Como as ameaças são variadas, nossa defesa precisa ser robusta e em camadas, como as defesas de um castelo. Uma única muralha não é suficiente. As camadas essenciais são:

* **🛡️ Antimalware:** O "guarda" que inspeciona arquivos e bloqueia executáveis e scripts maliciosos.
* **🧱 Firewall:** A "muralha" que controla o tráfego de entrada e saída da rede, bloqueando conexões suspeitas.
* **🔧 Atualizações e Patches:** O "time de manutenção" que está sempre consertando as brechas e janelas quebradas do sistema assim que são descobertas.
* **👨‍🏫 Treinamento de Usuários:** Ensinar as pessoas a terem hábitos seguros, como não clicar em links desconhecidos ou fornecer informações por telefone.

---

### **O Código Malicioso em Ação: Exemplos do Mundo Real**

Para entender o poder do malware, vamos analisar três ataques famosos onde diferentes tipos de código malicioso foram usados.

#### **1. WannaCry (Ransomware)**

* **Tipo de Código:** Um *worm* (verme) que se espalhava automaticamente e instalava um ransomware.
* **A Brecha:** Explorou uma vulnerabilidade no protocolo de compartilhamento de arquivos do Windows (**SMBv1**). Essa falha permitia a **execução de código arbitrário**, ou seja, o invasor podia rodar qualquer programa que quisesse na máquina da vítima.
* **O Impacto:** O malware criptografou os arquivos de milhões de computadores em todo o mundo, paralisando hospitais, empresas e governos, e exigiu um resgate em Bitcoin para liberá-los.

#### **2. British Airways (Roubo de Cartões de Crédito)**

* **Tipo de Código:** Injeção de código **JavaScript** malicioso (semelhante a um ataque de *Cross-Site Scripting*).
* **A Brecha:** Invasores conseguiram acesso ao site da British Airways e inseriram apenas **22 linhas de código JavaScript** nas páginas de pagamento.
* **O Impacto:** Esse pequeno script capturava os dados do cartão de crédito dos clientes enquanto eles digitavam. Quando a falha foi descoberta, os dados de aproximadamente **380.000 vítimas** já haviam sido roubados.

#### **3. Banco de Dados de Saúde da Estônia (Vazamento de Dados)**

* **Tipo de Código:** Comandos SQL maliciosos em um ataque de **Injeção de SQL (*SQL Injection*)**.
* **A Brecha:** O sistema do banco de dados não validava corretamente as informações inseridas pelos usuários, permitindo que os invasores enviassem comandos diretamente para o banco de dados.
* **O Impacto:** Os invasores conseguiram acesso ao banco de dados nacional de saúde inteiro, vazando as informações médicas de todos os cidadãos da Estônia.