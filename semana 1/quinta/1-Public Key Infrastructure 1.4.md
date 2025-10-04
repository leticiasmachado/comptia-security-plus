Resumo da aula **Infraestrutura de Chave Pública (PKI)** 

---

## Conceitos Fundamentais de Criptografia

A base da PKI reside na diferença e na combinação de dois tipos de criptografia:

### 1. Criptografia Simétrica (Chave Única)
* **Mecanismo:** Usa a **mesma chave** secreta para criptografar e descriptografar dados.
* **Vantagem:** É **muito mais rápida** do que a criptografia assimétrica, com baixa sobrecarga.
* **Desafio:** O problema logístico de **compartilhar a chave secreta** com segurança pela internet. Não é escalável para muitos usuários.

### 2. Criptografia Assimétrica (Par de Chaves)
* **Mecanismo:** Usa duas chaves matematicamente relacionadas:
    * **Chave Pública:** Compartilhada abertamente. Usada para **criptografar** dados para o proprietário ou para **verificar** uma assinatura digital.
    * **Chave Privada:** Mantida **secreta** pelo proprietário. Usada para **descriptografar** dados criptografados pela chave pública correspondente ou para **criar** uma assinatura digital.
* **Vantagem:** Resolve o problema da troca de chaves. Se alguém criptografa uma mensagem usando sua chave pública, apenas você (com sua chave privada) pode descriptografá-la.
* **Processo:** A criação do par de chaves (**Key Generation**) envolve muita aleatoriedade e matemática (grandes números primos).

---

## O Papel da Infraestrutura de Chave Pública (PKI)

**PKI** é um termo amplo que se refere às políticas, procedimentos, hardware e software usados para **criar, distribuir, gerenciar, armazenar e revogar certificados digitais** e associar chaves públicas a indivíduos ou dispositivos.

* O componente principal é a **Autoridade Certificadora (CA - Certificate Authority)**, que é a entidade confiável que emite e gerencia certificados.

### Uso Combinado de Criptografia (Troca de Chaves)
Em cenários práticos (como HTTPS), a criptografia assimétrica é usada para resolver o desafio de compartilhamento inicial de chaves, enquanto a simétrica é usada para a comunicação em si.

1.  Um cliente quer se comunicar com um servidor de forma segura.
2.  O cliente gera uma **chave de sessão** simétrica (rápida e temporária).
3.  O cliente usa a **chave pública do servidor** (criptografia assimétrica) para criptografar essa chave de sessão.
4.  O cliente envia a chave de sessão criptografada para o servidor.
5.  O servidor usa sua **chave privada** para descriptografar e obter a chave de sessão simétrica.
6.  A partir deste ponto, ambos os lados usam a **chave de sessão simétrica** para criptografar e descriptografar rapidamente o resto da comunicação.

### Outros Conceitos de Gerenciamento de Chaves
* **Key Escrow:** Processo onde as chaves privadas são armazenadas e gerenciadas por terceiros confiáveis (como uma CA) para fins de backup, recuperação ou acesso legal, caso o proprietário perca a chave ou deixe a organização.
* **Trusted Platform Module (TPM):** Um chip de hardware em placas-mãe projetado para fornecer funções criptográficas, como geração de números aleatórios e armazenamento de chaves em memória persistente, melhorando a segurança.
* **Hardware Security Module (HSM):** Dispositivo de hardware de alta segurança usado em grandes ambientes (como clusters de servidores) para gerenciamento centralizado, armazenamento seguro e aceleração de operações criptográficas.
* **Sistema de Gerenciamento de Chaves (Key Management System):** Software centralizado para gerenciar todos os tipos de chaves (SSL/TLS, SSH, BitLocker) em um ambiente, permitindo rotação automática, registro e relatórios.