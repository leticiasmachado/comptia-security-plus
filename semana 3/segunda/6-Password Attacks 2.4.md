Resumo do vídeo **Password Attacks – CompTIA Security+ SY0-701 – 2.4**

---

### **Hashing de Senhas**

Em vez de salvar a senha original, os sistemas seguros salvam uma representação matemática dela chamada **hash**.

* **O que é um Hash?** Pense no hash como uma **"impressão digital"** da sua senha. É um processo de mão única: é fácil gerar a impressão digital a partir da sua mão, mas é impossível reconstruir sua mão a partir da impressão digital.
* **Características Importantes:**
    1.  **É Irreversível:** Não há como "desfazer" um hash para descobrir a senha original.
    2.  **Efeito Avalanche:** Uma pequena mudança na senha (adicionar um único caractere) gera um hash completamente diferente.
    3.  **Tamanho Fixo:** Senhas curtas e longas produzem hashes do mesmo tamanho.


Observe como as senhas `123456` e `1234567` têm hashes totalmente distintos, apesar da pequena diferença entre elas.

---

### **Ataques a Senhas: Como os Invasores Tentam Adivinhar**

Mesmo com hashes, os invasores tentam descobrir as senhas. Para se proteger, os sistemas geralmente implementam o **bloqueio de conta** após várias tentativas de login falhas. Os invasores usam técnicas para contornar ou lidar com isso.

#### **1. Ataque de Pulverização (Password Spraying) 💦**

Este é um ataque do tipo "devagar e sempre", projetado para **evitar o bloqueio de contas**.

* **Como Funciona?** Em vez de tentar muitas senhas em uma única conta, o invasor pega **uma ou duas senhas muito comuns** (como `123456` ou `password`) e as "pulveriza" em **centenas ou milhares de contas de usuário diferentes**.
* **O Objetivo:** Encontrar as "frutas mais baixas no pé" — aquelas contas protegidas por senhas extremamente fracas — sem disparar nenhum alarme. Se a senha não funcionar, ele simplesmente passa para a próxima conta.

#### **2. Ataque de Força Bruta (Brute Force) 💥**

Este é o método de "tentativa e erro" em massa, onde o invasor tenta **todas as combinações possíveis** de caracteres até encontrar a senha.

* **Força Bruta Online:** Tentar adivinhar a senha no site ou aplicativo real. É **lento e ineficaz**, pois rapidamente levará ao bloqueio da conta.
* **Força Bruta Offline (O Perigo Real):** Este é o método mais poderoso e comum.
    1.  **O Roubo:** Primeiro, o invasor precisa obter o arquivo do sistema que contém a lista de usuários e seus **hashes de senha**.
    2.  **A "Adivinhação":** Com o arquivo em mãos, o invasor usa seus próprios computadores potentes para trabalhar *offline*. Ele pega um hash roubado e começa a testar senhas (`aaaaa`, `aaaab`, `aaaac`...).
    3.  **A Comparação:** Para cada tentativa, ele calcula o hash correspondente e o compara com o hash roubado. Quando os dois hashes batem, ele descobriu a senha.

Como o ataque é offline, **não há bloqueio de contas, não há alarmes e não há lentidão da rede**. As únicas limitações do invasor são seu poder computacional e o tempo. É por isso que ter senhas longas e complexas é crucial, pois elas tornam o processo de força bruta offline exponencialmente mais demorado.