Resumdo do vídeo **Certificates - CompTIA Security+ SY0-701 - 1.4**

---

### 1. O Conceito de Confiança (Trust)
O Certificado Digital é uma forma de garantir confiança ao acessar dispositivos ou serviços, atuando como um "passaporte" digital. Ele **vincula uma chave pública** a uma identidade (de um site, servidor ou pessoa).

### 2. Autoridade Certificadora (CA)
* Para que o certificado seja confiável, ele deve ser emitido e assinado digitalmente por uma **Autoridade Certificadora (CA)**, uma entidade terceira amplamente confiável.
* Se o seu dispositivo confia na CA, ele confia automaticamente em qualquer certificado assinado por ela.
* O formato padrão para certificados digitais é o **X.509**.

### 3. O Ciclo de Vida do Certificado
O vídeo aborda as etapas importantes do gerenciamento de certificados:

| Conceito | Função |
| :--- | :--- |
| **CSR (Certificate Signing Request)** | É o pedido formal enviado à CA que contém a Chave Pública e a informação de identificação (por exemplo, o nome de domínio). |
| **Revogação de Chave** | É o processo de anular a validade de um certificado antes de sua data de expiração, geralmente porque a Chave Privada foi comprometida ou o serviço foi desativado. |
| **CRL (Certificate Revocation List)** | Uma lista grande de todos os certificados que foram revogados. Os navegadores precisam baixar e verificar periodicamente essa lista. |
| **OCSP (Online Certificate Status Protocol)** | Uma forma mais eficiente de verificar a revogação. O cliente envia uma consulta em tempo real à CA para perguntar *apenas* sobre o status de um certificado específico. |
| **OCSP Stapling** | O servidor web (o site que hospeda o certificado) anexa a resposta OCSP em sua primeira mensagem TLS, economizando a etapa de consulta do cliente à CA. |
| **Certificate Pinning** | Garantir que o aplicativo ou o navegador só aceite certificados específicos e pré-aprovados para um determinado domínio, protegendo contra CAs comprometidas ou emissões maliciosas. |

### 4. Root of Trust e Cadeia de Confiança 🔗

O sistema de confiança de certificados é construído sobre uma hierarquia, com a **Autoridade Certificadora Raiz (Root CA)** no topo.

* **Root of Trust (Raiz de Confiança):** O seu navegador ou sistema operacional (Windows, macOS, etc.) já vem com um conjunto de certificados de **Root CAs pré-instalados e confiáveis** em seu repositório de chaves. Essa Root CA é o ponto de partida da confiança – se o seu sistema confia nela, ele confia em todos os certificados que ela endossa.
* **Cadeia de Confiança:** O certificado de um site 💻 que você acessa (a entidade final) não é assinado diretamente pela Root CA (por razões de segurança). Em vez disso, a Root CA assina uma **Autoridade Certificadora Intermediária (Intermediate CA)**, e esta, por sua vez, assina o certificado do site. A união desses certificados (site, Intermediária e Raiz) forma a **Cadeia de Confiança**.
* **Verificação:** Ao acessar um site, seu dispositivo verifica a assinatura digital do certificado do site e segue a cadeia até o topo. Se a cadeia terminar em uma Root CA que está na sua lista de confiança, a conexão é validada como segura.


