Resumo do vídeo **Cross-site Scripting – CompTIA Security+ SY0-701 – 2.3**

---

#### **1. O que é Cross-Site Scripting (XSS)?**

**Cross-Site Scripting (XSS)** é um dos ataques mais comuns em aplicações web. Ele permite que um invasor **injete scripts maliciosos** (geralmente JavaScript) em um site confiável. Quando uma vítima visita esse site, o script malicioso é executado no navegador dela.

O ataque explora a confiança que o navegador tem no site visitado, usando-o como um "mensageiro" para entregar o código malicioso.

> **Por que XSS e não CSS?** A sigla `CSS` já era usada para *Cascading Style Sheets* (folhas de estilo), então a comunidade de segurança adotou `XSS` para evitar confusão.

#### **2. Como Funciona um Ataque XSS? (Visão Geral)**

O fluxo básico de um ataque XSS geralmente segue estes passos:

1.  **O Atacante Cria um Link Malicioso:** O atacante prepara um link que aponta para um site legítimo, mas que contém um script malicioso embutido.
2.  **O Atacante Envia o Link para a Vítima:** Isso pode ser feito por e-mail, mensagem de texto ou qualquer outro meio.
3.  **A Vítima Clica no Link:** O navegador da vítima acessa o site confiável.
4.  **Execução do Script:** O site vulnerável executa o script malicioso no navegador da vítima, que acredita que o código é parte do site legítimo.
5.  **Roubo de Dados:** O script, rodando secretamente, envia informações privadas da vítima (como cookies, IDs de sessão, etc.) para o atacante.

#### **3. Tipos de Ataques XSS**

##### **3.1. XSS Refletido (Non-Persistent): O Ataque via Link**

Neste tipo, o script malicioso está contido no próprio link enviado pelo atacante. O servidor do site vulnerável "reflete" esse script de volta para o navegador da vítima, que o executa.

* **Característica Principal:** O ataque não é permanente. Ele só funciona se a vítima clicar no link especialmente criado pelo atacante.
* **Exemplo Prático:** Um campo de busca em um site que não valida o que é digitado. Um atacante pode criar um link de busca que, em vez de um termo, contém um script. Ao clicar, o site exibe a "busca" e executa o script. No vídeo, um script é injetado no campo do número do cartão de crédito de um carrinho de compras, roubando o ID da sessão do usuário. Um ataque real faria isso de forma invisível para a vítima.

##### **3.2. XSS Persistente (Stored): O Ataque Armazenado no Site**

Este tipo é mais perigoso. O atacante consegue **salvar o script malicioso diretamente no servidor** do site.

* **Característica Principal:** O script fica "armazenado" em locais como seções de comentários, posts de fóruns ou perfis de redes sociais. **Qualquer pessoa** que visitar a página onde o script está salvo se tornará uma vítima.
* **Analogia:** É como uma "pichação" maliciosa em um mural público. Todos que olharem para o mural serão afetados.
* **Potencial Viral:** Em redes sociais, o script pode ser programado para se auto-compartilhar no perfil de cada vítima, espalhando o ataque de forma exponencial.

#### **4. Estudo de Caso Real: A Vulnerabilidade no Site da Subaru (2017)**

Este caso mostra como o XSS pode ser combinado com outras falhas para criar um risco enorme.

* **Falha 1: Token que Nunca Expira:** Ao logar no site da Subaru para gerenciar seu veículo, o usuário recebia um token de autenticação que era válido para sempre.
* **Falha 2: Token Superpoderoso:** Este token permitia executar qualquer ação no veículo e até mesmo adicionar o e-mail do atacante na conta de outra pessoa.
* **Falha 3: A Vulnerabilidade XSS:** O site possuía uma falha de XSS Refletido.

**Ataque Combinado:** Um atacante poderia enviar um link malicioso para um dono de Subaru. Ao clicar, o script XSS roubaria o token de autenticação da vítima. Como o token era permanente e superpoderoso, o atacante ganhava **controle total e para sempre** sobre o veículo da vítima. Felizmente, a falha foi descoberta por um pesquisador de segurança e corrigida.

#### **5. Como se Proteger Contra XSS?**

A proteção envolve ações tanto do usuário quanto do desenvolvedor.

* **Para Usuários:**
    * **Não clique em links suspeitos** recebidos por e-mail ou mensagens.
    * **Digite os endereços** dos sites importantes diretamente no navegador.
    * **Mantenha seu navegador e aplicativos sempre atualizados.** As atualizações frequentemente corrigem vulnerabilidades de XSS conhecidas.
    * Desabilitar o JavaScript oferece proteção, mas pode quebrar a funcionalidade da maioria dos sites modernos.

* **Para Desenvolvedores:**
    * **A regra de ouro: Validação de Entrada (Input Validation).** A responsabilidade final é do desenvolvedor. É essencial verificar e "limpar" (sanitizar) **TODAS** as entradas de dados do usuário para garantir que nenhum script possa ser injetado e executado.
