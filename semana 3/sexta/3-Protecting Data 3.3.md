Resumo do vídeo **Protecting Data – CompTIA Security+ SY0-701 – 3.3**

---

### 1. Restrições Geográficas e Geofencing

Uma forma de proteger dados é tomar decisões de política baseadas em **onde os dados estão** e **onde o usuário está**.

* **Restrições Geográficas:**
    * **Método Antigo (Sub-rede IP):** Tentar adivinhar a localização de um usuário com base em sua sub-rede IP.
        * **Problema:** Funciona razoavelmente bem em uma rede interna (privada), mas é **muito impreciso** para dispositivos móveis (telefones, tablets), que podem estar em qualquer lugar.
    * **Método Moderno (Geolocalização):** Usar tecnologias mais precisas para determinar a localização.
        * **GPS:** Muito preciso em dispositivos móveis.
        * **Redes 802.11 (Wi-Fi):** Existem bancos de dados que mapeiam os SSIDs (nomes de redes Wi-Fi) conhecidos em uma área. Ao cruzar os SSIDs que seu dispositivo pode ver com esse banco de dados, é possível obter uma localização bastante precisa.

* **Geofencing (Cercamento Geográfico):**
    * **Definição:** É a **política** que aplicamos com base na geolocalização. É o ato de criar uma "cerca" virtual.
    * **Exemplo:** Criar uma regra que diz: "Funcionários só podem acessar o banco de dados de 'segredos comerciais' se estiverem fisicamente **dentro** do prédio da empresa". Se o mesmo funcionário tentar acessar de fora, o acesso é bloqueado.

---

### 2. O Desafio da Proteção de Dados

Os dados são um ativo crítico; perdê-los pode significar o fim do negócio. O desafio é que os dados existem em muitos locais diferentes (HDs de laptops, dispositivos móveis, atravessando a rede, na memória/CPU) e todos são vulneráveis.

Precisamos aplicar a proteção adequada independentemente de onde os dados estejam, usando criptografia, políticas de segurança e permissões.

---

### 3. Criptografia (Encryption)

* **Definição:** O processo de pegar dados legíveis (abertos) e transformá-los em um formato completamente ilegível.
* **Terminologia Chave:**
    * **Plaintext (Texto Simples):** Os dados originais, legíveis.
    * **Ciphertext (Texto Cifrado):** Os dados resultantes, ilegíveis e criptografados.
* **Processo:** A criptografia sempre precisa de um método (algoritmo) para descriptografar os dados de volta à sua forma original. Para isso, você precisa da **chave de decodificação** correta.
* **Conceito de "Confusão" (Confusion):** Uma propriedade importante da criptografia. O texto cifrado (ciphertext) deve ser **drasticamente diferente** do texto simples (plaintext).
    * **Exemplo:** Criptografar "Hello, world" com PGP resulta em um bloco de texto grande e indecifrável que não tem nenhuma semelhança com a mensagem original.

---

### 4. Hashing

* **Definição:** Um processo **irreversível (one-way)** que representa dados como uma string de texto de tamanho fixo.
* **Outros Nomes:** Message Digest, **Fingerprint (Impressão Digital)**.
* **Analogia da Impressão Digital:** É a melhor descrição. Você pode usar uma impressão digital para identificar uma pessoa, mas você **não pode recriar a pessoa inteira** apenas a partir da impressão digital.
* **Propriedade Chave:** Com um hash, você **NÃO PODE** recriar os dados originais.

#### Usos Comuns do Hashing:

1.  **Armazenamento de Senhas:** É o mecanismo perfeito para armazenar senhas. Quando você digita sua senha, o sistema calcula o hash dela e o compara com o hash armazenado. A senha real nunca é armazenada.
2.  **Verificação de Integridade de Arquivos:** Ao baixar um arquivo (como uma distribuição Linux), o site geralmente lista um hash. Após o download, você pode calcular o hash do arquivo que baixou. Se o seu hash **bater** com o do site, significa que o arquivo não foi corrompido ou modificado durante o download (a **integridade** foi mantida).
3.  **Assinaturas Digitais:** Usado com criptografia de chave pública para autenticar o remetente e garantir a integridade da mensagem.

#### Colisões (Collisions)

* **Definição:** Uma **colisão** ocorre quando dois *inputs* (dados) diferentes produzem **exatamente o mesmo *output* (hash)**.
* **Problema:** Isso é uma falha grave em um algoritmo de hash. Algoritmos mais antigos que se mostraram suscetíveis a colisões (como o MD5) foram aposentados e substituídos por algoritmos mais novos e fortes (como a família SHA).

* **Exemplo (SHA-256):** O SHA-256 produz um hash de 256 bits (64 caracteres hexadecimais).
    * `Input 1:` "My name is Professor Messer**."** (termina com ponto)
    * `Hash 1:` `[hash longo e complexo A]`
    * `Input 2:` "My name is Professor Messer**!**" (termina com exclamação)
    * `Hash 2:` `[hash longo e complexo B, totalmente diferente do A]`
    * **Lição:** Uma mudança mínima no input (1 caractere) gera um hash completamente diferente (Efeito Avalanche).

---

### 5. Ofuscação (Obfuscation)

* **Definição:** O processo de transformar algo perfeitamente compreensível em algo muito **difícil para um humano reconhecer**, mas que ainda funciona da mesma forma para o computador.
* **Uso (Legítimo):** Desenvolvedores ofuscam seu código-fonte para proteger sua propriedade intelectual, tornando-o difícil de ser copiado ou entendido por concorrentes.
* **Uso (Malicioso):** Atacantes usam ofuscação para esconder o que um script ou código malicioso realmente faz.
* **Exemplo:**
    * `Código Original:` `echo "Hello, world";` (PHP simples e legível)
    * `Código Ofuscado:` Um bloco de código PHP complexo e ilegível que, quando executado, produz a mesma saída: "Hello, world".

---

### 6. Mascaramento de Dados (Data Masking)

* **Definição:** Um tipo de ofuscação que **oculta partes** de dados originais para protegê-los.
* **Uso:** Proteger PII ou dados financeiros sensíveis.
* **Exemplo Clássico:** Um recibo de cartão de crédito.
    * O recibo mostra: `Cartão: **** **** **** 1234`
    * O restante do número é "mascarado" (geralmente com asteriscos).
    * No backend, a empresa *tem* o número completo, mas o que é apresentado ao usuário é protegido.

---

### 7. Tokenização (Tokenization)

* **Definição:** Um método de proteção que **substitui** informações sensíveis por um valor não sensível equivalente, chamado **"token"**.
* **Propriedade Chave:** O token **não é derivado matematicamente** dos dados originais (diferente de criptografia ou hash). Não há como reverter o token para os dados originais; é apenas um ponteiro.
* **Exemplo de Pagamento (Apple Pay / Google Pay):**
    1.  Quando você cadastra seu cartão no celular, seu telefone envia o número real do cartão para um "Servidor de Token" seguro.
    2.  O servidor armazena seu cartão e envia de volta ao seu telefone uma série de **tokens temporários**.
    3.  Ao pagar na loja (via NFC), seu telefone **nunca envia o número real do seu cartão**. Ele envia um **token de uso único**.
    4.  A loja envia esse token para a rede de pagamento.
    5.  O Servidor de Token valida aquele token específico e autoriza a compra.
* **Vantagem:** Se um invasor capturar o token, ele é inútil, pois é de uso único e não contém seu número de cartão real.

---

### 8. Segmentação de Dados (Data Segmentation)

* **O Problema:** Muitas empresas sofrem violações massivas porque armazenam *todos* os dados de *todos* os clientes em **um único banco de dados gigante**. Se o invasor entra, ele leva tudo.
* **A Solução (Segmentação):** Separar os dados em "pedaços" menores e colocá-los em locais (bancos de dados) diferentes.
* **Benefícios:**
    1.  **Dificulta o Ataque:** O invasor agora precisa invadir *vários* bancos de dados diferentes para roubar tudo.
    2.  **Segurança Granular:** Permite aplicar diferentes níveis de segurança. (Ex: Banco de dados de "nomes" pode ter segurança mínima, mas o banco de "informações de saúde" pode ter segurança máxima).

---

### 9. Restrições de Permissão (Permission Restrictions)

* **Definição:** O tipo de proteção de dados que usamos todos os dias, baseada em **autenticação** (quem você é) e **autorização** (o que você pode fazer).
* **Processo:**
    1.  **Autenticação Segura:** Garantir que o login é seguro (políticas de senha forte, autenticação multifator - MFA).

    2.  **Autorização (Permissões):** Uma vez logado, o que você pode acessar? Isso é controlado por permissões de arquivo e associações a grupos, que limitam quais dados aquele usuário específico pode ver ou modificar.
