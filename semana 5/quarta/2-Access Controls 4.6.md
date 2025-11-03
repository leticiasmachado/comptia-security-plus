Resumo do vídeo **Access Controls – CompTIA Security+ SY0-701 – 4.6**

---

### 1. O que é Controle de Acesso?

Após um usuário se **autenticar** (provar quem é), o **controle de acesso** é o processo que define quais recursos e dados ele pode acessar. Trata-se de aplicar as políticas de segurança da organização para permitir ou negar o acesso a dados, seja para um indivíduo ou para um grupo.

---

### 2. O Princípio Fundamental: Menor Privilégio (Least Privilege)

Antes de ver os modelos, a melhor prática de segurança que se aplica a *todos* eles é o **princípio do menor privilégio**.

* **Definição:** Significa que a um usuário devem ser atribuídos *exatamente* os direitos e permissões necessários para ele realizar seu trabalho, e **nada mais**.
* **Por que usá-lo?** Por padrão, todos os usuários têm privilégios limitados. Se um usuário executar um software malicioso (malware), esse malware só terá as permissões limitadas daquele usuário, o que ajuda a conter o escopo do dano.

---

### 3. Modelos de Controle de Acesso

Existem diferentes modelos que as organizações podem escolher para gerenciar o acesso.

#### 1. Controle de Acesso Mandatório (MAC - Mandatory Access Control)
* **Como funciona:** Usado em ambientes de altíssima segurança. O **administrador** do sistema atribui "rótulos" (labels) a todos os recursos (arquivos, pastas, etc.).
* **Exemplos de Rótulos:** Confidencial, Secreto, Ultra-Secreto.
* **Quem controla:** O **administrador** é quem define quais usuários podem acessar quais rótulos (ex: "Usuários do departamento de envio só podem ver dados Confidenciais", "A alta administração pode ver dados Ultra-Secretos").
* **Ponto-chave:** O usuário **não pode** alterar essas permissões.

#### 2. Controle de Acesso Discricionário (DAC - Discretionary Access Control)
* **Como funciona:** O **dono** (ou criador) do dado tem a "discrição" (o poder) de decidir quem pode acessá-lo e quais permissões essa pessoa terá.
* **Exemplo:** Você cria uma planilha e decide quem pode apenas ler e quem pode editar o arquivo.
* **Vantagem:** Muito flexível para o usuário.
* **Desvantagem:** Menos seguro, pois depende que cada usuário individual configure as permissões de segurança corretamente para cada dado que cria.

#### 3. Controle de Acesso Baseado em Função (RBAC - Role-Based Access Control)
* **Como funciona:** É um modelo centralizado e o mais comum em empresas. O acesso é baseado na **função (cargo)** do usuário na organização.
* **Fluxo de Trabalho:**
    1.  O administrador cria **grupos** que correspondem a funções (ex: "Gerentes", "Diretores", "Equipe de Envio").
    2.  O administrador atribui as permissões necessárias diretamente ao *grupo*.
    3.  Os usuários são simplesmente adicionados aos grupos apropriados e **herdam** implicitamente todas as permissões daquele grupo.
* **Exemplo:** O grupo "Envio" tem permissão para usar o software de envio. O grupo "Gerentes de Envio" tem as permissões do grupo "Envio" *mais* permissão para ver os logs de envio.

#### 4. Controle de Acesso Baseado em Regras (Rule-Based Access Control)
* **Como funciona:** O acesso é determinado por uma lista de **regras** impostas pelo sistema e criadas pelo administrador. O usuário não tem controle sobre elas.
* **Lógica:** Uma regra é criada e associada a um objeto (recurso). Quando um usuário tenta acessar o objeto, o sistema verifica se alguma regra se aplica a ele.
* **Exemplo 1 (Horário):** Usuários só podem acessar os dados do laboratório entre 9h e 17h.
* **Exemplo 2 (Software):** Um formulário em uma página web só pode ser preenchido por alguém usando o navegador Chrome.

#### 5. Controle de Acesso Baseado em Atributos (ABAC - Attribute-Based Access Control)
* **Como funciona:** É um modelo mais moderno e complexo, considerado a "próxima geração". Ele toma decisões de acesso combinando múltiplos **atributos** (critérios).
* **Exemplos de Atributos:**
    * Endereço IP do usuário
    * Hora do dia
    * Ação desejada (leitura vs. escrita)
    * Localização geográfica
    * Relação do usuário com o dado
* **Vantagem:** Permite que administradores criem conjuntos de regras muito complexos e granulares.

---

### 4. Restrição Comum: Restrições de Horário (Time of Day)

* Uma restrição de "hora do dia" pode ser aplicada *sobre* muitos dos modelos acima (especialmente RBAC e Rule-Based).
* O administrador pode permitir ou negar acesso a um recurso com base no horário.
* **Desafio:** Em organizações globais, é preciso gerenciar fusos horários diferentes.
* **Exemplo:** Os bancos de dados de P&D (Pesquisa e Desenvolvimento) só podem ser acessados entre 8h e 18h. A rede da sala de treinamento fica inacessível entre meia-noite e 6h.