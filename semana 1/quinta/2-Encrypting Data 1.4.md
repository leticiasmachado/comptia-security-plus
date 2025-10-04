Resumo do vídeo "Encrypting Data - CompTIA Security+ SY0-701 - 1.4"

---

## 1. Criptografia de Dados em Repouso

Envolve a proteção de dados armazenados em dispositivos (SSDs e HDDs).

* **Criptografia de Disco Completo (FDE):** Criptografa todo o volume de armazenamento.
    * Exemplos: **BitLocker** (Windows) e **FileVault** (macOS).
* **Criptografia de Arquivos:** Proteção de arquivos individuais.
    * Exemplo: **Sistema de Arquivos Criptografado (EFS)** no Windows.

## 2. Criptografia em Bancos de Dados

O foco é proteger informações sensíveis dentro de sistemas de gerenciamento de banco de dados.

* Técnicas como **criptografia transparente** e **criptografia em nível de coluna** são discutidas.
* A criptografia em **nível de coluna** permite acesso rápido a dados não sensíveis, enquanto protege apenas os campos mais confidenciais.

## 3. Criptografia em Trânsito

Envolve a proteção de dados enquanto são transmitidos entre dispositivos em uma rede.

* É destacada a importância do uso de conexões **HTTPS** e **VPNs** (Redes Privadas Virtuais) para estabelecer **túneis seguros** e criptografados.

## 4. Algoritmos e Chaves de Criptografia

A eficácia da criptografia depende tanto do processo matemático quanto do segredo da chave.

* **Algoritmos de Criptografia:** É essencial que ambos os lados de uma comunicação utilizem o **mesmo algoritmo** para que a descriptografia seja bem-sucedida. O vídeo compara padrões como **DES** e **AES**.
* **Chaves de Criptografia:** A segurança do sistema é baseada na proteção das **chaves privadas**.
    * **Resistência a Ataques:** A resistência a ataques de força bruta é crucial.
    * **Key Stretching:** O conceito de "*key stretching*" (estiramento de chave) é introduzido como uma técnica para aumentar a segurança das chaves e dificultar ataques.