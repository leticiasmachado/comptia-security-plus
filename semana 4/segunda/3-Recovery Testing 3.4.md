Resumo do vídeo **Recovery Testing – CompTIA Security+ SY0-701 – 3.4**

---

Ter um plano de recuperação de desastres (DRP) não é suficiente; é crucial testar esse plano regularmente para garantir que ele funcione.

#### **1. Testes de Recuperação (Recovery Testing)**

* **Objetivo:** Validar o processo e os procedimentos de recuperação em caso de um desastre real.
* **Características Principais:**
    * **Regularidade:** Devem ser feitos periodicamente.
    * **Escopo Definido:** Foca em um cenário de recuperação específico (ex: falha de um servidor, perda de um site).
    * **Segurança:** O teste **não deve afetar** os sistemas de produção.
    * **Processo:** Tem um tempo alocado para o teste e, ao final, a equipe avalia o desempenho e faz os ajustes necessários no plano.

#### **2. Exercício de Simulação Teórica (Tabletop Exercise)**

* **Problema:** Testes de recuperação completos são caros e complexos (ex: mover toda a equipe para um site de recuperação apenas para um teste).
* **Solução (Tabletop):** Uma alternativa de baixo custo. É uma reunião onde a equipe *discute* os passos do plano de recuperação, "como se" estivessem executando-o.
* **Benefício:** Permite que diferentes departamentos (TI, negócios) validem seus planos em conjunto e identifiquem falhas logísticas ou lacunas no plano sem o custo e a interrupção de uma execução real.

#### **3. Teste de Failover (Failover Test)**

* **Objetivo:** Testar especificamente se as configurações redundantes (como Alta Disponibilidade - HA) conseguem "virar a chave" (fazer o failover) automaticamente em caso de falha.
* **Funcionamento Ideal:** A falha ocorre, o sistema de backup assume automaticamente, e os usuários são redirecionados sem perceber que estão usando os sistemas secundários.
* **Requisito:** Exige sistemas redundantes (ex: múltiplos switches, firewalls, roteadores, links de internet de provedores diferentes).
* **Exemplo de Design:** Uma infraestrutura pode ter múltiplas conexões de internet, múltiplos roteadores e firewalls. Se um link (ex: o firewall primário) falhar, o tráfego é automaticamente roteado pelo link secundário.

#### **4. Simulações de Segurança (Simulations)**

* **Objetivo:** Testar a eficácia dos controles de segurança e do treinamento dos usuários contra ameaças ativas.
* **Exemplos:**
    * Teste do processo de redefinição de senha.
    * Tentativa de exfiltração de dados (para ver se os sistemas de monitoramento detectam).
    * Simulação de ataque de **phishing**.

* **Foco: Simulação de Phishing**
    * **Processo:** Criar um e-mail de phishing falso, mas convincente, e enviá-lo a todos os funcionários.
    * **Metas do Teste:**
        1.  Verificar se os filtros de e-mail e sistemas de segurança automatizados detectam e bloqueiam o phishing.
        2.  Identificar quais usuários clicam no link. Esses usuários podem (e devem) ser direcionados para um treinamento adicional.

#### **5. Processamento Paralelo (Como Método de Resiliência)**

* **Conceito:** Usar múltiplas CPUs ou processos simultaneamente para processar transações.
* **Implementação:** Pode ser um único dispositivo com múltiplos núcleos (multi-core) ou múltiplos computadores (nós) trabalhando juntos.
* **Benefício (Eficiência):** Em vez de uma única CPU processar transações complexas, a carga é distribuída, tornando o processo mais rápido.
* **Benefício (Resiliência):** Se um dos processadores falhar, a carga pode ser redistribuída entre os processadores restantes, mantendo o serviço operacional.