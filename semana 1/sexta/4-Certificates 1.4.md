Resumo do vídeo **Certificates - CompTIA Security+ SY0-701 - 1.4**

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
| **OCSP Stapling** | O servidor web (o site que hospeda o certificado) anexa a resposta OCSP em sua primeira mensagem TLS, economizando a etapa de consulta do cliente à CA. (funciona como um grampeador) |
| **Certificate Pinning** | Garantir que o aplicativo ou o navegador só aceite certificados específicos e pré-aprovados para um determinado domínio, protegendo contra CAs comprometidas ou emissões maliciosas. |

### 4. Root of Trust e Cadeia de Confiança 🔗

O sistema de confiança de certificados é construído sobre uma hierarquia, com a **Autoridade Certificadora Raiz (Root CA)** no topo.

* **Root of Trust (Raiz de Confiança):** O seu navegador ou sistema operacional (Windows, macOS, etc.) já vem com um conjunto de certificados de **Root CAs pré-instalados e confiáveis** em seu repositório de chaves. Essa Root CA é o ponto de partida da confiança – se o seu sistema confia nela, ele confia em todos os certificados que ela endossa.
* **Cadeia de Confiança:** O certificado de um site 💻 que você acessa (a entidade final) não é assinado diretamente pela Root CA (por razões de segurança). Em vez disso, a Root CA assina uma **Autoridade Certificadora Intermediária (Intermediate CA)**, e esta, por sua vez, assina o certificado do site. A união desses certificados (site, Intermediária e Raiz) forma a **Cadeia de Confiança**.
* **Verificação:** Ao acessar um site, seu dispositivo verifica a assinatura digital do certificado do site e segue a cadeia até o topo. Se a cadeia terminar em uma Root CA que está na sua lista de confiança, a conexão é validada como segura.

---

### 5. Tipos Especiais de Autoridades e Certificados 🔒


#### **Autoridades Certificadoras Privadas (Private Certificate Authorities)**
* Organizações podem criar suas próprias **Autoridades Certificadoras (CAs) internas** para emitir certificados.
* **Uso:** Isso é ideal para ambientes fechados (como uma rede corporativa, intranet ou laboratório de testes) onde não há necessidade de que o mundo externo confie nesses certificados.
* **Confiança:** Para que os certificados internos funcionem, o certificado da **Root CA Privada** da organização deve ser instalado manualmente ou via política em todos os dispositivos da rede (servidores, desktops, dispositivos móveis). Ao fazer isso, todos esses dispositivos passam a confiar em qualquer certificado assinado pela CA Privada.

#### **Certificados Autoassinados (Self-Signed Certificates)**
* Um certificado autoassinado é aquele que **não foi assinado por uma CA de terceiros** ou mesmo por uma CA Privada. Ele é assinado pela própria entidade que o está usando.
* **Uso:** Geralmente utilizados em ambientes de teste, desenvolvimento ou em equipamentos onde a única pessoa que precisa de confiança é o próprio administrador do sistema.
* **Alerta:** Ao usar um certificado autoassinado em um navegador comum, o usuário receberá um aviso de segurança (erro de "não confiável"), pois o certificado não está na cadeia de confiança pública ou privada do dispositivo.

#### **Certificados Wildcard (Wildcard Certificates)**
* Um certificado *Wildcard* usa um asterisco (`*`) no campo do nome de domínio para cobrir **todos os subdomínios** de um domínio específico.
* **Exemplo:** Um certificado emitido para `*.dominio.com` cobrirá automaticamente `www.dominio.com`, `ftp.dominio.com`, `mail.dominio.com`, e qualquer outro subdomínio.
* **Vantagem:** Reduz a complexidade e o custo administrativo, pois um único certificado pode ser instalado em múltiplos servidores para proteger vários serviços de subdomínio.
* **Limitação:** Não cobre o domínio raiz (por exemplo, `dominio.com` sem o prefixo). Ele precisa ser explicitamente listado como um **Subject Alternative Name (SAN)**, ou um certificado separado para o domínio raiz.
