Resumo do vídeo **Cryptographic Attacks – CompTIA Security+ SY0-701 – 2.4**

---

A segurança da criptografia geralmente depende de uma **chave secreta**. No entanto, como os invasores raramente têm acesso a essa chave, eles tentam atacar o "cofre" em si — ou seja, a própria criptografia.

Curiosamente, os algoritmos criptográficos são públicos para que todos possam analisá-los e encontrar falhas. Se uma fraqueza é descoberta, o algoritmo é abandonado. Por isso, a maior vulnerabilidade hoje em dia não costuma ser o algoritmo, mas sim a **implementação incorreta** da criptografia.

### **1. Ataque de Aniversário e Colisão de Hash**

Este ataque tem um nome curioso, baseado no **Paradoxo do Aniversário**: em um grupo de apenas 23 pessoas, a chance de duas delas fazerem aniversário no mesmo dia é de cerca de 50%. Isso acontece porque estamos procurando por *qualquer par* de pessoas, não por uma data específica.

Na criptografia, esse conceito é aplicado para encontrar uma **colisão de hash**.

* **O que é um Hash?** Um hash é como uma "impressão digital" digital de um dado. Duas informações diferentes deveriam, idealmente, ter hashes completamente diferentes.
* **O que é uma Colisão de Hash?** É quando **duas informações diferentes** acabam gerando **exatamente o mesmo hash**. É como encontrar duas pessoas diferentes com a mesma impressão digital, o que quebra a confiança no sistema.

#### **O Caso do MD5: Um Algoritmo Quebrado**

O **MD5** é um algoritmo de hash antigo. Em 2008, pesquisadores provaram que ele era inseguro ao criar um certificado de segurança falso que parecia legítimo porque conseguiram gerar uma colisão de hash. Eles criaram um certificado que nunca foi assinado por uma autoridade real, mas que passava na validação do hash MD5. Isso forçou a indústria a abandonar o MD5 para fins de segurança.



> **🛡️ Como se defender?** Usar algoritmos de hash modernos e com uma saída de dados muito grande (como o SHA-256). Quanto maior o hash, mais difícil é encontrar uma colisão.

---

### **2. Ataque de Downgrade (Rebaixamento)**

Este é um ataque à **implementação** da criptografia. O objetivo é forçar dois dispositivos que estão tentando se comunicar de forma segura a usarem uma criptografia mais fraca, ou pior, **nenhuma criptografia**.

#### **Exemplo Prático: SSL Stripping (Remoção de SSL)**

O SSL Stripping é um tipo de ataque de downgrade que requer que o invasor esteja "no meio do caminho" (um ataque *Man-in-the-Middle*).

* **Como Funciona?**
    1.  **O Início Inseguro:** Você digita `meubanco.com` no navegador. A primeira requisição é feita usando `HTTP` (inseguro).
    2.  **A Resposta do Servidor:** O servidor do banco responde: "Por favor, mude para a versão segura, `HTTPS`".
    3.  **A Interceptação:** O invasor, que está no meio, **intercepta essa resposta** e não a entrega a você.
    4.  **O Invasor como Ponte:**
        * O invasor estabelece uma conexão segura (`HTTPS`) com o servidor do banco.
        * Ao mesmo tempo, ele mantém a sua conexão com ele em `HTTP` (insegura).
    5.  **O Roubo:** Você vê uma página que parece normal (mas sem o cadeado de segurança) e insere seu usuário e senha. Como sua conexão com o invasor é `HTTP`, ele vê tudo em **texto plano**. Ele então pega suas credenciais e as envia para o banco pela conexão segura que ele abriu.



O resultado é que você consegue usar o site normalmente, mas o invasor está no meio, vendo, capturando e podendo modificar tudo o que você envia e recebe, sem que você perceba.