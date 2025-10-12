Resumo do vídeo **Denial of Service – CompTIA Security+ SY0-701 – 2.4**

---

Um ataque de **Negação de Serviço**, ou **DoS (Denial of Service)**, ocorre quando um invasor torna um serviço, como um site ou aplicativo, indisponível para seus usuários legítimos. O objetivo é causar uma falha ou interrupção intencional.

### **Por que um Ataque DoS Acontece?**

Existem vários motivos para um ataque DoS:

* **Sobrecarga:** O invasor envia tanto tráfego para um serviço que ele não consegue mais responder a ninguém.
* **Exploração de Falhas:** O ataque pode explorar uma vulnerabilidade de software ou uma falha de projeto para travar o sistema. (É por isso que é crucial manter tudo sempre atualizado com os patches mais recentes!)
* **Vantagem Competitiva:** Há casos documentados de empresas que atacaram concorrentes para tirá-los do ar e ganhar uma vantagem de mercado.
* **Distração (Cortina de Fumaça):** Um ataque DoS pode ser usado para distrair a equipe de TI enquanto o invasor explora outra vulnerabilidade mais crítica em outra parte da rede.

### **Quando o DoS é Acidental**

Curiosamente, às vezes nós mesmos causamos uma negação de serviço sem querer.

* **Erro de Configuração:** Conectar dois switches de rede um ao outro duas vezes pode criar um "loop", derrubando a rede se protocolos como o *Spanning Tree* não estiverem ativos.
* **Uso Excessivo de Recursos:** Tentar baixar um arquivo muito grande (como uma distribuição Linux) em uma conexão de internet lenta pode consumir toda a banda, tornando outros aplicativos inutilizáveis.
* **Acidentes Físicos:** Como no exemplo da aula, um cano de água que estoura sobre um data center certamente causa uma indisponibilidade geral dos serviços.

---

### **A Evolução: Ataque de Negação de Serviço Distribuído (DDoS) 🌐**

Os invasores raramente usam um único computador para atacar. Em vez disso, eles orquestram um **Ataque de Negação de Serviço Distribuído**, ou **DDoS (Distributed Denial of Service)**.

* **O que é?** Um DDoS utiliza milhares ou até milhões de dispositivos espalhados pelo mundo para atacar um único alvo ao mesmo tempo.
* **Como funciona?** Os invasores usam malwares para infectar computadores, criando uma rede de "robôs" ou "zumbis" chamada **Botnet**. O dono da botnet (o "pastor") pode enviar um único comando para que todos os dispositivos ataquem o alvo simultaneamente.
* **Escala do Problema:** Para se ter uma ideia, a botnet *Zeus*, em seu auge, controlava mais de **3,6 milhões de computadores**.

Isso é conhecido como uma **ameaça assimétrica**: um único invasor com recursos relativamente baixos pode derrubar organizações gigantescas com muito mais estrutura e banda de internet.

### **Técnica Avançada: Ataques de Amplificação e Reflexão**

Para tornar os ataques ainda mais eficientes, os invasores desenvolveram uma técnica inteligente que "amplifica" o poder de sua botnet. O princípio é: **enviar um pedido pequeno que gera uma resposta gigante**.

Essa técnica abusa de serviços de internet comuns e mal configurados, como servidores **DNS abertos** (*Open DNS Resolvers*).

#### **Como Funciona um Ataque de Amplificação de DNS?**

1.  **O Comando:** O invasor comanda sua botnet para iniciar o ataque.
2.  **O Pedido Falsificado (Spoofing):** Cada computador da botnet envia uma pequena consulta para um servidor DNS aberto. O truque é que eles **falsificam o endereço de origem**, colocando o endereço IP da vítima no lugar.
3.  **A Amplificação:** O servidor DNS, pensando que o pedido veio da vítima, responde com uma quantidade de dados muito maior.
    * **Exemplo:** Um pedido DNS de 15 caracteres (`dig any isc.org`) pode gerar uma resposta de 1.300 caracteres. Isso é uma **amplificação de 86 vezes!**
4.  **A Reflexão e a Sobrecarga:** Os servidores DNS enviam (refletem) essas respostas gigantescas para o endereço IP falsificado, ou seja, **a vítima**. Multiplique isso por milhares de bots e servidores DNS, e o alvo é rapidamente sobrecarregado e derrubado pelo volume massivo de tráfego que não solicitou.