Resumo do vídeo **"Non-repudiation - CompTIA Security+ SY0-701 - 1.2"** do Professor Messer.

## Resumo: Não Repúdio (Non-repudiation)

O vídeo explica o conceito de **Não Repúdio (Non-repudiation)** na segurança da informação, que é a garantia de que uma parte envolvida em uma comunicação ou transação não pode negar a validade de sua assinatura ou a autoria de uma mensagem enviada.

### Conceitos Chave

1.  **Não Repúdio:** A garantia de que o remetente de uma mensagem ou o autor de uma ação não pode negar tê-la realizado. É essencial para a **responsabilização (accountability)**.

2.  **Integridade (Proof of Integrity):** O vídeo enfatiza que para ter não repúdio, primeiro é preciso ter a **prova de integridade**, ou seja, a garantia de que os dados recebidos são exatamente os mesmos que foram enviados e não foram alterados.
    * **Método:** Isso é conseguido através de um **hash** (ou *message digest*), que é uma "impressão digital" única do arquivo ou mensagem. Qualquer alteração no dado resulta em um hash diferente.

3.  **Prova de Origem (Proof of Origin):** Em seguida, é necessária a prova de que a mensagem realmente veio da pessoa que alega ser o remetente.
    * **Método:** Isso é alcançado usando uma **Assinatura Digital (Digital Signature)**.

### Como Funciona a Assinatura Digital (e o Não Repúdio)

O vídeo usa o exemplo de Alice enviando uma mensagem digitalmente assinada para Bob:

1.  **Geração do Hash:** Alice pega a mensagem (o *plaintext*) e gera um **hash** dela.
2.  **Assinatura:** Alice usa sua **chave privada** (que só ela possui) para criptografar (assinar) o **hash**. A mensagem e o hash criptografado (a assinatura digital) são enviados a Bob.
3.  **Verificação (Por Bob):**
    * Bob recebe a mensagem e a assinatura digital.
    * Bob usa a **chave pública** de Alice (que é acessível a todos) para descriptografar a assinatura digital, recuperando o hash original que Alice gerou.
    * Bob pega a **mensagem** que recebeu e, independentemente, executa o mesmo algoritmo de hash para criar um novo hash da mensagem.
    * **Comparação:** Bob compara o hash que ele acabou de gerar com o hash que ele recuperou da assinatura digital de Alice.

### Resultado

Se os dois hashes forem **iguais**, Bob tem duas garantias (e consequentemente o não repúdio):

* **Integridade:** O conteúdo da mensagem não foi alterado no caminho.
* **Autenticidade/Não Repúdio:** A mensagem **só poderia ter sido enviada por Alice**, porque a única maneira de criar uma assinatura digital que possa ser validada com a chave pública de Alice é usando a chave privada dela. Alice não pode, posteriormente, negar o envio.

Em resumo, o Não Repúdio utiliza a **criptografia de chave assimétrica (par de chaves pública e privada)** em conjunto com o **hashing** para estabelecer a autoria e a integridade de uma ação, tornando-a legalmente verificável e inegável.