Resumo do vídeo **Password Security – CompTIA Security+ SY0-701 – 4.6**

---

### 1. Criando Políticas de Senha Fortes

O objetivo de uma senha forte é aumentar a **entropia** (imprevisibilidade) para dificultar que um invasor a adivinhe (seja por ataque de força bruta ou *password spraying*).

**Requisitos Comuns para Senhas Fortes:**
* **Complexidade:** Deve incluir uma mistura de:
    * Letras maiúsculas
    * Letras minúsculas
    * Números
    * Caracteres especiais
* **Comprimento:** Um mínimo de 8 caracteres é comum, mas esse número está aumentando à medida que o poder de processamento melhora. Usar "frases-senha" (um conjunto de palavras) é uma boa forma de criar senhas longas.
* **Idade da Senha (Expiração):** Um temporizador que define quando a senha deve ser alterada (ex: a cada 30, 60 ou 90 dias). Se a senha expirar, o usuário não consegue logar. Em sistemas críticos, esse tempo pode ser muito menor (7 ou 15 dias).
* **Histórico de Senha:** O sistema lembra suas senhas antigas para impedir que você as reutilize.

### 2. O Desafio: Gerenciadores de Senha

* **A Melhor Prática:** Usar uma senha **diferente** para **cada** conta.
* **O Problema:** É impossível lembrar de dezenas de senhas complexas e únicas.
* **A Solução: Gerenciador de Senhas (Password Manager):**
    * **O que é:** Um software que armazena todas as suas senhas em um único banco de dados.
    * **Segurança:** Esse banco de dados é **criptografado**, e o acesso a ele é protegido por uma senha mestra forte ou autenticação multifator.
    * **Recursos:**
        * Gera automaticamente senhas novas, longas e aleatórias.
        * Preenche formulários de login automaticamente.
        * Fornece um relatório da "saúde" das suas senhas (ex: se estão fracas, reutilizadas ou se foram comprometidas em vazamentos).
    * **Disponibilidade:** Podem ser integrados ao sistema operacional, aplicativos de terceiros ou soluções corporativas para empresas.

### 3. Alternativas às Senhas Tradicionais

Como muitas pessoas não usam gerenciadores e reutilizam senhas, os sistemas estão migrando para métodos alternativos.

#### A. Autenticação Sem Senha (Passwordless)
* **Por quê?** Resolve o problema da reutilização de senhas e a necessidade de memorizá-las.
* **O que é:** Fazer login em um sistema sem digitar uma senha tradicional.
* **Exemplos:**
    * Reconhecimento facial para desbloquear um celular.
    * Usar um PIN (Número de Identificação Pessoal) para logar no Windows.
* **Nota Importante:** Muitas vezes, a autenticação sem senha é usada *em conjunto* com uma senha. Você usa a senha na configuração inicial e, a partir daí, usa o método sem senha (como o PIN ou biometria) no dia a dia.

#### B. Acesso Just-in-Time (JIT)
* **O Problema (para TI):** Em departamentos de TI, muitos técnicos precisam de acesso administrativo a vários sistemas. Conceder-lhes acesso de administrador permanente em suas contas de usuário normais é um risco de segurança enorme.
* **A Solução (JIT):** Conceder permissões administrativas (ou outras permissões elevadas) de forma **temporária**, por um **tempo limitado**, usando **credenciais temporárias**.
* **Como Funciona o Fluxo do JIT:**
    1.  Um "Cofre de Senhas" (Password Vault) central armazena as credenciais *primárias* (as senhas de administrador reais).
    2.  O técnico solicita permissão a esse cofre para realizar uma tarefa.
    3.  O cofre **não** entrega a senha primária ao técnico. Em vez disso, ele cria um novo conjunto de credenciais *efêmeras* (temporárias) com os direitos necessários.
    4.  As credenciais temporárias são atribuídas ao técnico.
    5.  O técnico usa essas credenciais para resolver o problema.
    6.  Após a sessão terminar (ou o tempo expirar), as credenciais temporárias são excluídas.
* **Benefício de Segurança:** As credenciais primárias (de administrador) nunca são expostas. Se a conta normal do técnico for comprometida, o invasor não terá acesso administrativo.