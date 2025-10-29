Resumo do vídeo **Email Security – CompTIA Security+ SY0-701 – 4.5**

---

### 1. O Problema: Spoofing de Email

Seu e-mail está cheio de spam que *parece* vir de amigos ou empresas conhecidas. Isso é possível porque os protocolos de email fundamentais não possuem verificações de segurança robustas.

* **O que é Spoofing?** É a falsificação do nome do remetente em um email. O email diz que veio de `pessoa@empresa.com`, mas na verdade foi enviado por um invasor.
* **O Desafio:** Como um destinatário pode ter certeza de que um email que diz ser de `james@professormesser.com` realmente veio dele?
* **A Solução:** Adicionar camadas extras de verificação de segurança usando o **DNS** (Sistema de Nomes de Domínio).

### 2. O Verificador: O Mail Gateway

A decisão de validar um email é frequentemente tomada pelo **Mail Gateway** (Gateway de Email).

* **Função:** É o "porteiro" do email da sua organização. Ele recebe todos os emails vindos da internet *antes* que cheguem à sua caixa de entrada.
* **Processo:**
    1.  O gateway intercepta o email.
    2.  Ele verifica a validade do remetente (usando SPF, DKIM e DMARC).
    3.  Se for válido, entrega na sua caixa de entrada.
    4.  Se não for válido (ou for suspeito), ele o descarta ou o move para a pasta de spam.
* **Localização:** Pode ser um servidor local (geralmente em uma sub-rede de triagem/DMZ) ou um serviço de terceiros na nuvem.

### 3. Verificação nº 1: SPF (Sender Policy Framework)

* **O que é?** Um protocolo que define quais servidores de email estão **autorizados** a enviar emails em nome do seu domínio.
* **Como funciona?** O dono do domínio (ex: `professormesser.com`) adiciona um **Registro TXT** ao seu DNS.
* **Exemplo de Registro:** "v=spf1 include:mailgun.org ~all" (Isso diz: "O servidor `mailgun.org` tem permissão para enviar emails em meu nome.")
* **Verificação:** O mail gateway do destinatário consulta o registro TXT do SPF no DNS do remetente. Ele então verifica se o endereço IP do servidor que enviou o email está na lista de servidores autorizados. Se estiver, o email passa na verificação SPF.

### 4. Verificação nº 2: DKIM (DomainKeys Identified Mail)

* **O que é?** Uma verificação adicional que usa **assinaturas digitais** para provar a autenticidade.
* **Como funciona (Envio):** O servidor de email do remetente é configurado para adicionar automaticamente uma assinatura digital a cada email enviado. Essa assinatura fica oculta nos cabeçalhos (headers) do email, não sendo visível para o usuário.
* **Como funciona (Recebimento):** O mail gateway do destinatário consulta o DNS do remetente para encontrar o **Registro DKIM** (também um registro TXT).
* **Verificação:** Esse registro DKIM contém a **chave pública** do remetente. O gateway usa essa chave pública para validar a assinatura digital no cabeçalho do email. Se a assinatura for válida, isso prova que o email realmente veio daquele servidor e não foi alterado no caminho.

### 5. A Política: DMARC (Domain-based Message Authentication, Reporting, and Conformance)

* **O que é?** O DMARC é a "política" que une o SPF e o DKIM. Ele diz ao servidor do destinatário **o que fazer se o SPF ou o DKIM falharem**.
* **Como funciona?** O dono do domínio adiciona *outro* **Registro TXT** ao seu DNS, definindo a política DMARC.
* **Ações Possíveis (O que o receptor deve fazer):**
    1.  **Aceitar:** Aceitar a mensagem (usado geralmente para monitoramento inicial).
    2.  **Quarentena (Quarantine):** Enviar a mensagem para a pasta de spam.
    3.  **Rejeitar (Reject):** Rejeitar o email completamente; ele nem chega ao destinatário.

### 6. O Benefício do DMARC: Relatórios

O DMARC também permite que o dono do domínio especifique um destino para **Relatórios de Conformidade**.

* Servidores de email ao redor do mundo que recebem mensagens (legítimas ou falsas) do seu domínio podem enviar relatórios de volta.
* Esses relatórios mostram quantas mensagens passaram ou falharam nas verificações SPF e DKIM.
* Isso dá ao dono do domínio uma visibilidade crucial de quantas mensagens estão sendo validadas e, mais importante, quem está tentando falsificar (fazer spoofing) seu domínio na internet.