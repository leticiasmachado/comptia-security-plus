Resumo do vídeo **Physical Attacks – CompTIA Security+ SY0-701 – 2.4**

---

Quando falamos de um ataque físico, não importa a versão do sistema operacional ou uma vulnerabilidade de software específica. O foco do invasor é atacar o problema no nível físico, ou seja, ter acesso direto ao hardware e à infraestrutura.

### **A Importância da Segurança Física**

Assim como existem muitas maneiras de atacar a segurança digital de um sistema, também existem muitas formas de atacar sua segurança física. É crucial lembrar que **quem tem acesso físico a um computador, pode obter controle total sobre ele**. Se um invasor pode tocar fisicamente em um computador, ele pode encontrar uma maneira de contornar qualquer sistema operacional ou software de proteção.

Pense nisso: um cadeado ou uma porta trancada pode impedir pessoas comuns, mas alguém determinado sempre encontrará uma forma de entrar. Por isso, precisamos de múltiplas camadas de proteção para garantir a segurança física dos nossos dispositivos.

---

### **Tipos Comuns de Ataques Físicos**

#### **1. Força Bruta (Brute Force) 💪**

Geralmente associamos o termo "força bruta" à tentativa de adivinhar senhas. No entanto, no mundo físico, o conceito é literal: usar a força para superar uma barreira.

* **O que é?** Arrombar uma porta trancada, quebrar uma janela ou forçar fisicamente o acesso a uma área restrita.
* **Exemplo:** Um invasor poderia usar ferramentas para forçar a porta de um data center. Uma vez lá dentro, ele teria acesso direto a todos os servidores e à infraestrutura da empresa. É fundamental avaliar quão resistentes são as barreiras físicas do seu local de trabalho.

#### **2. Clonagem de RFID (RFID Cloning) 💳**

Muitas empresas usam crachás e chaveiros de acesso com tecnologia RFID (Identificação por Radiofrequência) para controlar o acesso a portas e áreas seguras.

* **O que é?** É o ato de copiar as informações de um cartão RFID para um cartão em branco, criando um clone perfeito.
* **Como funciona?** É surpreendentemente fácil e barato. Clonadores de RFID podem ser comprados online por menos de $50. O processo é rápido: basta aproximar o clonador do cartão original por um segundo e depois aproximá-lo do cartão em branco para transferir os dados.
* **Cenário de Risco:** Um invasor poderia "esbarrar" em um funcionário no transporte público e, com um leitor de RFID escondido, clonar seu crachá de acesso sem que a pessoa percebesse.

> **🔒 Como se proteger?** A **autenticação multifator (MFA)** é uma excelente defesa. Mesmo que o invasor clone o crachá, ele ainda precisaria de um segundo fator, como uma senha (algo que você sabe) ou sua biometria (algo que você é), para conseguir o acesso.

#### **3. Ataques Ambientais 🌡️🔥**

Se não é possível atacar os sistemas diretamente, um invasor pode atacar o ambiente ao redor deles para causar danos ou interrupções.

* **O que é?** Manipular as condições do ambiente (energia, temperatura, etc.) para afetar a operação dos equipamentos.
* **Exemplos:**
    * **Corte de Energia:** Um invasor pode desligar a fonte de energia principal de um prédio ou data center, muitas vezes a partir de um local externo, causando uma paralisação completa dos serviços (ataque de negação de serviço).
    * **Manipulação do HVAC:** Os sistemas de **HVAC** (Aquecimento, Ventilação e Ar Condicionado) costumam ser menos seguros. Um invasor que consiga acesso ao controle do HVAC pode desligar o ar condicionado. Com isso, os servidores superaquecem e se desligam automaticamente para evitar danos permanentes.
    * **Sistemas de Supressão de Incêndio:** Ativar indevidamente o sistema de supressão de incêndios (como os sprinklers de água) pode não apenas desligar os servidores, mas também danificá-los permanentemente.