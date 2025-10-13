Resumo do vídeo **Application Attacks – CompTIA Security+ SY0-701 – 2.4**

---

Muitos ataques cibernéticos não miram na rede ou no hardware, mas sim nas **aplicações** que usamos todos os dias, como sites, bancos de dados e sistemas operacionais. Esses ataques exploram falhas na programação ou na configuração do software. Vamos ver os tipos mais comuns.

### **1. Ataques de Injeção e Overflow**

Esses ataques acontecem quando uma aplicação não **valida corretamente os dados que recebe** de um usuário.

* **💉 Ataque de Injeção (Injection Attack):** O invasor insere um código malicioso em um campo de entrada (como um formulário de login ou uma barra de busca). Se a aplicação não filtrar essa entrada, ela pode executar o código do invasor. O tipo mais famoso é a **Injeção de SQL**, mas também pode ocorrer com HTML, XML e LDAP.

* **🗑️ Buffer Overflow:** Pense em uma variável na memória como um "copo" com um tamanho definido. O invasor tenta colocar mais "líquido" (dados) do que o copo suporta. O excesso de dados **transborda** para áreas de memória adjacentes, o que pode causar um travamento do sistema ou, no pior cenário, permitir que o invasor execute seu próprio código. É um ataque difícil de ser executado com sucesso, mas muito poderoso se funcionar.

### **2. Escalação de Privilégios (Privilege Escalation)**

Este ataque ocorre quando um invasor, que já conseguiu um acesso limitado ao sistema (como um usuário comum), explora uma vulnerabilidade para **obter permissões mais altas**.

* **O Objetivo:** "Subir na hierarquia" para se tornar um administrador ou obter acesso `SYSTEM`, o nível mais alto de privilégio.
* **Tipos:**
    * **Vertical:** Um usuário comum se torna administrador.
    * **Horizontal:** O invasor ganha acesso aos dados de outro usuário com o mesmo nível de permissão (ex: Usuário A acessa a conta do Usuário B).
* **Exemplo Real (CVE-2023-29336):** Uma vulnerabilidade no Windows que permitia a um invasor explorar o driver `win32k` para obter privilégios de `SYSTEM`, dando-lhe controle total sobre o sistema operacional.

> **🛡️ Como se defender?** A principal defesa é **manter tudo atualizado (patching)**. Sistemas operacionais modernos também usam técnicas como **DEP** (Prevenção de Execução de Dados) e **ASLR** (Randomização do Layout do Espaço de Endereçamento) para dificultar esses ataques.

### **3. Falsificação de Solicitação Entre Sites (CSRF / XSRF)**

Também conhecido como "Sea-Surf", este é um ataque engenhoso que engana o seu navegador para que ele realize ações indesejadas em um site no qual você já está logado.

* **Como funciona?** O ataque explora a **confiança** que um site (ex: seu banco) tem no seu navegador.
    1.  Você faz login no site do seu banco normalmente.
    2.  O invasor lhe envia um link malicioso (por e-mail, mensagem, etc.).
    3.  Você clica no link. Sem que você perceba, seu navegador envia uma solicitação forjada para o site do banco (que confia no seu navegador) para realizar uma ação, como transferir dinheiro para a conta do invasor.
* **A Vítima não Vê Nada:** Tudo acontece nos bastidores. O usuário muitas vezes nem percebe que a ação fraudulenta ocorreu.

> **🛡️ Como se defender?** Sites modernos usam **tokens anti-falsificação**. Para cada ação sensível, o servidor exige um "token" secreto e único que o invasor não possui, tornando a solicitação forjada inválida.

### **4. Travessia de Diretório (Directory Traversal)**

Este ataque explora uma **má configuração do servidor web** para permitir que um invasor acesse arquivos e pastas fora do diretório raiz do site.

* **O Truque:** O invasor manipula a URL, usando a sequência `../` para "subir" na árvore de diretórios do servidor.
* **O Objetivo:** Ler arquivos sensíveis que não deveriam ser públicos, como arquivos de configuração do sistema (`windows/system.ini`), senhas ou outros dados sigilosos.



> **Conclusão:** A causa raiz da maioria desses ataques a aplicações é a mesma: uma **falha na validação das entradas do usuário**. Práticas de programação segura e a manutenção constante de sistemas atualizados são as melhores defesas contra essas ameaças.