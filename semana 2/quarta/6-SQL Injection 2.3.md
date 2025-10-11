Resumo do vídeo **SQL Injection – CompTIA Security+ SY0-701 – 2.3**

-----

#### **1. O que é Injeção de Código?**

A **Injeção de Código (Code Injection)** é um tipo de ataque muito comum em que um invasor insere seu próprio código malicioso nos campos de entrada de dados de uma aplicação (como formulários de login, campos de busca, etc.).

A falha acontece quando os desenvolvedores da aplicação não implementam verificações adequadas para filtrar ou validar o que o usuário digita. Isso permite que o código do atacante seja processado pela aplicação como se fosse um comando legítimo.

Existem vários tipos de injeção de código, incluindo:

  * Injeção de HTML
  * **Injeção de SQL (a mais comum)**
  * Injeção de XML
  * E outras.

#### **2. Aprofundando em SQL Injection (SQLi)**

**SQL (Structured Query Language)** é a linguagem padrão usada por aplicações para se comunicar com bancos de dados (para buscar, inserir, ou deletar informações).

Um ataque de **Injeção de SQL (SQLi)** ocorre quando um atacante consegue inserir seus próprios comandos SQL em uma consulta que a aplicação faz ao banco de dados. Se a aplicação não tiver as devidas proteções, ela envia esses comandos maliciosos diretamente para o banco de dados, que os executa.

A exploração dessa vulnerabilidade muitas vezes é simples, podendo ser feita diretamente no navegador, apenas digitando o código malicioso nos campos de entrada da página.

#### **3. A Anatomia de um Ataque SQLi**

Para entender como funciona, vamos analisar a estrutura de uma consulta SQL.

  * **Consulta Normal (O que deveria acontecer):**
    Um usuário busca pelo nome "Professor" em um campo de pesquisa. A aplicação gera o seguinte comando SQL para o banco de dados:

    ```sql
    SELECT * FROM users WHERE name = 'Professor';
    ```

    Este comando pede ao banco de dados para selecionar todos os dados (`*`) da tabela `users` onde o `name` seja igual a `Professor`.

  * **Consulta com Injeção (O que o atacante faz):**
    O atacante, em vez de digitar apenas o nome, insere uma lógica SQL adicional. Por exemplo, ele digita no campo de busca: `Professor' OR '1'='1`. A aplicação, sem validar, gera o seguinte comando:

    ```sql
    SELECT * FROM users WHERE name = 'Professor' OR '1'='1';
    ```

    **Análise da Injeção:**

      * A condição `'1'='1'` é **universalmente verdadeira**.
      * A cláusula `WHERE` agora verifica se o nome é `Professor` **OU** se `1` é igual a `1`.
      * Como `1=1` é sempre verdade, a condição se torna verdadeira para **TODAS as linhas** da tabela, ignorando completamente a busca pelo nome.

    Se você vir um código sendo enviado a um banco de dados com a condição `'1'='1'`, é quase certeza que se trata de uma tentativa de SQL Injection.

#### **4. Consequências de um Ataque SQLi Bem-Sucedido**

Como o atacante consegue contornar a segurança da aplicação e enviar comandos diretamente ao banco de dados, ele ganha controle total sobre os dados. Um ataque bem-sucedido permite:

  * **Visualizar** todos os dados, incluindo informações sensíveis de outros usuários.
  * **Alterar** informações existentes.
  * **Deletar** todos os dados do banco.
  * **Derrubar** o banco de dados, causando uma Negação de Serviço (DoS).

#### **5. Exemplo Prático com WebGoat**

O vídeo usa o **WebGoat**, uma aplicação deliberadamente vulnerável para fins de treinamento.

  * **Cenário Normal:**
    Um funcionário chamado `Smith` insere seu nome e um número de autenticação (TAN), por exemplo, `3SL99A`. A aplicação retorna apenas o departamento de Smith.

  * **Cenário com Injeção:**
    O atacante insere o nome `Smith`, mas no campo do TAN, ele digita a seguinte string:
    `3SL99A' OR '1'='1`

    A consulta ao banco de dados se torna algo como: "Busque o departamento onde o TAN seja `3SL99A` **OU** onde `1` seja igual a `1`".

  * **Resultado:**
    Como `1=1` é sempre verdade, o banco de dados retorna as informações de **TODOS os funcionários**, não apenas de Smith. Com isso, o atacante obtém acesso irrestrito a todos os dados daquela tabela.
