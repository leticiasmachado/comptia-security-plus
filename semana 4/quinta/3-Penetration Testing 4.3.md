Resumo do vídeo **Penetration Testing – CompTIA Security+ SY0-701 – 4.3**

---

#### 1. O que é Teste de Penetração?

* **Definição:** O teste de penetração (ou "pen test") é um processo onde simulamos um ataque ativo contra nossos próprios sistemas.
* **Diferença (vs. Scan de Vulnerabilidade):** É semelhante a uma varredura de vulnerabilidades, com uma diferença crucial: no pen test, nós de fato **executamos *exploits*** para tentar ativamente ganhar acesso. A varredura apenas aponta *potenciais* falhas.
* **Por que fazer?** É considerado uma boa prática de segurança e, dependendo do tipo de negócio, pode ser obrigatório por questões de conformidade.
* **Referência:** O NIST (Instituto Nacional de Padrões e Tecnologia dos EUA) possui um documento guia sobre o assunto: "Guia Técnico para Teste e Avaliação de Segurança da Informação" (NIST 800-115).

#### 2. As Regras de Engajamento (Rules of Engagement - RoE)

Antes de qualquer teste, as "Regras de Engajamento" são fundamentais. Este é um documento formal que define o escopo e o propósito do teste para que todos os envolvidos estejam cientes.

* **Conteúdo das RoE:**
    * **Escopo (O que testar):** Quais sistemas, aplicativos ou faixas de endereço IP estão *em escopo* e podem ser testados.
    * **Fora de Escopo (O que NÃO testar):** Quais sistemas são críticos e **não** devem ser tocados para evitar a interrupção da produção.
    * **Cronograma:** Em que horários os testes são permitidos (ex: algumas empresas proíbem testes durante o horário comercial e só os permitem após as 18h).
    * **Tipo de Teste:** Define a abordagem (ex: invasão física do prédio, teste interno a partir da rede local, ou teste externo pela internet).
    * **Manuseio de Dados:** Como proceder caso informações sensíveis sejam descobertas durante o teste.
    * **Contatos de Emergência:** Quem contatar imediatamente caso algo saia do esperado.

#### 3. O Processo de Exploração

* **Objetivo:** Tentar se aproveitar de vulnerabilidades conhecidas para ganhar acesso a um sistema.
* **O Risco:** O próprio ato de explorar uma vulnerabilidade pode causar falhas. Por exemplo, tentar um *buffer overflow* para escalar privilégios pode travar o sistema operacional. É por isso que as RoE são tão importantes.
* **Métodos Comuns:** O teste pode envolver múltiplas técnicas:
    * Ataques de força bruta de senha.
    * Engenharia social (ex: por telefone).
    * Injeções de banco de dados (Database Injections).
    * Buffer overflows.
* **A Lógica:** Se nós conseguirmos explorar essas falhas, é altamente provável que um invasor externo também consiga.

#### 4. Pós-Exploração: O que Acontece Após o Acesso?

Obter acesso ao primeiro sistema é apenas o começo. O trabalho real começa *depois* da invasão inicial.

* **1. Persistência (Criar um Backdoor):**
    * O invasor (ou testador) quer garantir que poderá acessar o sistema novamente.
    * Eles não vão querer usar o mesmo *exploit* (pois a vulnerabilidade pode ser corrigida com um patch).
    * Em vez disso, eles criam um "backdoor": adicionam uma conta de usuário própria ou alteram senhas de contas existentes.
* **2. Movimento Lateral e Pivô (Pivoting):**
    * Firewalls geralmente protegem a rede de acessos *externos*. Mas, uma vez *dentro*, a movimentação entre sistemas internos é mais fácil.
    * O invasor usa o primeiro sistema comprometido como um "ponto de partida" (ou *pivô*).
    * Eles configuram esse sistema como um *relay* ou *proxy* para "pular" e atacar outros sistemas que estão dentro da mesma rede.

#### 5. Tópico Relacionado: Divulgação e Bug Bounties

* **O Ciclo de Vida de uma Vulnerabilidade:**
    1.  Um pesquisador identifica uma vulnerabilidade.
    2.  Ele informa o fabricante/desenvolvedor do software de forma privada.
    3.  O fabricante gasta tempo (semanas ou meses) para corrigir o código, testar e publicar um *patch* (atualização de segurança).
    4.  **Somente após** o patch estar disponível, a informação sobre a vulnerabilidade é tornada pública (ex: adicionada a uma lista CVE - Common Vulnerabilities and Exposures).
* **Bug Bounties (Recompensas por Falhas):**
    * É um processo incentivado por "bug bounties".
    * São recompensas em dinheiro, oferecidas por fabricantes, para pesquisadores que encontram e reportam vulnerabilidades de forma responsável (permitindo que a falha seja corrigida antes de se tornar pública).