Resumo do vídeo **Cloud-specific Vulnerabilities – CompTIA Security+ SY0-701 – 2.3**

---

#### **1. O Paradoxo da Nuvem: Acessibilidade vs. Segurança 🌐**

A nuvem se tornou essencial para quase todas as organizações, hospedando aplicações e dados sensíveis. A mesma característica que torna a nuvem pública tão poderosa — **a acessibilidade global** — é também sua maior fraqueza de segurança. Como a aplicação está disponível para o mundo todo, ela também está exposta a atacantes do mundo todo.

#### **2. Principais Ameaças e Vetores de Ataque**

Devido à sua natureza pública, as aplicações na nuvem são alvos de diversos tipos de ataques:

* **Ataques de Negação de Serviço (DDoS/DoS):** Atacantes podem facilmente tentar sobrecarregar a aplicação com tráfego para torná-la indisponível.
* **Falhas de Autenticação e Configuração:** Processos de autenticação fracos ou mal configurados são uma das principais causas de vazamento de dados.
* **Travessia de Diretórios (Directory Traversal):** Uma má configuração comum que permite a um atacante navegar pela estrutura de pastas do servidor web, acessando áreas que deveriam ser restritas. É como permitir que um visitante ande livremente pelos corredores de serviço de um prédio.
* **Sistemas Desatualizados (Unpatched):** A ameaça mais recorrente. Um sistema operacional ou aplicação sem as últimas correções de segurança pode permitir que um atacante execute facilmente um **ataque de execução remota de código (RCE)**, dando a ele controle total sobre o sistema na nuvem.

#### **3. Vulnerabilidades Específicas de Aplicação na Nuvem**

Além da infraestrutura, a própria aplicação pode ser o ponto fraco. Atacantes podem explorar falhas no código para ganhar acesso.

* **Exemplos de Alto Impacto: Log4j e Spring Cloud Function**
    * São vulnerabilidades recentes, famosas por serem **extremamente fáceis de explorar** e por concederem controle total do sistema ao atacante, tornando a "recompensa" pelo ataque muito alta.

* **Cross-Site Scripting (XSS):**
    * Ocorre quando a aplicação não valida corretamente os dados inseridos pelo usuário, permitindo que um atacante injete scripts maliciosos.

* **Escrita Fora dos Limites (Out-of-Bounds Write):**
    * Uma falha de manipulação de memória que permite a um atacante escrever dados em uma área da memória que não lhe é autorizada. Isso pode levar a uma execução remota de código ou simplesmente travar o sistema.

* **Injeção de SQL (SQL Injection):**
    * Como os dados também estão na nuvem, atacantes podem usar injeção de código, como SQLi, para contornar a segurança da aplicação e obter acesso direto ao banco de dados.
