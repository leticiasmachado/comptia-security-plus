Resumo do vídeo **Race Conditions – CompTIA Security+ SY0-701 – 2.3**.

---

#### **1. O que é uma Condição de Corrida?**

Uma **Condição de Corrida (Race Condition)** ocorre quando o resultado de uma operação depende da sequência ou do tempo de eventos que ocorrem de forma descontrolada. 
Em software, isso acontece quando dois ou mais processos tentam acessar e manipular o mesmo recurso (como uma área de memória ou um arquivo) quase ao mesmo tempo, e a aplicação 
não foi programada para lidar com essa simultaneidade.

Embora os desenvolvedores verifiquem isso, combinações inesperadas de eventos podem levar a resultados falhos ou a vulnerabilidades de segurança. É a falha clássica de 
"quem chegou primeiro?".

#### **2. Tipo Comum: Ataque TOCTOU (Time-Of-Check to Time-Of-Use)**

Uma das formas mais comuns de explorar uma condição de corrida é através de um ataque **TOCTOU**, que significa **"Tempo de Verificação para Tempo de Uso"**.

O ataque explora a pequena janela de tempo que existe entre o momento em que a aplicação **verifica** uma informação (por exemplo, "o usuário tem permissão para acessar este arquivo?") 
e o momento em que ela **usa** essa informação (por exemplo, "abrir o arquivo para o usuário").

* **Passo 1 (Check):** A aplicação verifica uma condição ou permissão.
* **Passo 2 (Intervalo Vulnerável):** Um atacante, agindo rapidamente, altera essa condição *antes* que a aplicação possa agir.
* **Passo 3 (Use):** A aplicação age com base na informação já desatualizada da verificação, permitindo uma ação não autorizada.

Se a aplicação não levar em conta que o valor pode mudar nesse intervalo, ela se torna vulnerável a uma condição de corrida.

#### **3. Exemplos Práticos**

**Exemplo 1: Transferência Bancária com Falha de Sincronização**

Imagine uma aplicação bancária com uma falha de design: depósitos são atualizados instantaneamente para todos, mas saques demoram para serem refletidos no sistema.

* **Cenário Inicial:**
    * Conta A: $100
    * Conta B: $100
    * Dois usuários (Usuário 1 e Usuário 2) tentarão transferir $50 da Conta A para a Conta B simultaneamente.

* **Passo a Passo da Falha:**
    1.  Ambos os usuários verificam os saldos e veem que ambas as contas têm $100.
    2.  O Usuário 1 deposita $50 na Conta B. O saldo de B é atualizado instantaneamente para **$150**.
    3.  O Usuário 2 também deposita $50 na Conta B. O saldo de B é atualizado novamente para **$200**. (Até aqui, tudo certo).
    4.  Agora, o Usuário 1 saca $50 da Conta A. Na sua visão, o saldo da Conta A se torna **$50**.
    5.  O Usuário 2 faz a mesma operação: saca $50 da Conta A. Como os saques não são atualizados instantaneamente para todos, o sistema ainda "pensa" que a Conta A tem o valor original antes do saque do Usuário 1. Portanto, na visão do Usuário 2, o saldo da Conta A também se torna **$50**.

* **Resultado Final (Incorreto):**
    * Conta A: **$50**
    * Conta B: **$200**

* **O que Deveria Ter Acontecido:**
    * Dois saques de $50 foram feitos da Conta A ($100 - $50 - $50). O saldo final da Conta A deveria ser **$0**. A condição de corrida permitiu que $50 fossem "criados do nada" devido à falta de sincronização dos saques.

**Exemplo 2: O Robô Mars Rover Spirit (2004)**

O robô da NASA em Marte entrou em uma condição de corrida real.
* **O Problema:** Um erro fatal no sistema de arquivos fazia com que o robô acionasse um mecanismo de segurança para reiniciar.
* **A Condição de Corrida:** Durante a reinicialização, o sistema detectava o mesmo erro no sistema de arquivos novamente *antes* de conseguir se corrigir, o que o forçava a reiniciar de novo. Isso criou um **loop de reinicialização infinito**.
* **A Solução:** Os desenvolvedores tiveram que enviar um código para o robô ignorar o erro temporariamente, quebrando o loop e permitindo que ele voltasse a operar.
