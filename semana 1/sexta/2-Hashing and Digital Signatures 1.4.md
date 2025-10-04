Resumdo do vídeo **Hashing and Digital Signatures - CompTIA Security+ SY0-701 - 1.4**

---

## Resumo: Hashing e Assinaturas Digitais

### 1. Hashing (Função Hash)

Hashing é um processo criptográfico **unidirecional** (one-way). Você alimenta um bloco de dados (como um arquivo ou uma senha) e recebe uma *string* de texto de tamanho fixo, chamada **hash** (ou *message digest* / *fingerprint*).

* **Não é Criptografia:** Você não pode reverter um hash para obter o dado original. Ele funciona como uma impressão digital digital.
* **Finalidade (Integridade):** Usamos o hash para verificar a integridade dos dados. Se você calcular o hash de um arquivo baixado e ele for **exatamente igual** ao hash original fornecido pelo *site*, você sabe que o arquivo não foi alterado (corrompido ou adulterado).
* **Sensibilidade a Alterações:** Qualquer pequena mudança no dado de entrada (como adicionar um ponto ou mudar uma letra) resulta (ou pelo menos deveria) em um hash de saída **completamente diferente**.


### Ameaça: Vulnerabilidade de Colisão em MD5
* **Definição de Colisão:** Uma colisão ocorre quando duas entradas de dados **diferentes** produzem o **mesmo hash de saída**.
* **Problema com MD5:** O algoritmo **MD5** demonstrou ser vulnerável a colisões há muitos anos. Isso significa que um atacante pode criar intencionalmente um arquivo malicioso que corresponda ao *hash* de um arquivo legítimo.
* **Implicação de Segurança:** Por causa dessa vulnerabilidade, o MD5 **não deve mais ser usado** para verificar a integridade de arquivos ou para o armazenamento seguro de senhas. Por isso, algoritmos mais fortes, como **SHA-256** ou **SHA-3**, são preferidos.


#### Hashing para Senhas e Salting
* **Armazenamento de Senhas:** Para proteger senhas, os sistemas armazenam apenas o **hash** da senha, nunca a senha em texto simples.
* **Salting (Adição de Sal):** Para dificultar ataques de força bruta usando **tabelas *rainbow*** (tabelas pré-calculadas de *hashes*), um valor aleatório exclusivo (o **sal**) é adicionado a cada senha antes do *hash*. Isso garante que duas pessoas com a mesma senha tenham *hashes* armazenados diferentes, invalidando as tabelas *rainbow*.

---

### 2. Assinaturas Digitais (Digital Signatures)

Assinaturas Digitais utilizam a função *hash* e a **criptografia assimétrica** (chave pública/privada) para provar a **autenticidade**, a **integridade** e o **não-repúdio** de um documento ou mensagem.

#### Processo de Criação (Pela Alice, a Remetente):

1.  O documento original (*plaintext*) é passado por um algoritmo de *hashing* para criar um **hash do documento**.
2.  A remetente (**Alice**) usa sua **Chave Privada** 🔑 para **criptografar esse hash** (assinando-o digitalmente).
3.  O documento e o *hash* criptografado (a **Assinatura Digital**) são enviados ao destinatário.

#### Processo de Verificação (Pelo Bob, o Destinatário):

1.  O destinatário (**Bob**) recebe o documento e a Assinatura Digital.
2.  Bob usa a **Chave Pública** de Alice para **descriptografar a assinatura** e extrair o *hash* original.
3.  Bob executa o documento recebido pelo **mesmo algoritmo de *hashing***, gerando um **novo hash local**.
4.  **Verificação:** Se o *hash* original (descriptografado) for igual ao novo *hash* local, ele tem as três garantias:
    * **Integridade:** O documento não foi alterado.
    * **Autenticação:** A assinatura foi feita pela Alice (somente ela tem a Chave Privada).
    * **Não-Repúdio:** Alice não pode negar que o enviou.

