Resumdo do vídeo **Blockchain Technology - CompTIA Security+ SY0-701 - 1.4**

---

## Estrutura da Tecnologia Blockchain

### 1. O Bloco (The Block)

O bloco é a unidade fundamental. Cada bloco contém elementos cruciais para sua segurança:

* **Dados:** As informações reais da transação ou registro.
* **Hash Próprio do Bloco:** A "impressão digital" criptográfica dos dados internos.
* **Hash do Bloco Anterior:** O link criptográfico que conecta este bloco ao bloco anterior na cadeia.

### 2. A Cadeia (The Chain) e Imutabilidade

O que torna o *blockchain* seguro é a sua dependência sequencial dos *hashes*:

* Ao incluir o **Hash do Bloco Anterior**, a ordem e a integridade da cadeia são estabelecidas.
* Se alguém tentar alterar **qualquer dado** em um bloco (por exemplo, no Bloco 5), o **Hash Próprio do Bloco 5** é alterado.
* Isso imediatamente quebra o link no Bloco 6 (que ainda aponta para o *hash* antigo e agora incorreto do Bloco 5). A partir desse ponto, toda a cadeia se torna **inválida**.

### 3. Natureza Distribuída e Segurança

* O *blockchain* é uma **contabilidade distribuída (distributed ledger)**. O registro da cadeia é mantido e validado por inúmeros participantes na rede, não por um único servidor central.
* Para que uma alteração seja bem-sucedida, um atacante precisaria não apenas recriar o *hash* de um bloco adulterado e de **todos** os blocos subsequentes, mas também ter poder de computação suficiente para controlar **mais de 50%** da rede e convencer os outros nós de que a versão falsa é a verdadeira.

